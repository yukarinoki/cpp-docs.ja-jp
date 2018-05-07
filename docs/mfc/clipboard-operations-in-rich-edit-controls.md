---
title: リッチでのクリップボード操作エディット コントロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- pasting Clipboard data
- CRichEditCtrl class [MFC], paste operation
- cut operation in CRichEditCtrl class [MFC]
- CRichEditCtrl class [MFC], Clipboard operations
- copy operations in rich edit controls
- Clipboard, operations in CRichEditCtrl
- rich edit controls [MFC], Clipboard operations
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e831a76a491d1025ae45117d40362a85523742da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="clipboard-operations-in-rich-edit-controls"></a>リッチ エディット コントロールでのクリップボード操作
アプリケーションは、リッチ エディット コントロールに、クリップボードの内容を貼り付けることができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) 最適使用可能なクリップボード形式または特定のクリップボード形式を使用します。 リッチ エディット コントロールがクリップボードの形式を貼り付けることのできるかどうかを確認することもできます。  
  
 コピーしたりを使用して現在の選択範囲の内容を切り取り、[コピー](../mfc/reference/cricheditctrl-class.md#copy)または[切り取り](../mfc/reference/cricheditctrl-class.md#cut)メンバー関数。 同様に、貼り付けることのできる、クリップボードの内容、リッチ エディット コントロールを使用して、[貼り付け](../mfc/reference/cricheditctrl-class.md#paste)メンバー関数。 コントロールは、おそらく最もわかりやすい形式であることを認識する最初の使用可能な書式を貼り付けます。  
  
 貼り付けるには、特定のクリップボード形式を使用することができます、 [PasteSpecial](../mfc/reference/cricheditctrl-class.md#pastespecial)メンバー関数。 この関数は、ユーザーがクリップボード形式を選択できる貼り付けコマンドを使用してアプリケーションに役立ちます。 使用することができます、 [CanPaste](../mfc/reference/cricheditctrl-class.md#canpaste)メンバー関数を指定した形式がコントロールによって認識されるかどうかを判断します。  
  
 使用することも`CanPaste`をリッチ エディット コントロールで使用できる任意のクリップボード形式を認識するかどうかを判断します。 この関数では、`OnInitMenuPopup`ハンドラー。 アプリケーションで有効にする可能性があります、灰色のコントロールが任意の使用可能な形式に貼り付けることができるかどうかによって [貼り付け] コマンド。  
  
 リッチ エディット コントロール レジスタ 2 つクリップボードの形式: リッチ テキスト形式と RichEdit テキストおよびオブジェクトと呼ばれる形式です。 アプリケーションを使用してこれらの形式を登録することができます、[独自のデータ](http://msdn.microsoft.com/library/windows/desktop/ms649049)関数を指定する、 **CF_RTF**と**CF_RETEXTOBJ**値。  
  
## <a name="see-also"></a>関連項目  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

