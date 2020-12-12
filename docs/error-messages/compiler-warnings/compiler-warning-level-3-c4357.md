---
description: '詳細情報: コンパイラの警告 (レベル 3) C4357'
title: コンパイラの警告 (レベル 3) C4357
ms.date: 11/04/2016
f1_keywords:
- C4357
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
ms.openlocfilehash: 89446d131d62134c181c691d8103f75b8cdbe4a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274243"
---
# <a name="compiler-warning-level-3-c4357"></a>コンパイラの警告 (レベル 3) C4357

' function ' を生成するときに、デリゲート ' del ' の仮引数リストの param 配列引数が無視されました

`ParamArray`属性は無視されました `function` 。可変個の引数を指定して呼び出すことはできません。

次の例では、C4357 が生成されます。

```cpp
// C4357.cpp
// compile with: /clr /W3 /c
using namespace System;
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357

public delegate void g(int i, array<Object^>^ varargs);   // OK
```
