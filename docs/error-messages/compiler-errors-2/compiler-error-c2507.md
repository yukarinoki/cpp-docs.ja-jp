---
description: 詳細については、「コンパイラエラー C2507」を参照してください。
title: コンパイラ エラー C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: b2043f01cea9a64ace11fbdaa8d905fd892cc99c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212975"
---
# <a name="compiler-error-c2507"></a>コンパイラ エラー C2507

' identifier ': 基底クラスの仮想修飾子が多すぎます

クラスまたは構造体が複数回宣言されてい **`virtual`** ます。 **`virtual`** 基底クラスのリスト内の各クラスに対して、1つの修飾子のみを表示できます。

次の例では、C2507 が生成されます。

```cpp
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```
