---
title: ウィンドウ オブジェクトの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4c00649c51e34bbbac7adbf7aa5f3c7d04790ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="working-with-window-objects"></a>ウィンドウ オブジェクトの操作
Windows の呼び出しの 2 種類のアクティビティの使用。  
  
-   Windows メッセージの処理  
  
-   ウィンドウでの描画  
  
 独自の子ウィンドウを含めて、どのウィンドウにある Windows メッセージを処理するために、次を参照してください。[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)C++ ウィンドウ クラスにメッセージをマップします。 メッセージ ハンドラー メンバー関数を記述、クラスです。  
  
 ビューでは、発生 framework アプリケーションで描画のほとんどが[OnDraw](../mfc/reference/cview-class.md#ondraw)ウィンドウの内容を描画する必要があるたびに、メンバー関数が呼び出されます。 ウィンドウがビューの子である場合は、委任したりビューの描画の一部を子ウィンドウ用意することによって`OnDraw`メンバー関数は、ウィンドウのいずれかを呼び出します。  
  
 いずれの場合は、描画のデバイス コンテキストを必要があります。 ストックのペン、ブラシ、および現在のウィンドウに関連付けられているデバイス コンテキストに含まれているその他のグラフィック オブジェクトを使用することができます。 または、これらのオブジェクトを取得する必要があります、描画効果を変更することができます。 好きなように、設定、デバイス コンテキストにメンバーを呼び出すクラスの関数は[CDC](../mfc/reference/cdc-class.md) (デバイス コンテキスト クラス) 線、図形、およびテキストを描画する; 色; を使用して、座標系を使用します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)  
  
-   [ビューの描画](../mfc/drawing-in-a-view.md)  
  
-   [デバイス コンテキスト](../mfc/device-contexts.md)  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md)  
  
## <a name="see-also"></a>関連項目  
 [Window オブジェクト](../mfc/window-objects.md)

