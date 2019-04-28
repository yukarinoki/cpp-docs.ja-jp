---
title: コンパイラ エラー C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: d320f78937fc60910bbed4a5b1b89841ea674fb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303516"
---
# <a name="compiler-error-c2396"></a>コンパイラ エラー C2396

'your_type::operator'type'' :CLR または WinRT のユーザー定義変換 functionnot 無効です。 必要がありますから変換または変換先。'T^', 'T^%', 'T^&', where T = 'your_type'

Windows ランタイム型またはマネージド型の変換関数に、変換関数が含まれる型と同じ型を持つ 1 つ以上のパラメーターがありません。

次の例では、C2396 を生成し、その修正方法を示しています。

```
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