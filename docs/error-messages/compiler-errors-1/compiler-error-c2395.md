---
title: コンパイラ エラー C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: dd3bd922e2bfa61da2da87d368bb4b28237161f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303663"
---
# <a name="compiler-error-c2395"></a>コンパイラ エラー C2395

'your_type::operator'op'' :CLR または WinRT 演算子が無効です。 次の種類の少なくとも 1 つのパラメーターがあります。'T', 'T%', 'T&', 'T^', 'T^%', 'T^&', where T = 'your_type'

Windows ランタイムまたはマネージド型の演算子に、演算子の戻り値の型と同じ型を持つ 1 つ以上のパラメーターがありません。

次の例では、C2395 を生成し、その修正方法を示しています。

```
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```