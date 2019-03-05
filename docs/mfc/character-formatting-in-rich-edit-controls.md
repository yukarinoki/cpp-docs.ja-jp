---
title: リッチ エディット コントロールでの文字書式の設定
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: a7467f9cd6a14dc6dfc2c03b6eb35f71802454fb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268643"
---
# <a name="character-formatting-in-rich-edit-controls"></a>リッチ エディット コントロールでの文字書式の設定

リッチ エディット コントロールのメンバー関数を使用することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 文字の書式設定して、書式設定情報を取得します。 文字は、フォント、サイズ、色、および太字、斜体などの効果を指定し、保護されています。

使用して文字の書式設定を適用することができます、 [SetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#setselectioncharformat)と[SetWordCharFormat](../mfc/reference/cricheditctrl-class.md#setwordcharformat)メンバー関数。 選択したテキストの書式設定の現在の文字を調べるには、 [GetSelectionCharFormat](../mfc/reference/cricheditctrl-class.md#getselectioncharformat)メンバー関数。 [CHARFORMAT](/windows/desktop/api/richedit/ns-richedit-_charformat)構造がこれらのメンバー関数で使用を文字の属性を指定します。 いずれかの重要なメンバー **CHARFORMAT**は**dwMask**します。 `SetSelectionCharFormat`と`SetWordCharFormat`、 **dwMask**文字属性は、この関数の呼び出しによって設定されますを指定します。 `GetSelectionCharFormat` レポートの選択範囲の最初の文字の属性**dwMask**選択範囲全体で一貫性のある属性を指定します。

取得でき、"既定の文字の書式設定、"これは、その後に挿入された文字に適用される書式設定できます。 たとえば、アプリケーションは、既定の文字を太字に書式を設定し、ユーザーが文字を入力し場合、その文字が太字にします。 既定の文字書式設定を使用して、 [GetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#getdefaultcharformat)と[SetDefaultCharFormat](../mfc/reference/cricheditctrl-class.md#setdefaultcharformat)メンバー関数。

"Protected"文字の属性には、テキストの外観は変わりません。 リッチ エディット コントロールがその親ウィンドウを送信する場合は、ユーザーが保護されたテキストを変更しようとすると、 **EN_PROTECTED**通知メッセージを許可するか、変更を禁止する親ウィンドウ。 この通知メッセージを受信する必要があります有効にするを使用して、 [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask)メンバー関数。 詳細については、イベント マスクは、次を参照してください。[リッチ エディット コントロールからの通知](../mfc/notifications-from-a-rich-edit-control.md)、このトピックで後述します。

前景の色は文字の属性が、背景色はリッチ エディット コントロールのプロパティです。 背景色を設定するには、使用、 [SetBackgroundColor](../mfc/reference/cricheditctrl-class.md#setbackgroundcolor)メンバー関数。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
