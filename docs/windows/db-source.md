---
title: db_source |Microsoft Docs
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
ms.openlocfilehash: f7c1f02c3791e75d3f42db6a942f5b2055234517
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570611"
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
  
### <a name="parameters"></a>パラメーター  
 *db_source*  
 データ ソースに接続するために使用する接続文字列。 接続文字列の形式の場合、次を参照してください。[データ リンクの接続文字列と](https://msdn.microsoft.com/library/ms718376.aspx)で、Microsoft Data Access Components (MDAC) SDK。  
  
 *name* (省略可能)  
 使用すると**db_source**クラスで*名前*を持つデータ ソース オブジェクトのインスタンスです、 **db_source**属性 (例 1 を参照してください) を適用します。 使用すると**db_source**インライン メソッドの実装で*名前*データにアクセスするために使用される変数 (ローカル メソッド) は、ソース (例 2 を参照してください)。 これを渡す*名前*を*source_name*のパラメーター`db_command`にデータ ソースを関連付けるコマンド。  
  
 *hresult* (省略可能)  
 このデータベース コマンドの `HRESULT` を受け取る変数を示します。 変数が存在しない場合は、属性によって自動的に挿入されます。  
  
## <a name="remarks"></a>Remarks  
 **db_source**作成、 [CDataSource](../data/oledb/cdatasource-class.md)と[CSession](../data/oledb/csession-class.md)オブジェクトで、1 つと、OLE DB コンシューマーのデータ ソースの接続を表します。  
  
 使用すると**db_source**クラスで、`CSession`オブジェクト クラスのメンバーになります。  
  
 使用すると**db_source**メソッドのスコープ内で、挿入されたコードを実行メソッドでは、および`CSession`オブジェクトは、ローカル変数として作成されます。  
  
 **db_source**クラスまたはメソッド内では、データ ソースのプロパティを追加します。 組み合わせて使用されます`db_command`(受け取り、 *db_source* *名前*パラメーターとしてその*source_name*パラメーター)。  
  
 コンパイラにクラスの名前は、コンシューマー属性プロバイダーでは、この属性をクラスに適用されます、ときに\_ *YourClassName*、アクセサーで*YourClassName*に付けた名前を指定します、クラス、さらに、コンパイラはというクラスを作成も*YourClassName*から派生した\_ *YourClassName*アクセサー。  クラス ビューでは、両方のクラスが表示されます。  
  
 アプリケーションで使用されるこの属性の例では、サンプルを参照してください。 [AtlAgent](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409)と[MultiRead](http://msdn.microsoft.com/5a2a915a-77dc-492f-94b2-1b809995dd5e)します。  
  
## <a name="example"></a>例  
 このサンプルを呼び出す**db_source**データ ソースへの接続を作成するクラスの`ds`Northwind データベースを使用します。 `ds` 内部で使用できるデータ ソースのハンドル、`CMyCommand`クラス。  
  
```cpp  
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
|**対象**|**クラス**、**構造体**member、method、local|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)   