---
title: コンパイラ エラー C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: 63f9594eb9ee8a251faafe7323418b343c03063c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165230"
---
# <a name="compiler-error-c2507"></a>コンパイラ エラー C2507

'identifier': 基底クラスで virtual 修飾子が多すぎます

クラスまたは構造体として宣言`virtual`2 回以上。 1 つだけ`virtual`修飾子は基底クラスの一覧には、各クラスのことができます。

次の例では、C2507 が生成されます。

```
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```