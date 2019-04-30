---
title: コンパイラ エラー C2723
ms.date: 11/04/2016
f1_keywords:
- C2723
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
ms.openlocfilehash: bc07a99f12ed0e447427990969e54f7f3d3d3b7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383023"
---
# <a name="compiler-error-c2723"></a>コンパイラ エラー C2723

'function' : 'specifier' 指定子が関数の定義で誤って指定されています

この指定子は、クラス宣言の外側にある関数定義では使用できません。 `virtual` 指定子は、クラス宣言内のメンバー関数宣言にしか指定できません。

次の例では、C2723 を生成し、その修正方法を示しています。

```
// C2723.cpp
struct X {
   virtual void f();
   virtual void g();
};

virtual void X::f() {}   // C2723

// try the following line instead
void X::g() {}
```