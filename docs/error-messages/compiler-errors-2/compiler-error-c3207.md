---
title: コンパイラ エラー C3207
ms.date: 11/04/2016
f1_keywords:
- C3207
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
ms.openlocfilehash: 51873e089499e42f4ddeb97c95e3f18416df447c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515493"
---
# <a name="compiler-error-c3207"></a>コンパイラ エラー C3207

'function': 'arg' の無効なテンプレート引数です。クラス テンプレートが必要です

テンプレート関数は、テンプレート template 引数を取るものと定義されています。 しかし、テンプレート型引数が渡されました。

次の例では C3207 が生成されます。

```
// C3207.cpp
template <template <class T> class TT>
void f(){}

template <class T>
struct S
{
};

void f1()
{
   f<S<int> >();   // C3207
   // try the following line instead
   // f<S>();
}
```