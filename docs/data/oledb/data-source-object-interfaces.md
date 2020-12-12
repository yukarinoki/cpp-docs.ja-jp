---
description: 詳細については、「データソースオブジェクトインターフェイス」を参照してください。
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
ms.openlocfilehash: ecc37ca4286e288939ccd15bdcd073379c27f7c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287620"
---
# <a name="data-source-object-interfaces"></a>データ ソース オブジェクト インターフェイス

次の表は、データソースオブジェクトの OLE DB によって定義される必須および省略可能なインターフェイスを示しています。

|インターフェイス|必須|OLE DB テンプレートによって実装されますか?|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|Mandatory|はい|
|`IDBInitialize`|Mandatory|はい|
|`IDBProperties`|Mandatory|はい|
|[IPersist](/windows/win32/api/objidl/nn-objidl-ipersist)|Mandatory|はい|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|省略可能|×|
|`IDBDataSourceAdmin`|省略可能|×|
|`IDBInfo`|省略可能|×|
|[IPersistFile](/windows/win32/api/objidl/nn-objidl-ipersistfile)|省略可能|×|
|`ISupportErrorInfo`|省略可能|×|

データソースオブジェクトは、継承によって、、およびの各インターフェイスを実装し `IDBProperties` `IDBInitialize` `IDBCreateSession` ます。 これらの実装クラスの1つを継承するかどうかによって、追加の機能をサポートするように選択できます。 インターフェイスをサポートする場合は、 `IDBDataSourceAdmin` クラスから継承する必要があり `IDBDataSourceAdminImpl` ます。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
