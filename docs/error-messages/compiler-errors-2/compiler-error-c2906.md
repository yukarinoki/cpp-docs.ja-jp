---
title: コンパイラ エラー C2906
ms.date: 11/04/2016
f1_keywords:
- C2906
helpviewer_keywords:
- C2906
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
ms.openlocfilehash: 621b31cf362c1dcc740390cf9e405b7da3f05da8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587773"
---
# <a name="compiler-error-c2906"></a>コンパイラ エラー C2906

'specialization': 明示的な特殊化 'テンプレート <>' が必要です

テンプレートの明示的な特殊化には、新しい構文を使用する必要があります。

次の例では、C2906 が生成されます。

```
// C2906.cpp
// compile with: /c
template<class T> class X{};   // primary template
class X<int> { }   // C2906
template<> class X<int> { };   // new syntax
```