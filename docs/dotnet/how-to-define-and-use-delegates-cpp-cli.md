---
description: '詳細については、「方法: デリゲートを定義および使用する (C++/CLI)」を参照してください。'
title: '方法: デリゲートを定義および使用する (C++/CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- delegates
ms.assetid: 1cdf3420-89c1-47c0-b796-aa984020e0f8
ms.openlocfilehash: 4229af2015db3a9a77722e9e4cc24b80aa05a49b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175756"
---
# <a name="how-to-define-and-use-delegates-ccli"></a>方法: デリゲートを定義および使用する (C++/CLI)

この記事では、C++/CLI でデリゲートを定義および使用する方法について説明します。

.NET Framework には多数のデリゲートが用意されていますが、新しいデリゲートを定義することが必要になる場合があります。

という名前のデリゲートを定義するコード例を次に示し `MyCallback` ます。 イベント処理コード (この新しいデリゲートが発生したときに呼び出される関数) は、の戻り値の型を持ち、 **`void`** 参照を受け取る必要があり <xref:System.String> ます。

Main 関数は、によって定義された静的メソッドを使用して `SomeClass` 、デリゲートをインスタンス化し `MyCallback` ます。 デリゲートは、デリゲートオブジェクトに文字列 "single" を送信することによって示されているように、この関数を呼び出す別の方法になります。 次に、の追加のインスタンスを `MyCallback` 相互にリンクし、デリゲートオブジェクトの1回の呼び出しで実行します。

```cpp
// use_delegate.cpp
// compile with: /clr
using namespace System;

ref class SomeClass
{
public:
   static void Func(String^ str)
   {
      Console::WriteLine("static SomeClass::Func - {0}", str);
   }
};

ref class OtherClass
{
public:
   OtherClass( Int32 n )
   {
      num = n;
   }

   void Method(String^ str)
   {
      Console::WriteLine("OtherClass::Method - {0}, num = {1}",
         str, num);
   }

   Int32 num;
};

delegate void MyCallback(String^ str);

int main( )
{
   MyCallback^ callback = gcnew MyCallback(SomeClass::Func);
   callback("single");

   callback += gcnew MyCallback(SomeClass::Func);

   OtherClass^ f = gcnew OtherClass(99);
   callback += gcnew MyCallback(f, &OtherClass::Method);

   f = gcnew OtherClass(100);
   callback += gcnew MyCallback(f, &OtherClass::Method);

   callback("chained");

   return 0;
}
```

```Output
static SomeClass::Func - single
static SomeClass::Func - chained
static SomeClass::Func - chained
OtherClass::Method - chained, num = 99
OtherClass::Method - chained, num = 100
```

次のコードサンプルでは、デリゲートを値クラスのメンバーに関連付ける方法を示します。

```cpp
// mcppv2_del_mem_value_class.cpp
// compile with: /clr
using namespace System;
public delegate void MyDel();

value class A {
public:
   void func1() {
      Console::WriteLine("test");
   }
};

int main() {
   A a;
   A^ ah = a;
   MyDel^ f = gcnew MyDel(a, &A::func1);   // implicit box of a
   f();
   MyDel^ f2 = gcnew MyDel(ah, &A::func1);
   f2();
}
```

```Output
test
test
```

## <a name="how-to-compose-delegates"></a>デリゲートを作成する方法

"" 演算子を使用すると、 `-` 構成されたデリゲートからコンポーネントデリゲートを削除できます。

```cpp
// mcppv2_compose_delegates.cpp
// compile with: /clr
using namespace System;

delegate void MyDelegate(String ^ s);

ref class MyClass {
public:
   static void Hello(String ^ s) {
      Console::WriteLine("Hello, {0}!", s);
   }

   static void Goodbye(String ^ s) {
      Console::WriteLine("  Goodbye, {0}!", s);
   }
};

int main() {

   MyDelegate ^ a = gcnew MyDelegate(MyClass::Hello);
   MyDelegate ^ b = gcnew MyDelegate(MyClass::Goodbye);
   MyDelegate ^ c = a + b;
   MyDelegate ^ d = c - a;

   Console::WriteLine("Invoking delegate a:");
   a("A");
   Console::WriteLine("Invoking delegate b:");
   b("B");
   Console::WriteLine("Invoking delegate c:");
   c("C");
   Console::WriteLine("Invoking delegate d:");
   d("D");
}
```

**出力**

```Output
Invoking delegate a:
Hello, A!
Invoking delegate b:
  Goodbye, B!
Invoking delegate c:
Hello, C!
  Goodbye, C!
Invoking delegate d:
  Goodbye, D!
```

## <a name="pass-a-delegate-to-a-native-function-that-expects-a-function-pointer"></a>関数ポインターを要求するネイティブ関数にデリゲート ^ を渡す

