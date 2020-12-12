---
description: 詳細については、「コンパイラエラー C2808」を参照してください。
title: コンパイラ エラー C2808
ms.date: 11/04/2016
f1_keywords:
- C2808
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
ms.openlocfilehash: bdc47ff480afa77c22784536c1ed6337358e3d87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320575"
---
# <a name="compiler-error-c2808"></a>コンパイラ エラー C2808

単項演算子 ' operator operator ' に含まれている仮引数が多すぎます

単項演算子に void 以外のパラメーターリストがあります。

次の例では、C2808 が生成されます。

```cpp
// C2808.cpp
// compile with: /c
class X {
public:
   X operator! ( X );   // C2808 nonvoid parameter list
   X operator! ( void );   // OK
};
```
