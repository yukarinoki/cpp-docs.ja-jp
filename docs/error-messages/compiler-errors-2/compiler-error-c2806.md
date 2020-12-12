---
description: 詳細については、「コンパイラエラー C2806」を参照してください。
title: コンパイラ エラー C2806
ms.date: 11/04/2016
f1_keywords:
- C2806
helpviewer_keywords:
- C2806
ms.assetid: 7c9ff1f4-1590-4c47-991d-b1075a173b48
ms.openlocfilehash: ba215bdb5293644cc9d655055c2cc44da5de7add
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320667"
---
# <a name="compiler-error-c2806"></a>コンパイラ エラー C2806

' operator operator ' に含まれている仮引数が多すぎます

オーバーロードされた演算子のパラメーターが多すぎます。

次の例では、C2806 が生成されます。

```cpp
// C2806.cpp
// compile with: /c
class X {
public:
   X operator++ ( int, int );   // C2806 more than 1 parameter
   X operator++ ( int );   // OK
} ;
```
