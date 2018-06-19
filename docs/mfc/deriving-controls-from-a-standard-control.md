---
title: 標準コントロールからのコントロールの派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- standard controls [MFC], deriving controls from
- common controls [MFC], deriving from
- derived controls
- controls [MFC], derived
- Windows common controls [MFC], deriving from
- standard controls
ms.assetid: a6f84315-7007-4e0e-8576-78be81254802
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50db9d4c99e8ef538ffaa5352f9ec96e5b08217f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344501"
---
# <a name="deriving-controls-from-a-standard-control"></a>標準コントロールからのコントロールの派生
同じよう[CWnd](../mfc/reference/cwnd-class.md)-派生クラスでは、既存のコントロール クラスから新しいクラスを派生させることによってコントロールの動作を変更することができます。  
  
### <a name="to-create-a-derived-control-class"></a>派生コントロール クラスを作成するには  
  
1.  既存のコントロール クラスからクラスを派生し、必要に応じてオーバーライドして、**作成**メンバー関数の基底クラスのために必要な引数を提供するように**作成**関数。  
  
2.  メッセージ ハンドラー メンバー関数と特定の Windows メッセージへの応答で、コントロールの動作を変更するメッセージ マップ エントリを提供します。 参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)です。  
  
3.  (省略可能) のコントロールの機能を拡張する新しいメンバー関数を提供します。  
  
 ダイアログ ボックスで、派生するコントロールを使用するには、追加の作業が必要です。 型と、ダイアログ ボックスでコントロールの位置は通常、ダイアログ テンプレート リソースで指定します。 クラスを派生するコントロールを作成する場合できませんで指定するダイアログ テンプレート リソース コンパイラは、派生クラスを一切把握ためです。  
  
#### <a name="to-place-your-derived-control-in-a-dialog-box"></a>ダイアログ ボックスで、派生したコントロールを配置するには  
  
1.  派生ダイアログ クラスの宣言では、派生したコントロール クラスのオブジェクトを埋め込みます。  
  
2.  上書き、`OnInitDialog`メンバー関数を呼び出すダイアログ クラスで、`SubclassDlgItem`派生コントロールのメンバー関数。  
  
 `SubclassDlgItem` 「サブクラスでは動的に」コントロールは、ダイアログ テンプレートから作成されます。 コントロールが動的にサブクラス化する Windows にフック、独自のアプリケーション内でいくつかのメッセージを処理し、Windows にログオン残りのメッセージを渡します。 詳細については、次を参照してください。、 [SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem)クラスのメンバー関数`CWnd`で、 *『 MFC リファレンス*です。 次の例は、のオーバーライドを記述する方法を示しています`OnInitDialog`を呼び出す`SubclassDlgItem`:。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#3](../mfc/codesnippet/cpp/deriving-controls-from-a-standard-control_1.cpp)]  
  
 ダイアログ クラスでは、派生したコントロールが埋め込まれているため、構築時に、ダイアログ ボックスが構築され、ダイアログ ボックスが破棄されるときに破棄されます。 このコード例を比較[手動でコントロールを追加する](../mfc/adding-controls-by-hand.md)です。  
  
## <a name="see-also"></a>関連項目  
 [作成方法とコントロールの使用](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)

