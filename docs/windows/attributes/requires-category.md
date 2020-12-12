---
description: '詳細については、次を参照してください: requires_category'
title: requires_category (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requires_category
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
ms.openlocfilehash: 4d2a68e682c4247174ffba630126b5d2f6061788
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327299"
---
# <a name="requires_category"></a>requires_category

ターゲットクラスの必須コンポーネントカテゴリを指定します。

## <a name="syntax"></a>構文

```cpp
[ requires_category(
  requires_category) ]
```

### <a name="parameters"></a>パラメーター

*requires_category*<br/>
必須のカテゴリの ID。

## <a name="remarks"></a>解説

**Requires_category** C++ 属性は、ターゲットクラスに必要なコンポーネントカテゴリを指定します。 詳細については、「 [REQUIRED_CATEGORY](../../atl/reference/category-macros.md#required_category)」を参照してください。

この属性を使用するには、 [coclass](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。

## <a name="example"></a>例

次のコードでは、オブジェクトがコントロールカテゴリを実装する必要があります。

```cpp
// cpp_attr_ref_requires_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLibrary")];

[ coclass, requires_category("CATID_Control"),
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]
class CMyClass {};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**`class`**, **`struct`**|
|**Repeatable**|いいえ|
|**必須属性**|、、またはが1つ以上あり `coclass` `progid` `vi_progid` ます。|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[implements_category](implements-category.md)
