---
title: -SWAPRUN (ロード リンカー出力をスワップ ファイル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
dev_langs:
- C++
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 522cd693da1b4e1a72d11119f622d862413b409b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377418"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (リンカー出力をスワップ ファイルに読み込む)
```  
/SWAPRUN:{NET|CD}  
```  
  
## <a name="remarks"></a>コメント  
 /SWAPRUN オプション、リンカーは、オペレーティング システムを最初のコピーをスワップ ファイルに出力し、そこからイメージを実行します。 これは、Windows NT 4.0 以降) の機能です。  
  
 NET を指定すると、オペレーティング システムのバイナリ イメージをネットワークからスワップ ファイルをコピーはまず作成し、そこから読み込んでいます。 このオプションは、ネットワーク経由でアプリケーションを実行するために役立ちます。 CD を指定すると、オペレーティング システムがリムーバブル ディスク上のイメージをページファイルにコピーし、読み込むことです。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**システム**プロパティ ページ。  
  
4.  次のいずれかのプロパティを変更します。  
  
    -   **CD からスワップ実行**  
  
    -   **ネットワークからスワップ実行**  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> プロパティを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)