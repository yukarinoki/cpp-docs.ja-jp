---
description: '詳細については、「サーバー: サーバー項目」を参照してください。'
title: 'サーバー : サーバー アイテム'
ms.date: 11/04/2016
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
ms.openlocfilehash: e3fceb3abe89ca6cda432d60441a47fc0d452cfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217316"
---
# <a name="servers-server-items"></a>サーバー : サーバー アイテム

コンテナーがサーバーを起動して、ユーザーが埋め込み OLE 項目またはリンクされた OLE 項目を編集できるようにすると、サーバーアプリケーションによって "サーバー項目" が作成されます。 サーバー項目は、から派生したクラスのオブジェクトで `COleServerItem` あり、サーバードキュメントとコンテナーアプリケーションとの間にインターフェイスを提供します。

クラスは、 `COleServerItem` 通常、コンテナーからの要求に応答して OLE によって呼び出される、オーバーライド可能な複数のメンバー関数を定義します。 サーバー項目は、サーバードキュメントまたはドキュメント全体の一部を表すことができます。 OLE 項目がコンテナードキュメントに埋め込まれている場合、サーバー項目はサーバードキュメント全体を表します。 OLE 項目がリンクされている場合、サーバー項目は、そのリンクが部分または全体のどちらに関連しているかに応じて、サーバードキュメントの一部またはドキュメント全体を表すことができます。

たとえば、 [HIERSVR](../overview/visual-cpp-samples.md) サンプルでは、サーバー項目クラスには、 `CServerItem` クラスのオブジェクトへのポインターであるメンバーがあり `CServerNode` ます。 `CServerNode`オブジェクトは、HIERSVR アプリケーションのドキュメント (ツリー) 内のノードです。 `CServerNode`オブジェクトがルートノードの場合、オブジェクトは `CServerItem` ドキュメント全体を表します。 `CServerNode`オブジェクトが子ノードの場合、オブジェクトは `CServerItem` ドキュメントの一部を表します。 この相互作用の例については、「MFC OLE サンプル [HIERSVR](../overview/visual-cpp-samples.md) 」を参照してください。

## <a name="implementing-server-items"></a><a name="_core_implementing_server_items"></a> サーバー項目の実装

アプリケーションウィザードを使用してアプリケーションの "starter" コードを生成する場合、スタートコードにサーバー項目を含める必要があるのは、[OLE オプション] ページでサーバーオプションのいずれかを選択することだけです。 既存のアプリケーションにサーバー項目を追加する場合は、次の手順を実行します。

#### <a name="to-implement-a-server-item"></a>サーバー項目を実装するには

1. `COleServerItem` の派生クラスを作成します。

1. 派生クラスで、メンバー関数をオーバーライドし `OnDraw` ます。

   フレームワークはを呼び出して、 `OnDraw` OLE 項目をメタファイルに表示します。 コンテナーアプリケーションは、このメタファイルを使用して項目を表示します。 アプリケーションのビュークラスには `OnDraw` 、サーバーアプリケーションがアクティブなときに項目を表示するために使用されるメンバー関数もあります。

1. `OnGetEmbeddedItem`サーバードキュメントクラスののオーバーライドを実装します。 詳細については、「サーバー [: サーバードキュメントの実装](../mfc/servers-implementing-server-documents.md) 」および「MFC OLE サンプル [HIERSVR](../overview/visual-cpp-samples.md)」を参照してください。

1. サーバー項目クラスの `OnGetExtent` メンバー関数を実装します。 フレームワークは、この関数を呼び出して項目のサイズを取得します。 既定の実装では、何も行われません。

## <a name="a-tip-for-server-item-architecture"></a><a name="_core_a_tip_for_server.2d.item_architecture"></a> Server-Item アーキテクチャのヒント

「 [サーバー項目の実装](#_core_implementing_server_items)」で説明したように、サーバーアプリケーションは、サーバーのビューと、コンテナーアプリケーションで使用されるメタファイルの両方の項目を表示できる必要があります。 Microsoft Foundation Class ライブラリのアプリケーションアーキテクチャでは、ビュークラスの `OnDraw` メンバー関数は、編集時に項目をレンダリングします (*クラスライブラリリファレンス* の「 [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw) 」を参照してください)。 サーバー項目のは、 `OnDraw` その他のすべての場合に、その項目をメタファイルにレンダリングします (「 [COleServerItem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)」を参照)。

サーバー-ドキュメントクラスにヘルパー関数を記述し、 `OnDraw` ビューとサーバー項目クラスの関数からそれらを呼び出すことによって、コードの重複を回避できます。 MFC OLE サンプル [HIERSVR](../overview/visual-cpp-samples.md) では、この方法を使用して、関数 `CServerView::OnDraw` との両方の呼び出しによって `CServerItem::OnDraw` `CServerDoc::DrawTree` 項目がレンダリングされます。

ビューとアイテムは、 `OnDraw` それぞれ異なる条件で描画されるので、メンバー関数を持ちます。 このビューでは、ズーム、選択範囲のサイズと範囲、クリッピング、スクロールバーなどのユーザーインターフェイス要素を考慮に入れる必要があります。 一方、サーバー項目は、常に OLE オブジェクト全体を描画します。

詳細については、*クラスライブラリリファレンス* の「 [CView:: ondraw](../mfc/reference/cview-class.md#ondraw)、 [Coleserveritem](../mfc/reference/coleserveritem-class.md)、 [coleserveritem:: ondraw](../mfc/reference/coleserveritem-class.md#ondraw)、および [COleServerDoc:: OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) 」を参照してください。

## <a name="see-also"></a>関連項目

[サーバー](../mfc/servers.md)
