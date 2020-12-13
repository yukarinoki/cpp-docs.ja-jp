---
description: '詳細については、「方法: C++/CLI で safe_cast を使用する」を参照してください。'
title: '方法: C++/CLI で safe_cast を使用する'
ms.date: 11/04/2016
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
ms.openlocfilehash: f921371f97f967f9517121aaa163f79769781211
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145575"
---
# <a name="how-to-use-safe_cast-in-ccli"></a>方法: C++/CLI で safe_cast を使用する

この記事では、C++/CLI アプリケーションで safe_cast を使用する方法について説明します。 C++/CX の safe_cast の詳細については、「 [safe_cast](../extensions/safe-cast-cpp-component-extensions.md)」を参照してください。

## <a name="upcasting"></a>キャスト

アップキャストは、派生型からその基底クラスの1つへのキャストです。 このキャストは安全であり、明示的なキャスト表記は必要ありません。 次の例は、アップキャストを実行する方法を示して `safe_cast` います。

```cpp
// safe_upcast.cpp
// compile with: /clr
using namespace System;
interface class A {
   void Test();
};

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test");
   }

   void Test2() {
      Console::WriteLine("in B::Test2");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test");
   };
};

int main() {
   C ^ c = gcnew C;

   // implicit upcast
   B ^ b = c;
   b->Test();
   b->Test2();

   // upcast with safe_cast
   b = nullptr;
   b = safe_cast<B^>(c);
   b->Test();
   b->Test2();
}
```

```Output
in C::Test
in B::Test2
in C::Test
in B::Test2
```

## <a name="downcasting"></a>ダウンキャスト

ダウンキャストは、基本クラスから基底クラスから派生したクラスへのキャストです。  ダウンキャストが安全なのは、実行時にアドレス指定されたオブジェクトが、実際に派生クラスオブジェクトを指す場合だけです。  とは異なり **`static_cast`** 、は `safe_cast` 動的チェックを実行し、 <xref:System.InvalidCastException> 変換に失敗した場合はをスローします。

```cpp
// safe_downcast.cpp
// compile with: /clr
using namespace System;

interface class A { void Test(); };

ref struct B : public A {
   virtual void Test() {
      Console::WriteLine("in B::Test()");
   }

   void Test2() {
      Console::WriteLine("in B::Test2()");
   }
};

ref struct C : public B {
   virtual void Test() override {
      Console::WriteLine("in C::Test()");
   }
};

interface class I {};

value struct V : public I {};

int main() {
   A^ a = gcnew C();
   a->Test();
   B^ b = safe_cast<B^>(a);
   b->Test();
   b->Test2();

   V v;
   I^ i = v;   // i boxes V
   V^ refv = safe_cast<V^>(i);

   Object^ o = gcnew B;
   A^ a2= safe_cast<A^>(o);
}
```

```Output
in C::Test()
in C::Test()
in B::Test2()
```

## <a name="safe_cast-with-user-defined-conversions"></a>ユーザー定義の変換を使用した safe_cast

次のサンプルでは、を使用し `safe_cast` てユーザー定義の変換を呼び出す方法を示します。

```cpp
// safe_cast_udc.cpp
// compile with: /clr
using namespace System;
value struct V;

ref struct R {
   int x;
   R() {
      x = 1;
   }

   R(int argx) {
      x = argx;
   }

   static operator R::V^(R^ r);
};

value struct V {
   int x;
   static operator R^(V& v) {
      Console::WriteLine("in operator R^(V& v)");
      R^ r = gcnew R();
      r->x = v.x;
      return r;
   }

   V(int argx) {
      x = argx;
   }
};

   R::operator V^(R^ r) {
      Console::WriteLine("in operator V^(R^ r)");
      return gcnew V(r->x);
   }

int main() {
   bool fReturnVal = false;
   V v(2);
   R^ r = safe_cast<R^>(v);   // should invoke UDC
   V^ v2 = safe_cast<V^>(r);   // should invoke UDC
}
```

