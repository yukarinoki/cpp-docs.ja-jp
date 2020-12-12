---
description: 詳細については、「コンパイラエラー C2898」を参照してください。
title: コンパイラ エラー C2898
ms.date: 11/04/2016
f1_keywords:
- C2898
helpviewer_keywords:
- C2898
ms.assetid: 68466e11-2541-4f6b-b772-13a642f30dfb
ms.openlocfilehash: 3cffde947d5e2940a7625dda873b27e08324421a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270772"
---
# <a name="compiler-error-c2898"></a>コンパイラ エラー C2898

' 宣言 ': メンバー関数テンプレートを仮想にすることはできません

次の例では、C2898 が生成されます。

```cpp
// C2898.cpp
// compile with: /c
class X {
public:
   template<typename T> virtual void f(T t) {}   // C2898
};
```
