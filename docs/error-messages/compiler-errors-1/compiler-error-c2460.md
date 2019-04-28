---
title: コンパイラ エラー C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: 414b6e53cf1610a55db984a1127bfc884102494f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230322"
---
# <a name="compiler-error-c2460"></a>コンパイラ エラー C2460

'identifier1': は 'と 'identifier2' で定義されています。

クラスまたは構造体 (`identifier2`) 自体のメンバーとして宣言されています (`identifier1`)。 クラスと構造体の再帰的な定義を指定することはできません。

次の例では、C2460 が生成されます。

```
// C2460.cpp
class C {
   C aC;    // C2460
};
```

代わりに、クラスでポインターの参照を使用します。

```
// C2460.cpp
class C {
   C * aC;    // OK
};
```