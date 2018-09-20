---
title: switch_type |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.switch_type
dev_langs:
- C++
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ed603a416e7f56e4415ce36ad4b3fd8059d311f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415747"
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

*type*<br/>
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

参照してください、[ケース](../windows/case-cpp.md)の使用サンプルの例を**switch_type**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**typedef**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[export](../windows/export.md)  