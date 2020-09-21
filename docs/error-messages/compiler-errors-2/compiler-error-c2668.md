---
title: コンパイラエラー C2668
ms.date: 03/28/2017
f1_keywords:
- C2668
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
ms.openlocfilehash: f6b0539e7c794852f7e4b28d60f4b402a020bed1
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743205"
---
# <a name="compiler-error-c2668"></a>コンパイラエラー C2668

' function ': オーバーロードされた関数の呼び出しがあいまいです

指定されたオーバーロードされた関数呼び出しを解決できませんでした。 1つ以上の実際のパラメーターを明示的にキャストすることもできます。

このエラーは、テンプレートを使用して取得することもできます。 同じクラス内に、同じシグネチャを持つ通常のメンバー関数とテンプレート化されたメンバー関数がある場合、テンプレート化されたメンバー関数は最初に記述する必要があります。 これは、Visual C++ の現在の実装の制限です。

## <a name="examples"></a>例

次の例では、C2668 が生成されます。

```cpp
// C2668.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};

void func( X, X ){}
void func( A, B ){}
D d;
int main() {
   func( d, d );   // C2668 D has an A, B, and X
   func( (X)d, (X)d );   // OK, uses func( X, X )
}
```

このエラーを解決するもう1つの方法は、 [using 宣言を使用](../../cpp/using-declaration.md)することです。

```cpp
// C2668b.cpp
// compile with: /EHsc /c
// C2668 expected
#include <iostream>
class TypeA {
public:
   TypeA(int value) {}
};

class TypeB {
   TypeB(int intValue);
   TypeB(double dbValue);
};

class TestCase {
public:
   void AssertEqual(long expected, long actual, std::string
                    conditionExpression = "");
};

class AppTestCase : public TestCase {
public:
   // Uncomment the following line to resolve.
   // using TestCase::AssertEqual;
   void AssertEqual(const TypeA expected, const TypeA actual,
                    std::string conditionExpression = "");
   void AssertEqual(const TypeB expected, const TypeB actual,
                    std::string conditionExpression = "");
};

class MyTestCase : public AppTestCase {
   void TestSomething() {
      int actual = 0;
      AssertEqual(0, actual, "Value");
   }
};
```

このエラーは、Visual Studio .NET 2003 で実行されたコンパイラ準拠作業の結果として生成されることもあります。定数0のキャストであいまいな変換が発生しました。

Int は long 型と void 型の両方の変換を必要とするため、定数0を使用したキャストでの変換はあいまいです。 このエラーを解決するには、0を、使用されている関数パラメーターの正確な型にキャストします。これにより、変換を実行する必要がありません (このコードは、Visual Studio .NET 2003 および Visual Studio .NET バージョンの Visual C++) で有効になります。

```cpp
// C2668c.cpp
#include "stdio.h"
void f(long) {
   printf_s("in f(long)\n");
}
void f(void*) {
   printf_s("in f(void*)\n");
}
int main() {
   f((int)0);   // C2668

   // OK
   f((long)0);
   f((void*)0);
}
```

このエラーは、CRT にすべての数値演算関数の float 型と double 型が含まれるようになったために発生する可能性があります。

```cpp
// C2668d.cpp
#include <math.h>
int main() {
   int i = 0;
   float f;
   f = cos(i);   // C2668
   f = cos((float)i);   // OK
}
```

このエラーは、CRT の pow (int, int) が削除されたことが原因で発生する可能性があります。

```cpp
// C2668e.cpp
#include <math.h>
int main() {
   pow(9,9);   // C2668
   pow((double)9,9);   // OK
}
```

このコードは Visual Studio 2015 で成功しますが、Visual Studio 2017 以降の C2668 では失敗します。 Visual Studio 2015 では、コンパイラは、誤って copy-list-initialization を通常の copy-initialization と同じ方法で処理しました。これは、単なるオーバーロードの解決のためのコンストラクターの変換と見なされます。

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```
