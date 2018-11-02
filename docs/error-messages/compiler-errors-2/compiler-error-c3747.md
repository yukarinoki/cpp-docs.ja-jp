---
title: コンパイラ エラー C3747
ms.date: 11/04/2016
f1_keywords:
- C3747
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
ms.openlocfilehash: 860a990e35b0d51dfc1316a11a2d2512eb40c273
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574359"
---
# <a name="compiler-error-c3747"></a>コンパイラ エラー C3747

既定の型パラメーターがありません: パラメーターのパラメーター

ジェネリックまたはテンプレートのパラメーターに既定値は、既定値がないパラメーターでパラメーター リストの後にことはできません。

次の例では、C3747 が生成されます。

```
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

考えられる解決方法:

```
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```