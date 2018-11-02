---
title: コンパイラ エラー C2914
ms.date: 11/04/2016
f1_keywords:
- C2914
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
ms.openlocfilehash: 2500736f799032aea71173931139404b4406a16a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659589"
---
# <a name="compiler-error-c2914"></a>コンパイラ エラー C2914

'identifier': 関数の引数があいまいなために、型引数を推測できません

ジェネリックまたはテンプレートの引数に使用する関数をオーバー ロードをコンパイラで判断できません。

次の例では、C2914 が生成されます。

```
// C2914.cpp
// compile with: /c
void f(int);
void f(double);
template<class T> void g(void (*) (T));
void h() { g(f); }   // C2914
// try the following line instead
// void h() { g<int>(f); }
```

C2914 は、ジェネリックを使用しているときにも発生します。  次の例では、C2914 が生成されます。

```
// C2914b.cpp
// compile with: /clr /c
void f(int);
void f(double);

template<class T>
void gf(void (*) (T));

void h() { gf(f);}   // C2914
// try the following line instead
void h() { gf<int>(f); }
```