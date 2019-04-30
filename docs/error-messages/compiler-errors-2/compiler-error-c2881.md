---
title: コンパイラ エラー C2881
ms.date: 11/04/2016
f1_keywords:
- C2881
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
ms.openlocfilehash: 82a4fbe94bc7250244d57f549e52037d6a54c784
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378917"
---
# <a name="compiler-error-c2881"></a>コンパイラ エラー C2881

'namespace1': 'namespace2' のエイリアスとして既に使用されます

同じ名前は、2 つの名前空間のエイリアスとして使用できません。

次の例では、C2881 が生成されます。

```
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