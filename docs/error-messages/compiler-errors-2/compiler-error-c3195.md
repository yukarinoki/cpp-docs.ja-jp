---
title: コンパイラ エラー C3195 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3195
dev_langs:
- C++
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c299704b595ca6e6f6b81fb56ffad5534f81e6b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040597"
---
# <a name="compiler-error-c3195"></a>コンパイラ エラー C3195

'operator' : 予約されているため、値型または ref クラスのメンバーとして使用することはできません。 CLR または WinRT の演算子は、'operator' キーワードを使用して定義されなければなりません

コンパイラは、C++ マネージド拡張構文を使用した演算子定義を検出しました。 演算子の C++ 構文を使用する必要があります。

次の例では、C3195 を生成し、その修正方法を示しています。

```
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```