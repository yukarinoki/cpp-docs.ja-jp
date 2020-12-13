---
description: 詳細については、「コンパイラエラー C2396」を参照してください。
title: コンパイラ エラー C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: 654b812fbd152a6effb60e6f0919f99bf5039a1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145393"
---
# <a name="compiler-error-c2396"></a>コンパイラ エラー C2396

' your_type:: 演算子 ' type ' ': CLR または WinRT ユーザー定義の変換関数が無効です。 次のいずれかに変換または変換する必要があります: t ^ '、' t ^% '、' t ^& '、T = ' your_type '

Windows ランタイム型またはマネージド型の変換関数に、変換関数が含まれる型と同じ型を持つ 1 つ以上のパラメーターがありません。

次の例では、C2396 を生成し、その修正方法を示しています。

```cpp
// C2396.cpp
// compile with: /clr /c

ref struct Y {
   static operator int(char c);   // C2396

   // OK
   static operator int(Y^ hY);
   // or
   static operator Y^(char c);
};
```
