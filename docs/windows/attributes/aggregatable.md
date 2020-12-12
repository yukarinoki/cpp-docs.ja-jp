---
description: '詳細情報: 集計可能'
title: 集計可能 (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregatable
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
ms.openlocfilehash: 0ba6c96f1b12deb2db91c20f0558961ef1ed6f61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314257"
---
# <a name="aggregatable"></a>aggregatable

クラスが集計をサポートしていることを示します。

## <a name="syntax"></a>構文

```cpp
[ aggregatable(value) ]
```

### <a name="parameters"></a>パラメーター

*value*<br/>
OptionalCOM オブジェクトを集計できるかどうかを示すパラメーター。

- `never` COM オブジェクトを集計できません。

- `allowed` COM オブジェクトは、直接作成することも、集計することもできます。 既定値です。

- `always` COM オブジェクトを直接作成することはできず、集計することはできません。 このオブジェクトに対してを呼び出す場合は、 `CoCreateInstance` 集約オブジェクトの `IUnknown` インターフェイス (制御) を指定する必要があり `IUnknown` ます。

## <a name="remarks"></a>解説

**集計** 可能な C++ 属性には、[集計](/windows/win32/Midl/aggregatable)可能な MIDL 属性と同じ機能があります。 これは、コンパイラが **集計** 可能な属性をから生成された .idl ファイルに渡すことを意味します。

この属性を使用するには、 [coclass](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、が適用されている場合、 `progid` `vi_progid` と `coclass` も適用されます。

### <a name="atl-projects"></a>ATL プロジェクト

この属性が ATL を使用するプロジェクト内で使用されている場合、属性の動作は変わります。 前に説明した動作に加えて、属性は次のマクロのいずれかをターゲットクラスにも追加します。

|パラメーター値|挿入されたマクロ|
|---------------------|--------------------|
|`Never`|[DECLARE_NOT_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|
|`Allowed`|[DECLARE_POLY_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|
|`Always`|[DECLARE_ONLY_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|

## <a name="example"></a>例

```cpp
// cpp_attr_ref_aggregatable.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="MyModule")];

[ coclass, aggregatable(allowed),
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]
class CMyClass {};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|、、またはが1つ以上あり `coclass` `progid` `vi_progid` ます。|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[集計](/windows/win32/com/aggregation)
