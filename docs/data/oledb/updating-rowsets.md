---
title: 更新 (行セットを)
ms.date: 10/19/2018
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
ms.openlocfilehash: 7151d897469993b2f9be3575eb11a08844af3c69
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028361"
---
# <a name="updating-rowsets"></a>更新 (行セットを)

基本的なデータベース操作では、更新、またはデータ ストアにデータを書き込みます。 OLE DB の更新機構は単純です。コンシューマー アプリケーションは、バインドされたデータ メンバーの値を設定し、これらの値を行セットに書き込みます。その後、コンシューマーはプロバイダーにデータ ストアの更新を要求します。

コンシューマーは、次のような行セットのデータの更新を完了できます。 行内の列の値の設定や、行の挿入行を削除します。 OLE DB テンプレート クラスは、これらの操作を完了する[CRowset](../../data/oledb/crowset-class.md)実装、 [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))インターフェイスし、次のインターフェイス メソッドをオーバーライドします。

- [SetData](../../data/oledb/crowset-setdata.md)行セットの行の変更の列の値。 これは SQL の UPDATE コマンドに相当します。

- [挿入](../../data/oledb/crowset-insert.md)行セットに行を挿入には、SQL の INSERT コマンドに相当します。

- [削除](../../data/oledb/crowset-delete.md)行セットから行を削除します。 これは SQL の DELETE コマンドに相当します。

## <a name="supporting-update-operations"></a>更新操作のサポート

持つコンシューマーを作成するとき、 **ATL OLE DB コンシューマー ウィザード**、いずれかを選択して、更新操作をサポートすることができます、または 3 つのチェック ボックスをオン**変更**、**挿入**、**削除**します。 これらのオプションを選択した場合、ウィザード コードを変更適切に選択した変更の種類をサポートします。 ただし、ウィザードを使用しない場合に、次の行セット プロパティを設定する`VARIANT_TRUE`更新をサポートします。

- `DBPROPVAL_UP_CHANGE` 行のデータ値を変更することができます。

- `DBPROPVAL_UP_INSERT` 行を挿入することができます。

- `DBPROPVAL_UP_DELETE` 行を削除することができます。

プロパティを次のように設定します。

```cpp
CDBPropSet ps(DBPROPSET_ROWSET);

ps.AddProperty(DBPROP_IRowsetChange, true);
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
```

1 つまたは複数の列が書き込み可能でない場合は、変更、挿入、または削除操作が失敗する可能性があります。 この問題を解決するにはカーソル マップを変更します。

## <a name="setting-data-in-rows"></a>行のデータの設定

[CRowset::SetData](../../data/oledb/crowset-setdata.md) は、現在の行の 1 つ以上の列にデータ値を設定します。 次のコードの列にバインドされたデータ メンバーの値を設定する`Name`と`Units in Stock`テーブルの`Products`号餧ェヒェマル`SetData`行セットの 100 行目にこれらの値を記述します。

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the current row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_UnitsInStock = 10000;

// Set the data
HRESULT hr = product.SetData();
```

## <a name="inserting-rows-into-rowsets"></a>行セットへの行の挿入

[CRowset::Insert](../../data/oledb/crowset-insert.md) は、アクセサーのデータを使用して新しい行を作成し、初期化します。 `Insert` は現在の行の後、まったく新しい行を作成します。次の行に現在の行をインクリメントするか、そのままおくかどうかを指定する必要があります。 これを指定するには、 *bGetRow* パラメーターを設定します。

```cpp
HRESULT Insert(int nAccessor = 0, bool bGetRow = false)
```

- **false** (既定値) は、現在の行を次の行にインクリメントして、挿入された行を指すように指定します。

- **true**現在では引き続きが行であるを指定します。

次のコードは、テーブルの列にバインドされたデータ メンバーの値を設定`Products`号餧ェヒェマル`Insert`行セットの 100 行の後にそれらの値を持つ新しい行を挿入します。 新しい行で定義されていないデータを回避するためにすべての列の値を設定することをお勧めします。

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Set the column values for a row of the Product table, then insert the row
product.m_ProductID = 101;
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_SupplierID = 27857;
product.m_CategoryID = 372;
_tcscpy_s(product.m_QuantityPerUnit, product.m_sizeOfQuantityPerUnit, _T( "Pack of 10" ) );

product.m_UnitPrice = 20;
product.m_UnitsInStock = 10000;
product.m_UnitsOnOrder = 5201;
product.m_ReorderLevel = 5000;
product.m_Discontinued = false;

// You must also initialize the status and length fields before setting/inserting data
// Set the column status values
m_dwProductIDStatus = DBSTATUS_S_OK;
m_dwProductNameStatus = DBSTATUS_S_OK;
m_dwSupplierIDStatus = DBSTATUS_S_OK;
m_dwCategoryIDStatus = DBSTATUS_S_OK;
m_dwQuantityPerUnitStatus = DBSTATUS_S_OK;
m_dwUnitPriceStatus = DBSTATUS_S_OK;
m_dwUnitsInStockStatus = DBSTATUS_S_OK;
m_dwUnitsOnOrderStatus = DBSTATUS_S_OK;
m_dwReorderLevelStatus = DBSTATUS_S_OK;
m_dwDiscontinuedStatus = DBSTATUS_S_OK;

// Set the column length value for column data members that are not fixed-length types.
// The value should be the length of the string that you are setting.
m_dwProductNameLength = 6;             // "Candle" has 6 characters
m_dwQuantityPerUnitLength = 10;        // "Pack of 10" has 10 characters

// Insert the data
HRESULT hr = product.Insert();
```

