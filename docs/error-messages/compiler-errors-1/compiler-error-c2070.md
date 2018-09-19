---
title: コンパイラ エラー C2070 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2070
dev_langs:
- C++
helpviewer_keywords:
- C2070
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b23daf8a8c25e132aa0717715a742352537010c8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044081"
---
# <a name="compiler-error-c2070"></a>コンパイラ エラー C2070

'type': 無効な sizeof オペランド

[Sizeof](../../cpp/sizeof-operator.md)演算子に式または型名が必要です。

次の例では、C2070 が生成されます。

```
// C2070.cpp
void func() {}
int main() {
   int a;
   a = sizeof(func);   // C2070
}
```

考えられる解決方法:

```
// C2070b.cpp
void func() {}
int main() {
   int a;
   a = sizeof(a);
}
```