---
title: OLE DB アプリケーションでのリソース プール
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
ms.openlocfilehash: 3604f6eaaf0f34a0ff7e54826923c2aa92eef4a2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209778"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB アプリケーションでのリソース プール

アプリケーションでプーリングを活用するには、`IDataInitialize` または `IDBPromptInitialize`を使用してデータソースを取得することによって、OLE DB サービスが呼び出されるようにする必要があります。 `CoCreateInstance` を直接使用してプロバイダーの CLSID に基づいてプロバイダーを呼び出す場合、OLE DB サービスは呼び出されません。

OLE DB サービスは、`IDataInitialize` または `IDBPromptInitialize` への参照が保持されている限り、または使用中の接続がある限り、接続されたデータソースのプールを維持します。 プールは、COM + 1.0 サービスまたはインターネットインフォメーションサービス (IIS) 環境内でも自動的に維持されます。 アプリケーションが COM + 1.0 サービスまたは IIS 環境の外部でプーリングを利用している場合は、`IDataInitialize` への参照を保持するか、少なくとも1つの接続に `IDBPromptInitialize` する必要があります。 アプリケーションによって最後の接続が解放されたときにプールが破棄されないようにするには、アプリケーションの有効期間中は、参照を保持するか、接続を保持します。

OLE DB サービスは、`Initialize` が呼び出されたときに接続が描画されるプールを識別します。 プールから接続を取得した後は、別のプールに移動することはできません。 そのため、`Initialize`を呼び出す前に、`UnInitialize` の呼び出し、プロバイダー固有のインターフェイスの `QueryInterface` の呼び出しなどの初期化情報を変更するアプリケーションでは、処理を行わないようにしてください。 また、DBPROMPT_NOPROMPT 以外のプロンプト値で確立された接続はプールされません。 ただし、プロンプトを使用して確立された接続から取得した初期化文字列を使用して、同じデータソースへの追加のプールされた接続を確立できます。

プロバイダーによっては、セッションごとに個別の接続を確立する必要があります。 これらの追加の接続は、分散トランザクションに個別に参加する必要があります (存在する場合)。 OLE DB サービスでは、データソースごとに1つのセッションがキャッシュおよび再利用されますが、アプリケーションが1つのデータソースから一度に複数のセッションを要求した場合、プロバイダーは追加の接続を作成し、追加のトランザクションを参加させることができます。プールされていません。 1つのデータソースから複数のセッションを作成するよりも、プールされた環境のセッションごとに個別のデータソースを作成する方が効率的です。

また、ADO によって OLE DB サービスが自動的に使用されるため、ADO を使用して接続を確立し、プーリングと参加が自動的に行われるようにすることができます。

## <a name="see-also"></a>参照

[OLE DB リソース プールとサービス](../../data/oledb/ole-db-resource-pooling-and-services.md)
