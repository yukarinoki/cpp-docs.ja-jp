---
title: コンパイラ エラー C2885 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2885
dev_langs:
- C++
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf47d830980b9fb93481f575e3e3a806ce8bbf68
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035696"
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