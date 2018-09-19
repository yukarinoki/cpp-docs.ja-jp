---
title: コンパイラ エラー C2802 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2802
dev_langs:
- C++
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95b4f64aad9cb14151ca6128bedebcd15ece17ed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061256"
---
# <a name="compiler-error-c2802"></a>コンパイラ エラー C2802

静的メンバー 'operator 演算子' に仮パラメーターがありません。

演算子の宣言によって、`static`メンバー関数は、少なくとも 1 つのパラメーターをいる必要があります。

次の例では、C2802 が生成されます。

```
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```