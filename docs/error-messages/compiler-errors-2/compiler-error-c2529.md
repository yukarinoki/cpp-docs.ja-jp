---
description: 詳細については、「コンパイラエラー C2529」を参照してください。
title: コンパイラ エラー C2529
ms.date: 11/04/2016
f1_keywords:
- C2529
helpviewer_keywords:
- C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
ms.openlocfilehash: 007fa64332e9f7b5eb993f722e66924584d9c342
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302271"
---
# <a name="compiler-error-c2529"></a>コンパイラ エラー C2529

' name ': 参照への参照は無効です

このエラーは、ポインター構文を使用し、ポインターへの参照を宣言することで修正できます。

次の例では、C2529 が生成されます。

```cpp
// C2529.cpp
// compile with: /c
int i;
int &ri = i;
int &(&rri) = ri;   // C2529
```
