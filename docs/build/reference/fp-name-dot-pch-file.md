---
title: /Fp (.pch ファイルの名前の指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: 95506e17dff47e51cb7a3d83b629880f63422d26
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820391"
---
# <a name="fp-name-pch-file"></a>/Fp (.pch ファイルの名前の指定)

既定のパス名を使用する代わりにプリコンパイル済みヘッダーのパス名を提供します。

## <a name="syntax"></a>構文

> **/Fp**<em>パス名</em>

## <a name="remarks"></a>Remarks

このオプションを使用[/Yc (プリコンパイル済みヘッダー ファイルの作成)](yc-create-precompiled-header-file.md)または[/Yu (プリコンパイル済みヘッダー ファイルの使用)](yu-use-precompiled-header-file.md)プリコンパイル済みヘッダーの既定のパス名を使用する代わりにパス名を指定します。 使用することも **/Fp**で **/Yc**とは異なるプリコンパイル済みヘッダー ファイルの使用を指定する、 **/Yc**<em>filename</em>引数とソース ファイルのベース名にします。

パス名の一部として拡張機能を指定しない場合、拡張子を .pch と見なされます。 ファイル名のないディレクトリを指定する場合は、既定のファイル名、VC*x*0. pch 場所*x*使用中の Visual C のメジャー バージョンします。

使用することも、 **/Fp**オプションと **/Yu**します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**プリコンパイル済みヘッダー**プロパティ ページ。

1. 変更、**プリコンパイル済みヘッダー ファイル**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>

## <a name="example"></a>例

プログラムのデバッグ バージョンのプリコンパイル済みヘッダー ファイルを作成するヘッダー ファイルとソース コードの両方をコンパイルする場合などのコマンドを指定できます。

```
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

## <a name="example"></a>例

次のコマンドでは、MYPCH.pch をという名前のプリコンパイル済みヘッダー ファイルの使用を指定します。 MYAPP.h を通じて PROG.cpp でソース コードがプリコンパイルされていると、MYPCH.pch でプリコンパイルされたコードが置かれていると見なされます。 MYPCH.pch のコンテンツを使用し、.obj ファイルを作成する PROG.cpp の残りの部分をコンパイルします。 この例の出力は、PROG.exe という名前のファイルです。

```
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)<br/>
[パス名の指定](specifying-the-pathname.md)
