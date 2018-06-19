---
title: 予定表コントロールの月の通知メッセージの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26b4d73284b0cff362ba16248e0906b76c7f52a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346914"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>月間予定表コントロールでの通知メッセージの処理
月間予定表コントロール (日付を選択するや別の月を表示する)、コントロールを操作するユーザーと (`CMonthCalCtrl`)、その親ウィンドウに通知メッセージを送信通常ビューまたはダイアログのオブジェクト。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーを表示する新しい 1 か月を選択すると、強調する日付のセットを指定できます。  
  
 [プロパティ] ウィンドウを使用して、実装するメッセージの親クラスに通知ハンドラーを追加します。  
  
 次の一覧には、月間予定表コントロールから送信された通知がについて説明します。  
  
-   **MCN_GETDAYSTATE**太字で表示される必要があります日について情報を要求します。 この通知を処理する方法については、次を参照してください。[月間予定表コントロールの日付状態の設定](../mfc/setting-the-day-state-of-a-month-calendar-control.md)です。  
  
-   **MCN_SELCHANGE**を選択した日付または日付の範囲が変更された親に通知します。  
  
-   **MCN_SELECT**を明示的に日付選択された親に通知します。  
  
## <a name="see-also"></a>関連項目  
 [CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