```Output
in operator R^(V& v
in operator V^(R^ r)
```

## <a name="safe_cast-and-boxing-operations"></a>safe_cast とボックス化の操作

### <a name="boxing"></a>ボックス化

ボックス化は、コンパイラによって挿入されたユーザー定義の変換として定義されます。  したがって、を使用して `safe_cast` CLR ヒープの値をボックスに表示できます。

次のサンプルは、単純型とユーザー定義の値型のボックス化を示しています。  は、 `safe_cast` ガベージコレクションヒープの変数に割り当てることができるように、ネイティブスタック上にある値型の変数をボックスに格納します。

```cpp
// safe_cast_boxing.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct V : public I {
   int m_x;

   V(int i) : m_x(i) {}
};

int main() {
   // box a value type
   V v(100);
   I^ i = safe_cast<I^>(v);

   int x = 100;
   V^ refv = safe_cast<V^>(v);
   int^ refi = safe_cast<int^>(x);
}
```

次のサンプルでは、操作のユーザー定義変換よりもボックス化が優先されることを示してい `safe_cast` ます。

```cpp
// safe_cast_boxing_2.cpp
// compile with: /clr
static bool fRetval = true;

interface struct I {};
value struct V : public I {
   int x;

   V(int argx) {
      x = argx;
   }

   static operator I^(V v) {
      fRetval = false;
      I^ pi = v;
      return pi;
   }
};

ref struct R {
   R() {}
   R(V^ pv) {}
};

int main() {
   V v(10);
   I^ pv = safe_cast<I^>(v);   // boxing will occur, not UDC "operator I^"
}
```

### <a name="unboxing"></a>ボックス化解除

ボックス化解除は、コンパイラによって挿入されたユーザー定義の変換として定義されます。  したがって、を使用して、CLR ヒープの値のボックスを解除でき `safe_cast` ます。

ボックス化解除はユーザー定義の変換ですが、ボックス化解除は明示的にする必要があります。つまり、ボックス化解除は、C スタイルのキャストによって実行する必要があります。 **`static_cast`** また、ボックス化解除を暗黙的に実行することは `safe_cast` できません。

```cpp
// safe_cast_unboxing.cpp
// compile with: /clr
int main() {
   System::Object ^ o = 42;
   int x = safe_cast<int>(o);
}
```

次の例では、値型とプリミティブ型のボックス化を解除しています。

```cpp
// safe_cast_unboxing_2.cpp
// compile with: /clr
using namespace System;

interface struct I {};

value struct VI : public I {};

void test1() {
   Object^ o = 5;
   int x = safe_cast<Int32>(o);
}

value struct V {
   int x;
   String^ s;
};

void test2() {
   V localv;
   Object^ o = localv;
   V unboxv = safe_cast<V>(o);
}

void test3() {
   V localv;
   V^ o2 = localv;
   V unboxv2 = safe_cast<V>(o2);
}

void test4() {
   I^ refi = VI();
   VI vi  = safe_cast<VI>(refi);
}

int main() {
   test1();
   test2();
   test3();
   test4();
}
```

## <a name="safe_cast-and-generic-types"></a>safe_cast とジェネリック型

次のサンプルでは、を使用して、ジェネリック型を使用してダウンキャストを実行する方法を示し `safe_cast` ます。

```cpp
// safe_cast_generic_types.cpp
// compile with: /clr
interface struct I {};

generic<class T> where T:I
ref struct Base {
   T t;
   void test1() {}
};

generic<class T> where T:I
ref struct Derived:public Base <T> {};

ref struct R:public I {};

typedef Base<R^> GBase_R;
typedef Derived<R^> GDerived_R;

int main() {
   GBase_R^ br = gcnew GDerived_R();
   GDerived_R^ dr = safe_cast<GDerived_R^>(br);
}
```

## <a name="see-also"></a>関連項目

[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)
