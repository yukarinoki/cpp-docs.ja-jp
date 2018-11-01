---
title: リッチ エディット コントロールでのクリップボード操作
ms.date: 11/04/2016
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
ms.openlocfilehash: 345c0b3e79bc531101481dc7be9624539a06d832
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566188"
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>リッチ エディット コントロールでのクリップボード操作

アプリケーションを使用して、クリップボードの内容をリッチ エディット コントロールに貼り付けることができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 最適使用可能なクリップボード形式または特定のクリップボード形式のいずれかを使用します。 また、リッチ エディット コントロールがクリップボードの形式を貼り付けできるかどうかを確認することができます。

コピーしたり、現在の選択の内容の切り取りを使用して、[コピー](../mfc/reference/cricheditctrl-class.md#copy)または[切り取り](../mfc/reference/cricheditctrl-class.md#cut)メンバー関数。 同様に、貼り付けることができます、クリップボードの内容にリッチ エディット コントロールを使用して、[貼り付けます](../mfc/reference/cricheditctrl-class.md#paste)メンバー関数。 おそらく最もわかりやすい形式であることを認識する最初の使用可能な形式のコントロールに貼り付けます。

特定のクリップボード形式を貼り付け、使用することができます、 [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial)メンバー関数。 この関数は、ユーザーがクリップボード形式を選択できる貼り付けコマンドを使用してアプリケーションに適しています。 使用することができます、 [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste)メンバー関数は、特定の形式がコントロールによって認識されるかどうかを判断します。

使用することも`CanPaste`リッチ エディット コントロールで使用できる任意のクリップボード形式が認識されるかどうかを判断します。 この関数では、`OnInitMenuPopup`ハンドラー。 アプリケーションで有効にする場合があります、灰色のコントロールが任意の使用可能な形式に貼り付けることができるかどうかによって [貼り付け] コマンド。

リッチ エディット コントロールの登録 2 クリップボード形式: リッチ テキスト形式と RichEdit テキストおよびオブジェクトと呼ばれる形式。 アプリケーションを使用してこれらの形式を登録することができます、[独自のデータ](/windows/desktop/api/winuser/nf-winuser-registerclipboardformata)関数は、指定する、 **CF_RTF**と**CF_RETEXTOBJ**値。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

