---
title: ref (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ref
helpviewer_keywords:
- ref attribute
ms.assetid: 67e82d3e-07d9-4ef8-bf2b-0a4491d12557
ms.openlocfilehash: 92b3c7b2cddf17a70a949914ef82540457696f20
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846109"
---
# <a name="ref-c"></a>ref (C++)

参照ポインターを識別します。

## <a name="syntax"></a>構文

```cpp
[ref]
```

## <a name="remarks"></a>解説

**Ref** C++ 属性には[ref](/windows/win32/Midl/ref) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **ref** 属性の使用方法を示しています。

```cpp
// cpp_attr_ref_ref.cpp
// compile with: /LD
#include <windows.h>
[module(name="ATLFIRELib")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1), unique] char * GetFirstName([in, ref] char * pszFullName );
};
```

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`typedef`**、interface パラメーター、interface メソッド|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)
