---
description: '詳細情報: 制限付き'
title: restricted (C++ COM 属性)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: 8c0dc33d1ae7cff3625f1a938cac05c7ac72f474
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329625"
---
# <a name="restricted"></a>restricted

モジュール、インターフェイス、またはディスパッチインターフェイスのメンバーを任意に呼び出すことができないことを指定します。

## <a name="syntax"></a>構文

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>パラメーター

*interfaces*<br/>
COM オブジェクトで任意に呼び出すことができない1つ以上のインターフェイス。 このパラメーターは、クラスに適用された場合にのみ有効です。

## <a name="remarks"></a>解説

**Restricted** C++ 属性には、[制限付き](/windows/win32/Midl/restricted)MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **制限** された属性の使用方法を示しています。

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|Interface メソッド、 **interface**、 **`class`** 、 **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|**coclass** (またはに適用された場合 **`class`** **`struct`** )|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[メソッド属性](method-attributes.md)
