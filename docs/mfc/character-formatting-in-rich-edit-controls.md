---
description: 詳細については、「リッチエディットコントロールでの文字の書式設定」を参照してください。
title: リッチ エディット コントロールでの文字書式の設定
ms.date: 11/04/2016
helpviewer_keywords:
- formatting [MFC], characters
- rich edit controls [MFC], character formatting in
- CRichEditCtrl class [MFC], character formatting in
ms.assetid: c80f4305-75ad-45f9-8d17-d83d0fe79be5
ms.openlocfilehash: 47d44a7d586d52ba6a83314711af1350d1c2def6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339697"
---
# <a name="character-formatting-in-rich-edit-controls"></a>リッチ エディット コントロールでの文字書式の設定

リッチエディットコントロール ([CRichEditCtrl](reference/cricheditctrl-class.md)) のメンバー関数を使用すると、文字の書式を設定したり、書式設定情報を取得したりできます。 文字の場合は、字体、サイズ、色、および太字、斜体、保護などの効果を指定できます。

文字の書式設定を適用するには、 [SetSelectionCharFormat](reference/cricheditctrl-class.md#setselectioncharformat) および [SetWordCharFormat](reference/cricheditctrl-class.md#setwordcharformat) メンバー関数を使用します。 選択したテキストの現在の文字書式を確認するには、 [GetSelectionCharFormat](reference/cricheditctrl-class.md#getselectioncharformat) メンバー関数を使用します。 [CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata)構造体は、文字属性を指定するためにこれらのメンバー関数と共に使用されます。 **CHARFORMAT** の重要なメンバーの1つは **dwMask** です。 とでは `SetSelectionCharFormat` `SetWordCharFormat` 、 **dwMask** は、この関数呼び出しによって設定される文字属性を指定します。 `GetSelectionCharFormat` 選択範囲の最初の文字の属性を報告します。 **dwMask** は、選択範囲全体で一貫性のある属性を指定します。

また、"既定の文字書式" を取得して設定することもできます。これは、それ以降に挿入された文字に適用される書式です。 たとえば、アプリケーションで既定の文字書式を太字に設定し、ユーザーが文字を入力した場合、その文字は太字になります。 既定の文字書式を取得して設定するには、 [GetDefaultCharFormat](reference/cricheditctrl-class.md#getdefaultcharformat) および [SetDefaultCharFormat](reference/cricheditctrl-class.md#setdefaultcharformat) メンバー関数を使用します。

"Protected" 文字属性は、テキストの外観を変更しません。 ユーザーが保護されたテキストを変更しようとすると、リッチエディットコントロールは親ウィンドウに **EN_PROTECTED** 通知メッセージを送信し、親ウィンドウが変更を許可または禁止できるようにします。 この通知メッセージを受信するには、 [Seteventmask](reference/cricheditctrl-class.md#seteventmask) メンバー関数を使用して有効にする必要があります。 イベントマスクの詳細については、このトピックで後述 [する「リッチエディットコントロールからの通知](notifications-from-a-rich-edit-control.md)」を参照してください。

前景色は文字属性ですが、背景色はリッチエディットコントロールのプロパティです。 背景色を設定するには、 [Setbackgroundcolor](reference/cricheditctrl-class.md#setbackgroundcolor) メンバー関数を使用します。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](using-cricheditctrl.md)<br/>
[コントロール](controls-mfc.md)
