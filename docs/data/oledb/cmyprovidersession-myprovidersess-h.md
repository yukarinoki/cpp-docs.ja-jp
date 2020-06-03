---
title: CCustomSession (CustomSess.H)
ms.date: 10/22/2018
f1_keywords:
- cmyprovidersession
- myprovidersess.h
- ccustomsession
- customsess.h
helpviewer_keywords:
- CMyProviderSession class in MyProviderSess.H
- OLE DB providers, wizard-generated files
- CCustomSession class in CustomSess.H
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
ms.openlocfilehash: 4775f21c1e0fa7666d24b4d6a55e099bc6ae55a2
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079757"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*カスタム*には、OLE DB session オブジェクトの宣言と実装が含まれています。 データソースオブジェクトは、セッションオブジェクトを作成し、コンシューマーとプロバイダー間のメッセージ交換を表します。 1つのデータソースに対して複数の同時セッションを開くことができます。 `CCustomSession` の継承リストを次に示します。

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSession
class ATL_NO_VTABLE CCustomSession :
   public CComObjectRootEx<CComSingleThreadModel>,
   public IGetDataSourceImpl<CCustomSession>,
   public IOpenRowsetImpl<CCustomSession>,
   public ISessionPropertiesImpl<CCustomSession>,
   public IObjectWithSiteSessionImpl<CCustomSession>,
   public IDBSchemaRowsetImpl<CCustomSession>,
   public IDBCreateCommandImpl<CCustomSession, CCustomCommand>
```

セッションオブジェクトは、`IGetDataSource`、`IOpenRowset`、`ISessionProperties`、および `IDBCreateCommand`から継承されます。 `IGetDataSource` インターフェイスを使用すると、セッションによって作成されたデータソースを取得できます。 これは、作成したデータソースからプロパティを取得する必要がある場合や、データソースが提供できるその他の情報を取得する必要がある場合に便利です。 `ISessionProperties` インターフェイスは、セッションのすべてのプロパティを処理します。 データベースの処理には、`IOpenRowset` インターフェイスと `IDBCreateCommand` インターフェイスが使用されます。 プロバイダーがコマンドをサポートしている場合は、`IDBCreateCommand` インターフェイスを実装します。 コマンドを実行できるコマンドオブジェクトを作成するために使用されます。 プロバイダーは、常に `IOpenRowset` オブジェクトを実装します。 プロバイダーから行セットを生成するために使用されます。 プロバイダーからの既定の行セット (`"select * from mytable"`など) です。

このウィザードでは、`CCustomSessionColSchema`、`CCustomSessionPTSchema`、`CCustomSessionTRSchema`という3つのセッションクラスも生成されます。 これらのセッションは、スキーマ行セットに使用されます。 プロバイダーは、スキーマ行セットを使用して、コンシューマーがクエリを実行したりデータをフェッチしたりすることなく、メタデータをコンシューマーに返すことができます。 メタデータのフェッチは、プロバイダーの機能を見つけるよりもはるかに高速です。

OLE DB の仕様では、`IDBSchemaRowset` インターフェイスを実装するプロバイダーが、DBSCHEMA_COLUMNS、DBSCHEMA_PROVIDER_TYPES、および DBSCHEMA_TABLES の3つのスキーマ行セットをサポートしている必要があります。 ウィザードでは、各スキーマ行セットの実装が生成されます。 ウィザードによって生成される各クラスには、`Execute` メソッドが含まれています。 この `Execute` メソッドでは、サポートするテーブル、列、およびデータ型に関するデータをプロバイダーに返すことができます。 このデータは、コンパイル時に認識されます。

## <a name="see-also"></a>参照

[プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)<br/>
