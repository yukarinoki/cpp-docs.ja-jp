---
title: コンシューマー ウィザードで生成されたクラス
ms.date: 10/17/2018
helpviewer_keywords:
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- command classes in OLE DB consumer
- classes [C++], OLE DB Consumer Wizard-generated
- consumer wizard-generated classes and methods
- user record classes in OLE DB consumer
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
ms.openlocfilehash: 2ebc2094ba7f12087de51119a134e2ef65ef92d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641139"
---
# <a name="consumer-wizard-generated-classes"></a>コンシューマー ウィザードで生成されたクラス

使用すると、 **ATL OLE DB コンシューマー ウィザード**OLE DB テンプレートと OLE DB 属性を使用する選択肢があるコンシューマーを生成します。 どちらの場合も、ウィザードによってコマンド クラスとユーザー レコード クラスが生成されます。 コマンド クラスには、ウィザードで指定したデータ ソースと行セットを開くためのコードが含まれています。 ユーザー レコード クラスには、選択したデータベース テーブルの列マップが含まれています。 ただし、生成されるコードはそれぞれ異なります。

- テンプレート コンシューマーを選択した場合、ウィザードはコマンド クラスとユーザー レコード クラスを生成します。 コマンド クラスに入力した名前になります、**クラス**ボックス、ウィザードに (たとえば、 `CProducts`)、ユーザー レコード クラスは、フォームの名前が"*ClassName*アクセサー"(たとえば、`CProductsAccessor`). どちらのクラスも、コンシューマーのヘッダー ファイルに格納されます。

- 属性コンシューマーを選択した場合は、ユーザー レコード クラスのフォームは、"_*ClassName*Accessor" の名前で挿入されます。 つまり、ことができます、テキスト エディターで、コマンド クラスのみを表示するにはユーザー レコード クラスは、挿入されたコードとしてのみ表示できます。 挿入されたコードを表示する方法については、「 [挿入されたコードのデバッグ](/visualstudio/debugger/how-to-debug-injected-code)」を参照してください。

次の例で作成したコマンド クラスを使用して、`Products`のテーブル、`Northwind`コマンド クラスとユーザー レコード クラスのコンシューマーのウィザードで生成されたコードを示すためにデータベース。

## <a name="templated-user-record-classes"></a>テンプレート化されたユーザー レコード クラス

OLE DB 属性ではなく、OLE DB テンプレートを使用して OLE DB コンシューマーを作成する場合、ウィザードは、このセクションで説明したコードを生成します。

### <a name="column-data-members"></a>列データ メンバー

ユーザー レコード クラスの最初の部分には、データ メンバーの宣言とそれぞれのデータ バインド列のステータスや長さデータ メンバーが含まれます。 これらのデータ メンバーについては、「 [ウィザードで生成されたアクセサーのフィールド ステータスのデータ メンバー](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)」を参照してください。

> [!NOTE]
> ユーザー レコード クラスを変更するか、独自のコンシューマーを作成する場合、データ変数は、ステータス変数と長さ変数よりも前に記述する必要があります。

> [!NOTE]
> ATL OLE DB コンシューマー ウィザードを使用して、`DB_NUMERIC`数値データ型のバインド先の型。 これを使用していた`DBTYPE_VARNUMERIC`(される形式は、`DB_VARNUMERIC`入力は、Oledb.h を参照してください)。 コンシューマーの作成には、ウィザードを使用しない場合は、使用することをお勧め`DB_NUMERIC`します。

```cpp
// Products.H : Declaration of the CProducts class

class CProductsAccessor
{
public:
   // Column data members:
   LONG m_ProductID;
   TCHAR m_ProductName[41];
   LONG m_SupplierID;
   LONG m_CategoryID;
   TCHAR m_QuantityPerUnit[21];
   CURRENCY m_UnitPrice;
   SHORT m_UnitsInStock;
   SHORT m_UnitsOnOrder;
   SHORT m_ReorderLevel;
   VARIANT_BOOL m_Discontinued;

   // Column status data members:
   DBSTATUS m_dwProductIDStatus;
   DBSTATUS m_dwProductNameStatus;
   DBSTATUS m_dwSupplierIDStatus;
   DBSTATUS m_dwCategoryIDStatus;
   DBSTATUS m_dwQuantityPerUnitStatus;
   DBSTATUS m_dwUnitPriceStatus;
   DBSTATUS m_dwUnitsInStockStatus;
   DBSTATUS m_dwUnitsOnOrderStatus;
   DBSTATUS m_dwReorderLevelStatus;
   DBSTATUS m_dwDiscontinuedStatus;

   // Column length data members:
   DBLENGTH m_dwProductIDLength;
   DBLENGTH m_dwProductNameLength;
   DBLENGTH m_dwSupplierIDLength;
   DBLENGTH m_dwCategoryIDLength;
   DBLENGTH m_dwQuantityPerUnitLength;
   DBLENGTH m_dwUnitPriceLength;
   DBLENGTH m_dwUnitsInStockLength;
   DBLENGTH m_dwUnitsOnOrderLength;
   DBLENGTH m_dwReorderLevelLength;
   DBLENGTH m_dwDiscontinuedLength;
```

### <a name="rowset-properties"></a>行セット プロパティ

次に、ウィザードは行セット プロパティを設定します。 ATL OLE DB コンシューマー ウィザードで **[変更]**、 **[挿入]**、または **[削除]** を選択した場合、適切なプロパティがここで設定されます (DBPROP_IRowsetChange は常に設定され、それぞれの場合に DBPROPVAL_UP_CHANGE、DBPROPVAL_UP_INSERT、DBPROPVAL_UP_DELETE のいずれかが設定されます)。

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="command-or-table-class"></a>コマンドまたはテーブル クラス

