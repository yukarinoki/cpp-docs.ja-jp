---
title: vararg (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vararg
helpviewer_keywords:
- vararg attribute
ms.assetid: 20fc3244-18e9-411c-990e-d5b4fa29a570
ms.openlocfilehash: 4761f65e0862a8de07330305b292b5b3501cac68
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166017"
---
# <a name="vararg"></a>vararg

関数が異なる数の引数をとることを指定します。

## <a name="syntax"></a>構文

```cpp
[vararg]
```

## <a name="remarks"></a>解説

**Vararg** C++属性には、 [vararg](/windows/win32/Midl/vararg) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **vararg**の使用方法を示しています。

```cpp
// cpp_attr_ref_vararg.cpp
// compile with: /LD
#include "unknwn.h"
#include "oaidl.h"
[module(name="MyLibrary")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface X : public IUnknown
{
   [vararg] HRESULT Button([in, satype(VARIANT)]SAFEARRAY *psa);
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)
