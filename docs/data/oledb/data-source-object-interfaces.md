---
title: データ ソース オブジェクト インターフェイス
ms.date: 10/24/2018
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
ms.openlocfilehash: a615694a9db75cdaf3b187cf6d29248bd26ef978
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544604"
---
# <a name="data-source-object-interfaces"></a>データ ソース オブジェクト インターフェイス

次の表は、データソースオブジェクトの OLE DB によって定義される必須および省略可能なインターフェイスを示しています。

|インターフェイス|必須|OLE DB テンプレートによって実装されますか?|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|Mandatory|はい|
|`IDBInitialize`|Mandatory|はい|
|`IDBProperties`|Mandatory|はい|
|[IPersist](/windows/win32/api/objidl/nn-objidl-ipersist)|Mandatory|はい|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|［オプション］|いいえ|
|`IDBDataSourceAdmin`|［オプション］|いいえ|
|`IDBInfo`|［オプション］|いいえ|
|[IPersistFile](/windows/win32/api/objidl/nn-objidl-ipersistfile)|［オプション］|いいえ|
|`ISupportErrorInfo`|［オプション］|いいえ|

データソースオブジェクトは、継承によって `IDBProperties`、`IDBInitialize`、および `IDBCreateSession` インターフェイスを実装します。 これらの実装クラスの1つを継承するかどうかによって、追加の機能をサポートするように選択できます。 `IDBDataSourceAdmin` インターフェイスをサポートする場合は、`IDBDataSourceAdminImpl` クラスから継承する必要があります。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