コマンド クラスを指定すると、ウィザードはコマンド クラスを宣言します。テンプレート化されたコードの場合は、コマンドは以下のようになります。

```cpp
DEFINE_COMMAND_EX(CProductsAccessor, L" \
SELECT \
   ProductID, \
   ProductName, \
   SupplierID, \
   CategoryID, \
   QuantityPerUnit, \
   UnitPrice, \
   UnitsInStock, \
   UnitsOnOrder, \
   ReorderLevel, \
   Discontinued \
   FROM dbo.Products")
```

### <a name="column-map"></a>列マップ

ウィザードでは、列のバインドまたは列のマップが生成されます。 一部のプロバイダーで発生する問題を解決するため、下記のコードでの列のバインドの順序は、プロバイダーからの報告とは異なる場合があります。

```cpp
   BEGIN_COLUMN_MAP(CProductsAccessor)
      COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
      COLUMN_ENTRY_LENGTH_STATUS(3, m_SupplierID, m_dwSupplierIDLength, m_dwSupplierIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(4, m_CategoryID, m_dwCategoryIDLength, m_dwCategoryIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(5, m_QuantityPerUnit, m_dwQuantityPerUnitLength, m_dwQuantityPerUnitStatus)
      _COLUMN_ENTRY_CODE(6, DBTYPE_CY, _SIZE_TYPE(m_UnitPrice), 0, 0, offsetbuf(m_UnitPrice), offsetbuf(m_dwUnitPriceLength), offsetbuf(m_dwUnitPriceStatus))
      COLUMN_ENTRY_LENGTH_STATUS(7, m_UnitsInStock, m_dwUnitsInStockLength, m_dwUnitsInStockStatus)
      COLUMN_ENTRY_LENGTH_STATUS(8, m_UnitsOnOrder, m_dwUnitsOnOrderLength, m_dwUnitsOnOrderStatus)
      COLUMN_ENTRY_LENGTH_STATUS(9, m_ReorderLevel, m_dwReorderLevelLength, m_dwReorderLevelStatus)
      _COLUMN_ENTRY_CODE(10, DBTYPE_BOOL, _SIZE_TYPE(m_Discontinued), 0, 0, offsetbuf(m_Discontinued), offsetbuf(m_dwDiscontinuedLength), offsetbuf(m_dwDiscontinuedStatus))
   END_COLUMN_MAP()
};
```

### <a name="class-declaration"></a>クラス宣言

最後に、ウィザードでは、次のようなコマンド クラス宣言が生成されます。

```cpp
class CProducts : public CCommand<CAccessor<CProductsAccessor>>
```

## <a name="attribute-injected-user-record-classes"></a>属性が挿入されたユーザー レコード クラス

データベース属性 ([db_command](../../windows/db-command.md) または [db_table](../../windows/db-table.md)) を使用して OLE DB コンシューマーを作成する場合、この属性によって "_*ClassName*Accessor" の形式の名前でユーザー レコード クラスが挿入されます。 たとえば、コマンド クラスに `COrders`と名前を付けると、ユーザー レコード クラスは `_COrdersAccessor`となります。 表示されますが、ユーザー レコード クラス**クラス ビュー**、それをダブルクリックすると、ヘッダー ファイルでコマンドまたはテーブル クラスに代わりに移動します。 このような場合は、属性が挿入されたコードを表示すると、ユーザー レコード クラスの実際の宣言のみが表示されます。

属性付きコンシューマーでメソッドを追加またはオーバーライドすると、問題が発生することがあります。 たとえば、 `_COrdersAccessor` コンストラクターは `COrders` 宣言に追加できますが、実際には、このコンストラクターは挿入された `COrdersAccessor` クラスに追加されます。 このようなコンス トラクターは、列やパラメーターを初期化できますが作成できませんコピー コンス トラクターをこのようにして、直接インスタンス化できないため、`COrdersAccessor`オブジェクト。 上で直接コンス トラクター (またはその他のメソッド) が必要がある場合、`COrders`クラス、お勧めから派生する新しいクラスを定義する`COrders`し、必要なメソッドを追加します。

次の例では、ウィザードはクラスの宣言を生成`COrders`、ユーザー レコード クラスが、`COrdersAccessor`属性を挿入するため、表示されません。

```cpp
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>
[
   db_source(L"your connection string"),
   db_command(L"Select ShipName from Orders;")
]
class COrders
{
public:

   // COrders()            // incorrect constructor name
   _COrdersAccessor()      // correct constructor name
   {
   }
      [db_column(1) ] TCHAR m_ShipName[41];
   };
```

挿入されたコマンド クラス宣言は次のようになります。

```cpp
class CProducts : public CCommand<CAccessor<_CProductsAccessor>>
```

挿入されたコードのほとんどは、テンプレート バージョンと同じか類似するものです。 主な相違点は、「 [コンシューマー ウィザード生成メソッド](../../data/oledb/consumer-wizard-generated-methods.md)」で説明されている挿入されたメソッドの部分です。

挿入されたコードを表示する方法については、「 [挿入されたコードのデバッグ](/visualstudio/debugger/how-to-debug-injected-code)」を参照してください。

## <a name="see-also"></a>関連項目

[ウィザードを使用した OLE DB コンシューマーの作成](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)