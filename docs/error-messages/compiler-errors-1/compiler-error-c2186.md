---
title: コンパイラ エラー C2186
ms.date: 11/04/2016
f1_keywords:
- C2186
helpviewer_keywords:
- C2186
ms.assetid: 284bfb7e-ab85-4fcb-9864-1ddf7f6c94ae
ms.openlocfilehash: 191b7109640fd253b24d00d86021d909891a4f95
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62379006"
---
# <a name="compiler-error-c2186"></a>コンパイラ エラー C2186

'operator': void 型の無効なオペランドです

演算子は `void` オペランドを持っています。

次の例では C2186 が生成されます。

```
// C2186.cpp
// compile with: /c
void func1( void );
int  func2( void );
int i = 2 + func1();   // C2186 func1() is type void
int j = 2 + func2();   // OK both operands are type int
```