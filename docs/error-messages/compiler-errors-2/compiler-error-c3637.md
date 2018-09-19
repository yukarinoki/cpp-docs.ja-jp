---
title: コンパイラ エラー C3637 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3637
dev_langs:
- C++
helpviewer_keywords:
- C3637
ms.assetid: 72391377-8519-43d9-870a-73a6423deb74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 958ffc0d3aab641859b13570a94b159de80f2c7d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117466"
---
# <a name="compiler-error-c3637"></a>コンパイラ エラー C3637

'function': friend 関数の定義は、関数型の特殊化をすることはできません

フレンド関数は、テンプレートまたはジェネリックに対して適切に定義されました。

次の例では、C3637 が生成されます。

```
// C3637.cpp
template <class T>
void f();

struct S {
   friend void f<int>() {}   // C3637
};
```

考えられる解決方法:

```
// C3637b.cpp
// compile with: /c
template <class T>
void f();

struct S {
   friend void f() {}
};
```

C3637 は、ジェネリックを使用しているときにも発生します。

```
// C3637c.cpp
// compile with: /clr

generic <class T>
void gf();

struct S {
   friend void gf<int>() {}   // C3637
};
```

考えられる解決方法:

```
// C3637d.cpp
// compile with: /clr /c
generic <class T>
void gf();

struct S {
   friend void gf() {}
};
```