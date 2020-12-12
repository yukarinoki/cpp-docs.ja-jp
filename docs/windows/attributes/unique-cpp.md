---
description: '詳細情報: unique (C++)'
title: unique (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.unique
helpviewer_keywords:
- unique attribute
ms.assetid: abd7ed14-5ae7-44a8-8333-0058e9c92b2f
ms.openlocfilehash: 46db247e5e2106821fb3ab36746c1586409388ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118317"
---
# <a name="unique-c"></a>unique (C++)

一意のポインターを指定します。

## <a name="syntax"></a>構文

```cpp
[unique]
```

## <a name="remarks"></a>解説

**一意** の C++ 属性には、[固有](/windows/win32/Midl/unique)の MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Unique** の使用例については、「 [ref](ref-cpp.md)の例」を参照してください。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`typedef`**、 **`struct`** 、 **`union`** 、interface パラメーター、interface メソッド|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)
