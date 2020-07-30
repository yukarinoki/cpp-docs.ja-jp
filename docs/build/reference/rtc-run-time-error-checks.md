---
title: /RTC (ランタイム エラー チェック)
ms.date: 11/04/2016
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
ms.openlocfilehash: 49f0e4bace5f3dd199b58854e838204bd2cd5f3b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222018"
---
# <a name="rtc-run-time-error-checks"></a>/RTC (ランタイム エラー チェック)

[Runtime_checks](../../preprocessor/runtime-checks.md)プラグマと共に、実行時エラーチェック機能を有効または無効にするために使用します。

## <a name="syntax"></a>構文

```
/RTC1
/RTCc
/RTCs
/RTCu
```

## <a name="arguments"></a>引数

**1**<br/>
**/Rtc**に相当 `su` します。

**40u-c**<br/>
小さいデータ型に値が割り当てられ、その結果、データが失われる場合に報告します。 たとえば、型の値 `short 0x101` が型の変数に割り当てられているとし **`char`** ます。

このオプションは、たとえば、の最初の8ビットをとして返す場合に、切り捨てを行う状況を報告し **`int`** **`char`** ます。 **/RTC** `c` 割り当ての結果として情報が失われると、/rtc によって実行時エラーが発生するため、 **/rtc**の結果として実行時エラーを回避するために必要な情報をマスクすることができ `c` ます。 次に例を示します。

```
#include <crtdbg.h>

char get8bits(int value, int position) {
   _ASSERT(position < 32);
   return (char)(value >> position);
   // Try the following line instead:
   // return (char)((value >> position) & 0xff);
}

int main() {
   get8bits(12341235,3);
}
```

**2$s**<br/>
次のように、スタックフレームの実行時エラーチェックを有効にします。

- ローカル変数を0以外の値に初期化します。 これは、デバッグモードで実行しているときに表示されないバグを識別するのに役立ちます。 リリースビルドでのスタック変数のコンパイラ最適化により、リリースビルドと比較して、デバッグビルドでスタック変数がゼロになる可能性が高くなります。 プログラムがスタックの領域を使用すると、コンパイラによって0にリセットされることはありません。 そのため、同じスタック領域を使用するように初期化されていない、初期化されていないスタック変数は、このスタックメモリの以前の使用から残された値を返すことができます。

- 配列などのローカル変数のオーバーランとアンダーランの検出。 **/Rtc** `s`は、構造体内でコンパイラの埋め込みによって発生するメモリにアクセスするときにオーバーランを検出しません。 [アラインメント](../../cpp/align-cpp.md)、 [/Zp (構造体メンバーの配置)](zp-struct-member-alignment.md)、または[パック](../../preprocessor/pack.md)を使用して埋め込みを行うことができます。また、埋め込みを追加するようにコンパイラに要求するように構造体要素を順序付けすることもできます。

- スタックポインターの検証。スタックポインターの破損を検出します。 スタックポインターの破損は、呼び出し規約の不一致によって発生する可能性があります。 たとえば、関数ポインターを使用して、 [__stdcall](../../cpp/stdcall.md)としてエクスポートされた DLL 内の関数を呼び出しますが、関数へのポインターを[__cdecl](../../cpp/cdecl.md)として宣言します。

**u**<br/>
変数が初期化されずに使用された場合に報告します。 たとえば、を生成する命令によって、 `C4701` **/rtc**で実行時エラーが発生する場合もあり `u` ます。 [コンパイラの警告 (レベル1およびレベル 4) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)を生成する命令は、 **/rtc**の下で実行時エラーを生成 `u` します。

ただし、次のコードについて考えてみましょう。

```cpp
int a, *b, c;
if ( 1 )
b = &a;
c = a;  // No run-time error with /RTCu
```

変数が初期化されている場合は、実行時に **/rtc**によってレポートされません `u` 。 たとえば、ポインターを使用して変数にエイリアスを付けると、コンパイラは変数を追跡せず、未初期化の使用を報告します。 実際には、変数のアドレスを取得することによって変数を初期化できます。 & 演算子は、このような場合に代入演算子のように動作します。

## <a name="remarks"></a>解説

実行時エラーチェックを使用すると、実行中のコードで問題を見つけることができます。詳細については、「[方法: ネイティブランタイムチェックを使用する](/visualstudio/debugger/how-to-use-native-run-time-checks)」を参照してください。

**/Rtc**コンパイラオプションのいずれかを使用してコマンドラインでプログラムをコンパイルすると、コード内のプラグマの[最適化](../../preprocessor/optimize.md)命令が警告なしで失敗します。 これは、ランタイムエラーチェックがリリース (最適化) ビルドで有効でないためです。

開発ビルドでは、 **/rtc**を使用する必要があります。**/Rtc**をリテールビルドに使用することはできません。 **/Rtc**をコンパイラの最適化と共に使用することはできません ([/O オプション (コードの最適化)](o-options-optimize-code.md))。 **/Rtc**でビルドされたプログラムイメージは、 **/od** ( **/od**ビルドより最大5% 低速) を使用してビルドされたイメージよりも若干大きく、わずかに遅くなります。

__MSVC_RUNTIME_CHECKS プリプロセッサディレクティブは、 **/rtc**オプションまたは[/GZ](gz-enable-stack-frame-run-time-error-checking.md)を使用するときに定義されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [**コード生成**] プロパティページをクリックします。

1. 次のプロパティの一方または両方を変更します:**基本ランタイムチェック**または**小さい型チェック**。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A> プロパティを参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)<br/>
[方法: ネイティブ ランタイム チェックを使用する](/visualstudio/debugger/how-to-use-native-run-time-checks)
