---
title: OLE DB コンシューマー テンプレート リファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc.templates.ole
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, classes
ms.assetid: cfc7f698-1a0e-4a09-a4d3-ccb99e6654fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b5b599a1c7a1b256cc9c56d772a15621beda286f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-consumer-templates-reference"></a>OLE DB コンシューマー テンプレート リファレンス
OLE DB コンシューマー テンプレートには、次のクラスが含まれています。 参考資料には、上のトピックにはもが含まれています、 [OLE DB コンシューマー テンプレート用マクロ](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)です。  
  
## <a name="session-classes"></a>セッション クラス  
 [CDataConnection](../../data/oledb/cdataconnection-class.md)  
 データ ソースとの接続を管理します。 これは、必要なオブジェクト (データ ソースとセッション) とデータ ソースに接続する場合に行う必要がある作業の一部をカプセル化するためにクライアントを作成するために役立ちますクラスです。  
  
 [CDataSource](../../data/oledb/cdatasource-class.md)  
 データ ソースへのプロバイダーを経由して接続を表す、OLE DB データ ソース オブジェクトに対応します。 1 つまたは複数データベースのセッション、によって表される各、`CSession`オブジェクト、1 つの接続で実行できます。  
  
 [CEnumerator](../../data/oledb/cenumerator-class.md)  
 使用できるデータ ソースの行セット情報を取得する OLE DB 列挙子オブジェクトに対応します。  
  
 [CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)  
 によって使用される`CEnumerator`列挙子の行セットからデータにアクセスします。 この行セットは、データ ソースと現在の列挙子から見えるの列挙子で構成されます。  
  
 [CSession](../../data/oledb/csession-class.md)  
 1 つのデータベース アクセスのセッションを表します。 1 つまたは複数のセッションに関連付けられる各`CDataSource`オブジェクト。  
  
## <a name="accessor-classes"></a>アクセサー クラス  
 [CAccessor](../../data/oledb/caccessor-class.md)  
 データ ソースに静的にバインドされているレコードに使用されます。 データ ソースの構造がわかっている場合に、このアクセサー クラスを使用します。  
  
 [CAccessorBase](../../data/oledb/caccessorbase-class.md)  
 すべてのアクセサー クラスの基本クラス。  
  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
 行セットの列の情報に基づいて、実行時に作成できるアクセサー。 このクラスを使用して、データ ソースの構造がわからない場合は、データを取得します。  
  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)  
 コマンドの種類が不明な場合に使用できるアクセサー。 呼び出してパラメーター情報を取得、`ICommandWithParameters`プロバイダー インターフェイスをサポートする場合は、インターフェイスです。  
  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)  
 データベースの基になる構造に関する知識があるない場合にデータ ソースにアクセスできます。  
  
 [CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)  
 ような`CDynamicStringAccessor`ことを除き、このクラスは、ANSI 文字列データとしてデータ ストアからデータを要求します。  
  
 [CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)  
 ような`CDynamicStringAccessor`ことを除き、このクラスは、UNICODE 文字列データとしてデータ ストアからデータを要求します。  
  
 [CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
 コマンドのパラメーターと列の両方を処理するメソッドを持つアクセサー。 このクラスには、プロバイダーは、型を変換できる限り、任意のデータ型を使用できます。  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 出力列やパラメーターをサポートするクラスしたくない場合に、テンプレート引数として使用できます。  
  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)  
 ような`CDynamicStringAccessor`ことを除き、このクラスは、(タグあり) のデータを XML 形式として、データ ストアからアクセスされるすべてのデータを変換します。  
  
## <a name="rowset-classes"></a>行セット クラス  
 [CAccessorRowset](../../data/oledb/caccessorrowset-class.md)  
 行セットとその関連するアクセサーをカプセル化します。  
  
 [CArrayRowset](../../data/oledb/carrayrowset-class.md)  
 配列の構文を使用して行セットの要素にアクセスするために使用します。  
  
 [CBulkRowset](../../data/oledb/cbulkrowset-class.md)  
 フェッチし、1 回の呼び出しで複数の行ハンドルを取得することにより一括内の行を操作するために使用します。  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 コマンドが行セットを返さない場合は、テンプレート引数として使用できます。  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)  
 スキーマ行セットの制限を指定するために使用します。  
  
 [CRowset](../../data/oledb/crowset-class.md)  
 操作、セット、および行セットのデータを取得するために使用します。  
  
 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)  
 返します、`ISequentialStream`行セットではなくオブジェクト; を使用して、**読み取り**XML 形式でデータを取得します。 (SQL Server 2000 では、書式設定はこの機能が SQL Server 2000 でのみ動作ことに注意してください。)  
  
 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)  
 ダミー実装を提供`IRowsetNotify`、用の空の関数で、`IRowsetNotify`メソッド`OnFieldChange`、 `OnRowChange`、および`OnRowsetChange`です。  
  
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)  
  
 OLE DB テンプレートは、OLE DB スキーマ行セットに対応するクラスのセットを提供します。  
  
## <a name="command-classes"></a>コマンド クラス  
 [CCommand](../../data/oledb/ccommand-class.md)  
 設定し、パラメーター ベースの OLE DB コマンドを実行するために使用します。 単純な行セットを開くだけで、使用`CTable`代わりにします。  
  
 [CMultipleResults](../../data/oledb/cmultipleresults-class.md)  
 テンプレート引数として使用される、`CCommand`テンプレートを複数の結果セットを処理するコマンドを追加するときにします。  
  
 [CNoAccessor](../../data/oledb/cnoaccessor-class.md)  
 テンプレート クラスのテンプレート引数として使用される`CCommand`と`CTable`、アクセサー クラスの引数を受け取る。 使用して`CNoAccessor`出力列やパラメーターをサポートするクラスしたくない場合。  
  
 [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md)  
 テンプレート引数として使用される、`CCommand`テンプレートを 1 つの行セットを処理するコマンドを追加するときにします。 `CNoMultipleResults` テンプレート引数の既定値です。  
  
 [CNoRowset](../../data/oledb/cnorowset-class.md)  
 テンプレート引数として使用される`CCommand`または`CTable`コマンドまたはテーブルに行セットが返されない場合は。  
  
 [CTable](../../data/oledb/ctable-class.md)  
 パラメーターなしの単純な行セットにアクセスするために使用します。  
  
## <a name="property-classes"></a>プロパティ クラス  
 [CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)  
 コンシューマーがプロパティの情報を対象のプロパティ Id の配列を渡すために使用します。 プロパティは、1 つのプロパティ セットに属します。  
  
 [CDBPropSet](../../data/oledb/cdbpropset-class.md)  
 プロバイダーのプロパティを設定するために使用します。  
  
## <a name="bookmark-class"></a>ブックマーク クラス  
 [CBookmark](../../data/oledb/cbookmark-class.md)  
 行セット内のデータにアクセスするためのインデックスとして使用されます。  
  
## <a name="error-class"></a>エラー: クラス  
 [CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)  
 OLE DB エラー情報を取得するために使用します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート リファレンス](../../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB テンプレート](../../data/oledb/ole-db-templates.md)