詳しい例については、「 [CRowset::Insert](../../data/oledb/crowset-insert.md)」をご覧ください。

ステータスや長さのデータ メンバーを設定する方法について詳しくは、「 [ウィザードで生成されたアクセサーのフィールド ステータスのデータ メンバー](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)」をご覧ください。

## <a name="deleting-rows-from-rowsets"></a>行セットからの行の削除

[CRowset::Delete](../../data/oledb/crowset-delete.md) は、行セットから現在の行を削除します。 次のコード呼び出し`Delete`行セットの 100 行を削除します。

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Delete the row
HRESULT hr = product.Delete();
```

## <a name="immediate-and-deferred-updates"></a>即時更新と遅延更新

それ以外の場合、指定した場合を除き、呼び出し、 `SetData`、 `Insert`、および`Delete`メソッドは、データ ストアをすぐに更新します。 しかし、すべての変更をコンシューマーがローカル キャッシュに格納しておき、次の更新メソッドの 1 つが呼び出されたらそれらをデータ ストアに転送するという方法で、更新を遅らせることができます。

- [Crowset::update](../../data/oledb/crowset-update.md)保留中の最後のフェッチ、現在の行に加えられた変更を転送または`Update`を呼び出します。

- [Crowset::updateall](../../data/oledb/crowset-updateall.md)保留中の最後のフェッチで、以降のすべての行に加えられた変更を転送または`Update`を呼び出します。

更新プログラム、update メソッドで使用されるコマンドで変更を行うは、特定の意味を持つし、SQL と混同されない**更新**コマンド (`SetData`は SQL に相当**更新**コマンド).

遅延更新などの一連の銀行取引トランザクション; などの状況では役立ちます1 つのトランザクションが取り消された場合は、最後の 1 つがコミットされた後に一連の変更までを送信しないために、変更を取り消すことができます。 また、プロバイダーが変更を 1 つのネットワーク呼び出しにまとめられるので、効率が良くなります。

遅延更新をサポートするために設定する必要があります、`DBPROP_IRowsetChange`で説明するプロパティと共にプロパティ**更新操作のサポート**:

```cpp
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);
```

呼び出すと`Update`または`UpdateAll`メソッドは、データ ストアにローカル キャッシュからの変更を転送し、ローカル キャッシュをクリアします。 更新プログラムは、現在の行のみの変更を転送、ためには、更新プログラムと使用すると、更新する行は、アプリケーションの追跡ことが重要です。 連続する 2 つの行を更新する方法を次の例に示します。

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the 100th row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Wick" ) );

product.m_UnitsInStock = 10000;

HRESULT hr = product.SetData();  // No changes made to row 100 yet
product.Update();                 // Update row 100 now

// Change the values of columns "Name" and "Units in Stock" in the 101st row of the Product table
product.MoveNext();

_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName _T( "Wax" ) );

product.m_UnitsInStock = 500;

HRESULT hr = product.SetData();  // No changes made to row 101 yet
product.Update();                 // Update row 101 now
```

呼び出す必要がありますに保留中の変更が転送されることを確認するには、`Update`別の行に移動する前にします。 ただし、アプリケーションで数百行も更新する必要がある場合など、この処理では時間がかかって非効率的な場合は、 `UpdateAll` を使用してすべての行を一度に更新できます。

たとえば場合、最初`Update`呼び出しがない、上記のコードから、100 行案を変更せずに、101 行目が変更されます。 その後、アプリケーションはいずれかを呼び出す必要`UpdateAll`100 行と呼び出しに戻すまたは`Update`を更新するには、その行のできます。

変更を遅延させる主な理由は、変更を元に戻すことができるようにするためです。 [CRowset::Undo](../../data/oledb/crowset-undo.md) を呼び出すと、ローカル変更キャッシュの状態が、保留中の変更が作成される前のデータ ストアの状態にロールバックされます。 注意することが重要`Undo`重ね合わせを 1 ステップ (最新の変更のみ前に、の状態) のローカル キャッシュの状態のバックアップは、代わりに、その行に対してローカル キャッシュをクリアします。 また、`Undo`は現在の行のみに影響します。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)<br/>
[CRowset クラス](../../data/oledb/crowset-class.md)<br/>
[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))<br/>
