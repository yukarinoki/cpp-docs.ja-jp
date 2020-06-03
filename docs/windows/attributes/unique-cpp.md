---
title: unique (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.unique
helpviewer_keywords:
- unique attribute
ms.assetid: abd7ed14-5ae7-44a8-8333-0058e9c92b2f
ms.openlocfilehash: d8c01e2fcee6b906b7f70370a0d539192e348104
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214436"
---
# <a name="unique-c"></a>unique (C++)

一意のポインターを指定します。

## <a name="syntax"></a>構文

```cpp
[unique]
```

## <a name="remarks"></a>解説

**Unique** C++属性には、[固有](/windows/win32/Midl/unique)の MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Unique**の使用例については、「 [ref](ref-cpp.md)の例」を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**typedef**、 **struct**、 **union**、interface パラメーター、interface メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)
