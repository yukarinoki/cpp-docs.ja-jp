---
title: コンシューマー ウィザードで生成されたメソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OpenAll method
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- methods [C++], OLE DB Consumer Wizard-generated
- CloseDataSource method
- consumer wizard-generated classes and methods
- OpenDataSource method
- CloseAll method
- OpenRowset method
- GetRowsetProperties method
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0e03d24f61b3eba1ff4c6fa1e4d888a0252a21b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="consumer-wizard-generated-methods"></a>コンシューマー ウィザードで生成されたメソッド
ATL OLE DB コンシューマー ウィザードおよび MFC アプリケーション ウィザード、うち注意すべき特定の関数を生成します。 一部のメソッドが実装される異なる方法で、属性付きプロジェクトで; いくつかの注意事項があるので注意してください。各ケースは、以下について説明します。 挿入されたコードを表示する方法については、「 [挿入されたコードのデバッグ](/visualstudio/debugger/how-to-debug-injected-code)」を参照してください。  
  
-   `OpenAll` 行セットをデータ ソースを開き、ブックマークを有効に利用できる場合。  
  
-   `CloseAll` 開いているすべての行セットを閉じるし、すべてのコマンドの実行を解放します。  
  
-   `OpenRowset` OpenAll を開くには、コンシューマーの行セットまたは行セットによって呼び出されます。  
  
-   `GetRowsetProperties` 設定するプロパティを設定すると、行セットのプロパティへのポインターを取得します。  
  
-   `OpenDataSource` 指定した初期化文字列を使用して、データ ソースを開き、**データ リンク プロパティ** ダイアログ ボックス。  
  
-   `CloseDataSource` 適切な方法でデータ ソースを閉じます。  
  
## <a name="openall-and-closeall"></a>OpenAll と CloseAll  
  
```  
HRESULT OpenAll();   

void CloseAll();  
```  
  
 次の例を呼び出す方法を示しています。`OpenAll`と`CloseAll`繰り返し、同じコマンドを実行するとします。 コード例を比較[ccommand::close](../../data/oledb/ccommand-close.md)、バリエーションを呼び出すことが示されます**閉じる**と`ReleaseCommand`の代わりに`CloseAll`です。  
  
```  
int main(int argc, char* argv[])  
{  
   HRESULT hr;  
  
   hr = CoInitialize(NULL);  
  
   CCustOrdersDetail rs;      // Your CCommand-derived class  
   rs.m_OrderID = 10248;      // Open order 10248  
   hr = rs.OpenAll();         // (Open also executes the command)  
   hr = rs.MoveFirst();         // Move to the first row and print it  
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );  
  
   // Close the first command execution  
   rs.Close();  
  
   rs.m_OrderID = 10249;      // Open order 10249 (a new order)  
   hr = rs.Open();            // (Open also executes the command)  
   hr = rs.MoveFirst();         // Move to the first row and print it  
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );  
  
   // Close the second command execution;  
   // Instead of rs.CloseAll() you could call  
   // rs.Close() and rs.ReleaseCommand():  
   rs.CloseAll();  
  
   CoUninitialize();  
   return 0;  
}  
```  
  
## <a name="remarks"></a>コメント  
 定義する場合、 `HasBookmark` 、メソッド、 `OpenAll` DBPROP_IRowsetLocate プロパティを設定します。 のみこれを行う場合は、プロバイダーは、そのプロパティをサポートしているかどうかを確認します。  
  
## <a name="openrowset"></a>OpenRowset  
  
```  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
 **OpenAll**コンシューマーの行セットまたは行セットを開くには、このメソッドを呼び出します。 通常、呼び出す必要はありません`OpenRowset`複数データ ソースとセッション/行セットを使用する場合を除き、します。 `OpenRowset` コマンドまたはテーブル クラスのヘッダー ファイルで宣言されます。  
  
```  
// OLE DB Template version:  
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
{  
   HRESULT hr = Open(m_session, NULL, pPropSet);  
   #ifdef _DEBUG  
   if(FAILED(hr))  
      AtlTraceErrorRecords(hr);  
   #endif  
   return hr;  
}  
```  
  
 属性は、異なる方法でこのメソッドを実装します。 このバージョンは、セッション オブジェクトと別の名前を渡すことができますが、db_command で指定したコマンド文字列を既定値とするコマンド文字列を受け取ります。 定義する場合、 `HasBookmark` 、メソッド、 `OpenRowset` DBPROP_IRowsetLocate プロパティを設定します。 のみこれを行う場合は、プロバイダーは、そのプロパティをサポートしているかどうかを確認します。  
  
```  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)  
{  
  
   DBPROPSET *pPropSet = NULL;  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   __if_exists(HasBookmark)  
  
   {  
      propset.AddProperty(DBPROP_IRowsetLocate, true);  
      pPropSet= &propset;  
      }  
...  
}  
```  
  
## <a name="getrowsetproperties"></a>GetRowsetProperties  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet);  
```  
  
 このメソッドは、行セットのプロパティ セットへのポインターを取得します。このポインターを使用して、DBPROP_IRowsetChange などのプロパティを設定することができます。 `GetRowsetProperties` 以下を使用、ユーザー レコード クラスにします。 追加の行セット プロパティを設定するには、このコードを変更できます。  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## <a name="remarks"></a>コメント  
 グローバル定義しないでください`GetRowsetProperties`メソッドのいずれかと、競合する可能性がありますのでによって定義されたウィザード。 これは、テンプレートおよび属性のプロジェクトで得られるウィザードで生成されたメソッドであることに注意してください。属性は、このコードを挿入しません。  
  
## <a name="opendatasource-and-closedatasource"></a>OpenDataSource および CloseDataSource  
  
```  
HRESULT OpenDataSource();   

void CloseDataSource();  
```  
  
## <a name="remarks"></a>コメント  
 ウィザードは、メソッドを定義`OpenDataSource`と`CloseDataSource`です。`OpenDataSource`呼び出し[cdatasource::openfrominitializationstring](../../data/oledb/cdatasource-openfrominitializationstring.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ウィザードを使用した OLE DB コンシューマーの作成](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)