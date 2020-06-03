---
title: 'サーバー : サーバー アイテム'
ms.date: 11/04/2016
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
ms.openlocfilehash: 8ae24104a30a0b44e92b889006907911124310f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355112"
---
# <a name="servers-server-items"></a>サーバー : サーバー アイテム

コンテナーがサーバーを起動して、ユーザーが埋め込み OLE アイテムまたはリンク OLE アイテムを編集できるようにすると、サーバー アプリケーションは "サーバー アイテム" を作成します。 から派生`COleServerItem`したクラスのオブジェクトであるサーバー項目は、サーバードキュメントとコンテナアプリケーションの間のインタフェースを提供します。

この`COleServerItem`クラスは、通常はコンテナーからの要求に応答して、OLE によって呼び出されるオーバーライド可能なメンバー関数をいくつか定義します。 サーバーアイテムは、サーバードキュメントの一部またはドキュメント全体を表すことができます。 OLE アイテムがコンテナー ドキュメントに埋め込まれている場合、サーバー アイテムはサーバー ドキュメント全体を表します。 OLE アイテムがリンクされている場合、サーバー アイテムは、リンクが部分に対してあるか、全体に対してリンクされているかに応じて、サーバー ドキュメントの一部または全体を表すことができます。

[HIERSVR](../overview/visual-cpp-samples.md)サンプルでは、たとえば、サーバー項目クラス の メンバー`CServerItem`がクラスのオブジェクトへのポインターです`CServerNode`。 オブジェクト`CServerNode`は、HIERSVR アプリケーションのドキュメント内のノードであり、ツリーです。 オブジェクトが`CServerNode`ルート ノードの場合、オブジェクト`CServerItem`はドキュメント全体を表します。 オブジェクトが`CServerNode`子ノードの場合、オブジェクトは`CServerItem`ドキュメントの一部を表します。 この操作の例については、MFC OLE サンプル[HIERSVR](../overview/visual-cpp-samples.md)を参照してください。

## <a name="implementing-server-items"></a><a name="_core_implementing_server_items"></a>サーバー項目の実装

アプリケーション ウィザードを使用してアプリケーションの "スタート" コードを生成する場合は、サーバー項目をスタート コードに含める必要がある点は、[OLE オプション] ページからサーバー オプションのいずれかを選択することだけです。 既存のアプリケーションにサーバーアイテムを追加する場合は、次の手順を実行します。

#### <a name="to-implement-a-server-item"></a>サーバー項目を実装するには

1. `COleServerItem` の派生クラスを作成します。

1. 派生クラスで、メンバー関数を`OnDraw`オーバーライドします。

   フレームワークは、OLE アイテムをメタファイルにレンダリングする呼び出しを行`OnDraw`います。 コンテナー アプリケーションは、このメタファイルを使用してアイテムをレンダリングします。 アプリケーションのビュー クラスには、サーバー`OnDraw`アプリケーションがアクティブな場合にアイテムを表示するために使用されるメンバー関数もあります。

1. サーバー ドキュメント`OnGetEmbeddedItem`クラスの オーバーライドを実装します。 詳細については、「[サーバー: サーバー ドキュメントの実装](../mfc/servers-implementing-server-documents.md)」および MFC OLE サンプル[HIERSVR](../overview/visual-cpp-samples.md)を参照してください。

1. サーバー項目クラスのメンバー関数を`OnGetExtent`実装します。 フレームワークは、この関数を呼び出して、項目のサイズを取得します。 既定の実装では、何も行われません。

## <a name="a-tip-for-server-item-architecture"></a><a name="_core_a_tip_for_server.2d.item_architecture"></a>サーバーアイテムアーキテクチャのヒント

[サーバー項目の実装](#_core_implementing_server_items)で説明したように、サーバー アプリケーションは、サーバーのビューとコンテナー アプリケーションで使用されるメタファイルの両方でアイテムをレンダリングできる必要があります。 Microsoft Foundation クラス ライブラリのアプリケーション アーキテクチャでは、ビュー クラス`OnDraw`のメンバー関数は、編集中にアイテムをレンダリングします (*クラス ライブラリ リファレンス*の[CView::OnDraw](../mfc/reference/cview-class.md#ondraw)を参照)。 サーバー アイテムは、`OnDraw`その他のすべての場合にアイテムをメタファイルにレンダリング[します (COleServerItem::OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)を参照)。

サーバー ドキュメント クラスにヘルパー関数を記述し、ビュークラスやサーバー項目クラスの`OnDraw`関数から呼び出すことで、コードの重複を回避できます。 MFC OLE サンプル[HIERSVR](../overview/visual-cpp-samples.md)では、この`CServerView::OnDraw`方法`CServerItem::OnDraw`を使用`CServerDoc::DrawTree`して、関数と両方の呼び出しを使用してアイテムをレンダリングします。

ビューと項目は、異なる`OnDraw`条件で描画されるため、両方のメンバー関数を持ちます。 ビューでは、ズーム、選択範囲のサイズと範囲、クリッピング、スクロール バーなどのユーザー インターフェイス要素などの要素を考慮する必要があります。 一方、サーバーアイテムは常に OLE オブジェクト全体を描画します。

詳細については、「クラス ライブラリ リファレンスの[CView::オンドロー](../mfc/reference/cview-class.md#ondraw) [、COleServerItem、COleServerItem::](../mfc/reference/coleserveritem-class.md)[オンドロー](../mfc/reference/coleserveritem-class.md#ondraw)、および[COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) 」を*参照してください*。

## <a name="see-also"></a>関連項目

[サーバー](../mfc/servers.md)
