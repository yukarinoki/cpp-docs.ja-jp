---
description: 詳細については、「コンパイラエラー C2691」を参照してください。
title: コンパイラエラー C2691
ms.date: 11/04/2016
f1_keywords:
- C2691
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
ms.openlocfilehash: 575651d1da871a0514585fea010ef3fe98e8a3cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344329"
---
# <a name="compiler-error-c2691"></a>コンパイラエラー C2691

' data type ': マネージまたは WinRTarray は、この要素型を持つことはできません

マネージド配列または WinRT 配列の要素の型は、値型または参照型になります。

次の例では C2691 が生成されます。

```cpp
// C2691a.cpp
// compile with: /clr
class A {};

int main() {
   array<A>^ a1 = gcnew array<A>(20);   // C2691
   array<int>^ a2 = gcnew array<int>(20);   // value type OK
}
```
