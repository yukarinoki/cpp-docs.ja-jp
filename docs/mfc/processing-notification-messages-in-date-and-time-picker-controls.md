---
title: 通知メッセージの処理日時指定コントロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
dev_langs:
- C++
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 630792eb4bdd89cbe8081894c4ee026437568f3b
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930765"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>日時指定コントロールの通知メッセージの処理
日付と時刻の選択コントロールをコントロールにユーザーが操作すると (`CDateTimeCtrl`)、その親ウィンドウに通知メッセージを送信通常ビューまたはダイアログのオブジェクト。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、埋め込み月間予定表コントロールを表示する日付と時刻のピッカーを起動したときに、DTN_DROPDOWN 通知が送信されます。  
  
 [プロパティ] ウィンドウを使用して、実装するメッセージの親クラスに通知ハンドラーを追加します。  
  
 次の一覧には、さまざまな日付と時刻の選択コントロールから送信された通知がについて説明します。  
  
-   DTN_DROPDOWN では、埋め込み月間予定表のコントロールの親が表示されることを通知します。 この通知は DTS_UPDOWN スタイルが設定されていない場合にのみ送信されます。 この通知の詳細については、次を参照してください。[埋め込み月間予定表コントロールへのアクセス](../mfc/accessing-the-embedded-month-calendar-control.md)です。  
  
-   埋め込み月間予定表のコントロールの親が閉じられようは DTN_CLOSEUP 通知です。 この通知は DTS_UPDOWN スタイルが設定されていない場合にのみ送信されます。  
  
-   DTN_DATETIMECHANGE 通知が変更されたコントロールの親です。  
  
-   DTN_FORMAT コールバック フィールドに表示するために必要なテキストは、親に通知します。 この通知とコールバック フィールドの詳細については、次を参照してください。[日付と日時指定コントロールでのコールバック フィールドの使い方](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)です。  
  
-   DTN_FORMATQUERY は、コールバック フィールドに表示される文字列の最大許容サイズを指定する親を要求します。 この通知を処理すると、正しく表示出力が常に、コントロールの表示のちらつきを軽減するには、制御ができます。 この通知の詳細については、次を参照してください。[日付と日時指定コントロールでのコールバック フィールドの使い方](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)です。  
  
-   ユーザーの日付と時刻の選択の内容の編集が完了したこと、親は制御 DTN_USERSTRING に通知します。 この通知は DTS_APPCANPARSE スタイルが設定されている場合にのみ送信されます。  
  
-   コールバック フィールドに、ユーザーが入力したとき DTN_WMKEYDOWN を親に通知します。 日付と時刻の選択コントロールのコールバック以外のフィールドのサポートされている同じキーボード応答をエミュレートするためには、この通知を処理します。 この通知の詳細については、次を参照してください。 [DTP コントロールでのコールバック フィールドのサポート](http://msdn.microsoft.com/library/windows/desktop/bb761726)Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

