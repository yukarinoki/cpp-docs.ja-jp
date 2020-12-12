---
description: '詳細情報: synchronize'
title: synchronize (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.synchronize
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
ms.openlocfilehash: bbee19406396e4041b4d7ca1e2acf2b8d7193494
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329559"
---
# <a name="synchronize"></a>synchronize

ターゲットメソッドへのアクセスを同期します。

## <a name="syntax"></a>構文

```cpp
[synchronize]
```

## <a name="remarks"></a>解説

**Synchronize** C++ 属性は、オブジェクトのターゲットメソッドを同期するためのサポートを実装します。 同期を使用すると、ターゲットメソッドのアクセスを制御することによって、複数のオブジェクトが共通のリソース (クラスのメソッドなど) を使用できるようになります。

この属性によって挿入されたコードは、 `Lock` ターゲットメソッドの先頭にある (スレッドモデルによって決定される) 適切なメソッドを呼び出します。 メソッドが終了すると、 `Unlock` が自動的に呼び出されます。 これらの関数の詳細については、「 [CComAutoThreadModule:: Lock](../../atl/reference/ccomautothreadmodule-class.md#lock) 」を参照してください。

この属性を使用するには、 [coclass](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、が適用されている場合、 `progid` `vi_progid` と `coclass` も適用されます。

## <a name="example"></a>例

次のコードは、オブジェクトのメソッドの同期を提供し `UpdateBalance` `CMyClass` ます。

```cpp
// cpp_attr_ref_synchronize.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="SYNC")];

[coclass,
threading(both),
vi_progid("MyProject.MyClass"),
progid("MyProject.MyClass.1"),
uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")
]
class CMyClass {
   float m_nBalance;

   [synchronize]
   void UpdateBalance(float nAdjust) {
      m_nBalance += nAdjust;
   }
};
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|Class メソッド、メソッド|
|**Repeatable**|いいえ|
|**必須属性**|、、またはが1つ以上あり `coclass` `progid` `vi_progid` ます。|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)
