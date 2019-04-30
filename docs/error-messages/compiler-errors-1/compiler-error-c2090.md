---
title: コンパイラ エラー C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: d805a4d6e0da0e94288ac36c6680a952b7633b86
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347247"
---
# <a name="compiler-error-c2090"></a>コンパイラ エラー C2090

関数は、配列を返します。

関数は、配列を返すことはできません。 代わりに配列へのポインターを返します。

次の例では、C2090 が生成されます。

```
// C2090.cpp
int func1(void)[] {}   // C2090
```

考えられる解決方法:

```
// C2090b.cpp
// compile with: /c
int* func2(int * i) {
   return i;
}
```