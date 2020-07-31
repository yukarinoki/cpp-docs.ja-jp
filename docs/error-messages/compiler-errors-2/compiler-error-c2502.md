---
title: コンパイラ エラー C2502
ms.date: 11/04/2016
f1_keywords:
- C2502
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
ms.openlocfilehash: bb0e9cc16d403439dc74ae7c93cfe51e370b199a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218209"
---
# <a name="compiler-error-c2502"></a>コンパイラ エラー C2502

' identifier ': 基底クラスのアクセス修飾子が多すぎます

基底クラスに複数のアクセス修飾子があります。 1つのアクセス修飾子 ( **`public`** 、 **`private`** 、または **`protected`** ) のみが許可されます。

次の例では、C2502 が生成されます。

```cpp
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```
