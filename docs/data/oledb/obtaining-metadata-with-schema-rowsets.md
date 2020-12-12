---
description: '詳細情報: スキーマ行セットを使用したメタデータの取得'
title: スキーマ行セットを使用したメタデータの取得
ms.date: 10/24/2018
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
ms.openlocfilehash: 9692b27de6d949e23b3868b2c55b79b685d6b5fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317182"
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>スキーマ行セットを使用したメタデータの取得

プロバイダー、行セット、テーブル、列、またはその他のデータベース情報に関する情報を行セットを開かずに取得することが必要な場合があります。 データベース構造に関するデータはメタデータと呼ばれます。メタデータはさまざまな方法で取得できます。 1 つは、スキーマ行セットを使用する方法です。

OLE DB テンプレートは、スキーマ情報を取得するためのクラスのセットを提供します。これらのクラスは、定義済みのスキーマ行セットを作成し、 [スキーマ行セットクラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)に一覧表示します。

> [!NOTE]
> OLAP を使用していて、行セットの一部がスキーマ行セット クラスでサポートされていない場合 (列数が変数の場合など) は、`CManualAccessor` または `CDynamicAccessor` の使用を検討する必要があります。 列をスクロールし、case ステートメントを使用して、各列で可能なデータ型を処理できます。

## <a name="catalogschema-model"></a>カタログ/スキーマ モデル

ANSI SQL はデータ ストアのカタログ/スキーマ モデルを定義しています。OLE DB はこのモデルを使用します。 このモデルでは、カタログ (データベース) にスキーマがあり、スキーマにテーブルがあります。

- **カタログ** カタログは、データベースの別の名前です。 これは、関連するスキーマのコレクションです。 特定のデータソースに属するカタログ (データベース) を一覧表示するには、 [Ccatalog](./schema-rowset-classes-and-typedef-classes.md#catalog)を使用します。 多くのデータベースにはカタログが1つしかないため、メタデータはスキーマ情報と呼ばれることがあります。

- **スキーマ** スキーマは、特定のユーザーによって所有または作成されているデータベースオブジェクトのコレクションです。 特定のユーザーが所有するスキーマを一覧表示するには、 [CSchemata](./schema-rowset-classes-and-typedef-classes.md#schemata)を使用します。

   Microsoft SQL Server と ODBC 2.x の用語では、スキーマは所有者です。たとえば、dbo は一般的なスキーマ名です。 また、SQL Server では、テーブルのセットにメタデータを格納します。あるテーブルにはすべてのテーブルの一覧が含まれ、別のテーブルにはすべての列の一覧が含まれます。 Microsoft Access データベースのスキーマに相当するものはありません。

- **テーブル** テーブルは、特定の順序で配置された列のコレクションです。 特定のカタログ (データベース) で定義されているテーブルを一覧表示し、それらのテーブルに関する情報を表示するには、 [Ctables](./schema-rowset-classes-and-typedef-classes.md#table)を使用します。

## <a name="restrictions"></a>制限

スキーマ情報を照会するときに、制限を使用して、関心のある情報の種類を指定できます。 制約は、クエリのフィルターまたは修飾子として考えることができます。 たとえば、次のクエリについて考えます。

```sql
SELECT * FROM authors WHERE l_name = 'pivo'
```

このクエリでは、`l_name` が制約です。 これは、制限が1つだけの単純な例です。スキーマ行セットクラスでは、いくつかの制限がサポートされています。

[スキーマ行セット typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)は、すべての OLE DB スキーマ行セットをカプセル化して、他の行セットと同様に、スキーマ行セットにアクセスできるようにします。そのために、インスタンス化して開きます。 たとえば、typedef クラス [Ccolumns](./schema-rowset-classes-and-typedef-classes.md#columns) は次のように定義されます。

```cpp
CRestrictions<CAccessor<CColumnsInfo>
```

[CRestrictions](../../data/oledb/crestrictions-class.md)クラスは、制限のサポートを提供します。 スキーマ行セットのインスタンスを作成した後、 [CRestrictions:: Open](./crestrictions-class.md#open)を呼び出します。 このメソッドは、指定された制約に基づいて結果セットを返します。

制限を指定するには、 [「付録 B: スキーマ行セット](/previous-versions/windows/desktop/ms712921(v=vs.85)) 」を参照し、使用している行セットを参照してください。 たとえば、は `CColumns` [Columns 行セット](/previous-versions/windows/desktop/ms723052(v=vs.85))に対応します。このトピックでは、columns 行セットの制限列 TABLE_CATALOG、TABLE_SCHEMA、TABLE_NAME、COLUMN_NAME を示します。 制約を指定するときは、この順序に従う必要があります。

たとえば、テーブル名で制限する場合は、次の例に示すように、TABLE_NAME が3番目の制限列であり、を呼び出して、 `Open` 必要なテーブル名を3番目の制限パラメーターとして指定します。

### <a name="to-use-schema-rowsets"></a>スキーマ行セットを使用するには

1. ヘッダーファイルをインクルードし `Atldbsch.h` ます ( `Atldbcli.h` コンシューマーサポートにも必要です)。

1. コンシューマーまたはドキュメントのヘッダー ファイル内のスキーマ行セット オブジェクトをインスタンス化します。 テーブル情報が必要な場合は、オブジェクトを宣言します。 `CTables` 列情報が必要な場合は、オブジェクトを宣言し `CColumns` ます。 authors テーブルの列を取得する方法の例を次に示します。

    ```cpp
    CDataSource ds;
    ds.Open();
    CSession ss;
    ss.Open(ds);
    CColumns columnSchemaRowset;
    // TABLE_NAME is the third restriction column, so
    // specify "authors" as the third restriction parameter:
    HRESULT hr = columnSchemaRowset.Open(ss, NULL, NULL, L"authors");
    hr = columnSchemaRowset.MoveFirst();
    while (hr == S_OK)
    {
       hr = columnSchemaRowset.MoveNext();
    }
    ```

1. 情報をフェッチするには、スキーマ行セット オブジェクトの適切なデータ メンバーにアクセスします。たとえば、`ColumnSchemaRowset.m_szColumnName` にアクセスします。 このデータメンバーは COLUMN_NAME に対応しています。 各データメンバーが対応する OLE DB 列については、「 [Ccolumns](./schema-rowset-classes-and-typedef-classes.md#columns)」を参照してください。

スキーマ行セットのリファレンスについては、OLE DB テンプレートに用意されている typedef クラス (「 [スキーマ行セットクラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)」を参照してください)。

制限列を含む OLE DB スキーマ行セットの詳細については、 **OLE DB プログラマーリファレンス** の [「付録 B: スキーマ行セット](/previous-versions/windows/desktop/ms712921(v=vs.85))」を参照してください。

スキーマ行セットクラスの使用方法のより複雑な例については、 [CatDB](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) と [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) のサンプルを参照してください。

スキーマ行セットのプロバイダーサポートの詳細については、「 [スキーマ行セット](../../data/oledb/supporting-schema-rowsets.md)のサポート」を参照してください。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)
