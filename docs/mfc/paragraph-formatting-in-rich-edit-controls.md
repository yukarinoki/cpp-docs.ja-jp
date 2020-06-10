---
title: リッチ エディット コントロールでの段落書式の設定
ms.date: 11/04/2016
helpviewer_keywords:
- rich edit controls [MFC], paragraph formatting in
- paragraph formatting in CRichEditCtrl [MFC]
- CRichEditCtrl class [MFC], paragraph formatting in
- formatting [MFC], paragraphs
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
ms.openlocfilehash: e23976e64b3c9a4a76e5b05c90d0ad033b62657a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615334"
---
# <a name="paragraph-formatting-in-rich-edit-controls"></a>リッチ エディット コントロールでの段落書式の設定

リッチエディットコントロール ([CRichEditCtrl](reference/cricheditctrl-class.md)) のメンバー関数を使用すると、段落の書式設定や書式設定情報の取得を行うことができます。 段落の書式設定属性には、配置、タブ、インデント、および段落番号が含まれます。

[SetParaFormat](reference/cricheditctrl-class.md#setparaformat)メンバー関数を使用すると、段落書式を適用できます。 選択したテキストの現在の段落書式を確認するには、 [GetParaFormat](reference/cricheditctrl-class.md#getparaformat)メンバー関数を使用します。 これらのメンバー関数と共に[PARAFORMAT](/windows/win32/api/richedit/ns-richedit-paraformat)構造体を使用して、段落の属性を指定します。 **PARAFORMAT**の重要なメンバーの1つは*dwMask*です。 では `SetParaFormat` 、 *dwMask*は、この関数呼び出しによって設定される段落属性を指定します。 `GetParaFormat`選択範囲内の最初の段落の属性を報告します。*dwMask*は、選択範囲全体で一貫性のある属性を指定します。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](using-cricheditctrl.md)<br/>
[制限](controls-mfc.md)
