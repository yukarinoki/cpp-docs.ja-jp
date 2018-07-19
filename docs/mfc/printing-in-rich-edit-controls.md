---
title: リッチ エディット コントロールでの印刷 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC], CRichEditCtrl
- rich edit controls [MFC], printing
- CRichEditCtrl class [MFC], printing
ms.assetid: dbda0e40-018f-424e-b5d8-7b489aaf27af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23b958e6c770260082af069544480102f6d79926
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347664"
---
# <a name="printing-in-rich-edit-controls"></a>リッチ エディット コントロールでの印刷
リッチ エディット コントロールに指示することができます ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) プリンターなどの指定したデバイスの出力を表示するためにします。 出力デバイスをリッチ エディット コントロールがそのテキストを書式設定を指定することもできます。  
  
 特定のデバイスのリッチ エディット コントロールの内容の一部をフォーマットするには、使用することができます、 [FormatRange](../mfc/reference/cricheditctrl-class.md#formatrange)メンバー関数。 [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911)この関数で使用される構造体は、ターゲット デバイスのデバイス コンテキスト (DC) および書式設定テキストの範囲を指定します。  
  
 出力デバイス用のテキストを書式設定後にことができます、出力を送信するデバイスを使用して、[続いて](../mfc/reference/cricheditctrl-class.md#displayband)メンバー関数。 繰り返しを使用して`FormatRange`と`DisplayBand`、縞模様、リッチ エディット コントロールの内容を出力するアプリケーションで実装できます。 (縞模様は出力の小さな部分に分割印刷の目的で) です。  
  
 使用することができます、 [SetTargetDevice](../mfc/reference/cricheditctrl-class.md#settargetdevice)リッチ エディット コントロールを対象のターゲット デバイスを指定するメンバー関数は、そのテキストを書式設定します。 この関数は、WYSIWYG に役立つ (表示) 書式設定、アプリケーションが、画面の代わりに既定のプリンターのフォント メトリックを使用してテキストを配置します。  
  
## <a name="see-also"></a>関連項目  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

