---
title: 現在のビューの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], and OnActivateView method [MFC]
- views [MFC], deactivating
- views [MFC], activating
- frame windows [MFC], current view
- OnActivateView method [MFC]
- views [MFC], current
- deactivating views [MFC]
- current view in frame window [MFC]
ms.assetid: 0a1cc22d-d646-4536-9ad2-3cb6d7092e4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 323903d2e1285a4ee697bbd9d0c3a29c2e1248d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="managing-the-current-view"></a>現在のビューの管理
フレーム ウィンドウの既定の実装の一部として、フレーム ウィンドウを現在アクティブなビューの追跡を保持します。 フレーム ウィンドウには、分割ウィンドウなど、複数のビューが含まれている場合、現在のビューは、使用中で最新のビューがします。 アクティブなビューは、Windows または現在の入力フォーカスのアクティブ ウィンドウの依存しません。  
  
 変更すると、アクティブなビュー、フレームワークは、呼び出すことによって、現在のビューをユーザーに通知の[OnActivateView](../mfc/reference/cview-class.md#onactivateview)メンバー関数。 表示されているかどうかを指定するアクティブ化または確認するには非アクティブ化`OnActivateView`の`bActivate`パラメーター。 既定では、`OnActivateView`アクティブ化を現在のビューにフォーカスを設定します。 オーバーライドできます`OnActivateView`ビューが非アクティブ化または再アクティブ化したときに、特別な処理を実行します。 たとえば、アクティブなビューを非アクティブな他のビューから区別するために特別な視覚的な手掛かりを提供することができます。  
  
 フレーム ウィンドウは」の説明に従って、現在の (アクティブ) ビューをコマンドに転送[コマンド ルーティング](../mfc/command-routing.md)、標準のコマンド ルーティングの一部として。  
  
## <a name="see-also"></a>関連項目  
 [フレーム ウィンドウの使用](../mfc/using-frame-windows.md)

