---
description: 詳細については、「コンパイラエラー C2807」を参照してください。
title: コンパイラ エラー C2807
ms.date: 11/04/2016
f1_keywords:
- C2807
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
ms.openlocfilehash: 8ce98ee69bf3c41e822a5ecc40dc794b443b6ff0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320624"
---
# <a name="compiler-error-c2807"></a>コンパイラ エラー C2807

後置形式の ' operator operator ' に対する2番目の仮パラメーターは ' int ' でなければなりません

後置演算子の2番目のパラメーターの型が正しくありません。

次の例では、C2807 が生成されます。

```cpp
// C2807.cpp
// compile with: /c
class X {
public:
   X operator++ ( X );   // C2807 nonvoid parameter
   X operator++ ( int );   // OK, int parameter
};
```
