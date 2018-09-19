---
title: コンパイラ エラー C2503 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2503
dev_langs:
- C++
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b57ce28851d3948db5c14889fceb3594dbe2617a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048930"
---
# <a name="compiler-error-c2503"></a>コンパイラ エラー C2503

'class': 基底クラスは、サイズが 0 の配列を含めることはできません

基底クラスまたは構造体には、サイズが 0 の配列が含まれています。 配列クラスでは、少なくとも 1 つの要素が必要です。

次の例では、C2503 が生成されます。

```
// C2503.cpp
// compile with: /c
class A {
   public:
   int array [];
};

class B : A {};    // C2503

class C {
public:
   int array [10];
};

class D : C {};
```