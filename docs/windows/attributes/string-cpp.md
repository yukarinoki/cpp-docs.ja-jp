---
title: string (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: 96d5e609130b34a4a5f35109ce691c2de470e537
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166162"
---
# <a name="string-c"></a>string (C++)

1次元の**char**、 **wchar_t**、`byte` (またはそれと同等) の配列、またはこのような配列へのポインターを文字列として扱う必要があることを示します。

## <a name="syntax"></a>構文

```cpp
[string]
```

## <a name="remarks"></a>解説

**文字列** C++属性には、[文字列](/windows/win32/Midl/string)MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、インターフェイスおよび typedef で**文字列**を使用する方法を示しています。

```cpp
// cpp_attr_ref_string.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, string] typedef char a[21];
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl
{
   [id(1)] HRESULT Method3([in, string] char *pC);
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|配列または配列へのポインター、インターフェイスパラメーター、インターフェイスメソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[配列属性](array-attributes.md)<br/>
[export](export.md)
