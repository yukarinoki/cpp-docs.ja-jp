---
description: 詳細については、「コンパイラエラー C2756」を参照してください。
title: コンパイラエラー C2756
ms.date: 11/04/2016
f1_keywords:
- C2756
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
ms.openlocfilehash: 94a3211bd45136f74e87a971aa3fd3717355f8d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336193"
---
# <a name="compiler-error-c2756"></a>コンパイラエラー C2756

'template type': 既定のテンプレート引数は部分的特殊化では使用できません

部分的特殊化用のテンプレートに既定の引数を含めることはできません。

次の例では、C2756 を生成し、その修正方法を示しています。

```cpp
// C2756.cpp
template <class T>
struct S {};

template <class T=int>
// try the following line instead
// template <class T>
struct S<T*> {};   // C2756
```