マネージコンポーネントからは、関数ポインターパラメーターを使用してネイティブ関数を呼び出すことができます。この場合、ネイティブ関数はマネージコンポーネントのデリゲートのメンバー関数を呼び出すことができます。

このサンプルでは、ネイティブ関数をエクスポートする .dll を作成します。

```cpp
// delegate_to_native_function.cpp
// compile with: /LD
#include < windows.h >
extern "C" {
   __declspec(dllexport)
   void nativeFunction(void (CALLBACK *mgdFunc)(const char* str)) {
      mgdFunc("Call to Managed Function");
   }
}
```

次のサンプルでは、.dll を使用して、関数ポインターを要求するネイティブ関数にデリゲートハンドルを渡します。

```cpp
// delegate_to_native_function_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

delegate void Del(String ^s);
public ref class A {
public:
   void delMember(String ^s) {
      Console::WriteLine(s);
   }
};

[DllImportAttribute("delegate_to_native_function", CharSet=CharSet::Ansi)]
extern "C" void nativeFunction(Del ^d);

int main() {
   A ^a = gcnew A;
   Del ^d = gcnew Del(a, &A::delMember);
   nativeFunction(d);   // Call to native function
}
```

**出力**

```Output
Call to Managed Function
```

## <a name="to-associate-delegates-with-unmanaged-functions"></a>デリゲートをアンマネージ関数に関連付けるには

デリゲートをネイティブ関数に関連付けるには、ネイティブ関数をマネージ型でラップし、を通じて呼び出す関数を宣言する必要があり `PInvoke` ます。

```cpp
// mcppv2_del_to_umnangd_func.cpp
// compile with: /clr
#pragma unmanaged
extern "C" void printf(const char*, ...);
class A {
public:
   static void func(char* s) {
      printf(s);
   }
};

#pragma managed
public delegate void func(char*);

ref class B {
   A* ap;

public:
   B(A* ap):ap(ap) {}
   void func(char* s) {
      ap->func(s);
   }
};

int main() {
   A* a = new A;
   B^ b = gcnew B(a);
   func^ f = gcnew func(b, &B::func);
   f("hello");
   delete a;
}
```

**出力**

```Output
hello
```

## <a name="to-use-unbound-delegates"></a>バインドされるデリゲートを使用するには

バインドされていないデリゲートを使用して、デリゲートが呼び出されたときに呼び出す関数を持つ型のインスタンスを渡すことができます。

バインドされていないデリゲートは [、for each](../dotnet/for-each-in.md) をキーワードで使用してコレクション内のオブジェクトを反復処理し、各インスタンスでメンバー関数を呼び出す必要がある場合に特に便利です。

バインドされたデリゲートとバインドされていないデリゲートを宣言、インスタンス化、および呼び出す方法を次に示します。

|アクション|バインドされたデリゲート|バインドされていないデリゲート|
|------------|---------------------|-----------------------|
|Declare|デリゲートシグネチャは、デリゲートを通じて呼び出す関数のシグネチャと一致する必要があります。|デリゲートシグネチャの最初のパラメーターは、呼び出すオブジェクトのの型です **`this`** 。<br /><br /> 最初のパラメーターの後、デリゲートシグネチャは、デリゲートを通じて呼び出す関数のシグネチャと一致する必要があります。|
|インスタンス|バインドされたデリゲートをインスタンス化する場合は、インスタンス関数、グローバルメンバー関数、または静的メンバー関数を指定できます。<br /><br /> インスタンス関数を指定するために、最初のパラメーターは、呼び出すメンバー関数を持つ型のインスタンスです。2番目のパラメーターは、呼び出す関数のアドレスです。<br /><br /> グローバルまたは静的メンバー関数を呼び出す場合は、グローバル関数の名前または静的メンバー関数の名前を渡します。|バインドされていないデリゲートをインスタンス化する場合は、呼び出す関数のアドレスだけを渡します。|
|Call (英語の可能性あり)|バインドされたデリゲートを呼び出す場合は、デリゲートシグネチャに必要なパラメーターだけを渡します。|バインドされたデリゲートと同じですが、最初のパラメーターは、呼び出す関数を含むオブジェクトのインスタンスである必要があることに注意してください。|

このサンプルでは、バインドされていないデリゲートを宣言、インスタンス化、および呼び出す方法を示します。

