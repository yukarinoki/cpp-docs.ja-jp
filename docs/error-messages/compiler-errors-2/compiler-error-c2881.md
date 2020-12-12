---
description: 詳細については、「コンパイラエラー C2881」を参照してください。
title: コンパイラ エラー C2881
ms.date: 11/04/2016
f1_keywords:
- C2881
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
ms.openlocfilehash: a1bc3922ce315d29f84309849660b2574631b2fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194359"
---
# <a name="compiler-error-c2881"></a>コンパイラ エラー C2881

' 名前空間 ': ' 名前空間内 ' の別名として既に使用されています

2つの名前空間の別名と同じ名前を使用することはできません。

次の例では、C2881 が生成されます。

```cpp
// C2881.cpp
// compile with: /c
namespace A {
   int k;
}

namespace B {
   int i;
}

namespace C = A;
namespace C = B;   // C2881 C is already an alias for A
```
