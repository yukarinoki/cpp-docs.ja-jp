---
title: -Fd (プログラム データベース ファイル名) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /FD
- VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName
- VC.Project.VCCLCompilerTool.ProgramDataBaseFileName
dev_langs:
- C++
helpviewer_keywords:
- /FD compiler option [C++]
- program database file name [C++]
- -FD compiler option [C++]
- PDB files, creating
- program database compiler option [C++]
- .pdb files, creating
- FD compiler option [C++]
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07ab9f1d9c5c611b8da8b19860fe9e0c05351d75
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375624"
---
# <a name="fd-program-database-file-name"></a>/Fd (プログラム データベース ファイル名)
によって作成されたプログラム データベース (PDB) ファイルのファイル名を指定[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
/Fdpathname  
```  
  
## <a name="remarks"></a>コメント  
 せず **/Fd**、PDB ファイル名の既定値は VC*x*0. pdb、場所*x*メジャー バージョンの Visual C の使用中です。  
  
 ファイル名 (パスはバック スラッシュで終わる) を含まないパス名を指定する場合、コンパイラが VC をという名前の .pdb ファイルを作成*x*指定したディレクトリ内の 0 pdb です。  
  
 拡張機能を含まないファイル名を指定する場合、コンパイラは、拡張機能として .pdb を使用します。  
  
 このオプションも最小リビルドとインクリメンタル コンパイルの使用状態 (.idb) ファイルを名前します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[出力ファイル]** プロパティ ページをクリックします。  
  
4.  変更、**プログラム データベース ファイル名**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>」を参照してください。  
  
## <a name="example"></a>例  
 このコマンドラインには、名前付き PROG.pdb および名前付き PROG.idb .idb ファイルの .pdb ファイルが作成されます。  
  
```  
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP  
```  
  
## <a name="see-also"></a>関連項目  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [パス名の指定](../../build/reference/specifying-the-pathname.md)