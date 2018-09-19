---
title: コンパイラ エラー C2884 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2884
dev_langs:
- C++
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d9266162d4608e39982cce1e94751e427bc5e47
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054715"
---
# <a name="compiler-error-c2884"></a>コンパイラ エラー C2884

'name': ローカル関数 'function' と競合してを使用して宣言によって導入されました。

関数を複数回定義しようとしました。 最初の定義は、ローカルの定義です。 持つ名前空間からの 2 つ目は、`using`宣言します。

次の例では、C2884 が生成されます。

```
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```