---
title: フレーム ウィンドウの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], about frame widows
- frame windows [MFC], tasks
- MFC, frame windows
ms.assetid: 1148a952-6786-4622-b5a8-68a2d7eae584
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ed903238a812188d73093211265c9c8c028b0ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382568"
---
# <a name="what-frame-windows-do"></a>フレーム ウィンドウの機能
だけでなく、ビューをフレームだけで、フレーム ウィンドウは、ビューと、アプリケーションのフレームの調整に関連するさまざまなタスクを担当します。 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)と[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)から継承[CFrameWnd](../mfc/reference/cframewnd-class.md)であるため、`CFrameWnd`機能だけではなく、それらを追加する新しい機能です。 子ウィンドウの例には、ビュー、ボタン、リスト ボックス、およびコントロール バー、ツールバー、ステータス バー、およびダイアログ バーを含むなどのコントロールが含まれます。  
  
 フレーム ウィンドウは、その子ウィンドウのレイアウトの管理を担当します。 MFC フレームワークでは、フレーム ウィンドウは、コントロール バーは、すべて、ビュー、およびその他の子ウィンドウのクライアント領域の内側に配置します。  
  
 また、フレーム ウィンドウ、コマンドをビューに転送し、windows のコントロールから通知メッセージに応答できます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [コントロール バーを (それらにどのように適合フレーム ウィンドウ)](../mfc/control-bars.md)  
  
-   [メニューのコントロール バー、およびアクセラレータの管理 (これらにどのように適合フレーム ウィンドウ)](../mfc/managing-menus-control-bars-and-accelerators.md)  
  
-   [(そのビューおよびその他のコマンド ターゲットをフレーム ウィンドウ) からのコマンド ルーティング](../mfc/command-routing.md)  
  
-   [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)  
  
-   [コントロール バー](../mfc/control-bars.md)  
  
-   [コントロール](../mfc/controls-mfc.md)  
  
## <a name="see-also"></a>関連項目  
 [フレーム ウィンドウ](../mfc/frame-windows.md)

