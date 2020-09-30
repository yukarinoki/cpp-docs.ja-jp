---
title: OLE DB プロバイダー テンプレートのアーキテクチャ
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB [C++], object model
- architecture [C++], OLE DB Provider
- OLE DB provider templates, object model
ms.assetid: 639304a3-f9e0-44dc-8d0c-0ebd2455b363
ms.openlocfilehash: 89e07f95853c3611b7cceaef3f247c220c630add
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509543"
---
# <a name="ole-db-provider-template-architecture"></a>OLE DB プロバイダー テンプレートのアーキテクチャ

## <a name="data-sources-and-sessions"></a>データ ソースとセッション

OLE DB プロバイダーのアーキテクチャには、データソースオブジェクトと1つ以上のセッションが含まれています。 データソースオブジェクトは、すべてのプロバイダーがインスタンス化する必要がある初期オブジェクトです。 コンシューマーアプリケーションがデータを必要とする場合は、プロバイダーを起動するためにデータソースオブジェクトを共同で作成します。 データソースオブジェクトは、 `IDBCreateSession` コンシューマーがデータソースオブジェクトに接続するために使用するセッションオブジェクトを (インターフェイスを使用して) 作成します。 ODBC プログラマは、データソースオブジェクトをと等価と見なすことができます。このオブジェクトは `HENV` 、と同じ `HDBC` です。

![プロバイダー アーキテクチャ](../../data/oledb/media/vc4twb1.gif "プロバイダー アーキテクチャ")

**OLE DB プロバイダーウィザード**によって作成されたソースファイルと共に、OLE DB テンプレートはデータソースオブジェクトを実装します。 セッションは、OLE DB に対応するオブジェクトです `TSession` 。

## <a name="mandatory-and-optional-interfaces"></a>必須および省略可能なインターフェイス

OLE DB プロバイダーテンプレートによって、すべての必要なインターフェイスの実装が事前に提供されます。 必須および省略可能なインターフェイスは、いくつかの種類のオブジェクトの OLE DB によって定義されます。

- [データ ソース](../../data/oledb/data-source-object-interfaces.md)

- [セッション](../../data/oledb/session-object-interfaces.md)

- [[行セット]](../../data/oledb/rowset-object-interfaces.md)

- [コマンド](../../data/oledb/command-object-interfaces.md)

- [トランザクション](../../data/oledb/transaction-object-interfaces.md)

OLE DB プロバイダーテンプレートには、行オブジェクトとストレージオブジェクトが実装されていません。

次の表に、 [OLE DB 2.6 SDK のドキュメント](/previous-versions/windows/desktop/ms722784(v=vs.85))に従って、上記のオブジェクトの必須インターフェイスと省略可能なインターフェイスを示します。

