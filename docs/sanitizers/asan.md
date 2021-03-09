---
title: AddressSanitizer
description: Microsoft C/c + + の AddressSanitizer 機能のトップレベルの説明です。
ms.date: 03/05/2021
f1_keywords:
- AddressSanitizer
helpviewer_keywords:
- ASan
- AddressSanitizer
- Address Sanitizer
- compiling for AddressSanitizer
ms.openlocfilehash: db1760a37c610493cd3a3d95ab5e77b29bf89400
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102471278"
---
# <a name="addresssanitizer"></a>AddressSanitizer

## <a name="overview"></a>概要

C & C++ 言語は強力ですが、プログラムの正確性とプログラムのセキュリティに影響するバグのクラスを使用することはできません。 Visual Studio 2019 バージョン16.9 以降では、Microsoft C/c + + コンパイラ (MSVC) と IDE は *AddressSanitizer* をサポートしています。 AddressSanitizer (ASan) は、誤検知を **ゼロ** にして、発見しにくいバグを多数公開するコンパイラおよびランタイムテクノロジです。

- [Alloc/dealloc の不一致](error-alloc-dealloc-mismatch.md)と[ `new` / `delete` 型の不一致](error-new-delete-type-mismatch.md)
- [ヒープに対する割り当てが大きすぎます](error-allocation-size-too-big.md)
- [ `calloc` オーバーフロー](error-calloc-overflow.md)と[ `alloca` オーバーフロー](error-dynamic-stack-buffer-overflow.md)
- [無料で無料](error-double-free.md) で [使用する](error-heap-use-after-free.md)
- [グローバル変数のオーバーフロー](error-global-buffer-overflow.md)
- [ヒープのバッファー オーバーフロー](error-heap-buffer-overflow.md)
- [アラインされた値のアラインメントが無効です](error-invalid-allocation-alignment.md)
- [`memcpy`](error-memcpy-param-overlap.md)と[ `strncat` パラメーターの重複](error-strncat-param-overlap.md)
- [スタックバッファーのオーバーフロー](error-stack-buffer-overflow.md) と [アンダーフロー](error-stack-buffer-underflow.md)
- [後 `return` にスタックを使用する](error-stack-use-after-return.md)および[after スコープを使用する](error-stack-use-after-scope.md)
- [有害後のメモリ使用量](error-use-after-poison.md)

AddressSanitizer を使用して、にかかる時間を短縮します。

- 基本的な正確性
- クロスプラットフォームの移植性
- セキュリティ
- ストレス テスト
- 新しいコードの統合

