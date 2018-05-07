---
title: リッチ エディット コントロールの現在の選択 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- current selection in CRichEditCtrls
- CRichEditCtrl class [MFC], current selection in
- rich edit controls [MFC], current selection in
- selection, current in CRichEditCtrl
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 782984bc53bc16f8dc89e4e705811fef24b8931e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="current-selection-in-a-rich-edit-control"></a>リッチ エディット コントロールでの現在の選択項目
ユーザーは、リッチ エディット コントロールでテキストを選択することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))、マウスまたはキーボードを使用しています。 現在の選択は、選択した文字の範囲または文字を含まない場合に、カーソルの位置を選択します。 アプリケーションは現在の選択に関する情報を取得、現在の選択範囲を設定、現在の選択内容、および表示または非表示、選択範囲が強調表示を決定します。  
  
 リッチ エディット コントロールの現在の選択を確認するには[GetSel](../mfc/reference/cricheditctrl-class.md#getsel)メンバー関数。 現在の選択範囲を設定するには、使用、 [SetSel](../mfc/reference/cricheditctrl-class.md#setsel)メンバー関数。 [上](http://msdn.microsoft.com/library/windows/desktop/bb787885)構造がこれらの関数で使用を文字の範囲を指定します。 現在の選択の内容に関する情報を取得する際、 [GetSelectionType](../mfc/reference/cricheditctrl-class.md#getselectiontype)メンバー関数。  
  
 既定では、リッチ エディット コントロール表示/非表示の選択範囲の強調表示を取得して、フォーカスを失ったときにします。 表示または選択範囲の表示を使用していつでも非表示にすることができます、 [HideSelection](../mfc/reference/cricheditctrl-class.md#hideselection)メンバー関数。 たとえば、アプリケーションでは、リッチ エディット コントロールでテキストを検索する検索 ダイアログ ボックスを提供する可能性があります。 アプリケーションはダイアログ ボックスを閉じずに一致するテキストを選択する可能性があります、この場合を使用する必要があります`HideSelection`選択範囲を強調表示にします。  
  
 リッチ エディット コントロールで選択したテキストを取得する、 [GetSelText](../mfc/reference/cricheditctrl-class.md#getseltext)メンバー関数。 テキストは、指定した文字配列にコピーされます。 配列は、選択したテキストと終端の null 文字を保持するのに十分な大きさを確認する必要があります。  
  
 使用して、リッチ エディット コントロールで文字列を検索することができます、 [FindText](../mfc/reference/cricheditctrl-class.md#findtext)メンバー関数、[指定](http://msdn.microsoft.com/library/windows/desktop/bb787909)この関数で使用される構造体を検索し、検索する文字列をテキスト範囲を指定します。 検索は大文字小文字を区別するかどうかとしてこのようなオプションを指定することもできます。  
  
## <a name="see-also"></a>関連項目  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

