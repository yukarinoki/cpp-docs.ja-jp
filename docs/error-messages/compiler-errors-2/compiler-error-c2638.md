---
description: 詳細については、「コンパイラエラー C2638」を参照してください。
title: コンパイラエラー C2638
ms.date: 11/04/2016
f1_keywords:
- C2638
helpviewer_keywords:
- C2638
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
ms.openlocfilehash: 82921314b8861239e1686c95f8a0c3bc4eb41082
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272449"
---
# <a name="compiler-error-c2638"></a>コンパイラエラー C2638

' identifier ': __based 修飾子は、メンバーへのポインターでは無効です

修飾子は、 **`__based`** メンバーへのポインターには使用できません。

次の例では、C2638 が生成されます。

```cpp
// C2638.cpp
void *a;

class C {
public:
   int i;
   int j;
   int func();
};
int __based (a) C::* cpi = &C::i;  // C2638
int (__based (a) C::* cpf)() = &C::func; // c2638
```
