---
description: '詳細情報: スライダー通知メッセージ'
title: スライダー コントロールの通知メッセージ
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
ms.openlocfilehash: fab8d515e71fd2ca8fd390a41b6d1bf68442c24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216887"
---
# <a name="slider-notification-messages"></a>スライダー コントロールの通知メッセージ

スライダーコントロールは、スライダーコントロールの向きに応じて親 WM_HSCROLL または WM_VSCROLL メッセージを送信することによって、ユーザー操作の親ウィンドウに通知します。 これらのメッセージを処理するには、WM_HSCROLL と WM_VSCROLL メッセージのハンドラーを親ウィンドウに追加します。 [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll)および[onvscroll](../mfc/reference/cwnd-class.md#onvscroll)メンバー関数には、通知コード、スライダーの位置、および[csliderctrl 使い方](../mfc/reference/csliderctrl-class.md)オブジェクトへのポインターが渡されます。 ポインターは `CScrollBar *` オブジェクトを指しているにもかかわらず、型であることに注意して `CSliderCtrl` ください。 スライダーコントロールを操作する必要がある場合は、このポインターの型キャストが必要になることがあります。

スライダーコントロールは、スクロールバーの通知コードを使用するのではなく、異なる通知コードのセットを送信します。 スライダーコントロールは、ユーザーがキーボードを使用してスライダーコントロールを操作するときにのみ、TB_BOTTOM、TB_LINEDOWN、TB_LINEUP、および TB_TOP 通知コードを送信します。 TB_THUMBPOSITION および TB_THUMBTRACK 通知メッセージは、ユーザーがマウスを使用している場合にのみ送信されます。 どちらの場合も、TB_ENDTRACK、TB_PAGEDOWN、および TB_PAGEUP 通知コードが送信されます。

次の表に、通知が送信される原因となる、スライダーコントロールの通知メッセージとイベント (仮想キーコードまたはマウスイベント) を示します。 (標準の仮想キーコードの一覧については、「Winuser. h」を参照してください)。

|通知メッセージ|通知が送信される原因となったイベント|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP (ユーザーは、関連する仮想キーコードを送信したキーを解放しました)|
|TB_LINEDOWN|VK_RIGHT または VK_DOWN|
|TB_LINEUP|VK_LEFT または VK_UP|
|TB_PAGEDOWN|VK_NEXT (ユーザーがスライダーの下または右にあるチャネルをクリックした場合)|
|TB_PAGEUP|VK_PRIOR (ユーザーがスライダーの上または左にあるチャネルをクリックした場合)|
|TB_THUMBPOSITION|TB_THUMBTRACK 通知メッセージに続く WM_LBUTTONUP|
|TB_THUMBTRACK|スライダーの移動 (ユーザーがスライダーをドラッグ)|
|TB_TOP|VK_HOME|

## <a name="see-also"></a>関連項目

[CSliderCtrl の使い方](../mfc/using-csliderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
