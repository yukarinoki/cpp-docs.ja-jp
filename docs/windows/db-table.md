---
title: db_table |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_table
dev_langs:
- C++
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 07c126e2cc6efe0193f6cfd55b84d8dfa7021ffc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605620"
---
# <a name="dbtable"></a>db_table

OLE DB、テーブルを開きます。

## <a name="syntax"></a>構文

```cpp
[ db_table(
   db_table,
   name,
   source_name,
   hresult
) ]
```

#### <a name="parameters"></a>パラメーター

*db_table*  
("Products") などのデータベース テーブルの名前を指定する文字列。

*name* (省略可能)  
テーブルを操作に使用するためのハンドルの名前。 結果の 1 つ以上の行を取得する場合は、このパラメーターを指定する必要があります。 **db_table** 、指定した変数が生成されます*名前*行セットの走査または複数のアクション クエリを実行できます。

*source_name* (省略可能)  
`CSession` 変数、または `db_source` 属性が適用された、コマンドが実行されるクラスのインスタンス。 「 [db_source](../windows/db-source.md)」をご覧ください。

*hresult* (省略可能)  
このデータベース コマンドの HRESULT を受け取る変数を識別します。 変数が存在しない場合は、属性によって自動的に挿入されます。

## <a name="remarks"></a>Remarks

**db_table**作成、 [CTable](../data/oledb/ctable-class.md)オブジェクト、テーブルを開く、OLE DB コンシューマーによって使用されます。 この属性をクラス レベルでのみ使用できます。インラインを使用することはできません。 使用して、`db_column`テーブルの列を変数にバインドするを使用して、`db_param`を区切るために (パラメーターの型などで設定) のパラメーター。

コンパイラにクラスの名前は、コンシューマー属性プロバイダーでは、この属性をクラスに適用されます、ときに\_ *YourClassName*、アクセサーで*YourClassName*に付けた名前を指定します、クラス、さらに、コンパイラはというクラスを作成も*YourClassName*から派生した\_ *YourClassName*アクセサー。  クラス ビューでは、両方のクラスが表示されます。

## <a name="example"></a>例

次の例で使用するため、Products テーブルを開きます`CProducts`します。

```cpp
// db_table.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_table(L"dbo.Products") ]
class CProducts {
   [ db_column("1") ] LONG m_ProductID;
};
```

アプリケーションで使用されるこの属性の例では、サンプルを参照してください。 [AtlAgent](http://msdn.microsoft.com/52bef5da-c1a0-4223-b4e6-9e464b6db409)と[MultiRead](http://msdn.microsoft.com/5a2a915a-77dc-492f-94b2-1b809995dd5e)します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)  
