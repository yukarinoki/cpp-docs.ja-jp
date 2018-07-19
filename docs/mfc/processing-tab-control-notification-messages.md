---
title: タブ コントロール通知メッセージの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 462d9177b1f6300eb356d052cbdfff3b85db86a1
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928063"
---
# <a name="processing-tab-control-notification-messages"></a>タブ コントロールの通知メッセージの処理
ユーザーは、タブまたはボタン、タブ コントロールをクリックして、([CTabCtrl](../mfc/reference/ctabctrl-class.md))、親ウィンドウに通知メッセージを送信します。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、タブをクリックすると、可能性がある表示する前に、ページ上のコントロール データを事前設定します。  
  
 ビューまたはダイアログ クラスでのタブ コントロールから WM_NOTIFY メッセージを処理します。 [プロパティ] ウィンドウを使って作成、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) switch ステートメントを持つハンドラー関数が通知メッセージを処理しているに基づいて。 タブ コントロールは自らの親ウィンドウに送信できます通知の一覧は、次を参照してください。、**通知**のセクション[タブ コントロールの参照](http://msdn.microsoft.com/library/windows/desktop/bb760548)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

