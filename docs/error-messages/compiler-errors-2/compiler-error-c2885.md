---
description: 詳細については、「コンパイラエラー C2885」を参照してください。
title: コンパイラ エラー C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 040f7a151c34fe7b5e30b6aad1e5bc956b3e5cf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337484"
---
# <a name="compiler-error-c2885"></a>コンパイラ エラー C2885

' class:: identifier ': 非クラススコープでは有効な using 宣言ではありません

[Using](../../cpp/using-declaration.md)宣言を正しく使用しませんでした。

このエラーは、Visual Studio 2005 で実行されたコンパイラ準拠作業の結果として生成される場合があります。入れ子にされた型への宣言を持つことは無効になります。入れ子になった **`using`** 型に対する各参照を明示的に修飾するか、型を名前空間に配置するか、typedef を作成します。

## <a name="examples"></a>例

次の例では、C2885 が生成されます。

```cpp
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

**`using`** クラスメンバーでキーワードを使用する場合、C++ では、そのメンバーを別のクラス (派生クラス) 内で定義する必要があります。

次の例では、C2885 が生成されます。

```cpp
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
