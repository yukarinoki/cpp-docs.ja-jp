---
title: コンパイラ エラー C3463 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3463
dev_langs:
- C++
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2169897a3ad4a6d2d78f22b7ea323d70020e1b12
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036619"
---
# <a name="compiler-error-c3463"></a>コンパイラ エラー C3463

'type':型は属性 'implements' で使用できません

無効な型が渡された、[実装](../../windows/implements-cpp.md)属性。 たとえば、 `implements`にインターフェイスを渡すことはできますが、インターフェイスへのポインターを渡すことはできません。

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