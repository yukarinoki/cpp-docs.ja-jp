---
title: コンパイラ エラー C3255
ms.date: 11/04/2016
f1_keywords:
- C3255
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
ms.openlocfilehash: 129d2698a782d2b98267877e8d575a6ee641b94b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778216"
---
# <a name="compiler-error-c3255"></a>コンパイラ エラー C3255

'値の型': ネイティブ ヒープでこの値型のオブジェクトを動的に割り当てることはできません

値型のインスタンス (を参照してください[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)) メンバがマネージ ヒープではなく、スタック上に作成できます。

次の例では、C3255 が生成されます。

```
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
