---
title: リッチ エディット コントロールからの通知メッセージ
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
ms.openlocfilehash: 87168b6e58264b4257b7adfb32207ec1dd40729e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529208"
---
# <a name="notifications-from-a-rich-edit-control"></a>リッチ エディット コントロールからの通知メッセージ

レポートの編集コントロールの豊富な影響を与えるイベントの通知メッセージ ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 親ウィンドウによって処理されることができますか、メッセージ リフレクションを使用して、豊富な編集コントロール自体。 リッチ エディット コントロールでは、エディット コントロールに加えて、さらにいくつか使用される通知メッセージのすべてをサポートします。 Mask を設定して、"イベントです"通知メッセージ リッチ エディット コントロールの送信、親ウィンドウを指定できます。

リッチ エディット コントロールのイベントのマスクを設定するには、使用、 [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask)メンバー関数。 使用して、リッチ エディット コントロールのイベントの現在のマスクを取得することができます、 [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask)メンバー関数。

次の段落は、いくつかの特定の通知とその用途を一覧表示します。

- EN_MSGFILTER EN_MSGFILTER 通知の処理により、クラスか、リッチ エディット コントロールまたはその親ウィンドウは、すべてのキーボードとマウスをコントロールに入力をフィルター処理できます。 ハンドラーがキーボードまたはマウス メッセージが処理するを防ぐことができます、または指定した変更することによって、メッセージを変更できます[MSGFILTER](/windows/desktop/api/richedit/ns-richedit-_msgfilter)構造体。

- EN_PROTECTED では、ユーザーが保護されたテキストを変更しようとしたときを検出するために EN_PROTECTED 通知メッセージを処理します。 テキストの範囲をマークするは、保護対象として、保護されている文字の効果を設定できます。 詳細については、次を参照してください。[リッチ エディット コントロールで書式設定文字](../mfc/character-formatting-in-rich-edit-controls.md)します。

- EN_DROPFILES 通知メッセージを処理することによって、リッチ エディット コントロール内のファイルを削除するユーザーを有効にする EN_DROPFILES することができます。 指定した[ENDROPFILES](/windows/desktop/api/richedit/ns-richedit-_endropfiles)構造が削除されているファイルに関する情報が含まれています。

- EN_SELCHANGE 通知メッセージを処理することによって、現在の選択が変更されたとき、または EN_SELCHANGE アプリケーションを検出できます。 通知メッセージを指定します、 [SELCHANGE](/windows/desktop/api/richedit/ns-richedit-_selchange)新しい選択に関する情報を含む構造体。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

