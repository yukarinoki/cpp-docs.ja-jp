---
title: PDB (プログラム データベースを使用) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
dev_langs:
- C++
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 776d23c0c0c7ce392b1ff0d7a989c3c5503129b8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376000"
---
# <a name="pdb-use-program-database"></a>/PDB (プログラム データベースの使用)
```  
/PDB:filename  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ファイル名*  
 プログラム データベース (PDB)、リンカーによって作成されるユーザー指定の名前。 既定の名前に置き換えます。  
  
## <a name="remarks"></a>コメント  
 既定では、ときに[/debug](../../build/reference/debug-generate-debug-info.md)を指定すると、リンカーはデバッグ情報が保持されているプログラム データベース (PDB) を作成します。 PDB の既定のファイル名は、プログラムおよび拡張子 .pdb の基本の名前を持ちます。  
  
 /PDB を使用して:*filename* PDB ファイルの名前を指定します。 /DEBUG が指定されていない場合、/PDB オプションは無視されます。  
  
 PDB ファイルには、最大 2 GB を指定できます。  
  
 詳細については、次を参照してください。[リンカー入力としての .pdb ファイル](../../build/reference/dot-pdb-files-as-linker-input.md)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**デバッグ**プロパティ ページ。  
  
4.  変更、**プログラム データベース ファイルの生成**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)