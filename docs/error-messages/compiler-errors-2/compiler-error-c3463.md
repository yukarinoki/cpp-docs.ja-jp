---
title: コンパイラ エラー C3463
ms.date: 11/04/2016
f1_keywords:
- C3463
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
ms.openlocfilehash: a0c7772291085bcd872cbc1ca23b79d2fa829ad9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448673"
---
# <a name="compiler-error-c3463"></a>コンパイラ エラー C3463

'type':型は属性 'implements' で使用できません

[implements](../../windows/implements-cpp.md) 属性に正しくない型が渡されました。 たとえば、 `implements`にインターフェイスを渡すことはできますが、インターフェイスへのポインターを渡すことはできません。

## <a name="example"></a>例

次の例では C3463 が生成されます。

```
// C3463.cpp
// compile with: /c
#include <windows.h>
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface X {};

typedef X* PX;

[ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=PX) ]   // C3463
// try the following line instead
// [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=X) ]
class CMyClass : public X {};
```