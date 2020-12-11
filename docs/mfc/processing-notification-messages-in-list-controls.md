---
description: '詳細情報: リストコントロールでの通知メッセージの処理'
title: リスト コントロールでの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: b761f5213a73ce31484a7a252b9b441da2fe154d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154800"
---
# <a name="processing-notification-messages-in-list-controls"></a>リスト コントロールでの通知メッセージの処理

ユーザーが列見出しをクリックしたり、アイコンをドラッグしたり、ラベルを編集したりすると、リストコントロール ([CListCtrl](../mfc/reference/clistctrl-class.md)) によって通知メッセージが親ウィンドウに送信されます。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーが列ヘッダーをクリックしたときに、Microsoft Outlook のように、クリックされた列の内容に基づいて項目を並べ替えることができます。

ビューまたはダイアログクラスのリストコントロールからの WM_NOTIFY メッセージを処理します。 [クラスウィザード](reference/mfc-class-wizard.md)を使用して、処理されている通知メッセージに基づいた switch ステートメントを含む[OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) handler 関数を作成します。

リストコントロールが親ウィンドウに送信できる通知の一覧については、「Windows SDK の [リストビューコントロールリファレンス](/windows/win32/Controls/list-view-control-reference) 」を参照してください。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
