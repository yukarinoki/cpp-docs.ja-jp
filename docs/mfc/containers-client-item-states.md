---
title: 'コンテナー: クライアント アイテムの状態 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5046ea7f3f3775cfe0009afe50f33a6ce6723cc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="containers-client-item-states"></a>コンテナー : クライアント アイテムの状態
この記事では、クライアント アイテムがその有効期間に通過するさまざまな状態について説明します。  
  
 クライアント アイテムは、作成、アクティブ化、変更されると、および保存されるいくつかの状態を通過します。 フレームワークによって、項目の状態が変更されるたびに[として](../mfc/reference/coleclientitem-class.md#onchange)で、`OLE_CHANGED_STATE`通知します。 2 番目のパラメーターの値は、 **COleClientItem::ItemState**列挙します。 次のいずれかを指定できます。  
  
-   **COleClientItem::emptyState**  
  
-   **COleClientItem::loadedState**  
  
-   **COleClientItem::openState**  
  
-   **COleClientItem::activeState**  
  
-   **COleClientItem::activeUIState**  
  
 空の状態でクライアント アイテムいないまだ完全アイテムです。 メモリが割り当てられたが、OLE アイテムのデータで初期化されていません。 クライアント アイテムの状態を呼び出すことによって作成されたときに、この**新しい**が、一般的な 2 段階の作成の 2 番目の手順を実施されていません。  
  
 2 番目の手順を呼び出すことによって実行される`COleClientItem::CreateFromFile`別または **レプリカ * * * xxxx*関数、項目が作成される完全にします。 (ファイル、クリップボードなど、他のソースから) OLE データが関連付けられている、 `COleClientItem`-派生オブジェクト。 現在の項目は読み込まれた状態です。  
  
 項目がされているサーバーのウィンドウで開かれているではなく、コンテナーのドキュメント内の場所で開かれている、ときに、開いている (または完全にオープン) 状態にある必要があります。 この状態で、クロスハッチ通常は描画で項目がアクティブである他の場所を示すために、コンテナーのウィンドウ内の項目の表示されます。  
  
 項目はインプレース アクティブ化されて、ときに合格した通常のみアクティブな状態を簡単に、します。 そのメニューのツールバー、およびその他のユーザー インターフェイス コンポーネントとコンテナーのサーバーはマージ、UI のアクティブな状態を入力します。 これらのユーザー インターフェイス コンポーネントが存在するには、アクティブな状態からの UI のアクティブな状態が区別されます。 それ以外の場合、アクティブな状態では、UI のアクティブな状態に似ています。 サーバーは、元に戻すをサポートする場合、サーバーは、読み込まれたまたは開いている状態に到達するまで OLE 項目の元に戻す状態情報を保持するために必要です。  
  
## <a name="see-also"></a>関連項目  
 [コンテナー](../mfc/containers.md)   
 [アクティブ化](../mfc/activation-cpp.md)   
 [コンテナー: クライアント アイテム通知](../mfc/containers-client-item-notifications.md)   
 [(トラッカーを)](../mfc/trackers.md)   
 [CRectTracker クラス](../mfc/reference/crecttracker-class.md)
