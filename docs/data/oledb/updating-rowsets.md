---
title: 行セットの更新 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: be82fb1c1f77ae3204bed54257062f362d286844
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083828"
---
# <a name="updating-rowsets"></a>更新 (行セットを)

データベースの基本の操作は、データ ストアの更新、つまりデータの書き込みです。 OLE DB の更新機構は単純です。コンシューマー アプリケーションは、バインドされたデータ メンバーの値を設定し、これらの値を行セットに書き込みます。その後、コンシューマーはプロバイダーにデータ ストアの更新を要求します。  
  
コンシューマーが行セット データに対して実行できる更新の種類は、行内の列値の設定、行の挿入、行の削除です。 これらの操作を実行するために、OLE DB テンプレート クラスの [CRowset](../../data/oledb/crowset-class.md) は、[IRowsetChange](/previous-versions/windows/desktop/ms715790) インターフェイスを実装し、次のインターフェイス メソッドをオーバーライドします。  
  
- [SetData](../../data/oledb/crowset-setdata.md) は行セットの行の列値を変更します。これは SQL の UPDATE コマンドに相当します。  
  
- [Insert](../../data/oledb/crowset-insert.md) は行を行セットに挿入します。これは SQL の INSERT コマンドに相当します。  
  
- [Delete](../../data/oledb/crowset-delete.md) は行を行セットから削除します。これは SQL の DELETE コマンドに相当します。  
  
## <a name="supporting-update-operations"></a>更新操作のサポート  

ATL OLE DB コンシューマー ウィザードを使用してコンシューマーを作成する場合、 **[変更]**、 **[挿入]**、 **[削除]** の 3 つのチェック ボックスのうちの 1 つ以上をオンにすれば、更新操作をサポートできます。 これらのチェック ボックスをオンにすると、ウィザードによってコードが適宜変更され、選んだ変更の種類がサポートされます。 ただし、ウィザードを使用しない場合、更新をサポートするには次の行セット プロパティを `VARIANT_TRUE` に設定する必要があります。  
  
- `DBPROPVAL_UP_CHANGE` 行のデータ値を変更することができます。  
  
- `DBPROPVAL_UP_INSERT` 行を挿入することができます。  
  
- `DBPROPVAL_UP_DELETE` 行を削除することができます。  
  
プロパティを次のように設定します。  
  
```cpp  
CDBPropSet ps(DBPROPSET_ROWSET);  

ps.AddProperty(DBPROP_IRowsetChange, true)  
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
```  
  
1 つ以上の列が書き込み禁止になっている場合は、変更、挿入、または削除の操作が失敗することがあります。 これを修正するにはカーソル マップを変更します。  
  
## <a name="setting-data-in-rows"></a>行のデータの設定  

[CRowset::SetData](../../data/oledb/crowset-setdata.md) は、現在の行の 1 つ以上の列にデータ値を設定します。 次のコードは、Products テーブルの列 "Name" と "Units in Stock" にバインドされたデータ メンバーの値を設定し、 `SetData` を呼び出して、行セットの 100 行目にこれらの値を書き込みます。  
  
```cpp  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Change the values of columns "Name" and "Units in Stock" in the current row of the Product table  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Candle" ) );  

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
  
- **true** は、現在の行をそのままの場所に残すように指定します。  
  
次のコードは、Products テーブルの列にバインドされたデータ メンバーの値を設定しを呼び出して`Insert`行セットの 100 行の後にそれらの値を持つ新しい行を挿入します。 定義されていないデータが新しい行に含まれないように、すべての列値を設定することをお勧めします。  
  
```cpp  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Set the column values for a row of the Product table, then insert the row  
product.m_ProductID = 101;  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Candle" ) );  

product.m_SupplierID = 27857;  
product.m_CategoryID = 372;  
_tcscpy_s(product.m_QuantityPerUnit, product.m_sizeOfQuantityPerUnit,  
           _T( "Pack of 10" ) );  

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
  
更新メソッドで使用される "更新" には、"コマンド上の変更" という特有の意味があります。これを SQL の UPDATE コマンドと混同しないようにしてください (`SetData` が SQL の UPDATE コマンドに相当します)。  
  
遅延更新は、銀行の一連のトランザクションのような場面で役立ちます。最後の変更がコミットされるまでは一連の変更が送信されないため、1 つのトランザクションがキャンセルされた場合、変更を元に戻すことができます。 また、プロバイダーが変更を 1 つのネットワーク呼び出しにまとめられるので、効率が良くなります。  
  
遅延更新をサポートするために設定する必要があります、`DBPROP_IRowsetChange`プロパティに加えて、「更新操作のサポート」で説明されているプロパティ。  
  
```cpp  
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);  
```  
  
呼び出すと`Update`または`UpdateAll`メソッドは、データ ストアにローカル キャッシュからの変更を転送し、ローカル キャッシュをクリアします。 更新は現在の行に対する変更のみを転送するため、アプリケーションでどの行をどの時点で更新するかを追跡することが重要になります。 連続する 2 つの行を更新する方法を次の例に示します。  
  
```cpp  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Change the values of columns "Name" and "Units in Stock" in the 100th row of the Product table  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Wick" ) );  

product.m_UnitsInStock = 10000;  

HRESULT hr = product.SetData();  // No changes made to row 100 yet  
product.Update();                 // Update row 100 now  
  
// Change the values of columns "Name" and "Units in Stock" in the 101st row of the Product table  
product.MoveNext();  

_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName  
           _T( "Wax" ) );  

product.m_UnitsInStock = 500;  

HRESULT hr = product.SetData();  // No changes made to row 101 yet  
product.Update();                 // Update row 101 now  
```  
  
呼び出す必要がありますに保留中の変更が転送されることを確認するには、`Update`別の行に移動する前にします。 ただし、アプリケーションで数百行も更新する必要がある場合など、この処理では時間がかかって非効率的な場合は、 `UpdateAll` を使用してすべての行を一度に更新できます。  
  
たとえば場合、最初`Update`呼び出しがない、上記のコードから、100 行は変更されず、101 行目が変更されます。 その後、アプリケーションはいずれかを呼び出す必要`UpdateAll`100 行と呼び出しに戻すまたは`Update`を更新するには、その行のできます。  
  
変更を遅延させる主な理由は、変更を元に戻すことができるようにするためです。 [CRowset::Undo](../../data/oledb/crowset-undo.md) を呼び出すと、ローカル変更キャッシュの状態が、保留中の変更が作成される前のデータ ストアの状態にロールバックされます。 注意することが重要`Undo`はロールバックされませんを 1 ステップ (最新の変更のみ前に、の状態) のローカル キャッシュの状態のバックアップは、代わりに、その行に対してローカル キャッシュをクリアします。 また、`Undo`は現在の行のみに影響します。  
  
## <a name="see-also"></a>関連項目  

[OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)<br/>
[CRowset クラス](../../data/oledb/crowset-class.md)<br/>
[IRowsetChange](/previous-versions/windows/desktop/ms715790)