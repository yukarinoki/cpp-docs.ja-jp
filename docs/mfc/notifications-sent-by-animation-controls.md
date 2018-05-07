---
title: アニメーション コントロールによる通知の送信 |Microsoft ドキュメント
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
ms.openlocfilehash: c1696389ce3dc40c5d02ec660ebaeb6bf3e6c3ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="notifications-sent-by-animation-controls"></a>アニメーション コントロールによる通知の送信
アニメーション コントロール ([CAnimateCtrl](../mfc/reference/canimatectrl-class.md)) 2 つのさまざまな種類の通知メッセージを送信します。 形式で、通知を送信[WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591)メッセージ。  
  
 [ACN_START](http://msdn.microsoft.com/library/windows/desktop/bb761891)アニメーション コントロールのクリップの再生が開始されたときに、メッセージが送信されます。 [ACN_STOP](http://msdn.microsoft.com/library/windows/desktop/bb761893)アニメーション コントロールが完了またはクリップの再生を停止したときにメッセージが送信されます。  
  
## <a name="see-also"></a>関連項目  
 [CAnimateCtrl の使い方](../mfc/using-canimatectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

