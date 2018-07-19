---
title: db_source |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b826e5d630b52062892001c26efda01b5c7293f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873720"
---
# <a name="dbsource"></a>db_source
データ ソースへの接続を作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *db_source*  
 データ ソースに接続するために使用する接続文字列。 接続文字列の形式の場合、次を参照してください。[接続文字列およびデータ リンク](https://msdn.microsoft.com/en-us/library/ms718376.aspx)で、Microsoft Data Access Components (MDAC) SDK。  
  
 *name* (省略可能)  
 使用すると`db_source`クラスで*名前*を持つデータ ソース オブジェクトのインスタンス、 `db_source` (1 の例を参照してください) に適用される属性です。 使用すると`db_source`メソッドの実装にインライン*名前*データにアクセスするために使用する変数 (ローカル メソッド) は、ソース (例 2 を参照してください)。 これを渡す*名前*を`source_name`のパラメーター **db_command**に関連付けるコマンド データ ソース。  
  
 `hresult` (省略可能)  
 このデータベース コマンドの `HRESULT` を受け取る変数を示します。 変数が存在しない場合は、属性によって自動的に挿入されます。  
  
## <a name="remarks"></a>コメント  
 `db_source` 作成、 [CDataSource](../data/oledb/cdatasource-class.md)と[CSession](../data/oledb/csession-class.md)を一緒に OLE DB コンシューマーのデータ ソースとの接続を表すオブジェクト。  
  
 使用すると`db_source`クラスで、`CSession`オブジェクト クラスのメンバーになります。  
  
 使用する場合`db_source`メソッドのスコープ内で、挿入されたコードを実行メソッドでは、および`CSession`オブジェクトは、ローカル変数として作成します。  
  
 `db_source` クラスまたはメソッド内では、データ ソースのプロパティを追加します。 組み合わせて使用**db_command** (受け取り、 `db_source` *名前*パラメーターとしてその`source_name`パラメーター)。  
  
 コンシューマー属性プロバイダーは、クラスにこの属性を適用する場合、コンパイラの名前は変更するクラス\_*すると*アクセサー、場所*すると*指定した名前は、クラス、および、コンパイラと呼ばれるクラスを作成また*すると*から派生した\_*すると*アクセサー。  クラス ビューでは、両方のクラスが表示されます。  
  
 アプリケーションで使用されるこの属性の例は、サンプルを参照してください。 [AtlAgent](http://msdn.microsoft.com/en-us/52bef5da-c1a0-4223-b4e6-9e464b6db409)と[MultiRead](http://msdn.microsoft.com/en-us/5a2a915a-77dc-492f-94b2-1b809995dd5e)です。  
  
## <a name="example"></a>例  
 このサンプルを呼び出す`db_source`データ ソースへの接続を作成するためのクラスに`ds`Northwind データベースを使用します。 `ds` データ ソースには、内部的に使用できるハンドル、`CMyCommand`クラスです。  
  
```  
// db_source_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[  
  db_source(L"my_connection_string", name="ds"),  
  db_command(L"select * from Products")  
]  
class CMyCommand {};  
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
