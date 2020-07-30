---
title: コンパイラエラー C2703
ms.date: 11/04/2016
f1_keywords:
- C2703
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
ms.openlocfilehash: 62e03d1edc5806a9babc44eaf2dc388e3ed81de9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221108"
---
# <a name="compiler-error-c2703"></a>コンパイラエラー C2703

無効な __leave ステートメント

* * `__leave** statement must be inside a ` __Try ' ブロック。

次の例では、C2703 が生成されます。

```cpp
// C2703.cpp
int main() {
   __leave;   // C2703
   __try {
      // try the following line instead
      __leave;
   }
   __finally {}
}
```
