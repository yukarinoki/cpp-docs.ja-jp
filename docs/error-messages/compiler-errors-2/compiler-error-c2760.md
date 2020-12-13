---
description: 詳細については、「コンパイラエラー C2760」を参照してください。
title: コンパイラエラー C2760
ms.date: 11/04/2016
f1_keywords:
- C2760
helpviewer_keywords:
- C2760
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
ms.openlocfilehash: bba26b68a2e4c98cf478098b2e44e82962afd9f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336166"
---
# <a name="compiler-error-c2760"></a>コンパイラエラー C2760

> 構文エラー: '*name2*' ではなく '*name1*' が必要です

## <a name="remarks"></a>解説

このエラーを発生させるには、いくつかの方法があります。 通常、これは、コンパイラが意味を持たないトークンシーケンスによって発生します。

## <a name="example"></a>例

このサンプルでは、キャスト演算子が無効な演算子で使用されています。

```cpp
// C2760.cpp
class B {};
class D : public B {};

void f(B* pb) {
    D* pd1 = static_cast<D*>(pb);
    D* pd2 = static_cast<D*>=(pb);  // C2760
    D* pd3 = static_cast<D*=(pb);   // C2760
}
```
