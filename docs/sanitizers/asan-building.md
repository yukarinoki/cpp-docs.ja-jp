---
title: AddressSanitizer 言語、ビルド、およびデバッグのリファレンス
description: AddressSanitizer の構築に関する技術的な説明
ms.date: 03/02/2021
f1_keywords:
- __SANITIZE_ADDRESS__
- ASAN_VCASAN_DEBUGGING
helpviewer_keywords:
- ASan reference
- AddressSanitizer reference
- Address Sanitizer reference
ms.openlocfilehash: f2f173da6d39b460098afe123a7537e36cbdf6a7
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471044"
---
# <a name="addresssanitizer-language-build-and-debugging-reference"></a>AddressSanitizer 言語、ビルド、およびデバッグのリファレンス

この記事のセクションでは、AddressSanitizer 言語仕様、コンパイラオプション、およびリンカーオプションについて説明します。 また、AddressSanitizer に固有の Visual Studio デバッガーの統合を制御するオプションについても説明します。

AddressSanitizer ランタイム、インターセプトした関数、およびカスタムアロケーターをフックする方法の詳細については、「 [ランタイムリファレンス](./asan-runtime.md)」を参照してください。 AddressSanitizer の障害からのクラッシュダンプの保存の詳細については、 [クラッシュダンプのリファレンス](./asan-offline-crash-dumps.md)を参照してください。

## <a name="language-specification"></a>言語仕様

### `__SANITIZE_ADDRESS__`

`__SANITIZE_ADDRESS__`が設定されている場合、プリプロセッサマクロはとして定義され `1` [`/fsanitize=address`](../build/reference/fsanitize.md) ます。 このマクロは、上級ユーザーが AddressSanitizer ランタイムの存在に対してソースコードを条件付きで指定する場合に便利です。

```cpp
#include <cstdio>

int main() {
    #ifdef __SANITIZE_ADDRESS__
        printf("Address sanitizer enabled");
    #else
        printf("Address sanitizer not enabled");
    #endif
    return 1;
}
```

### `__declspec(no_sanitize_address)`

指定子を使用して、 [`__declspec(no_sanitize_address)`](../cpp/no-sanitize-address.md) 関数、ローカル変数、またはグローバル変数のサニタイザーを選択的に無効にすることができます。 これ `__declspec` は、_実行時_ の動作ではなく、_コンパイラ_ の動作に影響します。

```cpp
__declspec(no_sanitize_address)
void test1() {
    int x[100];
    x[100] = 5; // ASan exception not caught
}

void test2() {
    __declspec(no_sanitize_address) int x[100];
    x[100] = 5; // ASan exception not caught
}

__declspec(no_sanitize_address) int g[100];
void test3() {
    g[100] = 5; // ASan exception not caught
}
```

## <a name="compiler"></a>コンパイラ

### <a name="fsanitizeaddress-compiler-option"></a>`/fsanitize=address` コンパイラ オプション

[`/fsanitize=address`](../build/reference/fsanitize.md)コンパイラオプションは、実行時にメモリの安全性エラーをキャッチするために、コード内のメモリ参照をインストルメント化します。 インストルメンテーションは、読み込み、格納、スコープ、alloca、および CRT の各関数をフックします。 非境界、使用後の使用、スコープの使用など、非表示のバグを検出することができます。 実行時に検出されたエラーの完全でない一覧については、「 [AddressSanitizer error の例](./asan-error-examples.md)」を参照してください。

**`/fsanitize=address`** は、既存の C++ または C のすべての最適化レベルと互換性があります (たとえば、、、、 **`/Od`** **`/O1`** **`/O2`** **`/O2 /GL`** 、ガイド付き最適化のプロファイルなど)。 このオプションを使用して生成されたコードは、静的および動的な crt (たとえば、、、 **`/MD`** **`/MDd`** 、) で動作 **`/MT`** **`/MTd`** します。 このコンパイラオプションを使用して、を作成できます。EXE または。X86 または x64 を対象とする DLL。 呼び出し履歴を最適に書式設定するには、デバッグ情報が必要です。

いくつかの種類のエラー検出を示すコード例については、「 [AddressSanitizer error の例](asan-error-examples.md)」を参照してください。

### <a name="fsanitize-address-use-after-return-compiler-option-experimental"></a>`/fsanitize-address-use-after-return` コンパイラオプション (試験段階)

既定では、MSVC コンパイラ (Clang とは異なります) は、ヒープ内のフレームを割り当てて、after リターンエラーをキャッチするコードを生成しません。 AddressSanitizer を使用してこれらのエラーをキャッチするには、次のことが必要です。

1. オプションを使用してコンパイルし [`/fsanitize-address-use-after-return`](../build/reference/fsanitize.md) ます。
2. プログラムを実行する前に、を実行し `set ASAN_OPTIONS=detect_stack_use_after_return=1` てランタイムチェックオプションを設定します。

オプションを指定すると、 **`/fsanitize-address-use-after-return`** ローカル変数が "アドレス取得" と見なされた場合に、コンパイラによってコードが生成され、ヒープ内のデュアルスタックフレームが使用されます。 このコードは、だけを使用するよりも *はるかに低速* です **`/fsanitize=address`** 。 詳細と例については、「[エラー `stack-use-after-return` : ](error-stack-use-after-return.md)」を参照してください。

ヒープ内のデュアルスタックフレームは、ヒープを作成した関数からの戻り値の後に残っています。 戻り値の後に、ヒープ内のスロットに割り当てられたローカルのアドレスを使用する例を考えてみましょう。 フェイクヒープフレームに関連付けられているシャドウバイトには、値0xF9 が含まれます。 この0xF9 は、ランタイムがエラーを報告したときのスタック使用後エラーを意味します。

