---
title: db_column |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_column
dev_langs:
- C++
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35ab2472ac9e46b620ca735d06b23806126871e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879634"
---
# <a name="dbcolumn"></a>db_column
指定された列を行セット内の変数にバインドします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ db_column(   
   ordinal,   
   dbtype,   
   precision,   
   scale,   
   status,   
   length   
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ordinal`  
 序数の列数 (**DBCOLUMNINFO**序数) またはデータをバインドする、行セット内のフィールドに対応する列の名前 (ANSI または Unicode 文字列)。 数字を使用する場合は、連続した序数をスキップすることができます (例: 1、2、3、5)。 名前は、使用する OLE DB プロバイダーでサポートされている場合、スペースを含めることがあります。 たとえば、次の形式のいずれかを使用できます。  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *dbtype* (省略可能)  
 OLE DB[型インジケーター](https://msdn.microsoft.com/en-us/library/ms711251.aspx)列エントリにします。  
  
 *有効桁数*(省略可能)  
 列のエントリに使用される有効桁数です。 詳細については、説明を参照してください、`bPrecision`の要素、 [DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *スケール*(省略可能)  
 列のエントリに使用する小数点以下桁数。 詳細については、説明を参照してください`bScale`の要素、 [DBBINDING 構造体。](https://msdn.microsoft.com/en-us/library/ms716845.aspx)  
  
 *ステータス*(省略可能)  
 この列の状態を保持するために使用されるメンバー変数です。 状態がかどうか、列の値が、データ値または他のいくつかの値などを示す**NULL**です。 使用可能な値は、次を参照してください。[ステータス](https://msdn.microsoft.com/en-us/library/ms722617.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 *長さ*(省略可能)  
 列のサイズをバイト単位で保持するために使用されるメンバー変数です。  
  
## <a name="remarks"></a>コメント  
 **db_column**行セット内の変数に指定したテーブル列をバインドします。 OLE DB に参加できるメンバー データを区切る`IAccessor`-ベースのバインディングです。 この属性は、通常 OLE DB コンシューマーのマクロを使用して定義されている列のマッピングを設定[BEGIN_COLUMN_MAP](../data/oledb/begin-column-map.md)、 [END_COLUMN_MAP](../data/oledb/end-column-map.md)、および[COLUMN_ENTRY](../data/oledb/column-entry.md)です。 これらの操作、OLE DB [DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)に指定された列をバインドします。 各メンバーをマークする、 **db_column**属性は、列のエントリの形式で列マップの 1 つのエントリを占有します。 したがって、配置する位置列マップは、コマンドまたはテーブル クラスでこの属性を呼び出します。  
  
 使用して**db_column**いずれかと組み合わせて、 [db_table](../windows/db-table.md)または[db_command](../windows/db-command.md)属性。  
  
 コンシューマー属性プロバイダーは、クラスにこの属性を適用する場合、コンパイラの名前は変更するクラス\_*すると*アクセサー、場所*すると*指定した名前は、クラス、および、コンパイラと呼ばれるクラスを作成また*すると*から派生した\_*すると*アクセサー。  クラス ビューでは、両方のクラスが表示されます。  
  
 例については、アプリケーションで使用されるこの属性のサンプル[AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409)、および[MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e)です。  
  
## <a name="example"></a>例  
 このサンプルでは、列をバインドするテーブルで、**長い**データ メンバーし、ステータスや長さのフィールドを指定します。  
  
```  
// db_column_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   DBSTATUS m_dwProductIDStatus;  
   DBLENGTH m_dwProductIDLength;  
  
   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;  
};  
```  
  
## <a name="example"></a>例  
 このサンプルを次の 4 つの列をバインドする、**長い**、文字の文字列、タイムスタンプ、および**DB_NUMERIC**をこの順序での整数。  
  
```  
// db_column_2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   [db_column("1")] LONG m_OrderID;  
   [db_column("2")] TCHAR m_CustomerID[6];  
   [db_column("4")] DB_NUMERIC m_OrderDate;     
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**、`struct`メンバー、メソッド|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー属性します。](../windows/ole-db-consumer-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
