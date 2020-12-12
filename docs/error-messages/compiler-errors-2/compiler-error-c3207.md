---
description: 詳細については、「コンパイラエラー C3207」を参照してください。
title: コンパイラ エラー C3207
ms.date: 11/04/2016
f1_keywords:
- C3207
helpviewer_keywords:
- C3207
ms.assetid: 4a28b976-142a-4cff-aa2f-480b892c50ca
ms.openlocfilehash: 744dbee62e6247b07ca07354c44d4ebb7a438766
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173988"
---
# <a name="compiler-error-c3207"></a>コンパイラ エラー C3207

'function': 'arg' の無効なテンプレート引数です。クラス テンプレートが必要です

テンプレート関数は、テンプレート template 引数を取るものと定義されています。 しかし、テンプレート型引数が渡されました。

次の例では C3207 が生成されます。

```cpp
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
