---
title: コンパイラ エラー C2594 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2594
dev_langs:
- C++
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9be22544930bb94c36ec5906cbf60d5caac143fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058017"
---
# <a name="compiler-error-c2594"></a>コンパイラ エラー C2594

'operator': 'type1' から 'type2' へのあいまいな変換

変換なし*type1*に*type2*が他よりも直接的な。 変換する 2 つの考えられる解決策をお勧め*type1*に*type2*します。 最初のオプションからの直接変換を定義する*type1*に*type2*、2 番目のオプションからの変換のシーケンスを指定して*type1*に*type2*します。

次の例では、C2594 が生成されます。 エラーに提案された解決策は、変換のシーケンスを示します。

```
// C2594.cpp
// compile with: /c
struct A{};
struct I1 : A {};
struct I2 : A {};
struct D : I1, I2 {};

A *f (D *p) {
   return (A*) (p);    // C2594

// try the following line instead
// return static_cast<A *>(static_cast<I1 *>(p));
}
```