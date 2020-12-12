---
description: '詳細情報: ライセンス'
title: ライセンス済み (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.licensed
helpviewer_keywords:
- licensed attribute
ms.assetid: 09cf3b4a-d3f2-43e3-9180-d420333b23bf
ms.openlocfilehash: 348180412c1e8b19994cf5ef3e9bedb4115bfbda
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327525"
---
# <a name="licensed"></a>licensed

適用先の COM オブジェクトがライセンスされており、を使用してインスタンス化する必要があることを示し `IClassFactory2` ます。

## <a name="syntax"></a>構文

```cpp
[licensed]
```

## <a name="remarks"></a>解説

**ライセンス** された C++ 属性には、[ライセンス](/windows/win32/Midl/licensed)された MIDL 属性と同じ機能があります。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_licensed.cpp
// compile with: /LD
#include "unknwn.h"
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI : IUnknown {
   HRESULT f();
};

[coclass, version("2.1"), uuid(12345678-1111-2222-3333-123456789012),
licensed, threading(free), progid(some.name)]
class CSample : public IMyI {
public:
   int nSize;
};

[module(name="MyLibrary", version="1.0", helpstring="My Library Block")];
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|`coclass`|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[クラス属性](class-attributes.md)
