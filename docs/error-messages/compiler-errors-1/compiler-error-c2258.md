---
title: コンパイラ エラー C2258
ms.date: 11/04/2016
f1_keywords:
- C2258
helpviewer_keywords:
- C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
ms.openlocfilehash: 99936026929bbaad321abfaa106df41b99c5d19d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387050"
---
# <a name="compiler-error-c2258"></a>コンパイラ エラー C2258

純粋仮想関数の宣言に構文上の誤りがあります、'= 0' でなければなりません。

純粋仮想関数が正しくない構文で宣言されています。

次の例では C2258 が生成されます。

```
// C2258.cpp
// compile with: /c
class A {
public:
   void virtual func1() = 1; // C2258
   void virtual func2() = 0;   // OK
};
```