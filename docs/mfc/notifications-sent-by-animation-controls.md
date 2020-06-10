---
title: アニメーション コントロールによる通知の送信
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: e9e5b94736de44d5cfeef81f5b78a759df3b8aa0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619911"
---
# <a name="notifications-sent-by-animation-controls"></a>アニメーション コントロールによる通知の送信

アニメーションコントロール ([CAnimateCtrl](reference/canimatectrl-class.md)) は、2つの異なる種類の通知メッセージを送信します。 通知は[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージの形式で送信されます。

[ACN_START](/windows/win32/Controls/acn-start)メッセージは、アニメーションコントロールがクリップの再生を開始したときに送信されます。 [ACN_STOP](/windows/win32/Controls/acn-stop)メッセージは、アニメーションコントロールがクリップの再生を完了または停止したときに送信されます。

## <a name="see-also"></a>関連項目

[CAnimateCtrl の使い方](using-canimatectrl.md)<br/>
[制限](controls-mfc.md)
