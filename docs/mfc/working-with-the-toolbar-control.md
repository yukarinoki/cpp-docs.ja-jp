---
title: ツール バー コントロールの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- GetToolBarCtrl method [MFC]
- toolbars [MFC], accessing common control
- CToolBarCtrl class [MFC], accessing toolbar
- toolbar controls [MFC], accessing
ms.assetid: b19409d5-3831-42c7-80ae-195c49dc9085
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32d3cc6244bc2f928c8d1d0c6e46d1bc5a57aa3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-the-toolbar-control"></a>ToolBar コントロールの操作
この記事では、アクセスする方法について説明します、 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクトの基になる、 [CToolBar](../mfc/reference/ctoolbar-class.md)ツールバーをより細かく制御できます。 これは、高度なトピックです。  
  
## <a name="procedures"></a>手順  
  
#### <a name="to-access-the-toolbar-common-control-underlying-your-ctoolbar-object"></a>CToolBar オブジェクトの基になるツール バー コモン コントロールにアクセスするには  
  
1.  呼び出す[CToolBar::GetToolBarCtrl](../mfc/reference/ctoolbar-class.md#gettoolbarctrl)です。  
  
 `GetToolBarCtrl` 参照を返します、 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)オブジェクト。 その参照を使用して、ツール バー コントロールのクラス メンバー関数を呼び出すことができます。  
  
> [!CAUTION]
>  呼び出し中に`CToolBarCtrl`**取得**を呼び出す場合に注意を使用して関数が安全な**設定**関数。 これは、高度なトピックです。 通常、基になるツール バー コントロールにアクセスする必要はありません。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [コントロール (Windows のコモン コントロール)](../mfc/controls-mfc.md)  
  
-   [ツールバーに関する基本事項](../mfc/toolbar-fundamentals.md)  
  
-   [ドッキングとフローティング ツールバー](../mfc/docking-and-floating-toolbars.md)  
  
-   [ツールバーのサイズを動的に変更](../mfc/docking-and-floating-toolbars.md)  
  
-   [ツールバーのツール ヒント](../mfc/toolbar-tool-tips.md)  
  
-   [ステータス バーのフライ バイ更新](../mfc/toolbar-tool-tips.md)  
  
-   [ツール ヒントの通知の処理](../mfc/handling-tool-tip-notifications.md)  
  
-   [CToolBar](../mfc/reference/ctoolbar-class.md)と[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)クラス  
  
-   [カスタマイズ通知の処理](../mfc/handling-customization-notifications.md)  
  
-   [複数のツールバー](../mfc/toolbar-fundamentals.md)  
  
-   [古いツールバーの使用方法](../mfc/using-your-old-toolbars.md)  
  
-   [コントロール バー](../mfc/control-bars.md)  
  
 Windows コモン コントロールの使い方に関する概要については、次を参照してください。[コモン コントロール](http://msdn.microsoft.com/library/windows/desktop/bb775493)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC ツール バーの実装](../mfc/mfc-toolbar-implementation.md)

