---
description: 詳細については、OLE DB アプリケーションでのリソースプールに関するページを参照してください。
title: OLE DB アプリケーションでのリソース プール
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
ms.openlocfilehash: 504217092f4e4a19a3db2898b97e6a35269db7ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316870"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB アプリケーションでのリソース プール

アプリケーションでプーリングを活用するには、またはを使用してデータソースを取得することによって、OLE DB サービスが呼び出されるようにする必要があり `IDataInitialize` `IDBPromptInitialize` ます。 を直接使用してプロバイダー `CoCreateInstance` の CLSID に基づいてプロバイダーを呼び出すと、OLE DB サービスは呼び出されません。

またはへの参照が保持されている限り、または使用中の接続がある限り、OLE DB サービスは接続されたデータソースのプールを保持し `IDataInitialize` `IDBPromptInitialize` ます。 プールは、COM + 1.0 サービスまたはインターネットインフォメーションサービス (IIS) 環境内でも自動的に維持されます。 アプリケーションが COM + 1.0 サービスまたは IIS 環境の外部でプーリングを利用している場合は、少なくとも1つの接続に対して参照または保持する必要があり `IDataInitialize` `IDBPromptInitialize` ます。 アプリケーションによって最後の接続が解放されたときにプールが破棄されないようにするには、アプリケーションの有効期間中は、参照を保持するか、接続を保持します。

OLE DB サービスは、呼び出された時点で接続が描画されるプールを識別 `Initialize` します。 プールから接続を取得した後は、別のプールに移動することはできません。 そのため、を呼び出す前に、を呼び出し `UnInitialize` たり、プロバイダー固有のインターフェイスの呼び出しを行ったりするなど、初期化情報を変更するアプリケーションでは、処理を行わないように `QueryInterface` `Initialize` してください。 また、DBPROMPT_NOPROMPT 以外のプロンプト値で確立された接続はプールされません。 ただし、プロンプトを使用して確立された接続から取得した初期化文字列を使用して、同じデータソースへの追加のプールされた接続を確立できます。

プロバイダーによっては、セッションごとに個別の接続を確立する必要があります。 これらの追加の接続は、分散トランザクションに個別に参加する必要があります (存在する場合)。 OLE DB サービスでは、データソースごとに1つのセッションがキャッシュおよび再利用されますが、アプリケーションが1つのデータソースから一度に複数のセッションを要求した場合、プロバイダーは、追加の接続を作成し、プールされていない追加のトランザクション参加を行う可能性があります。 1つのデータソースから複数のセッションを作成するよりも、プールされた環境のセッションごとに個別のデータソースを作成する方が効率的です。

また、ADO によって OLE DB サービスが自動的に使用されるため、ADO を使用して接続を確立し、プーリングと参加が自動的に行われるようにすることができます。

## <a name="see-also"></a>関連項目

[リソースプーリングとサービスの OLE DB](../../data/oledb/ole-db-resource-pooling-and-services.md)
