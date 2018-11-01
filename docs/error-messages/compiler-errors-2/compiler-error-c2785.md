---
title: コンパイラ エラー C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: fcf2bbb01f2aac668ff52884a6ccfb36c66aa89d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445840"
---
# <a name="compiler-error-c2785"></a>コンパイラ エラー C2785

'declaration1' と 'declaration2' 異なる戻り値の型があります。

関数テンプレートの特殊化の戻り値の型は、プライマリ関数テンプレートの戻り値の型によって異なります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 一貫性を保つのための関数テンプレートのすべての特殊化を確認します。

## <a name="example"></a>例

次の例では、C2785 が生成されます。

```
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```