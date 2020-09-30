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
ms.openlocfilehash: 437f1d103420ec5727294894c02587c68cffbdda
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509131"
---
# <a name="accessing-xml-data"></a>XML データへのアクセス

データソースから XML データを取得する方法は2つあります。1つは [CStreamRowset](../../data/oledb/cstreamrowset-class.md) を使用し、もう1つは [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)を使用します。

|機能|CStreamRowset|CXMLAccessor|
|-------------------|-------------------|------------------|
|転送されたデータの量|すべての列と行のデータを一度に取得します。|すべての列からデータを取得しますが、一度に1行だけを取得します。 などのメソッドを使用して、行を移動する必要があり `MoveNext` ます。|
|文字列の書式設定|SQL Server XML 文字列を書式設定してコンシューマーに送信します。|ネイティブ形式で行セットデータを取得し (プロバイダーが Unicode 文字列として送信することを要求します)、データを保持する文字列を XML 形式で作成します。|
|書式設定を制御する|SQL Server 2000 固有のプロパティを設定することによって、XML 文字列の書式設定を制御することができます。|生成された XML 文字列の形式を制御することはできません。|

で `CStreamRowset` は、データを XML 形式で取得するための全体的な効率が向上していますが、SQL Server 2000 でのみサポートされています。

## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset を使用した XML データの取得

または宣言で、行セットの種類として [CStreamRowset](../../data/oledb/cstreamrowset-class.md) を指定し `CCommand` `CTable` ます。 これは、独自のアクセサーまたはアクセサーなしで使用できます。次に例を示します。

```cpp
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;
```

\- または -

```cpp
CCommand<CNoAccessor, CStreamRowset> myCmd;
```

通常、を呼び出すと `CCommand::Open` (たとえば、クラスとしてを指定した場合 `CRowset` `TRowset` )、ポインターが取得さ `IRowset` れます。 `ICommand::Execute``IRowset`オブジェクトのメンバーに格納されているポインターを返し `m_spRowset` `CRowset` ます。 、、などのメソッドは、 `MoveFirst` `MoveNext` そのポインターを使用してデータを `GetData` 取得します。

これに対して、を呼び出すと `CCommand::Open` (ただし、クラスとしてを指定した場合 `CStreamRowset` `TRowset` )、は `ICommand::Execute` `ISequentialStream` `m_spStream` [CStreamRowset](../../data/oledb/cstreamrowset-class.md)のデータメンバーに格納されているポインターを返します。 次に、メソッドを使用し `Read` て、XML 形式の (Unicode 文字列) データを取得します。 次に例を示します。

```cpp
myCmd.m_spStream->Read()
```

SQL Server 2000 では、XML の書式設定が行われ、すべての列と行セットのすべての行が1つの XML 文字列として返されます。

メソッドの使用例については `Read` 、「[単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md)」の「 **XML サポートをコンシューマーに追加**する」を参照してください。

> [!NOTE]
> を使用した XML サポートは `CStreamRowset` SQL Server 2000 でのみ動作し、SQL Server 2000 (MDAC と共にインストールされる) の OLE DB プロバイダーが必要です。

## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor を使用した XML データの取得

[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) を使用すると、データストアのスキーマに関する知識がなくても、データソースのデータに文字列データとしてアクセスできます。 `CXMLAccessor` と同様 `CDynamicStringAccessorW` に機能します。前者は、データストアからアクセスされるすべてのデータを XML 形式の (タグ付けされた) データとして変換する点が異なります。 XML タグ名は、データストアの列名にできるだけ一致します。

`CXMLAccessor`他のアクセサークラスと同様に、をまたはにテンプレートパラメーターとして渡し `CCommand` `CTable` ます。

```cpp
CTable<CXMLAccessor, CRowset> rs;
```

[GetXMLRowData](./cxmlaccessor-class.md#getxmlrowdata)を使用して一度に1行ずつテーブルからデータを取得し、などのメソッドを使用して行を移動し `MoveNext` ます。たとえば、次のようにします。

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

[Getxmlcolumndata](./cxmlaccessor-class.md#getxmlcolumndata)を使用して、列 (データ型) 情報を XML 形式の文字列データとして取得できます。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)
