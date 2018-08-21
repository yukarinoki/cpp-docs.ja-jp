---
title: OLE DB アプリケーションでのリソース プール |Microsoft Docs
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
ms.openlocfilehash: 4798b4bac8cc6f94e5199502a926eb084cc7534a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340242"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB アプリケーションでのリソース プール
アプリケーションでのプールを活用するには、OLE DB サービスが使用して、データ ソースを取得することによって呼び出されることを確認してください`IDataInitialize`または`IDBPromptInitialize`します。 直接使用する場合`CoCreateInstance`をプロバイダーの CLSID に基づいてプロバイダーを呼び出すには、OLE DB サービスは呼び出されません。  
  
 OLE DB サービスが接続されているデータ ソースへの参照と同じくらいのプールを維持`IDataInitialize`または`IDBPromptInitialize`が保持されているか使用中の接続がある限りです。 COM + 1.0 Services またはインターネット インフォメーション サービス (IIS) の環境内では、プールが自動的に保持もされます。 参照を保持する必要がある場合は、アプリケーションでは、COM + 1.0 Services または IIS 環境外でプールの利用、`IDataInitialize`または`IDBPromptInitialize`または少なくとも 1 つの接続を保持します。 最後の接続はをアプリケーションによってリリースされたときに、プールが破棄されないことを確認するには、アプリケーションの有効期間にわたって接続保持するか、参照を保持します。  
  
 OLE DB サービスの特定時点で、接続の描画元となるプールを`Initialize`が呼び出されます。 接続をプールから描画した後、別のプールに移動できません。 したがって、呼び出しなどの初期化情報を変更するアプリケーションでの作業を実行しないように`UnInitialize`呼び出しまたは`QueryInterface`呼び出す前に、プロバイダー固有のインターフェイスの`Initialize`します。 また、プロンプトの値を DBPROMPT_NOPROMPT 以外によって確立された接続はプールされていません。 ただし、プロンプトを通じて確立された接続から取得された初期化文字列は、同じデータ ソースに追加されているプールされた接続を確立するために使用できます。  
  
 一部のプロバイダーは、セッションごとに個別の接続を行う必要があります。 これらの接続を追加する必要がありますとは別に参加の分散トランザクションに存在する場合。 OLE DB サービスをキャッシュし、データ ソースごとに 1 つのセッションを再利用、プロバイダーが追加の接続を行うとは別のトランザクションの参加リストの実行を終了可能性があります、アプリケーションは、1 つのデータ ソースから一度に 1 つ以上のセッションを要求している場合プールされていません。 1 つのデータ ソースから複数のセッションを作成するよりも、プールされた環境でセッションごとに個別のデータ ソースを作成する方が効率的です。  
  
 最後に、ADO に自動的に利用するための OLE DB サービスでは、ADO を使用して接続を確立し、プールと参加リストが自動的に行われます。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB リソース プールとサービス](../../data/oledb/ole-db-resource-pooling-and-services.md)