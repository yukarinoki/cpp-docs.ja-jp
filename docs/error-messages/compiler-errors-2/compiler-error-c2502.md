---
title: コンパイラ エラー C2502
ms.date: 11/04/2016
f1_keywords:
- C2502
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
ms.openlocfilehash: e23ccae55c40c9652f5a3e1f55c834a968bca784
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165594"
---
# <a name="compiler-error-c2502"></a>コンパイラ エラー C2502

'identifier': 基底クラスでアクセス修飾子が多すぎます

基本クラスには、1 つ以上のアクセス修飾子があります。 1 つのみのアクセス修飾子 (`public`、 `private`、または`protected`) は許可されています。

次の例では、C2502 が生成されます。

```
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```