```cpp
// unbound_delegates.cpp
// compile with: /clr
ref struct A {
   A(){}
   A(int i) : m_i(i) {}
   void Print(int i) { System::Console::WriteLine(m_i + i);}

private:
   int m_i;
};

value struct V {
   void Print() { System::Console::WriteLine(m_i);}
   int m_i;
};

delegate void Delegate1(A^, int i);
delegate void Delegate2(A%, int i);

delegate void Delegate3(interior_ptr<V>);
delegate void Delegate4(V%);

delegate void Delegate5(int i);
delegate void Delegate6();

int main() {
   A^ a1 = gcnew A(1);
   A% a2 = *gcnew A(2);

   Delegate1 ^ Unbound_Delegate1 = gcnew Delegate1(&A::Print);
   // delegate takes a handle
   Unbound_Delegate1(a1, 1);
   Unbound_Delegate1(%a2, 1);

   Delegate2 ^ Unbound_Delegate2 = gcnew Delegate2(&A::Print);
   // delegate takes a tracking reference (must deference the handle)
   Unbound_Delegate2(*a1, 1);
   Unbound_Delegate2(a2, 1);

   // instantiate a bound delegate to an instance member function
   Delegate5 ^ Bound_Del = gcnew Delegate5(a1, &A::Print);
   Bound_Del(1);

   // instantiate value types
   V v1 = {7};
   V v2 = {8};

   Delegate3 ^ Unbound_Delegate3 = gcnew Delegate3(&V::Print);
   Unbound_Delegate3(&v1);
   Unbound_Delegate3(&v2);

   Delegate4 ^ Unbound_Delegate4 = gcnew Delegate4(&V::Print);
   Unbound_Delegate4(v1);
   Unbound_Delegate4(v2);

   Delegate6 ^ Bound_Delegate3 = gcnew Delegate6(v1, &V::Print);
   Bound_Delegate3();
}
```

**出力**

```Output
2
3
2
3
2
7
8
7
8
7
```

次のサンプルでは、バインドされていないデリゲートと [の for each](../dotnet/for-each-in.md) をキーワードで使用して、コレクション内のオブジェクトを反復処理し、各インスタンスでメンバー関数を呼び出す方法を示します。

```cpp
// unbound_delegates_2.cpp
// compile with: /clr
using namespace System;

ref class RefClass {
   String^ _Str;

public:
   RefClass( String^ str ) : _Str( str ) {}
   void Print() { Console::Write( _Str ); }
};

delegate void PrintDelegate( RefClass^ );

int main() {
   PrintDelegate^ d = gcnew PrintDelegate( &RefClass::Print );

   array< RefClass^ >^ a = gcnew array<RefClass^>( 10 );

   for ( int i = 0; i < a->Length; ++i )
      a[i] = gcnew RefClass( i.ToString() );

   for each ( RefClass^ R in a )
      d( R );

   Console::WriteLine();
}
```

このサンプルでは、プロパティのアクセサー関数にバインドされていないデリゲートを作成します。

```cpp
// unbound_delegates_3.cpp
// compile with: /clr
ref struct B {
   property int P1 {
      int get() { return m_i; }
      void set(int i) { m_i = i; }
   }

private:
   int m_i;
};

delegate void DelBSet(B^, int);
delegate int DelBGet(B^);

int main() {
   B^ b = gcnew B;

   DelBSet^ delBSet = gcnew DelBSet(&B::P1::set);
   delBSet(b, 11);

   DelBGet^ delBGet = gcnew DelBGet(&B::P1::get);
   System::Console::WriteLine(delBGet(b));
}
```

**出力**

```Output
11
```

次のサンプルは、1つのインスタンスがバインドされ、1つのインスタンスがバインド解除されているマルチキャストデリゲートを呼び出す方法を示しています。

```cpp
// unbound_delegates_4.cpp
// compile with: /clr
ref class R {
public:
   R(int i) : m_i(i) {}

   void f(R ^ r) {
      System::Console::WriteLine("in f(R ^ r)");
   }

   void f() {
      System::Console::WriteLine("in f()");
   }

private:
   int m_i;
};

delegate void Del(R ^);

int main() {
   R ^r1 = gcnew R(11);
   R ^r2 = gcnew R(12);

   Del^ d = gcnew Del(r1, &R::f);
   d += gcnew Del(&R::f);
   d(r2);
};
```

**出力**

```Output
in f(R ^ r)
in f()
```

次のサンプルでは、バインドされていない汎用デリゲートを作成して呼び出す方法を示します。

```cpp
// unbound_delegates_5.cpp
// compile with: /clr
ref struct R {
   R(int i) : m_i(i) {}

   int f(R ^) { return 999; }
   int f() { return m_i + 5; }

   int m_i;
};

value struct V {
   int f(V%) { return 999; }
   int f() { return m_i + 5; }

   int m_i;
};

generic <typename T>
delegate int Del(T t);

generic <typename T>
delegate int DelV(T% t);

int main() {
   R^ hr = gcnew R(7);
   System::Console::WriteLine((gcnew Del<R^>(&R::f))(hr));

   V v;
   v.m_i = 9;
   System::Console::WriteLine((gcnew DelV<V >(&V::f))(v) );
}
```

**出力**

```Output
12
14
```

## <a name="see-also"></a>関連項目

[delegate (C++ コンポーネント拡張)](../extensions/delegate-cpp-component-extensions.md)
