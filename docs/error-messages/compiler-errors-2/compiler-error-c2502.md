---
description: 詳細については、「コンパイラエラー C2502」を参照してください。
title: コンパイラ エラー C2502
ms.date: 11/04/2016
f1_keywords:
- C2502
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
ms.openlocfilehash: 6ee501a5fa3601ef5e4b97d4be5a8e59463ce797
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275933"
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
