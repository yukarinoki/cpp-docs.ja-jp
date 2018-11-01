---
title: リッチ エディット コントロールでの印刷
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
ms.openlocfilehash: bf402f5495ad85eb0c5067d60fcedfe29e6350bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641208"
---
# <a name="printing-in-rich-edit-controls"></a>リッチ エディット コントロールでの印刷

リッチ エディット コントロールがわかります ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) プリンターなどの指定されたデバイスには、その出力をレンダリングします。 リッチ エディット コントロールを対象の出力デバイスがそのテキストを書式設定を指定することもできます。

使用することができます、特定のデバイスのリッチ エディット コントロールの内容の一部を書式設定、 [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange)メンバー関数。 [FORMATRANGE](/windows/desktop/api/richedit/ns-richedit-_formatrange)この関数で使用される構造体は、対象デバイスのデバイス コンテキスト (DC) の書式設定テキストの範囲を指定します。

出力デバイス用のテキストを書式設定後に送信できます、出力デバイスを使用して、[続いて](../mfc/reference/cricheditctrl-class.md#displayband)メンバー関数。 繰り返しを使用して`FormatRange`と`DisplayBand`、縞模様、リッチ エディット コントロールの内容を出力するアプリケーションで実装できます。 バンド処理とは出力の小さな部分に印刷用です。)

使用することができます、 [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice)リッチ エディット コントロールを対象のターゲット デバイスを指定するメンバー関数は、そのテキストを書式設定します。 この関数は、WYSIWYG 場合に便利です (表示) の書式設定、アプリケーションが画面のではなく、既定のプリンターのフォント メトリックを使用してテキストを配置します。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

