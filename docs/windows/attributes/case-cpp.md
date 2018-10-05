---
title: ケース (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.case
dev_langs:
- C++
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89a8479564048ec7313fee17a444f3e8d34443b0
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791879"
---
# <a name="case-c"></a>case (C++)

使用される、 [switch_type](switch-type.md)属性、**共用体**します。

## <a name="syntax"></a>構文

```cpp
[ case(value) ]
```

#### <a name="parameters"></a>パラメーター

*値*<br/>
入力の処理を提供する値。 型**値**次の種類のいずれかを指定できます。

- `int`

- `char`

- `boolean`

- `enum`

または、このような種類の識別子。

## <a name="remarks"></a>Remarks

**ケース**C++ 属性と同じ機能を持つ、**ケース**MIDL 属性。 この属性でのみ使用、 [switch_type](switch-type.md)属性。

## <a name="example"></a>例

次のコードの使い方を示しています、**ケース**属性。

```cpp
// cpp_attr_ref_case.cpp
// compile with: /LD
#include <unknwn.h>
[export]
struct SizedValue2 {
   [switch_type(char), switch_is(kind)] union {
      [case(1), string]
          wchar_t* wval;
      [default, string]
          char* val;
   };
    char kind;
};
[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|メンバー、**クラス**または**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[クラス属性](class-attributes.md)  