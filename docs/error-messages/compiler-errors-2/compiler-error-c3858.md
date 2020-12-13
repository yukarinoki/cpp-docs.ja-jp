---
description: 詳細については、「コンパイラエラー C3858」を参照してください。
title: コンパイラ エラー C3858
ms.date: 11/04/2016
f1_keywords:
- C3858
helpviewer_keywords:
- C3858
ms.assetid: 46e178d5-a55f-4ac6-a9dc-561fbcba5c1f
ms.openlocfilehash: 16547372e30d20f961f1c7f011894b021d96d587
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336127"
---
# <a name="compiler-error-c3858"></a>コンパイラ エラー C3858

' type ': 現在のスコープでは再宣言できません

同じスコープ内で型を2回宣言することはできません。

次の例では、C3858 が生成されます。

```cpp
// C3858.cpp
// compile with: /LD
template <class T>
struct Outer
{
   struct Inner;
};

template <class T>
struct Outer<T>::Inner;   // C3858
// try the following line instead
// struct Outer<T>::Inner{};
```
