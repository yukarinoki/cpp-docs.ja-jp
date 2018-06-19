---
title: db_command |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_command
dev_langs:
- C++
helpviewer_keywords:
- db_command attribute
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e0fe3f712566345bb069b798207cfdb10a0aa636
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33886412"
---
# <a name="dbcommand"></a>db_command
OLE DB コマンドを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ db_command(   
   command,   
   name,   
   source_name,   
   hresult,   
   bindings,   
   bulk_fetch)  
]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `command`  
 OLE DB コマンドのテキストを含むコマンド文字列。 簡単な例を次に示します。  
  
```  
[ db_command ( command = "Select * from Products" ) ]  
```  
  
 *command* の構文は次のとおりです。  
  
```  
binding parameter block 1  
   OLE DB command  
binding parameter block 2  
   continuation of OLE DB command  
binding parameter block 3  
...  
```  
  
 *binding parameter block* は次のように定義します。  
  
 **([** `bindtype` **]** *szVar1* [*, szVar2* [, *nVar3* [, ...]]] **)**  
  
 それぞれの文字について以下に説明します。  
  
 **(** は、データ バインディング ブロックの開始を示します。  
  
 **[** `bindtype` **]** は次のいずれかの文字列です。大文字と小文字は区別されません。  
  
-   **[db_column]** は、各メンバー変数を行セットの列にバインドします。  
  
-   **[bindto]** ( **[db_column]** と同じ)。  
  
-   **[in]** は、入力パラメーターとしてメンバー変数をバインドします。  
  
-   **[out]** は、出力パラメーターとしてメンバー変数をバインドします。  
  
-   **[in,out]** は、入力/出力パラメーターとしてメンバー変数をバインドします。  
  
 *SzVarX* は、現在のスコープ内のメンバー変数に解決されます。  
  
 **)** は、データ バインディング ブロックの終了を示します。  
  
 コマンド文字列に [in]、[out]、[in/out] などの指定子が 1 つ以上含まれる場合、 **db_command** はパラメーター マップを作成します。  
  
 コマンド文字列に [db_column] や [bindto] などのパラメーターが 1 つ以上含まれる場合、 **db_command** は行セットと、これらのバインドされた変数を提供するためのアクセサー マップを生成します。 詳しくは、「 [db_accessor](../windows/db-accessor.md) 」をご覧ください。  
  
> [!NOTE]
>  [`bindtype`] 構文と `bindings` パラメーターは、 **db_command** をクラス レベルで使用するときは無効です。  
  
 バインディング パラメーター ブロックの例を次にいくつか示します。 次の例では、pubs データベースの authors テーブルの `m_au_fname` 列と `m_au_lname` 列に、それぞれ `au_fname` および `au_lname` データ メンバーをバインドします。  
  
```  
TCHAR m_au_fname[21];  
TCHAR m_au_lname[41];  
TCHAR m_state[3] = 'CA';  
  
[db_command (  
   command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \  
   "FROM dbo.authors " \  
   "WHERE state = ?([in]m_state)")  
```  
  
 ]  
  
 *name* (省略可能)  
 行セットの操作に使用するハンドルの名前。 *name*を指定した場合、 **db_command** は指定された *name*のクラスを生成します。このクラスを使用して、行セットを走査したり、複数のアクション クエリを実行したりできます。 *name*を指定しないと、複数の結果行をユーザーに返すことはできません。  
  
 *source_name* (省略可能)  
 `CSession` 変数、または `db_source` 属性が適用された、コマンドが実行されるクラスのインスタンス。 「 [db_source](../windows/db-source.md)」をご覧ください。  
  
 **db_command** は *source_name* に使用されている変数が有効であることを確認するので、指定する変数は関数スコープまたはグローバル スコープに存在する必要があります。  
  
 `hresult` (省略可能)  
 このデータベース コマンドの `HRESULT` を受け取る変数を示します。 変数が存在しない場合は、属性によって自動的に挿入されます。  
  
 *bindings* (省略可能)  
 OLE DB コマンドからバインディング パラメーターを分離できます。  
  
 `bindings`の値を指定すると、 **db_command** は関連付けられている値を解析し、[`bindtype`] パラメーターを解析しません。 これにより、OLE DB プロバイダーの構文を使用できます。 解析を無効にするには、バインディング パラメーターのない **Bindings=""** を指定します。  
  
 `bindings`の値を指定しないと、 **db_command** はバインディング パラメーター ブロックを解析し、"**(**"、角かっこで囲まれた **[**`bindtype`**]** 、前に宣言されている 1 つ以上の C++ メンバー変数、"**)**" という順番の記述を探します。 かっこで囲まれたすべてのテキストが最終的なコマンドから削除され、これらのパラメーターを使用してこのコマンドの列とパラメーターのバインディングが作成されます。  
  
 *bulk_fetch*(省略可能)  
 フェッチする行数を指定する整数値。  
  
 既定値は 1 で、単一行のフェッチを指定します (行セットは [CRowset](../data/oledb/crowset-class.md)型です)。  
  
 1 より大きい値は、バルク行フェッチを指定します。 バルク行フェッチとは、複数の行ハンドルをフェッチするバルク行セットの機能のことです (行セットは [CBulkRowset](../data/oledb/cbulkrowset-class.md) 型であり、指定された行数で `SetRows` を呼び出します)。  
  
 *bulk_fetch* が 1 より小さい場合は、 `SetRows` は 0 を返します。  
  
