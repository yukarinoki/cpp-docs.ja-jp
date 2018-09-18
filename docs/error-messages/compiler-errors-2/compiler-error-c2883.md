---
title: コンパイラ エラー C2883 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2883
dev_langs:
- C++
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50cc5b2abb34fae21bea78aa146e74b9aa9491c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019264"
---
# <a name="compiler-error-c2883"></a>コンパイラ エラー C2883

'name': 'identifier' を使用して宣言によって導入されると競合して関数の宣言

関数を複数回定義しようとしました。 最初の定義が、名前空間から行われた、`using`宣言します。 2 つ目は、ローカルの定義をしました。

次の例では、C2883 が生成されます。

```
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```