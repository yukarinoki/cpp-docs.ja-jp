---
description: 詳細については、「コンパイラエラー C2723」を参照してください。
title: コンパイラエラー C2723
ms.date: 11/04/2016
f1_keywords:
- C2723
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
ms.openlocfilehash: ab6eacd4279f0fd7b1c44b86b72cbe62ee51020e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155515"
---
# <a name="compiler-error-c2723"></a>コンパイラエラー C2723

'function' : 'specifier' 指定子が関数の定義で誤って指定されています

この指定子は、クラス宣言の外側にある関数定義では使用できません。 指定 **`virtual`** 子は、クラス宣言内のメンバー関数宣言に対してのみ指定できます。

次の例では、C2723 を生成し、その修正方法を示しています。

```cpp
// C2723.cpp
struct X {
   virtual void f();
   virtual void g();
};

virtual void X::f() {}   // C2723

// try the following line instead
void X::g() {}
```
