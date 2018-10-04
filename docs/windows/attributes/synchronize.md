---
title: 同期 (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.synchronize
dev_langs:
- C++
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 740d99bfbc0da4c290a09a95f5d4f8f227a11fc8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791367"
---
# <a name="synchronize"></a>同期

ターゲット メソッドへのアクセスを同期します。

## <a name="syntax"></a>構文

```cpp
[synchronize]
```

## <a name="remarks"></a>Remarks

**同期**C++ 属性には、オブジェクトのターゲット メソッドを同期するためのサポートが実装されています。 同期により、ターゲット メソッドへのアクセスを制御することで、クラスのメソッド) などの一般的なリソースを使用する複数のオブジェクト。

この属性によって挿入されたコードの呼び出し、適切な`Lock`ターゲット メソッドの先頭には、(スレッド処理モデルによって決定) メソッドです。 メソッドが終了したときに`Unlock`自動的に呼び出されます。 これらの関数の詳細については、次を参照してください[CComAutoThreadModule::Lock。](../../atl/reference/ccomautothreadmodule-class.md#lock)

この属性では、する必要があります、[コクラス](coclass.md)、 [progid](progid.md)、または[vi_progid](vi-progid.md)属性 (またはこれらのいずれかを意味する別の属性) も適用が同じ要素をします。 いずれか 1 つの属性を使用すると、他の 2 つも自動的に適用されます。 たとえば場合、`progid`が適用される`vi_progid`と`coclass`も適用されます。

## <a name="example"></a>例

次のコードの同期、`UpdateBalance`のメソッド、`CMyClass`オブジェクト。

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

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|クラスのメソッド|
|**反復可能**|いいえ|
|**必要な属性**|次のいずれかまたは: `coclass`、 `progid`、または`vi_progid`します。|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)  