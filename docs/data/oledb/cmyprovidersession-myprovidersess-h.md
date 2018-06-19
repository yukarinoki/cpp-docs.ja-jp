---
title: CMyProviderSession (MyProviderSess.H) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyprovidersession
- myprovidersess.h
dev_langs:
- C++
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5f5243edcbc6ad7781eb13caf6ec72021fd83506
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096536"
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession (MyProviderSess.H)
MyProviderSess.H には、宣言と OLE DB セッション オブジェクトの実装が含まれています。 データ ソース オブジェクトは、セッション オブジェクトを作成し、コンシューマーとプロバイダー間のメッセージ交換を表します。 複数の同時セッションは、1 つのデータ ソースを開くことができます。 継承リストに`CMyProviderSession`に従います。  
  
```cpp
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 セッション オブジェクトから継承**IGetDataSource**、 `IOpenRowset`、 **ISessionProperties**、および**IDBCreateCommand**です。 **IGetDataSource**インターフェイスにより、セッションを作成するデータ ソースを取得します。 これは、作成したデータ ソースまたはデータ ソースを提供できるその他の情報のプロパティを取得する必要がある場合に便利です。 **ISessionProperties**インターフェイスは、セッションのすべてのプロパティを処理します。 `IOpenRowset`と**IDBCreateCommand**データベース作業を行うためのインターフェイスが使用されます。 実装するプロバイダーは、コマンドをサポートする場合、 **IDBCreateCommand**インターフェイスです。 コマンドを実行できるコマンド オブジェクトの作成に使用されます。 プロバイダーは常に実装して、`IOpenRowset`オブジェクト。 プロバイダーからの単純な行セットの生成に使用されます。 既定の行セット (たとえば、 `"select * from mytable"`) プロバイダーからです。  
  
 ウィザードでは、次の 3 つのセッション クラスも生成されます: `CMyProviderSessionColSchema`、 `CMyProviderSessionPTSchema`、および`CMyProviderSessionTRSchema`です。 スキーマ行セットでは、これらのセッションが使用されます。 スキーマ行セットでは、プロバイダー、コンシューマーがデータのクエリやフェッチを実行することがなく、コンシューマーにメタデータを返すことができるようにします。 メタデータのフェッチがプロバイダーの機能を検出するよりも高速に実行できます。  
  
 OLE DB 仕様では、する必要がありますを実装するプロバイダー、 **IDBSchemaRowset**インターフェイス サポート 3 つのスキーマ行セットの種類: **DBSCHEMA_COLUMNS**、 **DBSCHEMA_PROVIDER_TYPES**、および`DBSCHEMA_TABLES`です。 ウィザードでは、各スキーマ行セットの実装を生成します。 ウィザードによって生成された各クラスが含まれています、`Execute`メソッドです。 この`Execute`メソッドをサポートするどのテーブル、列、およびデータ型は、プロバイダーにデータを返すことができます。 通常、このデータは、コンパイル時に呼ばれます。  
  
## <a name="see-also"></a>関連項目  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)