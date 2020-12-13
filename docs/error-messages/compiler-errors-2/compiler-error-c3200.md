---
description: 詳細については、「コンパイラエラー C3200」を参照してください。
title: コンパイラ エラー C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: c693878628ff0bd9dddcb2f100ca652910b0fb89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330658"
---
# <a name="compiler-error-c3200"></a>コンパイラ エラー C3200

' template ': テンプレートパラメーター ' parameter ' の無効なテンプレート引数です。クラステンプレートが必要です

クラステンプレートに無効な引数を渡しました。 クラステンプレートでは、パラメーターとしてテンプレートが想定されています。 次の例では、を呼び出す `Y<int, int> aY` と C3200 が生成されます。 最初のパラメーターは、のようなテンプレートである必要があり `Y<X, int> aY` ます。

```cpp
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
