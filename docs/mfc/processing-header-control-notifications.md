---
title: ヘッダー コントロール通知の処理
ms.date: 11/04/2016
helpviewer_keywords:
- CHeaderCtrl class [MFC], processing notifications
- controls [MFC], header
- notifications [MFC], processing for CHeaderCtrl
- header controls [MFC], processing notifications
- header control notifications
ms.assetid: e6c6af7c-d458-4d33-85aa-48014ccde5f6
ms.openlocfilehash: 3c5d147741123f97a53b18a854db9204738d0a2f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339619"
---
# <a name="processing-header-control-notifications"></a>ヘッダー コントロール通知の処理

ビューまたはダイアログ クラスで作成するプロパティ ウィンドウを使用して、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify)ハンドラー関数のヘッダー コントロールの switch ステートメントを ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) にする通知メッセージ処理 (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。 ユーザーをクリックするか、項目との間の区分線をドラッグが、ヘッダー項目をダブルクリックしたときに、親ウィンドウに通知が送信されます。

ヘッダー コントロールに関連付けられている通知メッセージに記載されて[ヘッダー コントロールのリファレンス](/windows/desktop/controls/header-control-reference)Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
