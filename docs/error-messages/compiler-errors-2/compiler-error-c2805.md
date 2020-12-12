---
description: 詳細については、「コンパイラエラー C2805」を参照してください。
title: コンパイラ エラー C2805
ms.date: 11/04/2016
f1_keywords:
- C2805
helpviewer_keywords:
- C2805
ms.assetid: c997dc56-e199-442f-b94e-ac551ec9b015
ms.openlocfilehash: a03e9e2199482d07238c30b0c3d78a77e1221082
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320680"
---
# <a name="compiler-error-c2805"></a>コンパイラ エラー C2805

バイナリ ' operator operator ' のパラメーターが少なすぎます

二項演算子にはパラメーターがありません。

次の例では、C2805 が生成されます。

```cpp
// C2805.cpp
// compile with: /c
class X {
public:
   X operator< ( void );   // C2805 must take one parameter
   X operator< ( X );   // OK
};
```
