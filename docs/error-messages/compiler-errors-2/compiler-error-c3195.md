---
description: 詳細については、「コンパイラエラー C3195」を参照してください。
title: コンパイラエラー C3195
ms.date: 11/04/2016
f1_keywords:
- C3195
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
ms.openlocfilehash: 691aa50fcb091f240253363a23671ac4db70894f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203797"
---
# <a name="compiler-error-c3195"></a>コンパイラエラー C3195

'operator' : 予約されているため、値型または ref クラスのメンバーとして使用することはできません。 CLR または WinRT の演算子は、'operator' キーワードを使用して定義されなければなりません

コンパイラは、C++ マネージド拡張構文を使用した演算子定義を検出しました。 演算子には C++ 構文を使用する必要があります。

次の例では、C3195 を生成し、その修正方法を示しています。

```cpp
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```
