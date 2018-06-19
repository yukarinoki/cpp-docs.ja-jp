---
title: OLE DB アプリケーションでのリソース プール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ece7ce128251f66360566c9b1965466352c4e493
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33107488"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB アプリケーションでのリソース プール
アプリケーションでのプールを活用するには、OLE DB サービスが使用して、データ ソースを取得することによって呼び出されることを確認してください**IDataInitialize**または**IDBPromptInitialize**です。 直接使用する場合`CoCreateInstance`呼び出すには、プロバイダーの CLSID に基づく、プロバイダー、OLE DB サービスは呼び出されません。  
  
 OLE DB サービスが接続されているデータ ソースへの参照と同じくらいのプールを維持**IDataInitialize**または**IDBPromptInitialize**が保持されているか、使用中の接続がある限りです。 プールは、COM + 1.0 Services またはインターネット インフォメーション サービス (IIS) の環境内で自動的に維持されます。 参照を保持する必要がある場合は、アプリケーションでは、COM + 1.0 Services または IIS 環境の外部でプールの利用、 **IDataInitialize**または**IDBPromptInitialize**には、少なくとも 1 つにするか接続です。 最後の接続はをアプリケーションによってリリースされたときに、プールが破棄されないことを確認するには、アプリケーションの有効期間にわたって接続保持するか、参照を保持します。  
  
 OLE DB サービスが接続の描画時に元となる、プールを特定する`Initialize`と呼びます。 接続がプールから描画されると、後に、別のプールに移動できません。 したがって、呼び出しなどの初期化情報を変更するアプリケーションでの作業を実行しないように`UnInitialize`呼び出しまたは`QueryInterface`呼び出す前に、プロバイダー固有のインターフェイスの`Initialize`します。 またで確立された接続プロンプトの値以外の**DBPROMPT_NOPROMPT**プールされていません。 ただし、プロンプトを通じて確立された接続から取得された初期化文字列は、同じデータ ソースに追加されているプールされた接続を確立するために使用できます。  
  
 一部のプロバイダーは、セッションごとに別々 の接続を作成する必要があります。 これらの接続を追加する必要がありますとは別にトランザクションに参加させる、分散、いずれかが存在する場合。 OLE DB サービスをキャッシュし、データ ソースごとに 1 つのセッションを再利用、プロバイダーが追加の接続を行うとは別のトランザクション参加リストの実行を最後可能性があります、アプリケーションは、1 つのデータ ソースから一度に 1 つ以上のセッションを要求している場合プールされていません。 1 つのデータ ソースから複数のセッションを作成するよりもされているプールされた環境でセッションごとに個別のデータ ソースを作成する方が効率的です。  
  
 最後に、ADO 自動的に利用するための OLE DB サービス、ADO を使用して接続を確立し、プールと参加リストが自動的に行われます。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB リソース プールとサービス](../../data/oledb/ole-db-resource-pooling-and-services.md)