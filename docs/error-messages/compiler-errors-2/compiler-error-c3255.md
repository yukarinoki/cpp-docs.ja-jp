---
description: 詳細については、「コンパイラエラー C3255」を参照してください。
title: コンパイラ エラー C3255
ms.date: 11/04/2016
f1_keywords:
- C3255
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
ms.openlocfilehash: 576b2c9126173f72470a6e741dd64d8a356c9224
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194203"
---
# <a name="compiler-error-c3255"></a>コンパイラ エラー C3255

' 値の型 ': この値型のオブジェクトをネイティブヒープで動的に割り当てることはできません

マネージメンバーを含む値の型のインスタンス (「 [クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照) は、スタック上で作成できますが、ヒープ上に作成することはできません。

次の例では、C3255 が生成されます。

```cpp
// C3255.cpp
// compile with: /clr
using namespace System;
value struct V {
   Object^ o;
};

value struct V2 {
   int i;
};

int main() {
   V* pv = new V;   // C3255
   V2* pv2 = new V2;
   V v2;
}
```
