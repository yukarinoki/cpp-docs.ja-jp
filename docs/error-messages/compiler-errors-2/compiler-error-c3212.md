---
description: 詳細については、「コンパイラエラー C3212」を参照してください。
title: コンパイラ エラー C3212
ms.date: 11/04/2016
f1_keywords:
- C3212
helpviewer_keywords:
- C3212
ms.assetid: 9e271bb6-a51f-4b96-b26b-9f4ca28fca0a
ms.openlocfilehash: f78234f1176319739be74841e0a982afa591045d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173845"
---
# <a name="compiler-error-c3212"></a>コンパイラ エラー C3212

'specialization': テンプレート メンバーの明示的特殊化は、明示的特殊化のメンバーである必要があります

明示的特殊化の形式が正しくありません。

次の例では C3212 が生成されます。

```cpp
// C3212.cpp
// compile with: /LD
template <class T>
struct S {
   template <class T1>
   struct S1;
};

template <class T>   // C3212
template <>
struct S<T>::S1<int> {};

/*
// try the following instead
template <>
template <>
struct S<int>::S1<int> {};
*/

/*
// or, the following
template <>
struct S<int> {
   template <class T1>
   struct S1;
};

template <>
struct S<int>::S1<int> {
};
*/
```
