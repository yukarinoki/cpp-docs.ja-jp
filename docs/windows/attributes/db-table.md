---
title: db_table (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 07910693b3236e3a90d7ad420392552d90abd747
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052149"
---
# <a name="dbtable"></a>db_table

OLE DB、テーブルを開きます。

## <a name="syntax"></a>構文

```cpp
[ db_table(db_table, name, source_name, hresult) ]
```

#### <a name="parameters"></a>パラメーター

*db_table*<br/>
("Products") などのデータベース テーブルの名前を指定する文字列。

*name*<br/>
(省略可能)テーブルを操作に使用するためのハンドルの名前。 結果の 1 つ以上の行を取得する場合は、このパラメーターを指定する必要があります。 **db_table** 、指定した変数が生成されます*名前*行セットの走査または複数のアクション クエリを実行できます。

*source_name*<br/>
(省略可能)`CSession`変数またはを持つクラスのインスタンス、`db_source`コマンドが実行されることに適用される属性。 「 [db_source](db-source.md)」をご覧ください。

*hresult*<br/>
(省略可能)このデータベース コマンドの HRESULT を受け取る変数を識別します。 変数が存在しない場合は、属性によって自動的に挿入されます。

## <a name="remarks"></a>Remarks

**db_table**作成、 [CTable](../../data/oledb/ctable-class.md)オブジェクト、テーブルを開く、OLE DB コンシューマーによって使用されます。 この属性をクラス レベルでのみ使用できます。インラインを使用することはできません。 使用して、`db_column`テーブルの列を変数にバインドするを使用して、`db_param`を区切るために (パラメーターの型などで設定) のパラメーター。

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

アプリケーションで使用されるこの属性の例では、サンプルを参照してください。 [AtlAgent](https://github.com/Microsoft/VCSamples)と[MultiRead](https://github.com/Microsoft/VCSamples)します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー属性](ole-db-consumer-attributes.md)
