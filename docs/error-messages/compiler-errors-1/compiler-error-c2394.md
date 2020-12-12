---
description: 詳細については、「コンパイラエラー C2394」を参照してください。
title: コンパイラ エラー C2394
ms.date: 11/04/2016
f1_keywords:
- C2394
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
ms.openlocfilehash: 116ab480c5a72c18bfa551e582fb797d3c216d6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194868"
---
# <a name="compiler-error-c2394"></a>コンパイラ エラー C2394

' your_type:: 演算子 ' op ' ": CLR または WinRToperator が無効です。 少なくとも1つのパラメーターは次の型でなければなりません: ' t ^ '、' t ^% '、' t ^& '、ここで T = ' your_type '

Windows ランタイムまたはマネージド型の演算子に、演算子の戻り値の型と同じ型を持つ 1 つ以上のパラメーターがありません。

次の例では C2394 が生成されます。

```cpp
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
