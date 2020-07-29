---
title: switch_type (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_type
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
ms.openlocfilehash: 13ea76e1153e1a42fd41fe0c087a7c7f15416760
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211932"
---
# <a name="switch_type"></a>switch_type

Union 判別として使用される変数の型を識別します。

## <a name="syntax"></a>構文

```cpp
[switch_type(
type
}]
```

### <a name="parameters"></a>パラメーター

*type*<br/>
スイッチの種類には、整数、文字、ブール値、または列挙型を指定できます。

## <a name="remarks"></a>解説

**Switch_type** C++ 属性には、 [switch_type](/windows/win32/Midl/switch-type) MIDL 属性と同じ機能があります。

C++ 属性は、カプセル化された[共用体](/windows/win32/Midl/encapsulated-unions)をサポートしていません。 [カプセル化](/windows/win32/Midl/nonencapsulated-unions)されていない共用体は、次の形式でのみサポートされます。

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

**Switch_type**の使用例については、[大文字と小文字](case-cpp.md)の例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|**`typedef`**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[輸出](export.md)
