---
title: フォース (Force ファイル出力) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
dev_langs:
- C++
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1daa27ce48590d4a122eafde9f63f7142271610
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373701"
---
# <a name="force-force-file-output"></a>/FORCE (ターゲットを強制的に出力)
```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## <a name="remarks"></a>コメント  
 /FORCE オプション、リンカーは有効な .exe ファイルを作成するか DLL がシンボルが参照される場合でも定義されているか複数回定義されました。  
  
 /FORCE オプションは、省略可能な引数を取ります。  
  
-   /Force:multiple をリンク、シンボルの 1 つ以上の定義を検索するかどうかは、出力ファイルを作成します。  
  
-   /FORCE を使用して: 未解決のリンクに未定義のシンボルを検索するかどうかは、出力ファイルを作成します。 /強制: 未解決エントリ ポイント シンボルが解決しない場合は無視されます。  
  
 /FORCE に引数なしでは、両方の複数のことを意味し、未解決のします。  
  
 このオプションで作成されたファイルは、正常に動作しない可能性があります。 /FORCE オプションが指定されている場合、リンカーはインクリメンタル リンクできません。  
  
 場合は、モジュールをコンパイル **/clr**、 **/force**イメージは作成されません。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  オプションを入力、**追加オプション**ボックス。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)