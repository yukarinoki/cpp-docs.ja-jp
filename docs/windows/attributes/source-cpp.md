---
title: source (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.source
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
ms.openlocfilehash: f9a1f576e26805c5dd84c2d83cdf3615d0661af3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842768"
---
# <a name="source-c"></a>source (C++)

クラスで、COM オブジェクトの接続ポイントのソースインターフェイスを指定します。 プロパティまたはメソッドで、メンバーがイベントのソースであるオブジェクトまたはバリアントを返すことを示します。

## <a name="syntax"></a>構文

```cpp
[ source(interfaces) ]
```

### <a name="parameters"></a>パラメーター

*interfaces*<br/>
ソース属性をクラスに適用するときに指定する1つ以上のインターフェイス。 Source がプロパティまたはメソッドに適用される場合、このパラメーターは使用されません。

## <a name="remarks"></a>解説

**Source** C++ 属性には、 [source](/windows/win32/Midl/source) MIDL 属性と同じ機能があります。

[既定](default-cpp.md)の属性を使用して、オブジェクトの既定のソースインターフェイスを指定できます。

## <a name="example"></a>例

```cpp
// cpp_attr_ref_source.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid(11111111-1111-1111-1111-111111111111)]
__interface b
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT get_I([out, retval]long *i);
};

[object, uuid(11111111-1111-1111-1111-111111111131)]
__interface c
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT et_I([out, retval]long *i);
};

[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]
class N : public b
{
};

[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]
class NN : public b
{
};
```

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**、 **`struct`** 、 **インターフェイス**|
|**Repeatable**|いいえ|
|**必須属性**|`coclass` (クラスまたは構造体に適用される場合)|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[coclass](coclass.md)
