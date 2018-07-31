---
title: CMyProviderSession (MyProviderSess.H) |Microsoft Docs
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
ms.openlocfilehash: 6bc3a9d377592b16c7e90cf0e75a6fba0eb00a64
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340128"
---
# <a name="cmyprovidersession-myprovidersessh"></a>CMyProviderSession (MyProviderSess.H)
MyProviderSess.H には、宣言と OLE DB セッション オブジェクトの実装が含まれています。 データ ソース オブジェクトは、セッション オブジェクトを作成し、コンシューマーとプロバイダー間のメッセージ交換を表します。 複数の同時セッションは、1 つのデータ ソース用に開かれることができます。 継承リストに`CMyProviderSession`に従います。  
  
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
  
 セッション オブジェクトから継承`IGetDataSource`、 `IOpenRowset`、 `ISessionProperties`、および`IDBCreateCommand`します。 `IGetDataSource`インターフェイスでは、セッションを作成したデータ ソースを取得できます。 これは、作成したデータ ソースまたはデータ ソースを提供するその他の情報のプロパティを取得する必要がある場合に便利です。 `ISessionProperties`インターフェイスは、セッションのすべてのプロパティを処理します。 `IOpenRowset`と`IDBCreateCommand`インターフェイスは、データベース処理のために使用します。 実装されているプロバイダーでは、コマンドをサポートするか、`IDBCreateCommand`インターフェイス。 コマンドを実行できるコマンド オブジェクトの作成に使用されます。 常に、プロバイダーを実装する、`IOpenRowset`オブジェクト。 プロバイダーからの単純な行セットの生成に使用されます。 既定の行セットが (たとえば、 `"select * from mytable"`) プロバイダーからです。  
  
 ウィザードでは、次の 3 つのセッション クラスも生成されます: `CMyProviderSessionColSchema`、 `CMyProviderSessionPTSchema`、および`CMyProviderSessionTRSchema`します。 スキーマ行セットでは、これらのセッションが使用されます。 スキーマ行セットには、プロバイダーがコンシューマーのデータのクエリまたはフェッチを実行することがなく、コンシューマーにメタデータを返すことができるようにします。 メタデータをフェッチは、プロバイダーの機能を検出するよりも高速に実行できます。  
  
 OLE DB 仕様では、する必要がありますを実装するプロバイダー、`IDBSchemaRowset`インターフェイス サポートの 3 つのスキーマ行セットの種類: DBSCHEMA_COLUMNS、DBSCHEMA_PROVIDER_TYPES、および DBSCHEMA_TABLES します。 ウィザードでは、各スキーマ行セットの実装を生成します。 ウィザードによって生成される各クラスが含まれています、`Execute`メソッド。 この`Execute`メソッドをサポートするどのテーブル、列、およびデータ型について、プロバイダーにデータを返すことができます。 このデータは通常、コンパイル時に呼ばれます。  
  
## <a name="see-also"></a>関連項目  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)