[Google によって初めて導入](https://www.usenix.org/conference/atc12/technical-sessions/presentation/serebryany)された AddressSanitizer は、両方[ `/RTC` (ランタイムエラーチェック)](../build/reference/rtc-run-time-error-checks.md)と[ `/analyze` (スタティック分析)](../build/reference/analyze-code-analysis.md)の両方にとって優れた手段です。 既存のビルドシステムと既存のテスト資産を直接使用する、実行時のバグ検索テクノロジを提供します。

AddressSanitizer は、Visual Studio プロジェクトシステム、CMake ビルドシステム、IDE と統合されています。 プロジェクトで AddressSanitizer を有効にするには、プロジェクトのプロパティを設定するか、を使用して追加のコンパイラオプションを使用し **`/fsanitize=address`** ます。 新しいオプションは、x86 および x64 のすべてのレベルの最適化および構成と互換性があります。 ただし、 [エディットコンティニュ](/visualstudio/debugger/edit-and-continue-visual-cpp)、 [インクリメンタルリンク](../build/reference/incremental-link-incrementally.md)、およびには互換性がありません [`/RTC`](../build/reference/rtc-run-time-error-checks.md) 。

Visual Studio 2019 バージョン16.9 以降では、Microsoft の AddressSanitizer テクノロジにより、Visual Studio IDE との統合が可能になります。 この機能は、実行時にサニタイザーがバグを発見したときに、必要に応じてクラッシュダンプファイルを作成できます。 プログラムを実行する `ASAN_SAVE_DUMPS=MyFileName.dmp` 前に環境変数を設定した場合、クラッシュダンプファイルが追加のメタデータを使用して作成され、正確に診断されるバグの事後分析が効率的に [デバッグ](#crash-dumps) されます。 これらのダンプファイルを使用すると、次のように AddressSanitizer を簡単に使用できます。

- ローカルコンピューターのテスト、
- オンプレミスの分散テスト、および
- テスト用のクラウドベースのワークフロー。

### <a name="install-the-addresssanitizer"></a>AddressSanitizer をインストールする

AddressSanitizer IDE の統合とライブラリは、既定では Visual Studio インストーラーの C++ ワークロードと共にインストールされます。 ただし、以前のバージョンの Visual Studio 2019 からアップグレードする場合は、インストーラーを使用して、アップグレード後の ASan のサポートを有効にします。

:::image type="content" source="media/asan-installer-option.png" alt-text="C++ AddressSanitizer コンポーネントを強調表示した Visual Studio インストーラースクリーンショット":::

Visual Studio インストーラーから既存の Visual Studio インストールの [ **変更** ] を選択して、上の画面に移動できます。

> [!NOTE]
> 新しい更新プログラムで Visual Studio を実行しても、ASan がインストールされていない場合は、コードの実行時にエラーが発生します。
>
> LNK1356: ライブラリ ' clang_rt ' が見つかりません。

### <a name="use-the-addresssanitizer"></a><a name="using-asan"></a> AddressSanitizer を使用する

**`/fsanitize=address`** 次のいずれかの一般的な開発方法を使用して、コンパイラオプションを使用して実行可能ファイルのビルドを開始します。

- コマンドラインビルド
- Visual Studio のプロジェクト システム
- Visual Studio CMake 統合

 再コンパイルしてから、プログラムを通常どおり実行します。 このコード生成 [では、さまざまな種類のバグを正確に診断](#error-types)できます。 これらのエラーは、デバッガー IDE のコマンドラインで、または [新しい種類のダンプファイル](#crash-dumps) に格納されている、正確なオフライン処理の3つの方法で報告されます。

Microsoft では、次の3つの標準ワークフローで AddressSanitizer を使用することをお勧めします。

- **開発者の内側のループ**
  - Visual Studio- [コマンドライン](#command-prompt)
  - Visual Studio- [プロジェクトシステム](#ide-msbuild)
  - Visual Studio- [Cmake](#ide-cmake)

- **CI/CD** -継続的インテグレーション/継続的開発
  - エラー報告- [新しい AddressSanitizer ダンプファイル](#crash-dumps)

- **ファジー** 化- [libFuzzer](https://llvm.org/docs/LibFuzzer.html) ラッパーを使用したビルド
  - [Azure OneFuzz](https://www.microsoft.com/security/blog/2020/09/15/microsoft-onefuzz-framework-open-source-developer-tool-fix-bugs/)
  - ローカル コンピューター

この記事では、上記の3つのワークフローを有効にするために必要な情報について説明します。 この情報は、プラットフォームに **依存** する AddressSanitizer の Windows 10 実装に固有のものです。 このドキュメントでは、既に公開され [ている Google、Apple、および GCC](#external-docs) からの優れたドキュメントを補足します。

> [!NOTE]
> 現在のサポートは、Windows 10 では x86 と x64 に制限されています。 今後のリリースで見たいことについて[フィードバックをお送り](https://aka.ms/vsfeedback/browsecpp)ください。 フィードバックは、、、 **`/fsanitize=thread`** **`/fsanitize=leak`** **`/fsanitize=memory`** 、 **`/fsanitize=undefined`** 、またはなど、その他の sanitizers の優先順位付けに役立ち **`/fsanitize=hwaddress`** ます。 問題が発生した場合は、 [ここでバグを報告](https://aka.ms/feedback/report?space=62) できます。

## <a name="use-the-addresssanitizer-from-a-developer-command-prompt"></a><a name="command-prompt"></a> 開発者コマンドプロンプトから AddressSanitizer を使用する

**`/fsanitize=address`** AddressSanitizer ランタイムのコンパイルを有効にするには、[開発者コマンドプロンプト](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)でコンパイラオプションを使用します。 この **`/fsanitize=address`** オプションは、既存の C++ または C のすべての最適化レベルと互換性があります (たとえば、、、、 `/Od` `/O1` 、など `/O2` `/O2 /GL` `PGO` )。 このオプションは、static および dynamic crt と連動します (たとえば、、、 `/MD` `/MDd` `/MT` 、 `/MTd` )。 EXE または DLL を作成するかどうかによって動作します。 呼び出し履歴を最適に書式設定するには、デバッグ情報が必要です。 次の例で `cl /fsanitize=address /Zi` は、コマンドラインでが渡されます。

AddressSanitizer ライブラリ (.lib ファイル) は、自動的にリンクされます。 詳細については、「 [AddressSanitizer language、build、およびデバッグリファレンス](asan-building.md)」を参照してください。

### <a name="example---basic-global-buffer-overflow"></a>例-基本グローバルバッファーオーバーフロー

```cpp
// basic-global-overflow.cpp
#include <stdio.h>
int x[100];
int main() {
    printf("Hello!\n");
    x[100] = 5; // Boom!
    return 0;
}
```

Visual Studio 2019 の開発者コマンドプロンプトを使用し *`main.cpp`* て、を使用してコンパイルする `/fsanitize=address /Zi`

:::image type="content" source="media/asan-command-basic-global-overflow.png" alt-text="AddressSanitizer オプションを使用してコンパイルするコマンドを示すコマンドプロンプトのスクリーンショット。":::

結果のをコマンドラインで実行すると、 *`main.exe`* 次に示す形式のエラーレポートが作成されます。

7つの主要な情報を強調表示する、次のような赤色の枠が表示されているとします。

:::image type="content" source="media/asan-basic-global-overflow.png" alt-text="基本的なグローバルオーバーフローエラーを示すデバッガーのスクリーンショット。":::

### <a name="red-highlights-from-top-to-bottom"></a>赤の強調表示 (上から下)

1. メモリの安全性のバグは、グローバルバッファーオーバーフローです。
2. ユーザー定義変数の外側に **4 バイト** (32 ビット) が **格納さ** れています。
3. ストアは、 `main()` `basic-global-overflow.cpp` 7 行目のファイルで定義されている関数で実行されました。
4. という名前の変数は、 `x` 3 行目の basic-global-overflow で定義されています (列 8)
5. このグローバル変数 `x` のサイズは400バイトです。
6. ストアの対象となるアドレスを記述する正確な [シャドウバイト](./asan-shadow-bytes.md) の値は、 `0xf9`
7. シャドウバイトの凡例 `0xf9` は、の右側に余白があることを示します。 `int x[100]`

> [!NOTE]
> 呼び出し履歴内の関数名は、エラー発生時にランタイムによって呼び出される [Llvm のシンボル](https://llvm.org/docs/CommandGuide/llvm-symbolizer.html) によって生成されます。

## <a name="use-the-addresssanitizer-in-visual-studio"></a><a name="ide-msbuild"></a> Visual Studio での AddressSanitizer の使用

AddressSanitizer は、Visual Studio IDE に統合されています。 MSBuild プロジェクトの AddressSanitizer をオンにするには、ソリューションエクスプローラーでプロジェクトを右クリックし、[ **プロパティ**] を選択します。 [**プロパティページ**] ダイアログボックスで、[**構成プロパティ**] [  >  **C/c + +** 全般] を選択し、  >  [ **Enable AddressSanitizer** ] プロパティを変更します。 **[OK]** を選択して変更を保存します。

:::image type="content" source="media/asan-project-system-dialog.png" alt-text="[プロパティページ] ダイアログのスクリーンショット。 &quot;Enable AddressSanitizer&quot; プロパティが表示されます。":::

IDE からビルドするには、互換性のない [オプション](./asan-known-issues.md#incompatible-options)を選択解除します。 (またはデバッグモード) を使用してコンパイルされた既存のプロジェクトでは **`/Od`** 、次のオプションを無効にする必要がある場合があります。

- [エディットコンティニュを](/visualstudio/debugger/how-to-enable-and-disable-edit-and-continue)無効にする
- オフ[ `/RTC1` (ランタイムチェック)](../build/reference/rtc-run-time-error-checks.md)
- オフ[ `/INCREMENTAL` (インクリメンタルリンク)](../build/reference/incremental-link-incrementally.md)

デバッガーをビルドして実行するには、「 **F5**」と入力します。 Visual Studio では、次のウィンドウが表示されます。

:::image type="content" source="media/asan-global-buffer-overflow-F5.png" alt-text="グローバルバッファーオーバーフローエラーを示すデバッガーのスクリーンショット。":::

## <a name="using-the-addresssanitizer-from-visual-studio-cmake"></a><a name="ide-cmake"></a> Visual Studio からの AddressSanitizer の使用: CMake

[Windows を対象とするように作成された CMake プロジェクト](../build/cmake-projects-in-visual-studio.md)の AddressSanitizer を有効にするには、次の手順を実行します。

1. IDE の上部にあるツールバーの [ **構成** ] ドロップダウンを開き、[ **構成の管理**] を選択します。

   :::image type="content" source="media/asan-cmake-configuration-dropdown.png" alt-text="CMake 構成ドロップダウンのスクリーンショット。":::

   このオプションを選択すると、[CMake プロジェクト設定エディター] が開き、ファイルの CMakeSettings.jsに保存されます。

1. エディターで [ **JSON の編集** ] リンクを選択します。 この選択により、ビューが未加工の JSON に切り替わります。

1. プロパティ **"addressSanitizerEnabled": true** を追加します。

   このイメージは、その変更後に CMakeSettings.jsます。

   :::image type="content" source="media/asan-cmake-json.png" alt-text="CMakeSettings.jsのテキストエディタービューのスクリーンショット。":::

1. **Ctrl + S キーを押し** てこの JSON ファイルを保存し、 **F5** キーを押してデバッガーで再コンパイルして実行します。

このスクリーンショットでは、CMake ビルドからエラーをキャプチャします。

:::image type="content" source="media/asan-cmake-error-f5.png" alt-text="CMake ビルドエラーメッセージのスクリーンショット。":::

## <a name="addresssanitizer-crash-dumps"></a><a name="crash-dumps"></a> AddressSanitizer クラッシュダンプ

クラウドおよび分散ワークフローで使用するために、AddressSanitizer に新機能が導入されました。 この機能により、IDE での AddressSanitizer エラーのオフライン表示が可能になります。 ライブデバッグセッションで発生する場合と同様に、エラーはソースの上にオーバーレイされます。

これらの新しいダンプファイルを使用すると、バグを分析する際の効率が向上する可能性があります。 リモートデータを再実行したり、オフラインになったコンピューターを探したりする必要はありません。

後で別のコンピューターの Visual Studio で表示できる新しい種類のダンプファイルを生成するには、次のようにします。

```cmd
set ASAN_SAVE_DUMPS=MyFileName.dmp
```

Visual Studio 16.9 以降では、ファイルに格納されている、ソースコードの上に正確に診断された **エラーを** 表示でき *`*.dmp`* ます。

[この新しいクラッシュダンプ機能](./asan-offline-crash-dumps.md) により、クラウドベースのワークフローまたは分散テストが可能になります。 また、この方法を使用して、あらゆるシナリオで、実用的な詳細なバグをファイルに登録することもできます。

## <a name="example-errors"></a><a name="error-types"></a> エラーの例

AddressSanitizer は、いくつかの種類のメモリ誤用エラーを検出できます。 AddressSanitizer () コンパイラオプションを使用してコンパイルされたバイナリを実行したときに報告されるランタイムエラーの多くを次に示し **`/fsanitize=address`** ます。

- [`alloc-dealloc-mismatch`](error-alloc-dealloc-mismatch.md)
- [`allocation-size-too-big`](error-allocation-size-too-big.md)
- [`calloc-overflow`](error-calloc-overflow.md)
- [`double-free`](error-double-free.md)
- [`dynamic-stack-buffer-overflow`](error-dynamic-stack-buffer-overflow.md)
- [`global-buffer-overflow`](error-global-buffer-overflow.md)
- [`heap-buffer-overflow`](error-heap-buffer-overflow.md)
- [`heap-use-after-free`](error-heap-use-after-free.md)
- [`invalid-allocation-alignment`](error-invalid-allocation-alignment.md)
- [`memcpy-param-overlap`](error-memcpy-param-overlap.md)
- [`new-delete-type-mismatch`](error-new-delete-type-mismatch.md)
- [`stack-buffer-overflow`](error-stack-buffer-overflow.md)
- [`stack-buffer-underflow`](error-stack-buffer-underflow.md)
- [`stack-use-after-return`](error-stack-use-after-return.md)
- [`stack-use-after-scope`](error-stack-use-after-scope.md)
- [`strncat-param-overlap`](error-strncat-param-overlap.md)
- [`use-after-poison`](error-use-after-poison.md)

例の詳細については、「 [AddressSanitizer error の例](./asan-error-examples.md)」を参照してください。

## <a name="differences-with-clang-120"></a><a name="differences"></a> Clang 12.0 との違い

MSVC は、次の2つの機能領域で Clang 12.0 と現在異なります。

- **stack-スコープ適用後** -この設定は既定でオンになっており、無効にすることはできません。
- **スタック使用-戻り値** -この機能には追加のコンパイラオプションが必要であり、設定でのみ使用することはできません `ASAN_OPTIONS` 。

これらの決定は、この最初のバージョンを配信するために必要なテストマトリックスを減らすために行われました。

Visual Studio 2019 16.9 で誤検知につながる可能性がある機能は含まれていませんでした。 この作業分野は、数十年の既存のコードとの相互運用を検討する際に必要な、効果的なテストの整合性を強制しています。 今後のリリースでは、より多くの機能を考慮することができます。

- [初期化順序 Fiasco](https://github.com/google/sanitizers/wiki/AddressSanitizerInitializationOrderFiasco)
- [オブジェクト内のオーバーフロー](https://github.com/google/sanitizers/wiki/AddressSanitizerIntraObjectOverflow)
- [コンテナーオーバーフロー](https://github.com/google/sanitizers/wiki/AddressSanitizerContainerOverflow)
- [ポインターの減算/比較](https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html)

詳細については、「MSVC を使用した [AddressSanitizer のビルド](./asan-building.md)」を参照してください。

## <a name="existing-industry-documentation"></a><a name="external-docs"></a> 既存の業界ドキュメント

これらの言語およびプラットフォームに依存する AddressSanitizer テクノロジの実装については、広範なドキュメントが既に存在します。

- [Google](https://github.com/google/sanitizers/wiki/AddressSanitizer)
- [Apple](https://developer.apple.com/documentation/xcode/diagnosing_memory_thread_and_crash_issues_early)
- [GCC](https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html)

この [AddressSanitizer](https://www.usenix.org/system/files/conference/atc12/atc12-final39.pdf) のよる著書ペーパーでは、実装について説明しています。

## <a name="see-also"></a>関連項目

[AddressSanitizer の既知の問題](./asan-known-issues.md)\
[AddressSanitizer ビルドと言語リファレンス](./asan-building.md)\
[AddressSanitizer ランタイムリファレンス](./asan-runtime.md)\
[AddressSanitizer shadow bytes](./asan-shadow-bytes.md)\
[AddressSanitizer クラウドまたは分散テスト](./asan-offline-crash-dumps.md)\
[AddressSanitizer デバッガーの統合](./asan-debugger-integration.md)\
[AddressSanitizer エラーの例](./asan-error-examples.md)
