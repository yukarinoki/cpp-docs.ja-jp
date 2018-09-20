---
title: アニメーション コントロールによる通知の送信 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb83fe6195c01c1e9dbcc2c00e43738af9ebc8e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386393"
---
# <a name="notifications-sent-by-animation-controls"></a>アニメーション コントロールによる通知の送信

アニメーション コントロール ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) 2 つのさまざまな種類の通知メッセージを送信します。 形式で、通知が送信[WM_COMMAND](/windows/desktop/menurc/wm-command)メッセージ。

[ACN_START](/windows/desktop/Controls/acn-start)アニメーション コントロールのクリップの再生が開始されたときにメッセージを送信します。 [ACN_STOP](/windows/desktop/Controls/acn-stop)アニメーション コントロールが完了またはクリップの再生を停止したときにメッセージが送信されます。

## <a name="see-also"></a>関連項目

[CAnimateCtrl の使い方](../mfc/using-canimatectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

