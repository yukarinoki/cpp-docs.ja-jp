---
title: /Gd、/Gr、/Gv、/Gz (呼び出し規約)
ms.date: 09/05/2018
f1_keywords:
- /Gr
- /Gv
- /Gd
- VC.Project.VCCLCompilerTool.CallingConvention
helpviewer_keywords:
- -Gd compiler option [C++]
- -Gv compiler option [C++]
- /Gv compiler option [C++]
- -Gr compiler option [C++]
- Gd compiler option [C++]
- Gr compiler option [C++]
- /Gz compiler option [C++]
- -Gz compiler option [C++]
- /Gd compiler option [C++]
- Gz compiler option [C++]
- Gv compiler option [C++]
- /Gr compiler option [C++]
ms.assetid: fd3110cb-2d77-49f2-99cf-a03f9ead00a3
ms.openlocfilehash: 73fce079a98a3f4afaa35f8b8c6630fc8a9b4ca4
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825527"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd、/Gr、/Gv、/Gz (呼び出し規約)

これらのオプションでは、関数の引数をスタックにプッシュする順序、呼び出し元と呼び出し先のどちらの関数が呼び出しの最後にスタックから引数を削除するか、および個々の関数を識別するためにコンパイラが使用する名前装飾規約を決定します。

## <a name="syntax"></a>構文

> **/Gd**\
> **/Gr**\
> **/Gv**\
> **/Gz**

## <a name="remarks"></a>解説

**/Gd** では、[__stdcall](../../cpp/stdcall.md)、[__fastcall](../../cpp/fastcall.md)、または [__vectorcall](../../cpp/vectorcall.md) が指定されている関数と C++ メンバー関数を除く、すべての関数の [__cdecl](../../cpp/cdecl.md) 呼び出し規約を指定します。これは既定の設定です。

**/Gr**は、 `__fastcall` C++ メンバー関数、 `main`という名前の関数、、、また`__cdecl`は`__stdcall` `__vectorcall`とマークされている関数を除くすべての関数の呼び出し規約を指定します。 すべての `__fastcall` 関数には、プロトタイプ宣言が必要です。 この呼び出し規約は、x86 を対象とするコンパイラでのみ使用され、他のアーキテクチャを対象とするコンパイラでは無視されます。

**/Gz**は、 `__stdcall` C++ メンバー関数、 `main`という名前の関数、、、また`__cdecl`は`__fastcall` `__vectorcall`とマークされている関数を除くすべての関数の呼び出し規約を指定します。 すべての `__stdcall` 関数には、プロトタイプ宣言が必要です。 この呼び出し規約は、x86 を対象とするコンパイラでのみ使用され、他のアーキテクチャを対象とするコンパイラでは無視されます。

**/Gv**は、 `__vectorcall` C++ メンバー関数、という名前`main` `vararg`の関数、可変個引数リストを持つ関数、または競合`__cdecl`する、 `__stdcall`、または`__fastcall`属性でマークされている関数を除くすべての関数の呼び出し規約を指定します。 この呼び出し規約は、/arch:SSE2 以上をサポートする x86 アーキテクチャおよび x64 アーキテクチャのみで使用され、ARM アーキテクチャを対象とするコンパイラでは無視されます。

可変数の引数を受け取る関数には `__cdecl` が指定されている必要があります。

**/Gd**、**/Gr**、**/Gv**、および **/Gz** は、[/clr:safe](clr-common-language-runtime-compilation.md) または **/clr:pure** と互換性がありません。 **/clr:pure** および **/clr:safe** コンパイラ オプションは Visual Studio 2015 では非推奨とされており、Visual Studio 2017 以降ではサポートされていません。

> [!NOTE]
> 既定では、x86 プロセッサの場合、C++ メンバー関数では [__thiscall](../../cpp/thiscall.md) が使用されます。

