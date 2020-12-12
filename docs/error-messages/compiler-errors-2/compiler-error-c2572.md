---
description: 詳細については、「コンパイラエラー C2572」を参照してください。
title: コンパイラ エラー C2572
ms.date: 11/04/2016
f1_keywords:
- C2572
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
ms.openlocfilehash: ff0549309df0567e2d1d7f26f98f95c3c3b629d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208958"
---
# <a name="compiler-error-c2572"></a>コンパイラ エラー C2572

' class:: member ': 既定のパラメーターの再定義: パラメーター param

既定のパラメーターを再定義することはできません。 パラメーターに別の値が必要な場合は、既定のパラメーターを未定義のままにする必要があります。

次の例では、C2572 が生成されます。

```cpp
// C2572.cpp
// compile with: /c
void f(int i = 1);   // function declaration

// function definition
void f(int i = 1) {}   // C2572

// try the following line instead
// void f(int i) {}
```
