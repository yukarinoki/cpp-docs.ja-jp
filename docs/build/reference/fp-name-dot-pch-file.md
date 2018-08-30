---
title: -Fp (名前です。Pch ファイル) |Microsoft Docs
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
ms.openlocfilehash: 723bf8d6f49157a2cdc02376e1a628ba697eceb2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217992"
---
# <a name="fp-name-pch-file"></a>/Fp (.pch ファイルの名前の指定)
既定のパス名を使用する代わりにプリコンパイル済みヘッダーのパス名を提供します。  
  
## <a name="syntax"></a>構文  
  
> **/Fp**<em>パス名</em>  
  
## <a name="remarks"></a>Remarks  
 このオプションを使用[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)または[/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)プリコンパイル済みヘッダーの既定のパス名を使用する代わりにパス名を指定します。 使用することも **/Fp**で **/Yc**とは異なるプリコンパイル済みヘッダー ファイルの使用を指定する、 **/Yc**<em>filename</em>引数とソース ファイルのベース名にします。  
  
 パス名の一部として拡張機能を指定しない場合、拡張子を .pch と見なされます。 ファイル名のないディレクトリを指定する場合は、既定のファイル名、VC*x*0. pch 場所*x*使用中の Visual C のメジャー バージョンします。  
  
 使用することも、 **/Fp**オプションと **/Yu**します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  をクリックして、**プリコンパイル済みヘッダー**プロパティ ページ。  
  
4.  変更、**プリコンパイル済みヘッダー ファイル**プロパティ。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>  
  
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
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)