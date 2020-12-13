---
description: 詳細については、「コンパイラエラー C2395」を参照してください。
title: コンパイラ エラー C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: 86b6123646ca91945a861e9b9822076877421ac8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145471"
---
# <a name="compiler-error-c2395"></a>コンパイラ エラー C2395

'your_type::operator'op'' : CLR または WinRT 演算子が無効です。 少なくとも1つのパラメーターは次の型である必要があります: ' t '、' t% '、' t& '、' t ^ '、' t ^% '、' t ^& '、where T = ' your_type '

Windows ランタイムまたはマネージド型の演算子に、演算子の戻り値の型と同じ型を持つ 1 つ以上のパラメーターがありません。

次の例では、C2395 を生成し、その修正方法を示しています。

```cpp
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
