---
description: 詳細については、「コンパイラエラー C2765」を参照してください。
title: コンパイラエラー C2765
ms.date: 11/04/2016
f1_keywords:
- C2765
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
ms.openlocfilehash: 496f28645dddc0ac426716cc80ee0d6760042ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239546"
---
# <a name="compiler-error-c2765"></a>コンパイラエラー C2765

' function ': 関数テンプレートの明示的な特殊化に既定の引数を指定することはできません

関数テンプレートの明示的な特殊化では、既定の引数を使用できません。 詳細については、「 [関数テンプレートの明示的な特殊化](../../cpp/explicit-specialization-of-function-templates.md)」を参照してください。

次の例では、C2765 が生成されます。

```cpp
// C2765.cpp
template<class T> void f(T t) {};

template<> void f<char>(char c = 'a') {}   // C2765
// try the following line instead
// template<> void f<char>(char c) {}
```
