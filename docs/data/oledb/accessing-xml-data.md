---
title: XML データへのアクセス
ms.date: 10/18/2018
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
ms.openlocfilehash: be4225003211449a98d3fbe5fd686b9b8058a651
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212278"
---
# <a name="accessing-xml-data"></a>XML データへのアクセス

データソースから XML データを取得する方法は2つあります。1つは[CStreamRowset](../../data/oledb/cstreamrowset-class.md)を使用し、もう1つは[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)を使用します。

|機能|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|転送されたデータの量|すべての列と行のデータを一度に取得します。|すべての列からデータを取得しますが、一度に1行だけを取得します。 `MoveNext`などのメソッドを使用して、行を移動する必要があります。|
|文字列の書式設定|SQL Server XML 文字列を書式設定してコンシューマーに送信します。|ネイティブ形式で行セットデータを取得し (プロバイダーが Unicode 文字列として送信することを要求します)、データを保持する文字列を XML 形式で作成します。|
|書式設定を制御する|SQL Server 2000 固有のプロパティを設定することによって、XML 文字列の書式設定を制御することができます。|生成された XML 文字列の形式を制御することはできません。|

`CStreamRowset` では、XML 形式でデータを取得するための全体的な効率が向上していますが、SQL Server 2000 でのみサポートされています。

## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset を使用した XML データの取得

`CCommand` または `CTable` 宣言で、行セットの種類として[CStreamRowset](../../data/oledb/cstreamrowset-class.md)を指定します。 これは、独自のアクセサーまたはアクセサーなしで使用できます。次に例を示します。

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

または

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

通常は、`CCommand::Open` (たとえば、`TRowset` クラスとして `CRowset` を指定) を呼び出すと、`IRowset` ポインターが取得されます。 `ICommand::Execute` は、`CRowset` オブジェクトの `m_spRowset` メンバーに格納されている `IRowset` ポインターを返します。 `MoveFirst`、`MoveNext`、`GetData` などのメソッドは、そのポインターを使用してデータを取得します。

これに対し、`CCommand::Open` を呼び出すと (ただし、`CStreamRowset` を `TRowset` クラスとして指定)、`ICommand::Execute` は `ISequentialStream` ポインターを返します。これは、 [CStreamRowset](../../data/oledb/cstreamrowset-class.md)の `m_spStream` データメンバーに格納されています。 次に、`Read` メソッドを使用して、XML 形式の (Unicode 文字列) データを取得します。 次に例を示します。

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000 では、XML の書式設定が行われ、すべての列と行セットのすべての行が1つの XML 文字列として返されます。

`Read` メソッドの使用例については、「[単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md)」の「 **XML サポートをコンシューマーに追加**する」を参照してください。

> [!NOTE]
> `CStreamRowset` を使用した XML サポートは SQL Server 2000 でのみ機能し、SQL Server 2000 (MDAC と共にインストールされる) の OLE DB プロバイダーが必要です。

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor を使用した XML データの取得

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)を使用すると、データストアのスキーマに関する知識がなくても、データソースのデータに文字列データとしてアクセスできます。 `CXMLAccessor` は `CDynamicStringAccessorW` のように機能しますが、前者はデータストアからアクセスされるすべてのデータを XML 形式の (タグ付けされた) データとして変換する点が異なります。 XML タグ名は、データストアの列名にできるだけ一致します。

他のアクセサークラスと同様に `CXMLAccessor` を使用して、`CCommand` または `CTable`にテンプレートパラメーターとして渡します。

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)を使用して、一度に1行ずつテーブルからデータを取得し、`MoveNext`などのメソッドを使用して行を移動します。次に例を示します。

```cpp
// Open data source, session, and rowset
hr = rs.MoveFirst();

while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
{
    CStringW strRowData;
    myCmd.GetXMLRowData(strRowData);

    printf_s( "%S\n", strRowData );

    hr = rs.MoveNext();
}
```

[Getxmlcolumndata](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)を使用して、列 (データ型) 情報を XML 形式の文字列データとして取得できます。

## <a name="see-also"></a>参照

[アクセサーの使用](../../data/oledb/using-accessors.md)
