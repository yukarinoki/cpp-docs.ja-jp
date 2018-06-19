---
title: -PDBSTRIPPED (プライベート シンボルの除去) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
dev_langs:
- C++
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 331e490512afe8e9267eb1d0d370cbcf99aa99aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376638"
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (プライベート シンボルの除去)
```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *pdb_file_name*  
 削除されたプログラム データベース (PDB)、リンカーによって作成されるユーザー指定の名前。  
  
## <a name="remarks"></a>コメント  
 コンパイラやリンカーのいずれかと、プログラム イメージの PDB ファイルを生成するオプションをビルドするときに/PDBSTRIPPED オプションが 2 番目のプログラム データベース (PDB) ファイルを作成 ([/debug](../../build/reference/debug-generate-debug-info.md)、 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)/Zd、または/Zi)。 2 番目の PDB ファイルでは、顧客に提供しないシンボルが省かれています。 2 番目の PDB ファイルにはのみが含まれます。  
  
-   パブリック シンボル  
  
-   オブジェクト ファイルと対象となる実行可能ファイルの部分の一覧  
  
-   フレーム ポインター最適化 (FPO) デバッグ レコードのスタックを走査するために使用  
  
 削除された PDB ファイルは含まれません。  
  
-   型情報  
  
-   行番号情報  
  
-   関数、ローカル変数、および静的なデータなどオブジェクトごとのファイルの CodeView シンボル  
  
 /PDBSTRIPPED を使用すると、完全な PDB ファイルが生成されます。  
  
 PDB ファイルを作成しない場合は、/PDBSTRIPPED が無視されます。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**デバッグ**プロパティ ページ。  
  
4.  変更、**プライベート シンボルの除去**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)