---
description: 詳細については、「コンパイラエラー C2277」を参照してください。
title: コンパイラ エラー C2277
ms.date: 11/04/2016
f1_keywords:
- C2277
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
ms.openlocfilehash: e5113587b22373eae4a197b5913430659447810a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344433"
---
# <a name="compiler-error-c2277"></a>コンパイラ エラー C2277

' identifier ': このメンバー関数のアドレスを取得できません

メンバー関数のアドレスを取得することはできません。

次の例では、C2277 が生成されます。

```cpp
// C2277.cpp
class A {
public:
   A();
};
(*pctor)() = &A::A;   // C2277
```
