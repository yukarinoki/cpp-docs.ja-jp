---
title: 文字列 (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.string
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
ms.openlocfilehash: e1b528fb922a15655de403c6099ee1d36e2fb3de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407277"
---
# <a name="string-c"></a>string (C++)

示します、1 次元**char**、 **wchar_t**、 `byte` (または同等の) このような配列へのポインターまたは配列を文字列として扱う必要があります。

## <a name="syntax"></a>構文

```cpp
[string]
```

## <a name="remarks"></a>Remarks

**文字列**C++ 属性と同じ機能を持つ、[文字列](/windows/desktop/Midl/string)MIDL 属性。

## <a name="example"></a>例

次のコードは、使用する方法を示しています**文字列**インターフェイスと typedef:。

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
|**対象**|配列またはポインター、配列、インターフェイスのパラメーター、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[配列属性](array-attributes.md)<br/>
[export](export.md)