---
title: アニメーション コントロールによる通知の送信
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 2a736e4315091b1b26daceb4fe0ce9672ab33ff6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238310"
---
# <a name="notifications-sent-by-animation-controls"></a>アニメーション コントロールによる通知の送信

アニメーション コントロール ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) 2 つのさまざまな種類の通知メッセージを送信します。 形式で、通知が送信[WM_COMMAND](/windows/desktop/menurc/wm-command)メッセージ。

[ACN_START](/windows/desktop/Controls/acn-start)アニメーション コントロールのクリップの再生が開始されたときにメッセージを送信します。 [ACN_STOP](/windows/desktop/Controls/acn-stop)アニメーション コントロールが完了またはクリップの再生を停止したときにメッセージが送信されます。

## <a name="see-also"></a>関連項目

[CAnimateCtrl の使い方](../mfc/using-canimatectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