すべてのプロセッサで、`__cdecl`、`__fastcall`、`__vectorcall`、または `__stdcall` のいずれかとして明示的に指定されているメンバー関数では、指定の呼び出し規約が使用されます (そのアーキテクチャで無視されない場合)。 可変個の引数を取るメンバー関数では、常に `__cdecl` 呼び出し規約が使われます。

これのコンパイラ オプションを指定しても、C++ のメソッドや関数の名前装飾規約には影響しません。 `extern "C"` として宣言しない限り、C++ のメソッドや関数では、別の名前装飾規約が使用されます。 詳細については、「[装飾名](decorated-names.md)」を参照してください。

呼び出し規則の詳細については、「[呼び出し規則](../../cpp/calling-conventions.md)」を参照してください。

## <a name="__cdecl-specifics"></a>__cdecl の場合

x86 プロセッサでは、すべての関数の引数は、スタックで右から左へ渡されます。 ARM アーキテクチャおよび x64 アーキテクチャでは、一部の引数はレジスタで渡され、残りの引数はスタックで右から左へ渡されます。 呼び出しルーチンによって、スタックから引数がポップされます。

C の `__cdecl` 名前付け規則では、関数名の前にアンダースコア (`_`) が付けられ、大文字小文字は変換されません。 `extern "C"` として宣言しない限り、C++ の関数では、別の名前装飾規約が使用されます。 詳細については、「[装飾名](decorated-names.md)」を参照してください。

## <a name="__fastcall-specifics"></a>__fastcall の場合

`__fastcall` 関数の一部の引数はレジスタ (x86 プロセッサの場合 ECX および EDX) で渡され、その他の引数は右から左の順にスタックにプッシュされます。 これらの引数は、呼び出し元に制御が戻る前に、呼び出し先のルーチンによってスタックからポップされます。 通常、**/Gr** オプションを使用すると実行時間が短縮されます。

> [!NOTE]
> インライン アセンブリ言語で記述された関数に対して `__fastcall` 呼び出し規則を使用する場合は注意してください。 レジスタを使用すると、コンパイラ側で使用するレジスタと競合する場合があります。

C の場合、 `__fastcall`名前付け規則では、関数名の前にアット**\@** マーク () を付け、その後に関数の引数のサイズ (バイト単位) を指定します。 大文字と小文字は変換されません。 コンパイラでは、次の名前付け規則用テンプレートが使用されます。

`@function_name@number`

`__fastcall` 名前付け規則を使う場合は、標準のインクルード ファイルを使用してください。 使用しないと、外部参照が解決されません。

## <a name="__stdcall-specifics"></a>__stdcall の場合

`__stdcall` 関数の引数は、右から左の順序でスタックにプッシュされます。これらの引数は、呼び出し元に制御が戻る前に、呼び出し先の関数によってポップされます。

C の場合、 `__stdcall`名前付け規則では、関数名の前に**\_** アンダースコア ()、続けてアットマーク**\@**()、および関数の引数のサイズ (バイト単位) を指定します。 大文字小文字は変換されません。 コンパイラでは、次の名前付け規則用テンプレートが使用されます。

`_functionname@number`

## <a name="__vectorcall-specifics"></a>__vectorcall の場合

`__vectorcall`関数の整数引数は、最大2つ (x86) または 4 (x64) の整数レジスタ、および浮動小数点とベクター値の最大6つの XMM レジスタを使用して値渡しされ、残りはスタックで右から左へ渡されます。 呼び出された関数は、制御を戻す前にスタックをクリーンオフします。 ベクターと浮動小数点戻り値は、XMM0 で返されます。

C の場合、 `__vectorcall`名前付け規則では、関数名の後に 2**\@** つのアット記号 () と、関数の引数のサイズ (バイト単位) を指定します。 大文字小文字は変換されません。 コンパイラでは、次の名前付け規則用テンプレートが使用されます。

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **C/c + +** > **詳細設定**] プロパティページを選択します。

1. **[呼び出し規約]** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A> 」を参照してください。

## <a name="see-also"></a>関連項目

- [MSVC コンパイラ オプション](compiler-options.md)
- [MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