## <a name="remarks"></a>コメント  
 OLE DB コンシューマーは、**db_command** によって作成された [CCommand](../data/oledb/ccommand-class.md) オブジェクトを使用して、コマンドを実行します。  
  
 **db_command** はクラス スコープまたは関数スコープで使用できます。主な違いは、 `CCommand` オブジェクトのスコープです。 関数スコープでは、バインディングなどのデータは関数の終了時に終了します。 クラスと関数の両方のスコープの使用法は、OLE DB コンシューマー テンプレートのクラスを伴う**CCommand <>** 関数やクラスの場合、テンプレート引数の点が異なります。 関数スコープではバインディングはローカル変数を構成する **Accessor** に対して行われますが、クラス スコープでは引数として `CAccessor`派生クラスを予期します。 クラス属性として使用すると、 **db_command** は **db_column**と共に動作します。  
  
 **db_command** を使用して、結果セットを返さないコマンドを実行できます。  
  
 コンシューマー属性プロバイダーは、クラスにこの属性を適用する場合、コンパイラの名前は変更するクラス\_*すると*アクセサー、場所*すると*指定した名前は、クラス、および、コンパイラと呼ばれるクラスを作成また*すると*から派生した\_*すると*アクセサー。  クラス ビューでは、両方のクラスが表示されます。  
  
## <a name="example"></a>例  
 この例では、テーブルから state 列が 'CA' と一致する姓と名を選択するコマンドを定義しています。 **db_command** は、ウィザードで生成される [OpenAll and CloseAll](../data/oledb/consumer-wizard-generated-methods.md)などの関数および `CRowset` MoveNext [などの](../data/oledb/crowset-movenext.md)メンバー関数を呼び出すことができる行セットを作成して読み取ります。  
  
 このコードでは、pubs データベースに接続する独自の接続文字列を指定する必要があることに注意してください。 開発環境でこれを行う方法については、「 [How to: Connect to a Database from Server Explorer](http://msdn.microsoft.com/en-us/7c1c3067-0d77-471b-872b-639f9f50db74) 」および「 [How to: Add New Data Connections in Server Explorer/Database Explorer](http://msdn.microsoft.com/en-us/fb2f513b-ddad-4142-911e-856bba0054c8)」をご覧ください。  
  
```  
// db_command.h  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
#pragma once  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
  
struct CAuthors {  
   // In order to fix several issues with some providers, the code below may bind  
   // columns in a different order than reported by the provider  
  
   DBSTATUS m_dwau_lnameStatus;  
   DBSTATUS m_dwau_fnameStatus;  
   DBLENGTH m_dwau_lnameLength;  
   DBLENGTH m_dwau_fnameLength;  
  
   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];  
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];  
  
   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];  
  
   void GetRowsetProperties(CDBPropSet* pPropSet) {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   }  
};  
```  
  
## <a name="example"></a>例  
  
```  
// db_command.cpp  
// compile with: /c  
#include "db_command.h"  
  
int main(int argc, _TCHAR* argv[]) {  
   HRESULT hr = CoInitialize(NULL);  
  
   // Instantiate rowset  
   CAuthors rs;  
  
   // Open rowset and move to first row  
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));  
   hr = rs.OpenAll();  
   hr = rs.MoveFirst();  
  
   // Iterate through the rowset  
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {  
      // Print out the column information for each row  
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);  
      hr = rs.MoveNext();  
   }  
  
   rs.CloseAll();  
   CoUninitialize();  
}  
```  
  
## <a name="example"></a>例  
 この例では、データ ソース クラス `db_source` で `CMySource`を使用し、コマンド クラス `db_command` と `CCommand1` で `CCommand2`を使用します。  
  
```  
// db_command_2.cpp  
// compile with: /c  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
// class usage for both db_source and db_command  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
struct CMySource {  
   HRESULT OpenDataSource() {  
      return S_OK;  
   }  
};  
  
[db_command(command = "SELECT * FROM Products")]  
class CCommand1 {};  
  
[db_command(command = "SELECT FNAME, LNAME FROM Customers")]  
class CCommand2 {};  
  
int main() {  
   CMySource s;  
   HRESULT hr = s.OpenDataSource();  
   if (SUCCEEDED(hr)) {  
      CCommand1 c1;  
      hr = c1.Open(s);  
  
      CCommand2 c2;  
      hr = c2.Open(s);  
   }  
  
   s.CloseDataSource();  
}  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、 `struct`、member、method、local|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー属性します。](../windows/ole-db-consumer-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   
