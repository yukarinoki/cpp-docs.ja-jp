---
title: コンパイラ エラー C2548
ms.date: 11/04/2016
f1_keywords:
- C2548
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
ms.openlocfilehash: 2c680d86a0ea69d67f9e53a481f2f096f4cc7878
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659595"
---
# <a name="compiler-error-c2548"></a>コンパイラ エラー C2548

'class::member': パラメーターのパラメーターの既定のパラメーターがありません

既定のパラメーター リストには、パラメーターがありません。 パラメーター リストの任意の場所の既定のパラメーターを指定する場合は、後続のすべてのパラメーターの既定のパラメーターを定義する必要があります。

## <a name="example"></a>例

次の例では、C2548 が生成されます。

```
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```