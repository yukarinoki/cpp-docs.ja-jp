---
description: 詳細については、「コンパイラエラー C2493」を参照してください。
title: コンパイラ エラー C2493
ms.date: 11/04/2016
f1_keywords:
- C2493
helpviewer_keywords:
- C2493
ms.assetid: 68316cd5-682b-49c3-b6ea-23c4e5d296cf
ms.openlocfilehash: 5b9f98fc2f21eadedd8316e60b249a387a0e80dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283675"
---
# <a name="compiler-error-c2493"></a>コンパイラ エラー C2493

無効な形式の __based

式は、 **`__based`** ポインターに基づいている必要があります。

次の例では、C2493 が生成されます。

```cpp
// C2493.cpp
// compile with: /c
char mybase;
int __based(mybase) ptr;   // C2493

// OK
char * mybase;
int __based(mybase) * ptr;
```