|コンポーネント|インターフェイス|コメント|
|---------------|---------------|-------------|
|[データソース](../../data/oledb/data-source-object-interfaces.md) ([CDataSource](../../data/oledb/cdatasource-class.md))|必ず `IDBCreateSession`<br /><br /> 必ず `IDBInitialize`<br /><br /> 必ず `IDBProperties`<br /><br /> 必ず `IPersist`<br /><br /> optional `IConnectionPointContainer`<br /><br /> optional `IDBAsynchStatus`<br /><br /> optional `IDBDataSourceAdmin`<br /><br /> optional `IDBInfo`<br /><br /> optional `IPersistFile`<br /><br /> optional `ISupportErrorInfo`|コンシューマーからプロバイダーへの接続。 オブジェクトは、ユーザー ID、パスワード、データソース名などの接続のプロパティを指定するために使用されます。 オブジェクトを使用して、データソース (作成、更新、削除、テーブルなど) を管理することもできます。|
|[セッション](../../data/oledb/session-object-interfaces.md) ([CSession](./cdataconnection-class.md#op_csession_amp))|必ず `IGetDataSource`<br /><br /> 必ず `IOpenRowset`<br /><br /> 必ず `ISessionProperties`<br /><br /> optional `IAlterIndex`<br /><br /> optional `IAlterTable`<br /><br /> optional `IBindResource`<br /><br /> optional `ICreateRow`<br /><br /> optional `IDBCreateCommand`<br /><br /> optional `IDBSchemaRowset`<br /><br /> optional `IIndexDefinition`<br /><br /> optional `ISupportErrorInfo`<br /><br /> optional `ITableCreation`<br /><br /> optional `ITableDefinition`<br /><br /> optional `ITableDefinitionWithConstraints`<br /><br /> optional `ITransaction`<br /><br /> optional `ITransactionJoin`<br /><br /> optional `ITransactionLocal`<br /><br /> optional `ITransactionObject`|セッションオブジェクトは、コンシューマーとプロバイダーの間の単一のメッセージ交換です。 これは、アクティブなセッションが多数存在する可能性があるという点で、ODBC に似て `HSTMT` います。<br /><br /> セッションオブジェクトは、OLE DB 機能にアクセスするための主要なリンクです。 コマンド、トランザクション、または行セットオブジェクトにアクセスするには、セッションオブジェクトを使用します。|
|[行セット](../../data/oledb/rowset-object-interfaces.md) ([CRowset](../../data/oledb/crowset-class.md))|必ず `IAccessor`<br /><br /> 必ず `IColumnsInfo`<br /><br /> 必ず `IConvertType`<br /><br /> 必ず `IRowset`<br /><br /> 必ず `IRowsetInfo`<br /><br /> optional `IChapteredRowset`<br /><br /> optional `IColumnsInfo2`<br /><br /> optional `IColumnsRowset`<br /><br /> optional `IConnectionPointContainer`<br /><br /> optional `IDBAsynchStatus`<br /><br /> optional `IGetRow`<br /><br /> optional `IRowsetChange`<br /><br /> optional `IRowsetChapterMember`<br /><br /> optional `IRowsetCurrentIndex`<br /><br /> optional `IRowsetFind`<br /><br /> optional `IRowsetIdentity`<br /><br /> optional `IRowsetIndex`<br /><br /> optional `IRowsetLocate`<br /><br /> optional `IRowsetRefresh`<br /><br /> optional `IRowsetScroll`<br /><br /> optional `IRowsetUpdate`<br /><br /> optional `IRowsetView`<br /><br /> optional `ISupportErrorInfo`<br /><br /> optional `IRowsetBookmark`|行セットオブジェクトは、データソースのデータです。 オブジェクトは、そのデータのバインドと、データに対する基本的な操作 (更新、フェッチ、移動など) に使用されます。 データを保持して操作するための行セットオブジェクトは、常に存在します。|
|[コマンド](../../data/oledb/command-object-interfaces.md) ([CCommand](ccommand-class.md))|必ず `IAccessor`<br /><br /> 必ず `IColumnsInfo`<br /><br /> 必ず `ICommand`<br /><br /> 必ず `ICommandProperties`<br /><br /> 必ず `ICommandText`<br /><br /> 必ず `IConvertType`<br /><br /> optional `IColumnsRowset`<br /><br /> optional `ICommandPersist`<br /><br /> optional `ICommandPrepare`<br /><br /> optional `ICommandWithParameters`<br /><br /> optional `ISupportErrorInfo`<br /><br /> optional `ICommandStream`|Command オブジェクトは、クエリなどのデータに対する操作を処理します。 パラメーター化またはパラメーター化されていないステートメントを処理できます。<br /><br /> Command オブジェクトは、パラメーターと出力列のバインドも処理します。 バインディングは、行セット内の列を取得する方法に関する情報を格納する構造体です。 序数、データ型、長さ、状態などの情報が含まれています。|
|[トランザクション](../../data/oledb/transaction-object-interfaces.md) (省略可能)|必ず `IConnectionPointContainer`<br /><br /> 必ず `ITransaction`<br /><br /> optional `ISupportErrorInfo`|トランザクションオブジェクトは、データソースのアトミックな作業単位を定義し、それらの作業単位が相互にどのように関連しているかを決定します。 このオブジェクトは、OLE DB プロバイダーテンプレートによって直接サポートされていません (つまり、独自のオブジェクトを作成します)。|

詳細については、次のトピックを参照してください。

- [プロパティマップ](../../data/oledb/property-maps.md)

- [ユーザーレコード](../../data/oledb/user-record.md)

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB インターフェイス](/previous-versions/windows/desktop/ms709709(v=vs.85))<br/>
