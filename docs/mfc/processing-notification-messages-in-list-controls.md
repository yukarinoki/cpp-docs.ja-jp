---
title: リスト コントロールでの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: e93e91a3219f81bf4027549fc84f1c85c8defb5b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507868"
---
# <a name="processing-notification-messages-in-list-controls"></a>リスト コントロールでの通知メッセージの処理

ユーザーが列見出しをクリックしたり、アイコンをドラッグしたり、ラベルを編集したりすると、リストコントロール ([CListCtrl](../mfc/reference/clistctrl-class.md)) によって通知メッセージが親ウィンドウに送信されます。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーが列ヘッダーをクリックしたときに、Microsoft Outlook のように、クリックされた列の内容に基づいて項目を並べ替えることができます。

ビューまたはダイアログクラスのリストコントロールから、WM_NOTIFY メッセージを処理します。 プロパティウィンドウを使用して、処理されている通知メッセージに基づいて switch ステートメントを含む[OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) handler 関数を作成します。

リストコントロールが親ウィンドウに送信できる通知の一覧については、「Windows SDK の[リストビューコントロールリファレンス](/windows/win32/Controls/list-view-control-reference)」を参照してください。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
