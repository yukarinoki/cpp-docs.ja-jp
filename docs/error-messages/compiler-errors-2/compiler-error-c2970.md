---
title: コンパイラ エラー C2970
ms.date: 11/04/2016
f1_keywords:
- C2970
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
ms.openlocfilehash: 425d1bf50d56c4455ccd9292b300e744625d34c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256337"
---
# <a name="compiler-error-c2970"></a>コンパイラ エラー C2970

'class': テンプレート パラメーター 'param': 'arg': 非型引数として内部リンケージを持つオブジェクトを含む式を使用することはできません

テンプレート引数として、名前または静的変数のアドレスを使用することはできません。 テンプレート クラスは、コンパイル時に評価される定数値が必要です。

次の例では、C2970 が生成されます。

```
// C2970.cpp
// compile with: /c
static int si;
// could declare nonstatic to resolve all errors
// int si;

template <int i>
class X {};

template <int *pi>
class Y {};

X<si> anX;   // C2970 cannot use static variable in templates

// this would also work
const int i = 10;
X<i> anX2;
```