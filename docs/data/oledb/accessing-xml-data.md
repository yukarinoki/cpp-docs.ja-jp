---
title: XML データにアクセスする |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data access [C++], XML data
- XML [C++], accessing data
- CXMLAccessor class, retrieving XML data
- data [C++], XML data access
- rowsets [C++], retrieving XML data
- CStreamRowset class, retrieving XML data
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f3abe00adee2a88d0414d688984232422a5bcfc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-xml-data"></a>XML データへのアクセス
データ ソースから XML データを取得する 2 つの異なるメソッドがある: いずれかを使用して[CStreamRowset](../../data/oledb/cstreamrowset-class.md)およびその他の用途[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)です。  
  
|機能|CStreamRowset|CXMLAccessor|  
|-------------------|-------------------|------------------|  
|転送されるデータ量|1 回にすべての列と行からデータを取得します。|すべての列からデータが一度に 1 つだけの行を取得します。 などのメソッドを使用して行を移動する必要があります`MoveNext`です。|  
|文字列の書式設定|SQL Server では、XML 文字列を書式設定され、コンシューマーに送信されます。|ネイティブ形式 (プロバイダーが Unicode 文字列として送信する要求) の行セットのデータを取得し、次の XML 形式のデータを含む文字列を構築します。|  
|書式設定の制御します。|SQL Server 2000 に固有のプロパティを設定して、XML 文字列を書式設定する方法を制御の程度があります。|あるない生成された XML 文字列の形式を制御します。|  
  
 中に`CStreamRowset`SQL Server 2000 でのみサポートされている XML 形式でデータの取得の詳細の全体的な効率的な方法を提供します。  
  
## <a name="retrieving-xml-data-using-cstreamrowset"></a>CStreamRowset を使用して XML データを取得します。  
 指定した[CStreamRowset](../../data/oledb/cstreamrowset-class.md)で行セットの種類として、`CCommand`または`CTable`宣言します。 またはと共に使用して、独自のアクセサー アクセサーはありません、たとえば。  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 - または -  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 通常どおり呼び出す`CCommand::Open`(指定すると、たとえば、`CRowset`として、`TRowset`クラス)、取得、`IRowset`ポインター。 `ICommand::Execute` 返します、`IRowset`に格納されているポインター、`m_spRowset`のメンバー、`CRowset`オブジェクト。 などのメソッド`MoveFirst`、 `MoveNext`、および`GetData`ポインターを使用してデータを取得します。  
  
 これに対し、呼び出す`CCommand::Open`(指定しますが、`CStreamRowset`として、`TRowset`クラス)、`ICommand::Execute`を返します、`ISequentialStream`に格納されているポインター、`m_spStream`データ メンバーの[CStreamRowset](../../data/oledb/cstreamrowset-class.md). 使用して、`Read`の XML 形式 (Unicode 文字列) のデータを取得します。 例えば:  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000 では、XML 書式設定を実行し、すべての列と 1 つの XML 文字列として、行セットのすべての行を返します。  
  
 使用例については、`Read`メソッド、「XML コンシューマー サポートの追加する」を参照してください[単純なコンシューマーを実装する](../../data/oledb/implementing-a-simple-consumer.md)です。  
  
> [!NOTE]
>  XML の使用をサポート`CStreamRowset`SQL Server 2000 でのみ動作し、(MDAC と共にインストールされた) SQL Server 2000 の OLE DB プロバイダーがある必要があります。  
  
## <a name="retrieving-xml-data-using-cxmlaccessor"></a>CXMLAccessor を使用して XML データを取得します。  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)データ ストアのスキーマの知識があるない場合に文字列データとしてデータ ソースからデータにアクセスすることができます。 `CXMLAccessor` 同様に動作`CDynamicStringAccessorW`前者 (タグあり) のデータを XML 形式として、データ ストアからアクセスされるすべてのデータを変換する点が異なります。 XML タグ名は、データ ストアの列名をできるだけ一致します。  
  
 使用して`CXMLAccessor`、他のアクセサー クラスと、同様にテンプレート パラメーターとして渡す`CCommand`または`CTable`:  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 使用して[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md) 、一度に 1 行のテーブルからデータを取得しなどのメソッドを使用して行を移動する`MoveNext`、例を示します。  
  
```  
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
  
 使用することができます[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) XML 形式の文字列データとして列 (データ型) の情報を取得します。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)