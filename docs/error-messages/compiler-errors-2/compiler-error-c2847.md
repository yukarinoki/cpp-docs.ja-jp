---
title: コンパイラ エラー C2847
ms.date: 11/04/2016
f1_keywords:
- C2847
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
ms.openlocfilehash: 99c49be746cea6fb80c5e24667bcd97556a0ad04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481485"
---
# <a name="compiler-error-c2847"></a>コンパイラ エラー C2847

マネージド型または WinRT 型の 'class' に対して sizeof を使用できません

[Sizeof](../../cpp/sizeof-operator.md)演算子は、コンパイル時にオブジェクトの値を取得します。 マネージドまたは WinRT のクラス、インターフェイス、または値型のサイズは、動的であるため、コンパイル時に確定できません。

たとえば、次の例では C2847 が生成されます。

```
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
