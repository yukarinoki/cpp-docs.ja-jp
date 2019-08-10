---
title: リッチ エディット コントロールでの印刷
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
ms.openlocfilehash: 6ae7212eaa8eed1088a507973c80311f169c7751
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916268"
---
# <a name="printing-in-rich-edit-controls"></a>リッチ エディット コントロールでの印刷

リッチエディットコントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) に対して、プリンターなど、指定されたデバイスの出力を表示するように指示できます。 リッチエディットコントロールがテキストを書式設定する出力デバイスを指定することもできます。

特定のデバイスのリッチエディットコントロールの内容の一部を書式設定するには、 [Formatrange](../mfc/reference/cricheditctrl-class.md#formatrange)メンバー関数を使用します。 この関数で使用される[formatrange](/windows/desktop/api/richedit/ns-richedit-formatrange)構造体は、フォーマットするテキストの範囲と、ターゲットデバイスのデバイスコンテキスト (DC) を指定します。

出力デバイスのテキストの書式を設定した後、 [Displayband](../mfc/reference/cricheditctrl-class.md#displayband)メンバー関数を使用して、出力をデバイスに送信できます。 とを繰り返し`FormatRange`使用`DisplayBand`すると、リッチエディットコントロールの内容を出力するアプリケーションでは、縞模様を実装できます。 (縞模様は出力を小さな部分に分割して印刷するために使用します)。

[Settargetdevice](../mfc/reference/cricheditctrl-class.md#settargetdevice)メンバー関数を使用すると、リッチエディットコントロールがテキストを書式設定する対象デバイスを指定できます。 この関数は、WYSIWYG (表示される内容) の書式設定に役立ちます。これは、アプリケーションが画面のではなく、既定のプリンターのフォントメトリックを使用してテキストを配置します。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
