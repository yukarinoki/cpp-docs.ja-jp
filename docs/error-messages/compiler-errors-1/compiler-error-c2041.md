---
title: コンパイラ エラー C2041
ms.date: 11/04/2016
f1_keywords:
- C2041
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
ms.openlocfilehash: 37d32285f9c01efb981c5f02acba21f2d6fe3dc2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165670"
---
# <a name="compiler-error-c2041"></a>コンパイラ エラー C2041

無効な数字基本 'number' の ' character'

指定した文字は、ベース (8 進数または 16 進数) などの有効な数字ではありません。

次の例では、C2041 が生成されます。

```
// C2041.cpp
int i = 081;   // C2041  8 is not a base 8 digit
```

考えられる解決方法:

```
// C2041b.cpp
// compile with: /c
int j = 071;
```