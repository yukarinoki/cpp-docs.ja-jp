---
description: 詳細については、CCustomSession (Customsession. H) を参照してください。
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
ms.openlocfilehash: 0c090e01b5cef1bc0fccad8a1c23948fb9ea09b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170426"
---
# <a name="ccustomsession-customsessh"></a>CCustomSession (CustomSess.H)

*カスタム* には、OLE DB session オブジェクトの宣言と実装が含まれています。 データソースオブジェクトは、セッションオブジェクトを作成し、コンシューマーとプロバイダー間のメッセージ交換を表します。 1つのデータソースに対して複数の同時セッションを開くことができます。 の継承リストを `CCustomSession` 次に示します。

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

セッションオブジェクトは、、、、およびから継承され `IGetDataSource` `IOpenRowset` `ISessionProperties` `IDBCreateCommand` ます。 `IGetDataSource`インターフェイスを使用すると、セッションによって作成されたデータソースを取得できます。 これは、作成したデータソースからプロパティを取得する必要がある場合や、データソースが提供できるその他の情報を取得する必要がある場合に便利です。 インターフェイスは、 `ISessionProperties` セッションのすべてのプロパティを処理します。 `IOpenRowset`および `IDBCreateCommand` インターフェイスは、データベースの動作を実行するために使用されます。 プロバイダーがコマンドをサポートしている場合は、インターフェイスを実装し `IDBCreateCommand` ます。 コマンドを実行できるコマンドオブジェクトを作成するために使用されます。 プロバイダーは、常にオブジェクトを実装し `IOpenRowset` ます。 プロバイダーから行セットを生成するために使用されます。 プロバイダーからの既定の行セット (たとえば、 `"select * from mytable"` ) です。

このウィザードでは `CCustomSessionColSchema` 、、、およびという3つのセッションクラスも生成され `CCustomSessionPTSchema` `CCustomSessionTRSchema` ます。 これらのセッションは、スキーマ行セットに使用されます。 プロバイダーは、スキーマ行セットを使用して、コンシューマーがクエリを実行したりデータをフェッチしたりすることなく、メタデータをコンシューマーに返すことができます。 メタデータのフェッチは、プロバイダーの機能を見つけるよりもはるかに高速です。

OLE DB 仕様では、インターフェイスを実装するプロバイダーは `IDBSchemaRowset` 、DBSCHEMA_COLUMNS、DBSCHEMA_PROVIDER_TYPES、および DBSCHEMA_TABLES の3種類のスキーマ行セットをサポートしている必要があります。 ウィザードでは、各スキーマ行セットの実装が生成されます。 ウィザードによって生成される各クラスには、メソッドが含まれてい `Execute` ます。 このメソッドでは、 `Execute` サポートするテーブル、列、およびデータ型について、プロバイダーにデータを返すことができます。 このデータは、コンパイル時に認識されます。

## <a name="see-also"></a>関連項目

[プロバイダー Wizard-Generated ファイル](../../data/oledb/provider-wizard-generated-files.md)<br/>
