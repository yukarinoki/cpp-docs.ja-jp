---
title: リッチ エディット コントロールでの段落書式の設定
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: f79d9a97554e2f73b42746c9e9094b07a37513d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581975"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>リッチ エディット コントロールでの段落書式の設定

リッチ エディット コントロールのメンバー関数を使用することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 段落の書式設定と書式設定情報を取得します。 段落の書式設定属性には、配置、タブ、インデント、および番号が含まれます。

段落を使用して書式を適用することができます、 [SetParaFormat](../mfc/reference/cricheditctrl-class.md#setparaformat)メンバー関数。 現在の段落を選択したテキストの書式設定を調べるには、 [GetParaFormat](../mfc/reference/cricheditctrl-class.md#getparaformat)メンバー関数。 [PARAFORMAT](/windows/desktop/api/richedit/ns-richedit-_paraformat)構造がこれらのメンバー関数で使用を段落属性を指定します。 いずれかの重要なメンバー **PARAFORMAT**は*dwMask*します。 `SetParaFormat`、 *DwMask*段落属性は、この関数の呼び出しによって設定されますを指定します。 `GetParaFormat` レポートの選択範囲の最初の段落の属性*dwMask*選択範囲全体で一貫性のある属性を指定します。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

