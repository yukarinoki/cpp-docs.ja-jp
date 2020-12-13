---
description: 詳細については、「コンパイラエラー C2460」を参照してください。
title: コンパイラ エラー C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: 6a6b521b356d4005906e97b085271369f2624c46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341855"
---
# <a name="compiler-error-c2460"></a>コンパイラ エラー C2460

' identifier1 ': 定義されている ' identifier2 ' を使用します

クラスまたは構造体 ( `identifier2` ) がそれ自体 () のメンバーとして宣言されて `identifier1` います。 クラスと構造体の再帰定義は許可されていません。

次の例では、C2460 が生成されます。

```cpp
// C2460.cpp
class C {
   C aC;    // C2460
};
```

代わりに、クラスでポインター参照を使用します。

```cpp
// C2460.cpp
class C {
   C * aC;    // OK
};
```
