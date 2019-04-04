---
title: requires_category (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requires_category
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
ms.openlocfilehash: e6621e2cec92eadb0ca4b4ac989b4ca7d578b2ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429845"
---
# <a name="requirescategory"></a>requires_category

ターゲット クラスの必須コンポーネントのカテゴリを指定します。

## <a name="syntax"></a>構文

```cpp
[ requires_category(
  requires_category) ]
```

### <a name="parameters"></a>パラメーター

*requires_category*<br/>
必要なカテゴリの ID。

## <a name="remarks"></a>Remarks

**Requires_category** C++ 属性がターゲット クラスに必須コンポーネントのカテゴリを指定します。 詳細については、[要求する](../../atl/reference/category-macros.md#required_category)を参照してください。

この属性を使用するには、 [coclass](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。

## <a name="example"></a>例

次のコードでは、オブジェクトがコントロールのカテゴリを実装することが必要です。

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

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|次のいずれかまたは: `coclass`、 `progid`、または`vi_progid`します。|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[implements_category](implements-category.md)