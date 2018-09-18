---
title: コンパイラ エラー C2460 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb2d85ffbc7aa799f0688fbb10021a04ef9455ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022621"
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