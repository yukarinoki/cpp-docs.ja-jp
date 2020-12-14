---
description: 詳細については、「コンパイラエラー C2770」を参照してください。
title: コンパイラエラー C2770
ms.date: 11/04/2016
f1_keywords:
- C2770
helpviewer_keywords:
- C2770
ms.assetid: 100001b5-80b0-4971-8ff6-9023f443c926
ms.openlocfilehash: 36148e13f0039e38cce26ebdfe4a94c00b0178eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223478"
---
# <a name="compiler-error-c2770"></a>コンパイラエラー C2770

' template ' の明示的な template_or_generic 引数が無効です

明示的なテンプレートまたは汎用引数を持つ関数テンプレート候補により、許可されていない関数型が生成されました。

次の例では、C2770 が生成されます。

```cpp
// C2770.cpp
#include <stdio.h>
template <class T>
int f(typename T::B*);   // expects type with member B

struct Err {};

int main() {
   f<int>(0);   // C2770 int has no B
   // try the following line instead
   f<OK>(0);
}
```
