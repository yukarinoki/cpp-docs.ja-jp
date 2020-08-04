---
title: /RTC (ランタイム エラー チェック)
ms.date: 07/31/2020
f1_keywords:
- /rtc
- VC.Project.VCCLCompilerTool.SmallerTypeCheck
- VC.Project.VCCLCompilerTool.UninitializedVariableCheck
- VC.Project.VCCLCompilerTool.StackFrameCheck
- VC.Project.VCCLCompilerTool.BasicRuntimeChecks
helpviewer_keywords:
- /RTCs compiler option [C++]
- -RTC1 compiler option [C++]
- run-time errors, error checks
- -RTCu compiler option [C++]
- /RTC1 compiler option [C++]
- /RTCc compiler option [C++]
- /RTCu compiler option [C++]
- __MSVC_RUNTIME_CHECKS macro
- -RTCs compiler option [C++]
- RTCs compiler option
- RTC1 compiler option
- run-time errors, run-time checks
- run-time checks, /RTC option
- RTCu compiler option
- RTCc compiler option
- -RTCc compiler option [C++]
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
ms.openlocfilehash: eefec0956bebe9f72324f3cbc61fccbc5e2e24d7
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520539"
---
# <a name="rtc-run-time-error-checks"></a>`/RTC`(ランタイムエラーチェック)

[Runtime_checks](../../preprocessor/runtime-checks.md)プラグマと共に、実行時エラーチェック機能を有効または無効にするために使用します。

## <a name="syntax"></a>構文

> **`/RTC1`**\
> **`/RTCc`**\
> **`/RTCs`**\
> **`/RTCu`**

## <a name="arguments"></a>引数

**`/RTC1`**<br/>
と同じ **`/RTCsu`** です。

**`/RTCc`**<br/>
小さいデータ型に値が割り当てられ、その結果、データが失われる場合に報告します。 たとえば、型の **`short`** 値 `0x0101` が型の変数に割り当てられているかどうかを報告し **`char`** ます。

このオプションを使用すると、切り捨ての対象となる状況を報告できます。 たとえば、の最初の8ビットを **`int`** として返す場合など **`char`** です。 では、 **`/RTCc`** 割り当てによって情報が失われた場合にランタイムエラーが発生するので、まず、実行時エラーを回避するために必要な情報をマスクします。 次に例を示します。

```C
#include <crtdbg.h>

char get8bits(unsigned value, int position) {
   _ASSERT(position < 32);
   return (char)(value >> position);
   // Try the following line instead:
   // return (char)((value >> position) & 0xff);
}

int main() {
   get8bits(12341235,3);
}
```

**`/RTCc`** は標準に準拠したコードを拒否するため、C++ 標準ライブラリではサポートされていません。 と C++ 標準ライブラリを使用するコードでは **`/RTCc`** 、コンパイラエラー [C1189](../../error-messages/compiler-errors-1/fatal-error-c1189.md)が発生する可能性があります。 `_ALLOW_RTCc_IN_STL`警告をサイレント状態にして、オプションを使用するように定義でき **`/RTCc`** ます。

**`/RTCs`**<br/>
次のように、スタックフレームの実行時エラーチェックを有効にします。

- ローカル変数を0以外の値に初期化します。 このオプションは、デバッグモードで実行しているときに表示されないバグを特定するのに役立ちます。 デバッグビルドでは、リリースビルドと比較してスタック変数の値がゼロになる可能性が高くなります。 これは、リリースビルドでのスタック変数のコンパイラの最適化によるものです。 プログラムがスタックの領域を使用すると、コンパイラによって0にリセットされることはありません。 これは、同じスタック領域を使用して初期化されていないスタック変数が、このスタックメモリの以前の使用から残された値を返す可能性があることを意味します。

- 配列などのローカル変数のオーバーランとアンダーランの検出。 **`/RTCs`** は、構造体内でコンパイラの埋め込みによって生成されるメモリにアクセスするときにオーバーランを検出しません。 埋め込みは [`align`](../../cpp/align-cpp.md) 、、 [ `/Zp` (構造体メンバーの配置)](zp-struct-member-alignment.md)、またはを使用して、また [`pack`](../../preprocessor/pack.md) は、コンパイラによるパディングの追加を要求するように構造体要素を順序付けする場合に発生する可能性があります。

- スタックポインターの検証。スタックポインターの破損を検出します。 スタックポインターの破損は、呼び出し規約の不一致によって発生する可能性があります。 たとえば、関数ポインターを使用して、としてエクスポートされた DLL 内の関数を呼び出し [`__stdcall`](../../cpp/stdcall.md) ますが、関数へのポインターはとして宣言し [`__cdecl`](../../cpp/cdecl.md) ます。

**`/RTCu`**<br/>
変数が初期化されずに使用された場合に報告します。 たとえば、警告 C4701 を生成する命令によって、で実行時エラーが発生する場合もあり **`/RTCu`** ます。 [コンパイラの警告 (レベル1およびレベル 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)を生成する命令では、で実行時エラーが発生 **`/RTCu`** します。

ただし、次のコードについて考えてみましょう。

```cpp
int a, *b, c;
if ( 1 )
b = &a;
c = a;  // No run-time error with /RTCu
```

変数が初期化されている場合は、実行時にによって報告されません **`/RTCu`** 。 たとえば、変数がポインターによってエイリアス化された後、コンパイラは変数を追跡せず、未初期化の使用をレポートします。 実際には、変数のアドレスを取得することによって変数を初期化できます。 **`&`** この場合、演算子は代入演算子のように動作します。

## <a name="remarks"></a>Remarks

実行時エラーチェックを使用すると、実行中のコードで問題を見つけることができます。詳細については、「[方法: ネイティブランタイムチェックを使用する](/visualstudio/debugger/how-to-use-native-run-time-checks)」を参照してください。

コマンドラインでは、複数のオプションを指定でき **`/RTC`** ます。 オプションの引数は、組み合わせて使用できます。たとえば、 **`/RTCcu`** はと同じ **`/RTCc /RTCu`** です。

任意のコンパイラオプションを使用してコマンドラインでプログラムをコンパイルした場合 **`/RTC`** 、 [`optimize`](../../preprocessor/optimize.md) コード内のプラグマ命令は警告なしで失敗します。 これは、実行時エラーチェックがリリース (最適化) ビルドで有効ではないためです。

**`/RTC`** 開発ビルドに使用します。**`/RTC`** リリースビルドには使用しないでください。 **`/RTC`** コンパイラの最適化では使用できません ([ `/O` オプション (コードの最適化)](o-options-optimize-code.md))。 でビルドされたプログラムイメージ **`/RTC`** は、 **`/Od`** (ビルドより最大5% 低速) でビルドされたイメージよりも若干大きく、少し遅くなり **`/Od`** ます。

`__MSVC_RUNTIME_CHECKS`オプションまたはを使用すると、プリプロセッサディレクティブが定義されます **`/RTC`** [`/GZ`](gz-enable-stack-frame-run-time-error-checking.md) 。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +****コード生成**] プロパティページを選択します。  

1. 次のプロパティの一方または両方を変更します:**基本ランタイムチェック**または**小さい型チェック**。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> プロパティを参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[方法: ネイティブ ランタイム チェックを使用する](/visualstudio/debugger/how-to-use-native-run-time-checks)
