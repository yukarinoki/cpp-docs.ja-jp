---
title: コンパイラ エラー C2668 |Microsoft Docs
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2668
dev_langs:
- C++
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23bb1a6fcf64590670ede2eb6aca232a5a3b4f5c
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "48889997"
---
# <a name="compiler-error-c2668"></a>コンパイラ エラー C2668

'function': オーバー ロードされた関数のあいまいな呼び出し

指定されたオーバー ロードされた関数の呼び出しを解決できませんでした。 1 つ以上の実際のパラメーターを明示的にキャストすることがあります。

このエラーは、テンプレートを使用して取得することもできます。 同じクラスでは、通常のメンバー関数と同じシグネチャを持つ template 宣言されたメンバー関数がある場合、テンプレート化された 1 つは先にする必要があります。 これは、Visual C の現在の実装の制限です。

## <a name="example"></a>例

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

## <a name="example"></a>例

このエラーを解決するのには別の方法は、[宣言を使用して](../../cpp/using-declaration.md):

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

## <a name="example"></a>例

このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成することもできます。 あいまいな変換定数 0 のキャスト。

Long 型と void * int の両方への変換が必要なために、0 の定数を使用してキャストの変換はあいまいです。 このエラーを解決するには、0 が使用されている (このコードが Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C で有効になります) 実行する変換が必要ないように、関数のパラメーターの正確な型にキャストします。

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

## <a name="example"></a>例

CRT は float 型とすべての数値演算関数の 2 つのフォームを持つために、このエラーが発生することができます。

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

## <a name="example"></a>例

Pow (int, int) は、crt <math.h> から削除されたために、このエラーが発生することができます。

```cpp
// C2668e.cpp
#include <math.h>
int main() {
   pow(9,9);   // C2668
   pow((double)9,9);   // OK
}
```

## <a name="example"></a>例

このコードでは、Visual Studio 2015 で成功しますが、失敗した Visual Studio 2017 と C2668 で後で。 Visual Studio 2015 では、コンパイラは、誤って copy-list-initialization を通常の copy-initialization と同じ方法で処理しました。これは、単なるオーバーロードの解決のためのコンストラクターの変換と見なされます。

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