スタックフレームはヒープ内に割り当てられ、関数がを返した後もそのまま残ります。 ランタイムは、特定の時間間隔の後に、ガベージコレクションを使用して、これらのフェイク呼び出しフレームオブジェクトを非同期的に解放します。 ローカルのアドレスは、ヒープ内の永続的なフレームに転送されます。 これは、定義関数から制御が戻った後、どのような場合にローカル get が使用されたかをシステムが検出する方法です。 詳細については、Google のドキュメントに記載されている [戻り後のスタック使用のアルゴリズム](https://github.com/google/sanitizers/wiki/AddressSanitizerUseAfterReturn) に関する説明を参照してください。

## <a name="linker"></a><a name="linker"></a> Linker

### <a name="inferasanlibsno-linker-option"></a>`/INFERASANLIBS[:NO]` リンカーオプション

**`/fsanitize=address`** コンパイラオプションは、実行可能ファイルにリンクする AddressSanitizer ライブラリを指定するようにオブジェクトをマークします。 ライブラリには、で始まる名前が付いてい *`clang_rt.asan*`* ます。 [`/INFERASANLIBS`](../build/reference/inferasanlibs.md)リンカーオプション (既定では on) は、これらのライブラリを既定の場所から自動的にリンクします。 選択され、自動的にリンクされるライブラリは次のとおりです。

| CRT オプション | DLL または EXE | デバック? | AddressSanitizer ランタイムライブラリ |
|--|--|--|--|
| MT | EXE | NO | *`clang_rt.asan-{arch}`*, *`clang_rt.asan_cxx-{arch}`* |
| MT | [DLL] | NO | *`clang_rt.asan_dll_thunk-{arch}`* |
| MD | いずれか | NO | *`clang_rt.asan_dynamic-{arch}`*, *`clang_rt.asan_dynamic_runtime_thunk-{arch}`* |
| MT | EXE | YES | *`clang_rt.asan_dbg-{arch}`*, *`clang_rt.asan_dbg_cxx-{arch}`* |
| MT | [DLL] | YES | *`clang_rt.asan_dbg_dll_thunk-{arch}`* |
| MD | いずれか | YES | *`clang_rt.asan_dbg_dynamic-{arch}`*, *`clang_rt.asan_dbg_dynamic_runtime_thunk-{arch}`* |

リンカーオプションは、 [`/INFERASANLIBS:NO`](../build/reference/inferasanlibs.md) リンカーがライブラリファイルを既定の場所からリンクしないようにし *`clang_rt.asan*`* ます。 このオプションを使用する場合は、ビルドスクリプトにライブラリパスを追加します。 それ以外の場合、リンカーは未解決の外部シンボルエラーを報告します。

## <a name="visual-studio-integration"></a>Visual Studio の統合環境

### <a name="fno-sanitize-address-vcasan-lib-compiler-option"></a>`/fno-sanitize-address-vcasan-lib` コンパイラ オプション

オプションは、 **`/fsanitize=address`** AddressSanitizer 例外がスローされたときに Visual Studio のデバッグエクスペリエンスを向上させるために、extra ライブラリにリンクされています。 これらのライブラリは **Vcasan** と呼ばれます。 ライブラリを使用すると、Visual Studio でソースコードに AddressSanitizer エラーを表示できます。 また、AddressSanitizer エラーレポートが作成されたときに、実行可能ファイルでクラッシュダンプを生成することもできます。 詳細については、「 [Visual Studio AddressSanitizer 拡張機能ライブラリ](./asan-debugger-integration.md)」を参照してください。

選択したライブラリはコンパイラオプションによって異なり、自動的にリンクされます。

| Runtime オプション | VCAsan バージョン |
|--------------|----------------|
| **`/MT`**        | *`libvcasan.lib`*  |
| **`/MD`**        | *`vcasan.lib`*     |
| **`/MTd`**       | *`libvcasand.lib`* |
| **`/MDd`**       | *`vcasand.lib`*    |

ただし、(既定のライブラリ名を省略して) を使用してコンパイルする場合は、 **`/Zl`** 手動でライブラリを指定する必要があります。 そうしないと、外部シンボルリンクエラーが未解決の状態になります。 一般的な例をいくつか次に示します。

```Output
error LNK2001: unresolved external symbol __you_must_link_with_VCAsan_lib
error LNK2001: unresolved external symbol ___you_must_link_with_VCAsan_lib
```

強化されたデバッグは、オプションを使用してコンパイル時に無効にすることができ [`/fno-sanitize-address-vcasan-lib`](../build/reference/fsanitize.md) ます。

### <a name="asan_vcasan_debugging-environment-variable"></a>`ASAN_VCASAN_DEBUGGING` 環境変数

**`/fsanitize=address`** コンパイラオプションは、実行時にメモリの安全性に関するバグを公開するバイナリを生成します。 バイナリがコマンドラインから開始され、ランタイムがエラーを報告すると、エラーの詳細が出力されます。 その後、プロセスを終了します。 `ASAN_VCASAN_DEBUGGING`環境変数は、ランタイムがエラーを報告したときに Visual STUDIO IDE をすぐに起動するように設定できます。 このコンパイラオプションを使用すると、エラーの原因となった正確な行と列に、ソースコードに重ねて表示されたエラーを表示できます。

この動作を有効にするには、アプリケーションを実行する前にコマンドを実行し `set ASAN_VCASAN_DEBUGGING=1` ます。 を実行することで、強化されたデバッグエクスペリエンスを無効にすることができ `set ASAN_VCASAN_DEBUGGING=0` ます。

## <a name="see-also"></a>関連項目

[AddressSanitizer の概要](./asan.md)\
[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer のエラー例](./asan-error-examples.md)
