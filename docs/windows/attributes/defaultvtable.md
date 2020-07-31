---
title: defaultvtable (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultvtable
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
ms.openlocfilehash: 2da0d8070f961f1ae0fc075585eb28881f712fb4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215258"
---
# <a name="defaultvtable"></a>defaultvtable

COM オブジェクトの既定の vtable インターフェイスとしてインターフェイスを定義します。

## <a name="syntax"></a>構文

```cpp
[ defaultvtable(interface) ]
```

### <a name="parameters"></a>パラメーター

*interface*<br/>
COM オブジェクトの既定の vtable を持つ、指定されたインターフェイス。

## <a name="remarks"></a>解説

**Defaultvtable** C++ 属性には、 [defaultvtable](/windows/win32/Midl/defaultvtable) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **defaultvtable**を使用して既定のインターフェイスを指定するクラスの属性を示しています。

```cpp
// cpp_attr_ref_defaultvtable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI1 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMyI2 {
   HRESULT x();
};

[object, uuid("00000000-0000-0000-0000-000000000003")]
__interface IMyI3 {
   HRESULT x();
};

[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),
uuid("00000000-0000-0000-0000-000000000004")]
class CMyC3 : public IMyI3 {};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|**coclass**|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[クラス属性](class-attributes.md)
