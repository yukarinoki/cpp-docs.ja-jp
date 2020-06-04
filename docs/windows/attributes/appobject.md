---
title: appobject (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.appobject
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
ms.openlocfilehash: ebbb3ce71dc9b947ef49a42ee41a5ce2d5abbb34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168513"
---
# <a name="appobject"></a>appobject

コクラスをアプリケーションオブジェクトとして識別します。このオブジェクトは、完全な .exe アプリケーションに関連付けられています。また、コクラスの関数とプロパティは、この[タイプライブラリ](../../mfc/automation-clients-using-type-libraries.md)でグローバルに使用できることを示します。

## <a name="syntax"></a>構文

```cpp
[appobject]
```

## <a name="remarks"></a>解説

**Appobject** C++属性には、 [appobject](/windows/win32/Midl/appobject) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **appobject**を含む属性ブロックの前にある単純なクラス定義を示しています。

```cpp
// cpp_attr_ref_appobject.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];

[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]
__interface ICustom {};

[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]
class A : public ICustom {
   int i;
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|`coclass`|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)
