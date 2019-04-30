---
title: implements_category (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.implements_category
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
ms.openlocfilehash: beca804fae8d6e82b4664102b39d76a23e66ca59
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409409"
---
# <a name="implementscategory"></a>implements_category

ターゲット クラスで実装されたコンポーネントのカテゴリを指定します。

## <a name="syntax"></a>構文

```cpp
[ implements_category(implements_category="uuid") ]
```

### <a name="parameters"></a>パラメーター

*implements_category*<br/>
実装済みのカテゴリの ID。

## <a name="remarks"></a>Remarks

**Implements_category** C++属性がターゲット クラスで実装されたコンポーネントのカテゴリを指定します。 これは、カテゴリのマップを作成して、によって指定された別のエントリを追加することで、 **implements_category**属性。 詳細については、次を参照してください。[コンポーネントのカテゴリと方法は、作業には何ですか?](https://msdn.microsoft.com/library/windows/desktop/ms694322)します。

この属性を使用するには、 [coclass](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば場合、`progid`が適用される`vi_progid`と`coclass`も適用されます。

## <a name="example"></a>例

次のコードでは、次のオブジェクト実装を指定します、`Control`カテゴリ。

```cpp
// cpp_attr_ref_implements_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLib")];
[ coclass, implements_category("CATID_Control"),
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]
class CMyClass {};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|はい|
|**必要な属性**|次のいずれか: `coclass`、 `progid`、または `vi_progid`|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../../atl/reference/category-macros.md#implemented_category)