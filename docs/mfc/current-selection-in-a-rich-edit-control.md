---
title: リッチ エディット コントロールでの現在の選択項目
ms.date: 11/04/2016
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
ms.openlocfilehash: 4516c4506419169ac3ab284e6c59cae71595be59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62241806"
---
# <a name="current-selection-in-a-rich-edit-control"></a>リッチ エディット コントロールでの現在の選択項目

ユーザーは、リッチ エディット コントロールでテキストを選択することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))、マウスまたはキーボードを使用しています。 現在の選択は、選択した文字の範囲または文字がない場合、カーソルの位置を選択します。 アプリケーションでは、現在の選択に関する情報を取得、セットの現在の選択、現在の選択内容、および表示または非表示選択が強調表示を決定できます。

リッチ エディット コントロールの現在の選択を調べるには、 [GetSel](../mfc/reference/cricheditctrl-class.md#getsel)メンバー関数。 現在の選択範囲を設定するには、使用、 [SetSel](../mfc/reference/cricheditctrl-class.md#setsel)メンバー関数。 [上](/windows/desktop/api/richedit/ns-richedit-_charrange)構造がこれらの関数で使用を文字の範囲を指定します。 現在の選択の内容に関する情報を取得するには、使用することができます、 [GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype)メンバー関数。

既定では、リッチ エディット コントロールを示しを取得し、フォーカスを失ったときに、選択範囲の表示を非表示になります。 表示または選択範囲の表示を使用して、いつでも非表示にすることができます、 [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection)メンバー関数。 たとえば、アプリケーションは、リッチ エディット コントロールでテキストを検索する検索 ダイアログ ボックスを提供する可能性があります。 アプリケーションは、一致するテキストを選択します ダイアログ ボックスを閉じずに可能性があります、その場合を使用する必要があります`HideSelection`選択範囲を強調表示します。

リッチ エディット コントロールで選択したテキストを取得する、 [GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext)メンバー関数。 テキストは、指定した文字配列にコピーされます。 配列は、選択したテキストと終端の null 文字を保持するのに十分な大きさを確認する必要があります。

使用して、リッチ エディット コントロールで文字列を検索することができます、 [FindText](../mfc/reference/cricheditctrl-class.md#findtext)メンバー関数は、[指定](/windows/desktop/api/richedit/ns-richedit-_findtextexa)この関数で使用される構造を検索し、検索する文字列をテキスト範囲を指定します。 検索は大文字小文字を区別するかどうかなどのオプションを指定することもできます。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
