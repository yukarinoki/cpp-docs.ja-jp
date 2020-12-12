---
description: 詳細については、OLE DB コンシューマーテンプレートリファレンスを参照してください。
title: OLE DB コンシューマー テンプレート リファレンス
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
ms.openlocfilehash: e904237a7fbdef84c5f7f902ba352301a608b544
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286957"
---
# <a name="ole-db-consumer-templates-reference"></a>OLE DB コンシューマー テンプレート リファレンス

OLE DB コンシューマーテンプレートには、次のクラスが含まれています。 参照資料には、 [OLE DB コンシューマーテンプレートのマクロ](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)に関するトピックも含まれています。

## <a name="session-classes"></a>セッションクラス

[CDataConnection](../../data/oledb/cdataconnection-class.md)<br/>
データソースとの接続を管理します。 これは、クライアントを作成するのに便利なクラスです。これは、必要なオブジェクト (データソースとセッション) と、データソースに接続するときに必要な作業の一部をカプセル化するためです。

[CDataSource](../../data/oledb/cdatasource-class.md)<br/>
データソースへのプロバイダーによる接続を表す、OLE DB のデータソースオブジェクトに対応します。 オブジェクトによって表される1つ以上のデータベースセッションは、 `CSession` 1 つの接続で実行できます。

[CEnumerator](../../data/oledb/cenumerator-class.md)<br/>
使用可能なデータソースに関する行セット情報を取得する OLE DB 列挙子オブジェクトに対応します。

[CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)<br/>
によって、 `CEnumerator` 列挙子行セットからデータにアクセスするために使用されます。 この行セットは、現在の列挙子から参照できるデータソースと列挙子で構成されます。

[CSession](../../data/oledb/csession-class.md)<br/>
単一データベースアクセスセッションを表します。 1つ以上のセッションを各オブジェクトに関連付けることができ `CDataSource` ます。

## <a name="accessor-classes"></a>アクセサークラス

[CAccessor](../../data/oledb/caccessor-class.md)<br/>
データソースに静的にバインドされているレコードに使用されます。 データソースの構造がわかっている場合は、このアクセサークラスを使用します。

[CAccessorBase](../../data/oledb/caccessorbase-class.md)<br/>
すべてのアクセサークラスの基本クラスです。

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
行セットの列情報に基づいて実行時に作成できるアクセサー。 データソースの構造がわからない場合は、このクラスを使用してデータを取得します。

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
コマンドの種類が不明な場合に使用できるアクセサー。 プロバイダーがインターフェイスをサポートしている場合は、インターフェイスを呼び出すことによってパラメーター情報を取得し `ICommandWithParameters` ます。

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
では、データベースの基になる構造に関する知識がない場合に、データソースにアクセスできます。

[CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
と似て `CDynamicStringAccessor` いますが、このクラスは、データストアからアクセスされるデータを ANSI 文字列データとして要求する点が異なります。

[CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
に似 `CDynamicStringAccessor` ていますが、このクラスは、データストアからアクセスされるデータを UNICODE 文字列データとして要求する点が異なります。

[CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
列とコマンドパラメーターの両方を処理するメソッドを持つアクセサー。 このクラスでは、プロバイダーが型を変換できる限り、任意のデータ型を使用できます。

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
クラスがパラメーターまたは出力列をサポートしないようにする場合は、テンプレート引数としてを使用できます。

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)<br/>
に似 `CDynamicStringAccessor` ていますが、このクラスは、データストアからアクセスされるすべてのデータを XML 形式の (タグ付けされた) データとして変換する点が異なります。

## <a name="rowset-classes"></a>行セットクラス

[CAccessorRowset](../../data/oledb/caccessorrowset-class.md)<br/>
行セットとそれに関連付けられたアクセサーをカプセル化します。

[CArrayRowset](../../data/oledb/carrayrowset-class.md)<br/>
配列構文を使用して行セットの要素にアクセスするために使用します。

[CBulkRowset](../../data/oledb/cbulkrowset-class.md)<br/>
1回の呼び出しで複数の行ハンドルを取得することによって、行を一括でフェッチして操作するために使用されます。

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
コマンドが行セットを返さない場合は、テンプレート引数として使用できます。

[CRestrictions](../../data/oledb/crestrictions-class.md)<br/>
スキーマ行セットの制限を指定するために使用します。

[CRowset](../../data/oledb/crowset-class.md)<br/>
行セットデータを操作、設定、および取得するために使用します。

[CStreamRowset](../../data/oledb/cstreamrowset-class.md)<br/>
は、 `ISequentialStream` 行セットではなくオブジェクトを返します。その後、メソッドを使用して `Read` XML 形式でデータを取得します。 (SQL Server 2000 では書式設定が行われます。この機能は SQL Server 2000 でのみ機能することに注意してください)。

[IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)<br/>
のダミーの実装を提供し `IRowsetNotify` `IRowsetNotify` ます。メソッド、、およびの空の関数を使用し `OnFieldChange` `OnRowChange` `OnRowsetChange` ます。

[スキーマ行セットクラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)

OLE DB テンプレートには、OLE DB スキーマ行セットに対応する一連のクラスが用意されています。

## <a name="command-classes"></a>コマンドクラス

[CCommand](../../data/oledb/ccommand-class.md)<br/>
パラメーターベースの OLE DB コマンドを設定して実行するために使用します。 単純な行セットを開くだけの場合は、代わりにを使用 `CTable` します。

[CMultipleResults](../../data/oledb/cmultipleresults-class.md)<br/>
`CCommand`コマンドで複数の結果セットを処理する場合に、テンプレートのテンプレート引数として使用されます。

[CNoAccessor](../../data/oledb/cnoaccessor-class.md)<br/>
アクセサークラスの引数を受け取るやなど、テンプレートクラスのテンプレート引数として使用され `CCommand` `CTable` ます。 `CNoAccessor`クラスでパラメーターまたは出力列がサポートされないようにする場合は、を使用します。

[CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)<br/>
`CCommand`コマンドで1つの行セットを処理する場合に、テンプレートのテンプレート引数として使用されます。 `CNoMultipleResults` は、テンプレート引数の既定値です。

[CNoRowset](../../data/oledb/cnorowset-class.md)<br/>
のテンプレート引数として使用され `CCommand` `CTable` ます。コマンドまたはテーブルが行セットを返さない場合は、を使用します。

[CTable](../../data/oledb/ctable-class.md)<br/>
パラメーターを使用せずに単純な行セットにアクセスするために使用します。

## <a name="property-classes"></a>プロパティクラス

[CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)<br/>
コンシューマーがプロパティ情報を必要とするプロパティ Id の配列を渡すために使用します。 プロパティは、1つのプロパティセットに属します。

[CDBPropSet](../../data/oledb/cdbpropset-class.md)<br/>
プロバイダーのプロパティを設定するために使用します。

## <a name="bookmark-class"></a>Bookmark クラス

[CBookmark](../../data/oledb/cbookmark-class.md)<br/>
行セット内のデータにアクセスするためのインデックスとして使用されます。

## <a name="error-class"></a>Error クラス

[CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)<br/>
OLE DB エラー情報を取得するために使用します。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートのリファレンス](../../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB テンプレート](../../data/oledb/ole-db-templates.md)
