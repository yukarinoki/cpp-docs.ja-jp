---
title: 'サーバー: サーバー アイテム |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e83b75183fe226b4ff384a00b0b5260caba01efa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382503"
---
# <a name="servers-server-items"></a>サーバー : サーバー アイテム
コンテナーは、ユーザーは埋め込みまたはリンクされている OLE 項目を編集できるようにサーバーを起動したときに、サーバー アプリケーション項目を作成、"サーバーです" 派生したクラスのオブジェクトをあるサーバーのアイテムに`COleServerItem`サーバーのドキュメントとコンテナー アプリケーション間のインターフェイスを提供します。  
  
 `COleServerItem`クラスは、通常は、コンテナーからの要求に応えて、OLE、によって呼び出されるいくつかのオーバーライド可能なメンバー関数を定義します。 サーバーのアイテムには、サーバーのドキュメントまたはドキュメント全体の一部を表すことができます。 OLE 項目がコンテナー ドキュメントに埋め込まれている場合、サーバー項目は、サーバー全体のドキュメントを表します。 OLE 項目をリンクすると、サーバー項目は、サーバーのドキュメントまたはリンクが一部または全体があるかによって、ドキュメント全体の一部を表すことができます。  
  
 [HIERSVR](../visual-cpp-samples.md)サンプルは、たとえば、サーバー項目クラス**よう**、クラスのオブジェクトへのポインターであるメンバーを持つ**CServerNode**です。 **CServerNode**オブジェクトが、HIERSVR アプリケーションのドキュメントは、ツリー内のノードです。 ときに、 **CServerNode**オブジェクトは、ルート ノード、**よう**オブジェクトはドキュメント全体を表します。 ときに、 **CServerNode**オブジェクトが子ノード、**よう**オブジェクトは、ドキュメントの一部を表します。 MFC OLE サンプルを参照して[HIERSVR](../visual-cpp-samples.md)この相互作用の例についてはします。  
  
##  <a name="_core_implementing_server_items"></a> サーバーのアイテムを実装します。  
 アプリケーションの"starter"コードを生成するために、アプリケーションのウィザードを使用する場合に、スターター コードでサーバーのアイテムを含めるために必要は OLE オプション ページから、サーバー オプションのいずれかを選択してです。 既存のアプリケーション サーバーのアイテムを追加する場合は、次の手順を実行します。  
  
#### <a name="to-implement-a-server-item"></a>サーバー アイテムを実装するには  
  
1.  `COleServerItem` の派生クラスを作成します。  
  
2.  派生クラスでオーバーライド、`OnDraw`メンバー関数。  
  
     フレームワークによって`OnDraw`メタファイル OLE 項目を表示するためにします。 コンテナー アプリケーションでは、アイテムを表示するためにこのメタファイルを使用します。 アプリケーションのビュー クラスもあります、`OnDraw`メンバー関数は、サーバー アプリケーションがアクティブなときに、項目を表示するために使用します。  
  
3.  オーバーライドを実装する`OnGetEmbeddedItem`サーバー ドキュメント クラスです。 詳細については、記事を参照してください。[サーバー: サーバー ドキュメントの実装](../mfc/servers-implementing-server-documents.md)と MFC OLE サンプル[HIERSVR](../visual-cpp-samples.md)です。  
  
4.  サーバー項目クラスの実装`OnGetExtent`メンバー関数。 フレームワークは、アイテムのサイズを取得するには、この関数を呼び出します。 既定の実装では、何も行われません。  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> サーバー アイテムのアーキテクチャのヒント  
 説明したとおり[サーバー アイテムの実装](#_core_implementing_server_items)、サーバー アプリケーションは、サーバーのビューでは、コンテナー アプリケーションで使われるメタファイルの両方の項目をレンダリングする必要があります。 Microsoft Foundation Class ライブラリ アプリケーション アーキテクチャでは、ビュー クラスの`OnDraw`が編集されているときに、メンバー関数は、項目を表示 (を参照してください[詳細](../mfc/reference/cview-class.md#ondraw)で、*クラス ライブラリ リファレンス*). サーバー アイテムの`OnDraw`メタファイル以外の場合に、項目を表示 (を参照してください[:ondraw](../mfc/reference/coleserveritem-class.md#ondraw))。  
  
 サーバー ドキュメント クラスのヘルパー関数を記述してからそれらを呼び出すことのコードの重複を回避することができます、`OnDraw`クラス ビューとサーバー項目クラス内の関数。 MFC OLE サンプル[HIERSVR](../visual-cpp-samples.md)はこの方法を使用します関数は、 **CServerView::OnDraw**と**修正**両方を呼び出す**CServerDoc::DrawTree。** アイテムを表示するためにします。  
  
 ビューと項目の両方がある`OnDraw`メンバー関数のさまざまな条件で描画されるためです。 ビューは、ズーム、選択範囲のサイズとエクステント、領域、およびスクロール バーなどのユーザー インターフェイス要素としてなどの条件を考慮する必要があります。 サーバー アイテム、その一方で、常に描画全体の OLE オブジェクト。  
  
 詳細については、次を参照してください[詳細](../mfc/reference/cview-class.md#ondraw)、 [COleServerItem](../mfc/reference/coleserveritem-class.md)、 [:ondraw](../mfc/reference/coleserveritem-class.md#ondraw)、および[COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)。で、*クラス ライブラリ リファレンス*です。  
  
## <a name="see-also"></a>関連項目  
 [サーバー](../mfc/servers.md)

