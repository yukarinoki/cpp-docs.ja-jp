---
title: コンパイラ エラー C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 8174faed09bdffbdc6974390cceb7c17661eab4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388775"
---
# <a name="compiler-error-c2885"></a>コンパイラ エラー C2885

':identifier': いない有効な using 宣言非クラス スコープ

使用した、[を使用して](../../cpp/using-declaration.md)宣言が正しくないです。

## <a name="example"></a>例

このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができます: がすることは不要になった、 `using` ; 入れ子になった型の宣言型の名前に、入れ子にされた型に行った各参照を明示的に修飾する必要がありますスペース、または typedef を作成します。

次の例では、C2885 が生成されます。

```
// C2885.cpp
namespace MyNamespace {
   class X1 {};
}

struct MyStruct {
   struct X1 {
      int i;
   };
};

int main () {
   using MyStruct::X1;   // C2885

   // OK
   using MyNamespace::X1;
   X1 myX1;

   MyStruct::X1 X12;

   typedef MyStruct::X1 abc;
   abc X13;
   X13.i = 9;
}
```

## <a name="example"></a>例

使用する場合、`using`クラスのメンバーでは、C++ のキーワードでは、別のクラス (派生クラス) 内でそのメンバーを定義する必要があります。

次の例では、C2885 が生成されます。

```
// C2885_b.cpp
// compile with: /c
class A {
public:
   int i;
};

void z() {
   using A::i;   // C2885 not in a class
}

class B : public A {
public:
   using A::i;
};
```