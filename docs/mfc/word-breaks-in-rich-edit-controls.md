---
title: リッチ エディット コントロールでのワード区切り |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 373a30ed4a327cff99cb3cfce873707314608b57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382961"
---
# <a name="word-breaks-in-rich-edit-controls"></a>リッチ エディット コントロールでのワード区切り
リッチ エディット コントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) という「単語区切りプロシージャ」関数を呼び出します単語の区切り記号を検索し、行を壊すことを決定します。 コントロールは、テキストの折り返しの操作を実行して、ctrl キーを押しながら左および ctrl キーを押しながら右キーの組み合わせを処理するときに、この情報を使用します。 アプリケーションでは、メッセージ、リッチ エディット コントロールが既定単語区切りプロシージャ、単語区切りの情報を取得し、指定された文字がある行を決定するに当たるを送信できます。  
  
## <a name="see-also"></a>関連項目  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

