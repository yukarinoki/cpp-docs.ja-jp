---
title: ツールバーのツール ヒント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90f325df3825b3546616ce145d4477322a1b4eed
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956295"
---
# <a name="toolbar-tool-tips"></a>ツール バーのツール ヒント
ツール ヒントは、一定の時間のボタンにマウスを配置すると、ツール バー ボタンの目的の簡単な説明を表示する小さなポップアップ ウィンドウです。 ツールバーのあるアプリケーション ウィザードを使用してアプリケーションを作成するときにツール ヒントのサポートが提供します。 この記事では、アプリケーションのウィザードとツール ヒントのサポートをアプリに追加する方法によって作成された、両方のツール ヒント サポートについて説明します。  
  
 この記事では次の内容について説明します。  
  
-   [ツール ヒントをアクティブ化](#_core_activating_tool_tips)  
  
-   [ステータス バーのフライ バイ更新](#_core_fly_by_status_bar_updates)  
  
##  <a name="_core_activating_tool_tips"></a> ツール ヒントをアクティブ化  
 アプリケーションでのツール ヒントをアクティブ化するには、2 つの処理を行う必要があります。  
  
-   他のスタイルに CBRS_TOOLTIPS スタイルを追加 (WS_CHILD、WS_VISIBLE、およびその他のなど**cbrs _** スタイル) として渡される、 *dwStyle*パラメーターを[用意されて](../mfc/reference/ctoolbar-class.md#create)関数または[SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle)です。  
  
-   以下の手順に従って、ツール バー コマンドのコマンド ライン プロンプトを含む文字列リソースを改行文字 ('\n') で区切られた、ツールバーのヒント テキストを追加します。 文字列リソースは、ツールバーのボタンの ID を共有します。  
  
#### <a name="to-add-the-tool-tip-text"></a>ツール ヒントのテキストを追加するには  
  
1.  ツール バー エディターのツールバーを編集するときに開く、**ツール バー ボタン プロパティ**指定したボタンのウィンドウ。  
  
2.  **プロンプト**ボックスで、そのボタンのツールヒントに表示するテキストを指定します。  
  
> [!NOTE]
>  ツール バー エディターのボタンがこれまでの手順をする必要がありましたを置き換えると、テキストの設定を開き、文字列リソースを編集します。  
  
 ツール ヒントを有効になっているを持つコントロール バーに、上の子コントロールがある場合は、コントロール バーで、次の条件を満たしている限りにコントロール バー上のすべての子コントロールのツール ヒントが表示されます。  
  
-   コントロールの ID は 1 では不要です。  
  
-   リソース ファイル内の子コントロールと同じ ID を持つストリング テーブルのエントリは、ツール ヒントの文字列を持ちます。  
  
##  <a name="_core_fly_by_status_bar_updates"></a> ステータス バーのフライ バイ更新  
 ツール ヒントに関連する機能は、「フライ バイ」ステータス バーの更新です。 既定では、ステータス バーにメッセージは、ボタンがアクティブになったときにのみ特定のツール バー ボタンについて説明します。 渡されるスタイルの一覧で、CBRS_FLYBY を含めることによって`CToolBar::Create`、マウス カーソルが実際には、ボタンをアクティブ化せず、ツールバー上に置いたときに更新されたこれらのメッセージを持つことができます。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [MFC ツールバーの実装 (ツールバーに概要情報)](../mfc/mfc-toolbar-implementation.md)  
  
-   [ドッキングとフローティング ツールバー](../mfc/docking-and-floating-toolbars.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md)と[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)クラス  
  
-   [ツール バー コントロールの操作](../mfc/working-with-the-toolbar-control.md)  
  
-   [古いツールバーの使用方法](../mfc/using-your-old-toolbars.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)

