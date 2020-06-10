---
title: 'コンテナー : クライアント アイテムの状態'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
ms.openlocfilehash: 927211ccec35d8ec26e2f76b971c59b80248ab96
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625988"
---
# <a name="containers-client-item-states"></a>コンテナー : クライアント アイテムの状態

この記事では、クライアント項目が有効期間内に通過するさまざまな状態について説明します。

クライアント項目は、作成、アクティブ化、変更、および保存されると、いくつかの状態を通過します。 フレームワークは、項目の状態が変化するたびに、 **OLE_CHANGED_STATE**通知を使用して[COleClientItem:: OnChange](reference/coleclientitem-class.md#onchange)を呼び出します。 2番目のパラメーターは、列挙体の値です `COleClientItem::ItemState` 。 次のいずれかを指定できます。

- *COleClientItem:: emptyState*

- *COleClientItem:: ロード状態*

- *COleClientItem:: openState*

- *COleClientItem:: activeState*

- *COleClientItem:: activeUIState*

空の状態では、クライアント項目はまだ完全な項目ではありません。 メモリが割り当てられていますが、OLE 項目のデータでまだ初期化されていません。 これは、**新しい**への呼び出しによって作成されたクライアント項目の状態ですが、通常の2段階の作成の2番目の手順はまだ行われていません。

2番目の手順では、または別の xxxx 関数を呼び出すことで実行されます。この場合、 `COleClientItem::CreateFromFile` 項目は完全に `CreateFrom` *xxxx*作成されます。 OLE データ (ファイルまたはクリップボードなどの他のソース) が、から派生したオブジェクトに関連付けられてい `COleClientItem` ます。 これで、項目が読み込まれた状態になります。

コンテナーのドキュメント内ではなく、サーバーのウィンドウで項目が開かれている場合は、開いている (または完全に開いている) 状態になります。 この状態では、通常、項目が他の場所でアクティブであることを示すために、コンテナーのウィンドウ内の項目の表現に交差するハッチが描画されます。

項目が所定の位置でアクティブ化されると、通常は、アクティブな状態によって一時的にのみ渡されます。 次に、UI のアクティブ状態に入ります。この状態では、サーバーによって、メニュー、ツールバー、およびその他のユーザーインターフェイスコンポーネントがコンテナーのものと結合されています。 これらのユーザーインターフェイスコンポーネントが存在すると、UI のアクティブな状態がアクティブな状態と区別されます。 それ以外の場合、アクティブな状態は UI のアクティブな状態に似ています。 サーバーで Undo がサポートされている場合、読み込まれた状態または開いた状態になるまで、サーバーは OLE 項目の元に戻す状態の情報を保持する必要があります。

## <a name="see-also"></a>関連項目

[Containers](containers.md)<br/>
[アクティブ化](activation-cpp.md)<br/>
[コンテナー: クライアント アイテムへの通知](containers-client-item-notifications.md)<br/>
[トラッカー](trackers.md)<br/>
[CRectTracker クラス](reference/crecttracker-class.md)
