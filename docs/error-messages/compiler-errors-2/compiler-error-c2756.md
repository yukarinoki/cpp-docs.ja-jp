---
title: コンパイラ エラー C2756
ms.date: 11/04/2016
f1_keywords:
- C2756
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
ms.openlocfilehash: ccbbb7875fdae48fd00f87f9a63f3764c143daae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442836"
---
# <a name="compiler-error-c2756"></a>コンパイラ エラー C2756

'template type': 既定のテンプレート引数は部分的特殊化では使用できません

部分的特殊化用のテンプレートに既定の引数を含めることはできません。

次の例では、C2756 を生成し、その修正方法を示しています。

```
// C2756.cpp
template <class T>
struct S {};

template <class T=int>
// try the following line instead
// template <class T>
struct S<T*> {};   // C2756
```