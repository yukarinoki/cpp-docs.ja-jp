---
title: /Gd、/Gr、/Gv、/Gz (呼び出し規約)
ms.date: 09/05/2018
f1_keywords:
- /gr
- /Gv
- /gz
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
ms.openlocfilehash: 7c4f7e6edb020f5c8d2abf80f14df33e18a915c5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817466"
---
# <a name="gd-gr-gv-gz-calling-convention"></a>/Gd、/Gr、/Gv、/Gz (呼び出し規約)

これらのオプションでは、関数の引数をスタックにプッシュする順序、呼び出し元と呼び出し先のどちらの関数が呼び出しの最後にスタックから引数を削除するか、および個々の関数を識別するためにコンパイラが使用する名前装飾規約を決定します。

## <a name="syntax"></a>構文

> **/Gd**<br/>
> **/Gr**<br/>
> **/Gv**<br/>
> **/Gz**<br/>

## <a name="remarks"></a>Remarks

**/Gd**、既定の設定を指定します、 [_ _cdecl](../../cpp/cdecl.md)関数とマークされている関数に、C++ メンバーを除くすべての関数の呼び出し規約[_ _stdcall](../../cpp/stdcall.md)、 [_ _fastcall](../../cpp/fastcall.md)、または[_ _vectorcall](../../cpp/vectorcall.md)します。

**/Gr**を指定します、`__fastcall`関数という名前の C++ メンバー関数を除くすべての関数の呼び出し規約、`main`とマークされている関数`__cdecl`、 `__stdcall`、または`__vectorcall`します。 すべて`__fastcall`関数プロトタイプを用意する必要があります。 この呼び出し規約は、x86 を対象とするコンパイラでのみ使用され、他のアーキテクチャを対象とするコンパイラでは無視されます。

**/Gz**を指定します、`__stdcall`関数という名前の C++ メンバー関数を除くすべての関数の呼び出し規約、`main`とマークされている関数`__cdecl`、 `__fastcall`、または`__vectorcall`します。 すべて`__stdcall`関数プロトタイプを用意する必要があります。 この呼び出し規約は、x86 を対象とするコンパイラでのみ使用され、他のアーキテクチャを対象とするコンパイラでは無視されます。

**/Gv**を指定します、 `__vectorcall` C++ メンバー関数を除くすべての関数の呼び出し規約、main という名前の関数、関数、`vararg`可変個引数リスト、または競合するいるとマークされている関数`__cdecl`、`__stdcall`、または`__fastcall`属性。 この呼び出し規約は、/arch:SSE2 以上をサポートする x86 アーキテクチャおよび x64 アーキテクチャのみで使用され、ARM アーキテクチャを対象とするコンパイラでは無視されます。

可変数の引数を受け取る関数には `__cdecl` が指定されている必要があります。

**/Gd**、 **/Gr**、 **/Gv**と **/Gz**と互換性がない[/clr:safe](clr-common-language-runtime-compilation.md)または **/clr: 純粋な**. **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

> [!NOTE]
> 既定では x86 プロセッサでは、C++ メンバー関数を使用して、 [_ _thiscall](../../cpp/thiscall.md)します。

すべてのプロセッサで、`__cdecl`、`__fastcall`、`__vectorcall`、または `__stdcall` のいずれかとして明示的に指定されているメンバー関数では、指定の呼び出し規約が使用されます (そのアーキテクチャで無視されない場合)。 可変個の引数を取るメンバー関数では、常に `__cdecl` 呼び出し規約が使われます。

これのコンパイラ オプションを指定しても、C++ のメソッドや関数の名前装飾規約には影響しません。 
  `extern "C"` として宣言しない限り、C++ のメソッドや関数では、別の名前装飾規約が使用されます。 詳細については、[装飾名](decorated-names.md)を参照してください。

呼び出し規約の詳細については、[呼び出し規則](../../cpp/calling-conventions.md)を参照してください。

## <a name="cdecl-specifics"></a>__cdecl の場合

x86 プロセッサでは、すべての関数の引数は、スタックで右から左へ渡されます。 ARM アーキテクチャおよび x64 アーキテクチャでは、一部の引数はレジスタで渡され、残りの引数はスタックで右から左へ渡されます。 呼び出しルーチンによって、スタックから引数がポップされます。

C の `__cdecl` 名前付け規則では、関数名の前にアンダースコア (`_`) が付けられ、大文字小文字は変換されません。 
  `extern "C"` として宣言しない限り、C++ の関数では、別の名前装飾規約が使用されます。 詳細については、[装飾名](decorated-names.md)を参照してください。

## <a name="fastcall-specifics"></a>__fastcall の場合


  `__fastcall` 関数の一部の引数はレジスタ (x86 プロセッサの場合 ECX および EDX) で渡され、その他の引数は右から左の順にスタックにプッシュされます。 これらの引数は、呼び出し元に制御が戻る前に、呼び出し先のルーチンによってスタックからポップされます。 通常、 **/Gr** 実行時間を短縮します。

> [!NOTE]
> インライン アセンブリ言語で記述された関数に対して `__fastcall` 呼び出し規則を使用する場合は注意してください。 レジスタを使用すると、コンパイラ側で使用するレジスタと競合する場合があります。

C、`__fastcall`規則では、関数名の命名に続く、アット マーク (**\@**) サイズ (バイト単位)、関数の引数の後にします。 大文字と小文字は変換されません。 コンパイラでは、次の名前付け規則用テンプレートが使用されます。

`@function_name@number`


  `__fastcall` 名前付け規則を使う場合は、標準のインクルード ファイルを使用してください。 使用しないと、外部参照が解決されません。

## <a name="stdcall-specifics"></a>__stdcall の場合


  `__stdcall` 関数の引数は、右から左の順序でスタックにプッシュされます。これらの引数は、呼び出し元に制御が戻る前に、呼び出し先の関数によってポップされます。

C、`__stdcall`規則では、関数名の名前を付ける前にアンダー スコア (**\_**) 後に、アット マーク (**\@**) との関数のサイズ引数 (バイト単位)。 大文字小文字は変換されません。 コンパイラでは、次の名前付け規則用テンプレートが使用されます。

`_functionname@number`

## <a name="vectorcall-specifics"></a>__vectorcall の場合


  `__vectorcall` 関数の整数引数は、最大 2 個 (x86) または最大 4 個 (x64) の整数レジスタ、および浮動小数点とベクター値の場合は最大の 6 個の XMM レジスタを使用して値渡しされ、その他はスタックで右から左へ渡されます。 呼び出された関数は、制御を戻す前にスタックをクリーンオフします。 ベクターと浮動小数点戻り値は、XMM0 で返されます。

C、`__vectorcall`名前付け規則は、関数名の後に 2 つのアット (**\@\@**) と (バイト単位)、関数の引数のサイズ。 大文字小文字は変換されません。 コンパイラでは、次の名前付け規則用テンプレートが使用されます。

`functionname@@number`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 選択、 **C/C++** > **詳細**プロパティ ページ。

1. 変更、**呼び出し規約**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CallingConvention%2A>

## <a name="see-also"></a>関連項目

- [MSVC コンパイラ オプション](compiler-options.md)
- [MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)
