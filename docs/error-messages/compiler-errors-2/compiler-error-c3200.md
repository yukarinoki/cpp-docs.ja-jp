---
title: コンパイラ エラー C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: 7eb0c00f4f4c5c59766bf305acfef89e12a6cfb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505067"
---
# <a name="compiler-error-c3200"></a>コンパイラ エラー C3200

'template': テンプレート パラメーター 'parameter' に対する無効なテンプレート引数には、クラス テンプレートが必要です。

クラス テンプレートに無効な引数が渡されます。 クラス テンプレートでは、パラメーターとしてテンプレートを期待しています。 次の例では、呼び出す`Y<int, int> aY`C3200 が生成されます。 最初のパラメーターをテンプレートをなどある必要があります`Y<X, int> aY`します。

```
// C3200.cpp
template<typename T>
class X
{
};

template<template<typename U> class T1, typename T2>
class Y
{
};

int main()
{
   Y<int, int> y;   // C3200
}
```