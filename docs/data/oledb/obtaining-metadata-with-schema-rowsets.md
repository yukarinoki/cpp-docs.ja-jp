---
title: スキーマ行セットのメタデータの取得 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: da5a715be2ac6dc94ace25ee98781d2e9a4c5f8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33114735"
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>スキーマ行セットを使用したメタデータの取得
プロバイダー、行セット、テーブル、列、またはその他のデータベース情報に関する情報を行セットを開かずに取得することが必要な場合があります。 データベース構造に関するデータはメタデータと呼ばれます。メタデータはさまざまな方法で取得できます。 1 つは、スキーマ行セットを使用する方法です。  
  
 スキーマ情報を取得するクラスのセットを提供する OLE DB テンプレートこれらのクラスが定義済みのスキーマ行セットを作成しに記載されて[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)です。  
  
> [!NOTE]
>  OLAP を使用していて、行セットの一部がスキーマ行セット クラスでサポートされていない場合 (列数が変数の場合など) は、`CManualAccessor` または `CDynamicAccessor` の使用を検討する必要があります。 列をスクロールし、case ステートメントを使用して、各列で可能なデータ型を処理できます。  
  
## <a name="catalogschema-model"></a>カタログ/スキーマ モデル  
 ANSI SQL はデータ ストアのカタログ/スキーマ モデルを定義しています。OLE DB はこのモデルを使用します。 このモデルでは、カタログ (データベース) にスキーマが含まれ、スキーマにテーブルが含まれます。  
  
-   **カタログ**カタログはデータベースに別の名前。 これは、関連するスキーマのコレクションです。 指定したデータ ソースに属するカタログ (データベース) の一覧を表示する[CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md)です。 多くのデータベースにはカタログが 1 つしかないため、メタデータは、単純にスキーマ情報と呼ばれることがあります。  
  
-   **スキーマ**スキーマが所有または、特定のユーザーによって作成されたデータベース オブジェクトのコレクション。 特定のユーザーが所有するスキーマの一覧を表示する[CSchemata](../../data/oledb/cschemata-cschematainfo.md)です。  
  
     スキーマと所有者は Microsoft SQL Server と ODBC 2.x の用語で (たとえば、dbo は一般的なスキーマ名)。 また、SQL Server は、一連のテーブルでメタデータを格納します。 1 つのテーブルには、すべてのテーブルの一覧が含まれています。 と別のテーブルには、すべての列の一覧が含まれています。 Microsoft Access データベースにはスキーマに相当するものはありません。  
  
-   **テーブル**テーブルは、特定の順序で並べられた列のコレクション。 特定のカタログ (データベース) とそれらのテーブルに関する情報で定義されているテーブルの一覧を表示する[CTables](../../data/oledb/ctables-ctableinfo.md))。  
  
## <a name="restrictions"></a>制約  
 スキーマ情報を照会するときに、制約を使用して、目的の情報の種類を指定できます。 制約は、クエリのフィルターまたは修飾子として考えることができます。 たとえば、次のクエリについて考えます。  
  
```  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 このクエリでは、`l_name` が制約です。 これは制約が 1 つしかない単純な例です。スキーマ行セット クラスは複数の制約をサポートします。  
  
 [スキーマ行セット typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)他の行セットと同じように、スキーマ行セットをインスタンス化して開くことによってアクセスできるように、すべての OLE DB スキーマ行セットをカプセル化します。 たとえば、typedef クラス[CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)として定義されます。  
  
```  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md)クラスは、制約がサポートを提供します。 スキーマ行セットのインスタンスを作成した後で呼び出す[crestrictions::open](../../data/oledb/crestrictions-open.md)です。 このメソッドは、指定された制約に基づいて結果セットを返します。  
  
 制限を指定するを参照してください[付録 B スキーマ行セット](http://go.microsoft.com/fwlink/p/?linkid=64681)使用している行セットを検索します。 たとえば、 **CColumns**に対応する、 [COLUMNS 行セット](http://go.microsoft.com/fwlink/p/?linkid=64682); そのトピックには、COLUMNS 行セットの制限列が一覧表示: TABLE_CATALOG、table_schema、TABLE_NAME、COLUMN_NAME です。 制約を指定するときは、この順序に従う必要があります。  
  
 そのため、たとえば、テーブル名で制限する場合は、TABLE_NAME が 3 番目の制限列に注意してくださいおよびを呼び出す**開く**、次の例で示すように、3 番目の制限パラメーターとして目的のテーブル名を指定します。  
  
#### <a name="to-use-schema-rowsets"></a>スキーマ行セットを使用するには  
  
1.  Atldbsch.h ヘッダー ファイルをインクルードする必要があります (コンシューマー サポートでも Atldbcli.h が必要です)。  
  
2.  コンシューマーまたはドキュメントのヘッダー ファイル内のスキーマ行セット オブジェクトをインスタンス化します。 テーブルの情報を実行する場合に、宣言、 **CTables**オブジェクト以外の列情報を実行する場合に、宣言、 **CColumns**オブジェクト。 authors テーブルの列を取得する方法の例を次に示します。  
  
    ```  
    CDataSource ds;  
    ds.Open();  
    CSession ss;  
    ss.Open();  
    CColumns ColumnSchemaRowset;  
    // TABLE_NAME is the third restriction column, so  
    // specify "authors" as the third restriction parameter:  
    hr = ColumnSchemaRowset.Open(ss, NULL, NULL, "authors");  
    hr = ColumnSchemaRowset.MoveFirst();  
    while (hr == S_OK)  
    {  
       hr = ColumnSchemaRowset.MoveNext();  
    }  
    ```  
  
3.  情報をフェッチするには、スキーマ行セット オブジェクトの適切なデータ メンバーにアクセスします。たとえば、`ColumnSchemaRowset.m_szColumnName` にアクセスします。 これは COLUMN_NAME に対応します。 各データ メンバーに対応する OLE DB 列を表示するには、次を参照してください。 [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md)です。  
  
 OLE DB テンプレートのスキーマ行セットの参照の typedef クラスが提供される (を参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md))。  
  
 制限列を含む、OLE DB スキーマ行セットの詳細については、次を参照してください。[付録 b スキーマ行セット](http://go.microsoft.com/fwlink/p/?linkid=64681)OLE DB プログラマーズ リファレンスです。  
  
 スキーマ行セット クラスを使用する方法のより複雑な例については、次を参照してください。、 [CatDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046)と[DBViewer](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)サンプルです。  
  
 プロバイダーのスキーマ行セットのサポートについては、次を参照してください。[スキーマ行セットのサポート](../../data/oledb/supporting-schema-rowsets.md)です。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)