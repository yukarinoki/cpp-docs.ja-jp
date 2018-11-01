---
title: コンパイラ エラー C2394
ms.date: 11/04/2016
f1_keywords:
- C2394
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
ms.openlocfilehash: a18b09bcb5e6f4e743a8b1668cd0057b02a60a8a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642352"
---
# <a name="compiler-error-c2394"></a>コンパイラ エラー C2394

'your_type::operator'op'": CLR または WinRToperator が無効です。 少なくとも 1 つのパラメーターが次の型である必要があります: 'T^'、'T^%'、'T^&' (T = 'your_type')。

Windows ランタイムまたはマネージド型の演算子に、演算子の戻り値の型と同じ型を持つ 1 つ以上のパラメーターがありません。

次の例では C2394 が生成されます。

```
// C2394.cpp
// compile with: /clr /c
ref struct Y {
   static Y^ operator -(int i, char c);   // C2394

   // OK
   static Y^ operator -(Y^ hY, char c);
   // or
   static Y^ operator -(int i, Y^& rhY);
};
```