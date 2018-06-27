---
title: スライダー コントロールの通知メッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c383458905d16dda935254e56a5aa9f56a153e83
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956162"
---
# <a name="slider-notification-messages"></a>スライダー コントロールの通知メッセージ
スライダー コントロールでは、親のスライダー コントロールの向きに応じて、兄弟または WM_VSCROLL のメッセージを送信することによってユーザーの操作の親ウィンドウに通知します。 これらのメッセージを処理するには、親ウィンドウに兄弟と WM_VSCROLL メッセージのハンドラーを追加します。 [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll)と[OnVScroll](../mfc/reference/cwnd-class.md#onvscroll)メンバー関数は、スライダーとへのポインターの位置で、通知コードに渡される、 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)オブジェクト。 ポインター型の`CScrollBar *`を指しているにもかかわらず、`CSliderCtrl`オブジェクト。 スライダー コントロールを操作する必要がある場合は、このポインターをキャストする必要があります。  
  
 スクロール バーの通知コードを使用するではなくは、スライダー コントロールは、通知コードの異なるセットを送信します。 スライダー コントロールは、ユーザーは、キーボードを使用して、スライダー コントロールを操作するときにのみ、TB_BOTTOM、TB_LINEDOWN、TB_LINEUP、および TB_TOP 通知コードを送信します。 TB_THUMBPOSITION と TB_THUMBTRACK 通知メッセージは、ユーザーがマウスを使用する場合にのみ送信されます。 どちらの場合も、TB_ENDTRACK、TB_PAGEDOWN、および TB_PAGEUP 通知コードが送信されます。  
  
 次の表には、スライダー コントロールの通知メッセージと送信される通知を発生させるイベント (仮想キー コードまたはマウス イベント) が一覧表示します。 (標準の仮想キー コードの一覧は、Winuser.h を参照してください)。  
  
|通知メッセージ|イベント通知が送信されるが|  
|--------------------------|-------------------------------------------|  
|TB_BOTTOM|VK_END|  
|TB_ENDTRACK|WM_KEYUP (ユーザーは、関連する仮想キー コードを送信するキーをリリース)|  
|TB_LINEDOWN|VK_RIGHT または VK_DOWN|  
|TB_LINEUP|VK_LEFT または VK_UP|  
|TB_PAGEDOWN|VK_NEXT (ユーザーがクリックしたつまみの右側または下のチャネル)|  
|TB_PAGEUP|VK_PRIOR (ユーザーがクリックしたチャネルの上またはつまみの左側に)|  
|TB_THUMBPOSITION|TB_THUMBTRACK 通知メッセージに続くしました。|  
|TB_THUMBTRACK|スライダーの移動 (ユーザーは、スライダーをドラッグして)|  
|TB_TOP|VK_HOME|  
  
## <a name="see-also"></a>関連項目  
 [CSliderCtrl の使い方](../mfc/using-csliderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

