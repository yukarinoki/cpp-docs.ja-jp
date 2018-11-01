---
title: コンパイラ エラー C3208
ms.date: 11/04/2016
f1_keywords:
- C3208
helpviewer_keywords:
- C3208
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
ms.openlocfilehash: fa665f17de7ff6bec00ecdaf9d1749b0626c9181
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628147"
---
# <a name="compiler-error-c3208"></a>コンパイラ エラー C3208

'function': クラス テンプレート 'class' のテンプレート パラメーター リストは、テンプレート template パラメーター 'parameter' のテンプレート パラメーター リストと一致しません

テンプレート template パラメーターには、指定されたクラス テンプレートと同じ数のテンプレート パラメーターがありません。

次の例では C3208 が生成されます。

```
// C3208.cpp
template <template <class T> class TT >
int f();

template <class T1, class T2>
struct S;

template <class T1>
struct R;

int i = f<S>();   // C3208
// try the following line instead
// int i = f<R>();
```