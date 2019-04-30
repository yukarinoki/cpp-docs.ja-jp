---
title: コンパイラ エラー C2572
ms.date: 11/04/2016
f1_keywords:
- C2572
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
ms.openlocfilehash: 78402c054573de8c9860e96b6abe60ec5c3cfe38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395522"
---
# <a name="compiler-error-c2572"></a>コンパイラ エラー C2572

'class::member': 既定のパラメーターの再定義: パラメーターのパラメーター

既定のパラメーターを再定義することはできません。 別の値は、未定義のままパラメーター、既定のパラメーターに必要場合です。

次の例では、C2572 が生成されます。

```
// C2572.cpp
// compile with: /c
void f(int i = 1);   // function declaration

// function definition
void f(int i = 1) {}   // C2572

// try the following line instead
// void f(int i) {}
```