---
description: 詳細については、「コンパイラエラー C2738」を参照してください。
title: コンパイラエラー C2738
ms.date: 11/04/2016
f1_keywords:
- C2738
helpviewer_keywords:
- C2738
ms.assetid: 896b4640-1ee0-4cd8-9910-de3efa30006a
ms.openlocfilehash: 80d56a4491cf6205313b4da66cb695b956cb60a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123098"
---
# <a name="compiler-error-c2738"></a>コンパイラエラー C2738

' 宣言 ': があいまいであるか、' type ' のメンバーではありません。

関数が正しく宣言されていません。

次の例では、C2738 が生成されます。

```cpp
// C2738.cpp
struct A {
   template <class T> operator T*();
   // template <class T> operator T();
};

template <>
A::operator int() {   // C2738

// try the following line instead
// A::operator int*() {

// or use the commented member declaration

   return 0;
}
```
