---
description: 詳細については、「コンパイラエラー C2753」を参照してください。
title: コンパイラエラー C2753
ms.date: 11/04/2016
f1_keywords:
- C2753
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
ms.openlocfilehash: d7888086f81f26092d41be440f75ef60400229ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174404"
---
# <a name="compiler-error-c2753"></a>コンパイラエラー C2753

'*template*': 部分的特殊化をプライマリテンプレートの引数リストと一致させることはできません

テンプレート引数リストがパラメーターリストと一致する場合、コンパイラはそれを同じテンプレートとして扱います。 同じテンプレートを2回定義することはできません。

## <a name="example"></a>例

次の例では、C2753 を生成し、その修正方法を示しています。

```cpp
// C2753.cpp
// compile with: cl /c C2753.cpp
template<class T>
struct A {};

template<class T>
struct A<T> {};   // C2753
// try the following line instead
// struct A<int> {};

template<class T, class U, class V, class W, class X>
struct B {};
```
