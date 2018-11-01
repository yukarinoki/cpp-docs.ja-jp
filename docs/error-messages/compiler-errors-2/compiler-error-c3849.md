---
title: コンパイラ エラー C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: ec6725472d31b0b2ade0cd73da4440036239fde3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598563"
---
# <a name="compiler-error-c3849"></a>コンパイラ エラー C3849

型 'type' の式における関数スタイルの呼び出しはすべての数値の使用可能な演算子のオーバー ロードの const または volatile 修飾子が失われます

指定した const volatile 型の変数は、メンバーが const volatile の制限が同じかそれ以上定義されている関数を呼び出すのみできます。

このエラーを解決するを適切なメンバー関数を提供します。 資格の変換が失わ場合は、const または volatile の修飾オブジェクトに変換を実行できません。 修飾子を取得することができますが、変換で修飾子が失われることはできません。

次の例では、C3849 を生成します。

```
// C3849.cpp
void glbFunc3(int i, char c)
{
   i;
}
typedef void (* pFunc3)(int, char);

void glbFunc2(int i)
{
   i;
}

typedef void (* pFunc2)(int);

void glbFunc1()
{
}
typedef void (* pFunc1)();

struct S4
{
   operator ()(int i)
   {
      i;
   }

   operator pFunc1() const
   {
      return &glbFunc1;
   }

   operator pFunc2() volatile
   {
      return &glbFunc2;
   }

   operator pFunc3()
   {
      return &glbFunc3;
   }

   // operator pFunc1() const volatile
   // {
   //    return &glbFunc1;
   // }
};

int main()
{
   // Cannot call any of the 4 overloads of "operator ()(.....)" and
   // "operator pFunc()" because none is declared as "const volatile"
   const volatile S4 s4;  // can only call cv member functions of S4
   s4();   // C3849 to resolve, uncomment member function
}
```