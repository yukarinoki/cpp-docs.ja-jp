---
title: 文字列 (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.string
dev_langs:
- C++
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24d11a056d248e27be236f710cdd0532b3beca2d
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791823"
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

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|配列またはポインター、配列、インターフェイスのパラメーター、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[配列属性](array-attributes.md)<br/>
[export](export.md)  