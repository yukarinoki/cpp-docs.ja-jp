---
title: コンパイラ エラー C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: 944eaeadb038e6466d65859f72900db164cfe34d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221160"
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
