---
title: ビューを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4094f41f00266b229c755232f534e9c35d29fe7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-views"></a>ビューの使い方
ビューの役割は、ユーザーにドキュメントのデータをグラフィカルに表示してそのまま使用し、ドキュメントに対する操作として、ユーザー入力を解釈です。 ビュー クラスの作成で、タスクには。  
  
-   ビュー クラスの記述[OnDraw](../mfc/reference/cview-class.md#ondraw)メンバー関数は、ドキュメントのデータを表示します。  
  
-   ビュー クラスのメッセージ ハンドラー メンバー関数には、適切な Windows メッセージおよびメニュー項目などのユーザー インターフェイス オブジェクトを接続します。  
  
-   ユーザー入力を処理するハンドラーを実装します。  
  
 その他をオーバーライドする必要がありますさらに、`CView`派生ビュー クラスのメンバー関数。 具体的には、無効にすることがあります[フィルターと並べ替え順序](../mfc/reference/cview-class.md#oninitialupdate)ビューの特別な初期化を実行して[OnUpdate](../mfc/reference/cview-class.md#onupdate)ビュー自体を再描画する前に必要な特別な処理を実行します。 マルチページ ドキュメントは、上書きすることも必要があります[OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting)を印刷するページおよびその他の情報の数と印刷 ダイアログ ボックスを初期化します。 オーバーライドの詳細については`CView`メンバー関数は、クラスを参照してください[CView](../mfc/reference/cview-class.md)で、 *『 MFC リファレンス*です。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [MFC で使用できる派生ビュー クラス](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [ビューの描画](../mfc/drawing-in-a-view.md)  
  
-   [ビューを介してユーザー入力の解釈](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [印刷でのビューの役割](../mfc/role-of-the-view-in-printing.md)  
  
-   [スクロールとビューのスケーリング](../mfc/scrolling-and-scaling-views.md)  
  
-   [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>関連項目  
 [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)   
 [CFormView クラス](../mfc/reference/cformview-class.md)   
 [レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)   
 [シリアル化機構のバイパス](../mfc/bypassing-the-serialization-mechanism.md)

