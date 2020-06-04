---
title: synchronize (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.synchronize
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
ms.openlocfilehash: a0f4702de4cfde8586cc573f9ff5a6195984d207
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214514"
---
# <a name="synchronize"></a>synchronize

ターゲットメソッドへのアクセスを同期します。

## <a name="syntax"></a>構文

```cpp
[synchronize]
```

## <a name="remarks"></a>解説

**Synchronize** C++属性は、オブジェクトのターゲットメソッドを同期するためのサポートを実装します。 同期を使用すると、ターゲットメソッドのアクセスを制御することによって、複数のオブジェクトが共通のリソース (クラスのメソッドなど) を使用できるようになります。

この属性によって挿入されたコードは、ターゲットメソッドの先頭にある適切な `Lock` メソッド (スレッドモデルによって決まります) を呼び出します。 メソッドが終了すると、`Unlock` が自動的に呼び出されます。 これらの関数の詳細については、「 [CComAutoThreadModule:: Lock](../../atl/reference/ccomautothreadmodule-class.md#lock) 」を参照してください。

この属性を使用するには、 [coclass](coclass.md)、 [progid](progid.md)、または [vi_progid](vi-progid.md) 属性 (または、これらのいずれかを意味する別の属性) も同じ要素に適用する必要があります。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば、`progid` が適用されている場合、`vi_progid` と `coclass` も適用されます。

## <a name="example"></a>例

次のコードは、`CMyClass` オブジェクトの `UpdateBalance` メソッドの同期を提供します。

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

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|Class メソッド、メソッド|
|**反復可能**|いいえ|
|**必要な属性**|`coclass`、`progid`、または `vi_progid`の1つ以上。|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[COM 属性](com-attributes.md)
