---
title: switch_type (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_type
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
ms.openlocfilehash: b461769d3d988efae0be7380e1e0112e3f3cf801
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027858"
---
# <a name="switchtype"></a>switch_type

共用体の判別式として使用される変数の型を識別します。

## <a name="syntax"></a>構文

```cpp
[switch_type(
type
}]
```

### <a name="parameters"></a>パラメーター

*種類*<br/>
スイッチの種類は、整数、文字、ブール値、または列挙型を指定できます。

## <a name="remarks"></a>Remarks

**Switch_type** C++ 属性と同じ機能を持つ、 [switch_type](/windows/desktop/Midl/switch-type) MIDL 属性。

C++ 属性をサポートしていない[共用体をカプセル化された](/windows/desktop/Midl/encapsulated-unions)します。 [カプセル化されていない共用体](/windows/desktop/Midl/nonencapsulated-unions)次の形式でのみサポートされます。

```cpp
// cpp_attr_ref_switch_type.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];
[ export ]
struct SizedValue2 {
   [switch_type("char"), switch_is(kind)] union {
      [case(1), string]
         wchar_t* wval;
      [default, string]
         char* val;
   };
   char kind;
};
```

## <a name="example"></a>例

参照してください、[ケース](case-cpp.md)の使用サンプルの例を**switch_type**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**Typedef**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[export](export.md)