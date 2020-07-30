---
title: コンパイラ エラー C2186
ms.date: 11/04/2016
f1_keywords:
- C2186
helpviewer_keywords:
- C2186
ms.assetid: 284bfb7e-ab85-4fcb-9864-1ddf7f6c94ae
ms.openlocfilehash: a11b6b7aad4469c7151648a5f092265a4cb9d504
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209800"
---
# <a name="compiler-error-c2186"></a>コンパイラ エラー C2186

'operator': void 型の無効なオペランドです

演算子にはオペランドがあり **`void`** ます。

次の例では C2186 が生成されます。

```cpp
// C2186.cpp
// compile with: /c
void func1( void );
int  func2( void );
int i = 2 + func1();   // C2186 func1() is type void
int j = 2 + func2();   // OK both operands are type int
```
