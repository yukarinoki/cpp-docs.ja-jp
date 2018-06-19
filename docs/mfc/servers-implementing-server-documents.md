---
title: 'サーバー: サーバー ドキュメントの実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE server applications [MFC], managing server documents
- OLE server applications [MFC], implementing OLE servers
- servers, server documents
- server documents [MFC], implementing
ms.assetid: cca1451a-ad09-47ed-b56e-bccd78fc86d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f15dbd16b48aade59470bfbf7e84faf4aeb03c61
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380277"
---
# <a name="servers-implementing-server-documents"></a>サーバー : サーバー ドキュメントの実装
この記事では、アプリケーション ウィザードで、OLE サーバー オプションを指定しなかった場合、サーバー ドキュメントを正常に実装する手順について説明します。  
  
#### <a name="to-define-a-server-document-class"></a>サーバー ドキュメント クラスを定義するには  
  
1.  ドキュメント クラスを派生させる`COleServerDoc`の代わりに**CDocument**です。  
  
2.  派生したサーバー項目クラスを作成する`COleServerItem`です。  
  
3.  実装、`OnGetEmbeddedItem`サーバーのドキュメント クラスのメンバー関数。  
  
     `OnGetEmbeddedItem` コンテナー アプリケーションのユーザーが作成または埋め込みアイテムを編集するときと呼びます。 ドキュメント全体を表す項目を返します。 これは、値のオブジェクトには、 `COleServerItem`-クラスを派生します。  
  
4.  上書き、`Serialize`ドキュメントの内容をシリアル化するメンバー関数。 ドキュメントでネイティブのデータを表す使用している場合を除き、サーバーのアイテムの一覧をシリアル化する必要はありません。 詳細については、次を参照してください。*サーバー アイテムの実装*アーティクルで[サーバー: サーバー アイテム](../mfc/servers-server-items.md)です。  
  
 サーバー ドキュメントの作成時に、フレームワークは、ドキュメントを自動的に OLE システム Dll を登録します。 これにより、サーバーのドキュメントを識別する Dll です。  
  
 詳細については、次を参照してください。 [COleServerItem](../mfc/reference/coleserveritem-class.md)と[COleServerDoc](../mfc/reference/coleserverdoc-class.md)で、*クラス ライブラリ リファレンス*です。  
  
## <a name="see-also"></a>関連項目  
 [サーバー](../mfc/servers.md)   
 [サーバー: サーバー アイテム](../mfc/servers-server-items.md)   
 [サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)   
 [サーバー: 埋め込み先フレーム ウィンドウの実装](../mfc/servers-implementing-in-place-frame-windows.md)

