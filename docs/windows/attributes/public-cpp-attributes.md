---
title: public (C++ 属性) (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.public
helpviewer_keywords:
- public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
ms.openlocfilehash: 6a19a9a2718ad5f0e7ac59c71e9b4df6a7e92dd2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836908"
---
# <a name="public-c-attributes"></a>public (C++ 属性)

は、.idl ファイル内から参照されていない場合でも、typedef がタイプライブラリに入ることを保証します。

## <a name="syntax"></a>構文

```cpp
[public]
```

## <a name="remarks"></a>解説

C++ 属性には、 **`public`** [public](/windows/win32/Midl/public) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、属性の使用方法を示してい **`public`** ます。

```cpp
// cpp_attr_ref_public.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, public] typedef long MEMBERID;

[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]
__interface IFireTabCtrl : IDispatch
{
   [id(2)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`typedef`**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)
