---
title: 拡張コンボ ボックス コントロールでの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
ms.openlocfilehash: 6a007af9bf92868049edba99943e080d509a40da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430995"
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>拡張コンボ ボックス コントロールでの通知メッセージの処理

ユーザーが拡張コンボ ボックスを操作すると、コントロール (`CComboBoxEx`) から親ウィンドウ (通常はビュー オブジェクトかダイアログ オブジェクト) に通知メッセージが送信されます。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、ドロップダウン リストをアクティブにか、コントロールのエディット ボックスでクリックすると、CBEN_BEGINEDIT 通知が送信されます。

[プロパティ] ウィンドウを使用して、実装するメッセージの親クラスに通知ハンドラーを追加します。

拡張コンボ ボックス コントロールで送信される通知を一覧で説明します。

- CBEN_BEGINEDIT は、ユーザーがドロップダウン リストをアクティブ化またはコントロールのエディット ボックスでクリックしたときに送信されます。

- CBEN_DELETEITEM は、項目が削除されたときに送信されます。

- CBEN_DRAGBEGIN は、ユーザーがコントロールの編集部分に表示される項目のイメージのドラッグを開始するときに送信されます。

- CBEN_ENDEDIT は、ユーザーがエディット ボックス内の操作を完了またはコントロールのドロップダウン リストから項目が選択されているときに送信されます。

- CBEN_GETDISPINFO 送信コールバック項目に関する表示情報を取得します。

- CBEN_INSERTITEM は、コントロールに新しい項目が挿入されたときに送信されます。

## <a name="see-also"></a>関連項目

[CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)<br/>
[コントロール](../mfc/controls-mfc.md)

