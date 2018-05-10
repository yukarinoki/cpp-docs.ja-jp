---
title: db_param |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_param
dev_langs:
- C++
helpviewer_keywords:
- db_param attribute
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce7cf5c8e92e7fd6e6e10d7bef0519b1ced4cf62
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="dbparam"></a>db_param
入力または出力パラメーターを持つ指定したメンバー変数を関連付けるし、変数を区切ります。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ db_param(   
   ordinal,   
   paramtype="DBPARAMIO_INPUT",   
   dbtype,   
   precision,   
   scale,   
   status,   
   length  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ordinal`  
 列の番号 (**DBCOLUMNINFO**序数) にデータをバインドする、行セット内のフィールドに対応します。  
  
 *paramtype* (省略可能)  
 パラメーターに設定する型。 プロバイダーは、基になるデータ ソースでサポートされているパラメーター I/O 型のみをサポートします。 種類は 1 つまたは複数の組み合わせ**次**値。  
  
-   **DBPARAMIO_INPUT** 入力パラメーター。  
  
-   **DBPARAMIO_OUTPUT** 出力パラメーター。  
  
-   **DBPARAMIO_NOTPARAM** アクセサーにパラメーターがありません。 設定**eParamIO**行では、この値にアクセサー注意を促すユーザー パラメーターが無視されます。  
  
 *dbtype* (省略可能)  
 OLE DB[型インジケーター](https://msdn.microsoft.com/en-us/library/ms711251.aspx)列エントリにします。  
  
 *有効桁数*(省略可能)  
 列のエントリに使用される有効桁数です。 詳細については、説明を参照してください**bPrecision**の要素、 [DBBINDING 構造体。](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *スケール*(省略可能)  
 列のエントリに使用する小数点以下桁数。 詳細については、説明を参照してください**bScale**の要素、 [DBBINDING 構造体。](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *ステータス*(省略可能)  
 この列の状態を保持するために使用されるメンバー変数です。 状態がかどうか、列の値が、データ値または他のいくつかの値などを示す**NULL**です。 使用可能な値は、次を参照してください。[ステータス](https://msdn.microsoft.com/en-us/library/ms722617.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 *長さ*(省略可能)  
 列のサイズをバイト単位で保持するために使用されるメンバー変数です。  
  
## <a name="remarks"></a>コメント  
 **db_param**パラメーターを定義するコマンドで使用する; したがってと共に使用する**db_command**です。 たとえば、使用することができます**db_param** SQL クエリまたはストアド プロシージャでパラメーターをバインドします。 ストアド プロシージャのパラメーターが疑問符 (?) で表され、パラメーターの順序でのデータ メンバーをバインドする必要があります。  
  
 **db_param** OLE DB に参加できるメンバー データを取り出すため`ICommandWithParameters`-ベースのバインディングです。 パラメーターの型 (入力または出力)、OLE DB の型、有効桁数、小数点以下桁数、状態、および指定されたパラメーターの長さを設定します。 この属性は、OLE DB コンシューマー マクロ BEGIN_PARAM_MAP を挿入しています.END_PARAM_MAP です。 各メンバーをマークする、 **db_param**属性は、マップ、COLUMN_ENTRY の形式での 1 つのエントリを占有します。  
  
 **db_param**は組み合わせて使用するか、 [db_table](../windows/db-table.md)または[db_command](../windows/db-command.md)属性。  
  
 コンシューマー属性プロバイダーは、クラスにこの属性を適用する場合、コンパイラの名前は変更するクラス\_*すると*アクセサー、場所*すると*指定した名前は、クラス、および、コンパイラと呼ばれるクラスを作成また*すると*から派生した\_*すると*アクセサー。  クラス ビューでは、両方のクラスが表示されます。  
  
## <a name="example"></a>例  
 次の例では、Northwind データベースに格納されている SalesbyYear プロシージャに基づいたコマンド クラスを作成します。 使用してストアド プロシージャの最初のパラメーターに関連付けられます、`m_RETURN_VALUE`変数、出力パラメーターとして定義されているとします。 最後の 2 つ (入力) パラメーターに関連付けられます`m_Beginning_Date`と`m_Ending_Date`です。  
  
 次の使用例、 `nOutput` output パラメーターを持つ変数です。  
  
```  
// db_param.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_source(L"my_connection_string"),   
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")   
]  
struct CSalesbyYear {  
   DBSTATUS m_dwShippedDateStatus;  
   DBSTATUS m_dwOrderIDStatus;  
   DBSTATUS m_dwSubtotalStatus;  
   DBSTATUS m_dwYearStatus;  
  
   DBLENGTH m_dwShippedDateLength;  
   DBLENGTH m_dwOrderIDLength;  
   DBLENGTH m_dwSubtotalLength;  
   DBLENGTH m_dwYearLength;  
  
   // Bind columns  
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;  
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;  
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;  
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];  
  
   // Bind parameters  
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;  
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;  
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;  
};  
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
 [OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)   
