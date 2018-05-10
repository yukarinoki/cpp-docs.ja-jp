---
title: -Fp (名前です。Pch ファイル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80f59477695b83b33dd3cfa2b37837c5b52c8002
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="fp-name-pch-file"></a>/Fp (.pch ファイルの名前の指定)
プリコンパイル済みヘッダーの既定のパス名を使用する代わりに、パス名を提供します。  
  
## <a name="syntax"></a>構文  
  
> **/Fp**_パス名_  
  
## <a name="remarks"></a>コメント  
 このオプションを使用して[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)または[/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)プリコンパイル済みヘッダーの既定のパス名を使用する代わりに、パス名を指定します。 使用することも **/Fp**で **/Yc**とは異なるプリコンパイル済みヘッダー ファイルの使用を指定する、**/Yc * * * ファイル名*引数とソース ファイルのベース名から。  
  
 パス名の一部として、拡張機能を指定しないと、拡張子を .pch と見なされます。 ファイル名のないディレクトリを指定すると、既定のファイル名が VC*x*0. pch 場所*x*メジャー バージョンの Visual C の使用中です。  
  
 使用することも、 **/Fp**オプションは **/Yu**です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**プリコンパイル済みヘッダー**プロパティ ページ。  
  
4.  変更、**プリコンパイル済みヘッダー ファイル**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>」を参照してください。  
  
## <a name="example"></a>例  
 プログラムのデバッグ バージョンのプリコンパイル済みヘッダー ファイルを作成するヘッダー ファイルとソース コードの両方をコンパイルする場合は、コマンドをなどを指定できます。  
  
```  
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP  
```  
  
## <a name="example"></a>例  
 次のコマンドは、MYPCH.pch をという名前のプリコンパイル済みヘッダー ファイルの使用を指定します。 MYAPP.h を通じて PROG.cpp 内のソース コードがプリコンパイルされていると、プリコンパイルされたコードが MYPCH.pch に格納されていると見なされます。 MYPCH.pch のコンテンツを使用し、.obj ファイルを作成する PROG.cpp の残りの部分をコンパイルします。 この例の出力は、PROG.exe をという名前のファイルです。  
  
```  
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP  
```  
  
## <a name="see-also"></a>関連項目  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)