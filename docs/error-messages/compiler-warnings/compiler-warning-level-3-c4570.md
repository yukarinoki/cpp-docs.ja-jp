---
title: コンパイラの警告 (レベル 3) C4570 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4570
dev_langs:
- C++
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 063c976915e744df8eda3604bdfa121ba21ef36d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099452"
---
# <a name="compiler-warning-level-3-c4570"></a>コンパイラの警告 (レベル 3) C4570

'type': 抽象ですが、抽象関数として明示的に宣言されていません

含む型[抽象](../../windows/abstract-cpp-component-extensions.md)関数は自体が abstract としてマークされました。

## <a name="example"></a>例

次の例では、C4570 が生成されます。

```
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```