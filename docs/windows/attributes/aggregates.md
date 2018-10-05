---
title: 集計 (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregates
dev_langs:
- C++
helpviewer_keywords:
- aggregates attribute
- aggregation [C++]
- aggregate objects [C++], aggregates attribute
- aggregates [C++]
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5817267977ea1c8eeca00ef98357f31cb92d5bf4
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791938"
---
# <a name="aggregates"></a>aggregates

オブジェクトが CLSID で指定されたオブジェクトを集約することを示します。

## <a name="syntax"></a>構文

```cpp
[ aggregates(clsid, variable_name) ]
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
集約可能オブジェクトの CLSID を指定します。

*variable_name*<br/>
挿入する変数の名前。 この変数が含まれています、`IUnknown`の集約対象オブジェクト。

## <a name="remarks"></a>Remarks

オブジェクトに適用すると、 **aggregates** C++ 属性は ( `clsid`によって指定された) 集約対象オブジェクトのアウター ラッパーを実装します。

この属性では、する必要があります、[コクラス](coclass.md)、 [progid](progid.md)、または[vi_progid](vi-progid.md)属性 (またはこれらのいずれかを意味する別の属性) も適用が同じ要素をします。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば場合、`progid`が適用される`vi_progid`と`coclass`も適用されます。

### <a name="atl-projects"></a>ATL プロジェクト

この属性が ATL を使用するプロジェクト内で使用されている場合、属性の動作は変わります。 まず、次のエントリがターゲット オブジェクトの COM マップに追加されます。

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```

2 番目、 [DECLARE_GET_CONTROLLING_UNKNOWN](../../atl/reference/aggregation-and-class-factory-macros.md#declare_get_controlling_unknown)マクロも追加されます。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_aggregates.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

// requires 'aggregatable.dll'
// see aggregatable attribute to create 'aggregatable.dll'
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;

[module (name="MYObject")];
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]
__interface IObject
{
};

[ coclass, aggregates(__uuidof(CMyClass)),
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]
struct CObject : IObject
{
   int i;
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|はい|
|**必要な属性**|次のいずれかまたは: `coclass`、 `progid`、または`vi_progid`します。|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[集計](/windows/desktop/com/aggregation)<br/>
[集約可能](/windows/desktop/Midl/aggregatable)<br/>
[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](../../atl/reference/com-interface-entry-macros.md#com_interface_entry_autoaggregate_blind)  