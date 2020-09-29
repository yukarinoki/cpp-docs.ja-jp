---
title: '方法: クラスと構造体を定義および使用する (C++/CLI)'
description: C++/CLI コードでユーザー定義のクラスと構造体の型を作成および使用する方法について説明します。
ms.date: 09/25/2020
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
ms.openlocfilehash: 17d0885d42febc1d2789c8711b54a76066ee8176
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414582"
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>方法: クラスと構造体を定義および使用する (C++/CLI)

この記事では、C++/CLI でユーザー定義の参照型と値型を定義および使用する方法について説明します。

## <a name="object-instantiation"></a><a name="BKMK_Object_instantiation"></a> オブジェクトのインスタンス化

参照 (ref) 型は、スタックまたはネイティブヒープではなく、マネージヒープでのみインスタンス化できます。 値型は、スタックまたはマネージヒープでインスタンス化できます。

```cpp
// mcppv2_ref_class2.cpp
// compile with: /clr
ref class MyClass {
public:
   int i;

   // nested class
   ref class MyClass2 {
   public:
      int i;
   };

   // nested interface
   interface struct MyInterface {
      void f();
   };
};

ref class MyClass2 : public MyClass::MyInterface {
public:
   virtual void f() {
      System::Console::WriteLine("test");
   }
};

public value struct MyStruct {
   void f() {
      System::Console::WriteLine("test");
   }
};

int main() {
   // instantiate ref type on garbage-collected heap
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass -> i = 4;

   // instantiate value type on garbage-collected heap
   MyStruct ^ p_MyStruct = gcnew MyStruct;
   p_MyStruct -> f();

   // instantiate value type on the stack
   MyStruct p_MyStruct2;
   p_MyStruct2.f();

   // instantiate nested ref type on garbage-collected heap
   MyClass::MyClass2 ^ p_MyClass2 = gcnew MyClass::MyClass2;
   p_MyClass2 -> i = 5;
}
```

## <a name="implicitly-abstract-classes"></a><a name="BKMK_Implicitly_abstract_classes"></a> 暗黙的に抽象クラス

*暗黙的に抽象クラス*をインスタンス化することはできません。 クラスは、次の場合に暗黙的に抽象されます。

- クラスの基本型はインターフェイスです。
- クラスは、インターフェイスのすべてのメンバー関数を実装するわけではありません。

インターフェイスから派生したクラスからオブジェクトを構築できない可能性があります。 その理由として、クラスが暗黙的に抽象であることが考えられます。 抽象クラスの詳細については、「 [abstract](../extensions/abstract-cpp-component-extensions.md)」を参照してください。

次のコード例は、 `MyClass` 関数が実装されていないため、クラスをインスタンス化できないことを示して `MyClass::func2` います。 例をコンパイルできるようにするには、`MyClass::func2` のコメントを解除します。

```cpp
// mcppv2_ref_class5.cpp
// compile with: /clr
interface struct MyInterface {
   void func1();
   void func2();
};

ref class MyClass : public MyInterface {
public:
   void func1(){}
   // void func2(){}
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;   // C2259
                                          // To resolve, uncomment MyClass::func2.
}
```

## <a name="type-visibility"></a><a name="BKMK_Type_visibility"></a> 型の可視性

共通言語ランタイム (CLR) 型の表示を制御できます。 アセンブリが参照されている場合は、アセンブリ内の型をアセンブリの外部に表示するかどうかを制御します。

`public` 型を含むアセンブリのディレクティブを含む任意のソースファイルに対して、型が表示されることを示し `#using` ます。  `private` 型を含むアセンブリのディレクティブを含むソースファイルには、型が表示されないことを示し `#using` ます。 ただし、プライベート型は、同じアセンブリ内には表示されます。 既定では、クラスの可視性は `private` です。

Visual Studio 2005 より前の既定では、ネイティブ型のアクセシビリティはアセンブリの外部にありました。 [コンパイラの警告 (レベル 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md)を有効にすると、プライベートなネイティブ型が不適切に使用されている場所を確認するのに役立ちます。 [Make_public](../preprocessor/make-public.md)プラグマを使用して、変更できないソースコードファイルのネイティブ型にパブリックアクセシビリティを与えます。

詳細については、「[#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)」を参照してください。

次の例では、型を宣言してアクセシビリティを指定し、アセンブリ内でこれらの型にアクセスする方法を示しています。 プライベート型を持つアセンブリがを使用して参照されている場合 `#using` 、アセンブリ内のパブリック型のみが表示されます。

```cpp
// type_visibility.cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// default accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   Private_Class ^ b = gcnew Private_Class;
   b->Test();

   Private_Class_2 ^ c = gcnew Private_Class_2;
   c->Test();
}
```

**出力**

```Output
in Public_Class
in Private_Class
in Private_Class_2
```

ここで、DLL としてビルドされるように、前の例を書き直してみましょう。

```cpp
// type_visibility_2.cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref struct Public_Class {
   void Test(){Console::WriteLine("in Public_Class");}
};

// private type, visible inside but not outside the assembly
private ref struct Private_Class {
   void Test(){Console::WriteLine("in Private_Class");}
};

// by default, accessibility is private
ref class Private_Class_2 {
public:
   void Test(){Console::WriteLine("in Private_Class_2");}
};
```

次の例は、アセンブリ外で型にアクセスする方法を示しています。 このサンプルでは、クライアントは、前の例でビルドされたコンポーネントを実装しています。

```cpp
// type_visibility_3.cpp
// compile with: /clr
#using "type_visibility_2.dll"
int main() {
   Public_Class ^ a = gcnew Public_Class;
   a->Test();

   // private types not accessible outside the assembly
   // Private_Class ^ b = gcnew Private_Class;
   // Private_Class_2 ^ c = gcnew Private_Class_2;
}
```

**出力**

```Output
in Public_Class
```

## <a name="member-visibility"></a><a name="BKMK_Member_visibility"></a> メンバーの可視性

パブリッククラスのメンバーへのアクセスは、アクセス指定子のペア、、およびを使用して、アセンブリ外部からのアクセスとは異なる同じアセンブリ内から行うことができます。 **`public`** **`protected`****`private`**

次の表は、さまざまなアクセス指定子の効果を示しています。

|指定子|結果|
|---------------|------------|
|`public`|アセンブリの内部と外部の両方でメンバーにアクセスできます。 詳細については、[`public`](../cpp/public-cpp.md) を参照してください。|
|`private`|アセンブリの内部と外部の両方で、メンバーにアクセスできません。  詳細については、[`private`](../cpp/private-cpp.md) を参照してください。|
|`protected`|アセンブリの内部と外部の両方で、派生型のメンバーにのみアクセスできます。 詳細については、[`protected`](../cpp/protected-cpp.md) を参照してください。|
|`internal`|メンバーはアセンブリ内ではパブリックですが、アセンブリ外ではプライベートです。 `internal` は状況依存のキーワードです。  詳細については、「[状況依存キーワード](../extensions/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。|
|`public protected` または `protected public`|メンバーはアセンブリ内ではパブリックですが、アセンブリ外では保護されています。|
|`private protected` または `protected private`|メンバーはアセンブリ内では保護されていますが、アセンブリ外ではプライベートです。|

次のサンプルは、異なるアクセス指定子を使用して宣言されたメンバーを持つパブリック型を示しています。 次に、アセンブリ内からこれらのメンバーへのアクセスを示します。

```cpp
// compile with: /clr
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();
   a->Protected_Public_Function();
   a->Public_Protected_Function();

   // accessible inside but not outside the assembly
   a->Internal_Function();

   // call protected functions
   b->Test();

   // not accessible inside or outside the assembly
   // a->Private_Function();
}
```

**出力**

```Output
in Public_Function
in Protected_Public_Function
in Public_Protected_Function
in Internal_Function
=======================
in function of derived class
in Protected_Function
in Protected_Private_Function
in Private_Protected_Function
exiting function of derived class
=======================
```

次は、前のサンプルを DLL としてビルドします。

```cpp
// compile with: /clr /LD
using namespace System;
// public type, visible inside and outside the assembly
public ref class Public_Class {
public:
   void Public_Function(){System::Console::WriteLine("in Public_Function");}

private:
   void Private_Function(){System::Console::WriteLine("in Private_Function");}

protected:
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}

internal:
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}

protected public:
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}

public protected:
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}

private protected:
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}

protected private:
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}
};

// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Private_Function();
      Private_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};
```

次の例では、前のサンプルで作成したコンポーネントを使用します。 この例では、アセンブリの外部からメンバーにアクセスする方法を示します。

```cpp
// compile with: /clr
#using "type_member_visibility_2.dll"
using namespace System;
// a derived type, calls protected functions
ref struct MyClass : public Public_Class {
   void Test() {
      Console::WriteLine("=======================");
      Console::WriteLine("in function of derived class");
      Protected_Function();
      Protected_Public_Function();
      Public_Protected_Function();
      Console::WriteLine("exiting function of derived class");
      Console::WriteLine("=======================");
   }
};

int main() {
   Public_Class ^ a = gcnew Public_Class;
   MyClass ^ b = gcnew MyClass;
   a->Public_Function();

   // call protected functions
   b->Test();

   // can't be called outside the assembly
   // a->Private_Function();
   // a->Internal_Function();
   // a->Protected_Private_Function();
   // a->Private_Protected_Function();
}
```

**出力**

```Output
in Public_Function
=======================
in function of derived class
in Protected_Function
in Protected_Public_Function
in Public_Protected_Function
exiting function of derived class
=======================
```

## <a name="public-and-private-native-classes"></a><a name="BKMK_Public_and_private_native_classes"></a> パブリックおよびプライベートのネイティブクラス

ネイティブ型はマネージド型から参照できます。  たとえば、マネージド型の関数は、型がネイティブ構造体であるパラメーターを受け取ることができます。  マネージド型と関数がアセンブリ内でパブリックの場合は、ネイティブ型もパブリックである必要があります。

```cpp
// native type
public struct N {
   N(){}
   int i;
};
```

次に、ネイティブ型を使用するソース コード ファイルを作成します。

```cpp
// compile with: /clr /LD
#include "mcppv2_ref_class3.h"
// public managed type
public ref struct R {
   // public function that takes a native type
   void f(N nn) {}
};
```

次に、クライアントをコンパイルします。

```cpp
// compile with: /clr
#using "mcppv2_ref_class3.dll"

#include "mcppv2_ref_class3.h"

int main() {
   R ^r = gcnew R;
   N n;
   r->f(n);
}
```

## <a name="static-constructors"></a><a name="BKMK_Static_constructors"></a> 静的コンストラクター

クラスや構造体などの CLR 型は、静的データ メンバーの初期化に使用できる静的コンストラクターを持つことができます。  静的コンストラクターが呼び出されるのは、型の静的メンバーが初めてアクセスされる前の 1 度だけです。

静的コンストラクターの後は、インスタンス コンストラクターが常に実行されています。

クラスに静的コンストラクターがある場合、コンパイラはコンストラクターへの呼び出しをインライン化できません。 クラスが値型であり、静的コンストラクターを持ち、インスタンスコンストラクターがない場合、コンパイラはメンバー関数への呼び出しをインライン化できません。 CLR は呼び出しをインライン化できますが、コンパイラはできません。

静的コンストラクターは、CLR によってのみ呼び出されることが意図されているため、プライベートメンバー関数として定義します。

静的コンストラクターの詳細については、「 [方法: インターフェイス静的コンストラクターを定義する (C++/cli)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) 」を参照してください。

```cpp
// compile with: /clr
using namespace System;

ref class MyClass {
private:
   static int i = 0;

   static MyClass() {
      Console::WriteLine("in static constructor");
      i = 9;
   }

public:
   static void Test() {
      i++;
      Console::WriteLine(i);
   }
};

int main() {
   MyClass::Test();
   MyClass::Test();
}
```

**出力**

```Output
in static constructor
10
11
```

## <a name="semantics-of-the-this-pointer"></a><a name="BKMK_Semantics_of_the_this_pointer"></a>ポインターのセマンティクス `this`

C++-CLI を使用して型を定義する場合、 **`this`** 参照型のポインターは型 *ハンドル*です。 **`this`** 値型のポインターは、*内部ポインター*型です。

ポインターのこれらの異なるセマンティクス **`this`** により、既定のインデクサーが呼び出されたときに予期しない動作が発生する可能性があります。 次の例は、参照型と値型の両方で既定のインデクサーに適切にアクセスする方法を示しています。

詳細については、「[オブジェクト演算子へのハンドル (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) 」および「 [interior_ptr (C++/cli)](../extensions/interior-ptr-cpp-cli.md) 」を参照してください。

```cpp
// compile with: /clr
using namespace System;

ref struct A {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }

   A() {
      // accessing default indexer
      Console::WriteLine("{0}", this[3.3]);
   }
};

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      // accessing default indexer
      Console::WriteLine("{0}", this->default[3.3]);
   }
};

int main() {
   A ^ mya = gcnew A();
   B ^ myb = gcnew B();
   myb->Test();
}
```

**出力**

```Output
10.89
10.89
```

## <a name="hide-by-signature-functions"></a><a name="BKMK_Hide_by_signature_functions"></a> シグネチャによる隠ぺい関数

標準 C++ では、派生クラスの関数が同じ種類または数のパラメーターを持たない場合でも、基底クラスの関数は、派生クラスで同じ名前を持つ関数によって隠ぺいされます。 これは、 *名前の非表示* セマンティクスと呼ばれています。 参照型の場合、基底クラスの関数は、名前とパラメーターリストの両方が同じである場合、派生クラスの関数によってのみ非表示になります。 これは、 *シグネチャによる隠ぺい* セマンティクスと呼ばれています。

クラスの関数すべてがメタデータで `hidebysig` としてマークされていると、そのクラスはシグネチャによる隠ぺいクラスと見なされます。 既定では、の下に作成されるすべてのクラスに **`/clr`** 関数があり `hidebysig` ます。 クラスに `hidebysig` 関数が含まれる場合、コンパイラが、直接基底クラスで名前によって関数を隠ぺいすることはありませんが、継承チェーンで名前による隠ぺいクラスが見つかると、名前による隠ぺい動作が続行されます。

シグネチャによる隠ぺいセマンティクスでは、関数がオブジェクトで呼び出されると、関数呼び出しを満たす関数を含む最派生クラスがコンパイラによって特定されます。 呼び出しを満たす関数がクラス内に1つしかない場合、コンパイラはその関数を呼び出します。 呼び出しを満たすことができる関数がクラスに複数ある場合、コンパイラはオーバーロードの解決規則を使用して、呼び出す関数を決定します。 オーバーロード規則の詳細については、「 [関数のオーバーロード](../cpp/function-overloading.md)」を参照してください。

特定の関数呼び出しについては、基底クラスの関数のシグネチャの方が、派生クラスの関数よりも若干適していることがあるのですが、 派生クラスのオブジェクトで関数が明示的に呼び出されると、派生クラスの関数が呼び出されます。

戻り値は関数のシグネチャの一部とは見なされないため、基底クラスの関数は、戻り値の型が異なる場合でも、同じ名前を持ち、派生クラスの関数と同じ種類と数の引数を受け取る場合、非表示になります。

次の例では、基底クラスの関数が派生クラスの関数によって非表示になっていないことを示しています。

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test() {
      Console::WriteLine("Base::Test");
   }
};

ref struct Derived : public Base {
   void Test(int i) {
      Console::WriteLine("Derived::Test");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Test() in the base class will not be hidden
   t->Test();
}
```

**出力**

```Output
Base::Test
```

次のサンプルでは、Microsoft C++ コンパイラが最も派生クラスの関数を呼び出します。1つ以上のパラメーターに一致する必要がある場合でも、関数呼び出しに適した基底クラスの関数を呼び出すことはできません。

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   void Test2(Single d) {
      Console::WriteLine("Base::Test2");
   }
};

ref struct Derived : public Base {
   void Test2(Double f) {
      Console::WriteLine("Derived::Test2");
   }
};

int main() {
   Derived ^ t = gcnew Derived;
   // Base::Test2 is a better match, but the compiler
   // calls a function in the derived class if possible
   t->Test2(3.14f);
}
```

**出力**

```Output
Derived::Test2
```

次の例は、基底クラスのシグネチャが派生クラスと同じであっても、関数を非表示にできることを示しています。

```cpp
// compile with: /clr
using namespace System;
ref struct Base {
   int Test4() {
      Console::WriteLine("Base::Test4");
      return 9;
   }
};

ref struct Derived : public Base {
   char Test4() {
      Console::WriteLine("Derived::Test4");
      return 'a';
   }
};

int main() {
   Derived ^ t = gcnew Derived;

   // Base::Test4 is hidden
   int i = t->Test4();
   Console::WriteLine(i);
}
```

**出力**

```Output
Derived::Test4
97
```

## <a name="copy-constructors"></a><a name="BKMK_Copy_constructors"></a> コピーコンストラクター

C++ 標準では、オブジェクトの移動時にコピー コンストラクターが呼び出されることを通知します。このため、オブジェクトの作成と破棄が同じアドレスで行われます。

ただし、MSIL にコンパイルされた関数が、ネイティブクラス (または複数の) が値によって渡され、ネイティブクラスにコピーコンストラクターまたはデストラクターがある場合は、コピーコンストラクターが呼び出されず、オブジェクトは作成された場所とは異なるアドレスで破棄されます。 この動作により、クラスがそれ自体へのポインターを持っている場合、またはコードがアドレスによってオブジェクトを追跡している場合に問題が発生する可能性があります。

詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

コピーコンストラクターが生成されない場合の例を次に示します。

```cpp
// compile with: /clr
#include<stdio.h>

struct S {
   int i;
   static int n;

   S() : i(n++) {
      printf_s("S object %d being constructed, this=%p\n", i, this);
   }

   S(S const& rhs) : i(n++) {
      printf_s("S object %d being copy constructed from S object "
               "%d, this=%p\n", i, rhs.i, this);
   }

   ~S() {
      printf_s("S object %d being destroyed, this=%p\n", i, this);
   }
};

int S::n = 0;

#pragma managed(push,off)
void f(S s1, S s2) {
   printf_s("in function f\n");
}
#pragma managed(pop)

int main() {
   S s;
   S t;
   f(s,t);
}
```

**出力**

```Output
S object 0 being constructed, this=0018F378
S object 1 being constructed, this=0018F37C
S object 2 being copy constructed from S object 1, this=0018F380
S object 3 being copy constructed from S object 0, this=0018F384
S object 4 being copy constructed from S object 2, this=0018F2E4
S object 2 being destroyed, this=0018F380
S object 5 being copy constructed from S object 3, this=0018F2E0
S object 3 being destroyed, this=0018F384
in function f
S object 5 being destroyed, this=0018F2E0
S object 4 being destroyed, this=0018F2E4
S object 1 being destroyed, this=0018F37C
S object 0 being destroyed, this=0018F378
```

## <a name="destructors-and-finalizers"></a><a name="BKMK_Destructors_and_finalizers"></a> デストラクターとファイナライザー

参照型のデストラクターは、リソースの決定的なクリーンアップを実行します。 ファイナライザーはアンマネージリソースをクリーンアップし、デストラクターによって決定的に、またはガベージコレクターによってランダムに呼び出されることができます。 標準 C++ のデストラクターの詳細については、「 [デストラクター](../cpp/destructors-cpp.md)」を参照してください。

```cpp
class classname {
   ~classname() {}   // destructor
   ! classname() {}   // finalizer
};
```

CLR ガベージコレクターは、不要になったマネージオブジェクトを削除し、そのメモリを解放します。 ただし、型は、ガベージコレクターが解放方法を認識していないリソースを使用する場合があります。 これらのリソースは、 *アンマネージ* リソース (たとえば、ネイティブファイルハンドル) と呼ばれます。 ファイナライザーでアンマネージリソースをすべて解放することをお勧めします。 ガベージコレクターは、マネージリソースを確定的に解放するため、ファイナライザーでマネージリソースを参照するのは安全ではありません。 これは、ガベージコレクターによって既にクリーンアップされている可能性があるためです。

Visual C++ ファイナライザーがメソッドと同じでは <xref:System.Object.Finalize%2A> ありません。 (CLR ドキュメントでは、ファイナライザーと <xref:System.Object.Finalize%2A> メソッドが同じ意味で使用されます)。 <xref:System.Object.Finalize%2A> メソッドはガベージ コレクターによって呼び出され、これにより、クラス継承チェーンの各ファイナライザーが開始されます。 Visual C++ デストラクターとは異なり、派生クラスのファイナライザー呼び出しでは、コンパイラがすべての基底クラスでファイナライザーを呼び出すことはありません。

Microsoft C++ コンパイラではリソースの決定的な解放がサポートされているため、 <xref:System.IDisposable.Dispose%2A> メソッドまたはメソッドを実装しないようにしてください <xref:System.Object.Finalize%2A> 。 ただし、これらのメソッドに慣れている方を対象に、ここでは、Visual C++ ファイナライザーとそのファイナライザーを呼び出すデストラクターが、どのように <xref:System.IDisposable.Dispose%2A> パターンに割り当てられるかを示します。

```cpp
// Visual C++ code
ref class T {
   ~T() { this->!T(); }   // destructor calls finalizer
   !T() {}   // finalizer
};

// equivalent to the Dispose pattern
void Dispose(bool disposing) {
   if (disposing) {
      ~T();
   } else {
      !T();
   }
}
```

マネージ型では、決定的に解放するマネージリソースを使用することもできます。 オブジェクトが不要になった後で、ガベージコレクターによってオブジェクトが確定的に解放されないようにすることができます。 リソースを確定的に解放すると、パフォーマンスが大幅に向上する可能性があります。

Microsoft C++ コンパイラを使用すると、デストラクターの定義によってオブジェクトを確定的にクリーンアップできます。 デストラクターを使用して、確定的に解放するすべてのリソースを解放します。  ファイナライザーが存在する場合は、デストラクターからそのファイナライザーを呼び出して、コードの重複を回避します。

```cpp
// compile with: /clr /c
ref struct A {
   // destructor cleans up all resources
   ~A() {
      // clean up code to release managed resource
      // ...
      // to avoid code duplication,
      // call finalizer to release unmanaged resources
      this->!A();
   }

   // finalizer cleans up unmanaged resources
   // destructor or garbage collector will
   // clean up managed resources
   !A() {
      // clean up code to release unmanaged resources
      // ...
   }
};
```

型を使用するコードがデストラクターを呼び出さない場合、ガベージコレクターは最終的にすべてのマネージリソースを解放します。

デストラクターが存在する場合、ファイナライザーは存在しません。 ただし、ファイナライザーが存在する場合は、デストラクターを定義し、そのデストラクターからファイナライザーを呼び出す必要があることを意味します。 この呼び出しは、アンマネージリソースの決定的な解放のためのを提供します。

デストラクターを呼び出すと、<xref:System.GC.SuppressFinalize%2A> を使用して、オブジェクトの終了処理が回避されます。 デストラクターが呼び出されない場合、型のファイナライザーは最終的にガベージコレクターによって呼び出されます。

デストラクターを呼び出してオブジェクトのリソースを確定的にクリーンアップすることで、パフォーマンスを向上させることができます。

Visual C++ に記述され、を使用してコンパイルされたコードは **`/clr`** 、次の場合に型のデストラクターを実行します。

- スタック セマンティクスを使用して作成されたオブジェクトがスコープから外れる。 詳細については、「 [参照型の C++ スタックセマンティクス](../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。

- オブジェクトの作成時に例外がスローされる。

- オブジェクトが、デストラクターが実行されているオブジェクトのメンバーである。

- ハンドルに対して [delete](../cpp/delete-operator-cpp.md) 演算子を呼び出します ([オブジェクト演算子 (^) へのハンドル](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md))。

- 明示的にデストラクターを呼び出す。

別の言語で記述されたクライアントが型を使用している場合、デストラクターは次のように呼び出されます。

- <xref:System.IDisposable.Dispose%2A> への呼び出しで。

- 型の `Dispose(void)` への呼び出しで。

- 型が C# ステートメントでスコープ外に出る場合は **`using`** 。

参照型にスタックセマンティクスを使用せず、マネージヒープで参照型のオブジェクトを作成する場合は、 [try-finally](../cpp/try-finally-statement.md) 構文を使用して、例外によってデストラクターが実行されないようにします。

```cpp
// compile with: /clr
ref struct A {
   ~A() {}
};

int main() {
   A ^ MyA = gcnew A;
   try {
      // use MyA
   }
   finally {
      delete MyA;
   }
}
```

型にデストラクターがある場合は、`Dispose` を実装する <xref:System.IDisposable> メソッドがコンパイラによって生成されます。 型が Visual C++ で記述されており、他の言語で実行されるデストラクターがその型にある場合は、その型で `IDisposable::Dispose` を呼び出すと、その型のデストラクターが呼び出されます。 型が Visual C++ クライアントから使用される場合、を直接呼び出すことはできません。 `Dispose` 代わりに、演算子を使用してデストラクターを呼び出して **`delete`** ください。

型にファイナライザーがある場合は、`Finalize(void)` をオーバーライドする <xref:System.Object.Finalize%2A> メソッドがコンパイラによって生成されます。

型にデストラクターまたはファイナライザーのいずれかがある場合は、デザイン パターンに従って `Dispose(bool)` メソッドが生成されます  (詳細については、「 [Dispose Pattern](/dotnet/standard/design-guidelines/dispose-pattern)」を参照してください)。 Visual C++ では、明示的に作成したり、呼び出したりすることはできません `Dispose(bool)` 。

デザイン パターンに準拠する基底クラスが型にある場合、すべての基底クラスのデストラクターは、派生クラスのデストラクターが呼び出されるときに呼び出されます  (型が Visual C++ で記述されている場合、コンパイラは型がこのパターンを実装することを保証します)。言い換えると、参照クラスのデストラクターは、C++ 標準によって指定された基本とメンバーにチェーンされます。 まず、クラスのデストラクターが実行されます。 次に、そのメンバーのデストラクターが、構築された順序と逆の順序で実行されます。 最後に、基底クラスのデストラクターは、構築された順序と逆の順序で実行されます。

デストラクターとファイナライザーは、値型またはインターフェイス内では使用できません。

ファイナライザーは、参照型でのみ定義または宣言できます。 コンストラクターおよびデストラクターと同様、ファイナライザーには戻り値の型がありません。

オブジェクトのファイナライザーの実行後に、すべての基底クラスのファイナライザーも呼び出されます。最初に呼び出されるのは最小限の派生型です。 データメンバーのファイナライザーは、クラスのファイナライザーによって自動的にチェーンされることはありません。

ファイナライザーがマネージ型のネイティブポインターを削除する場合、ネイティブポインターへの参照またはネイティブポインターによる参照が早期に収集されていないことを確認する必要があります。 を使用するのではなく、マネージ型でデストラクターを呼び出し <xref:System.GC.KeepAlive%2A> ます。

コンパイル時に、型にファイナライザーまたはデストラクターがあるかどうかを検出できます。 詳細については、「[型の特徴のコンパイラ サポート](../extensions/compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。

次のサンプルでは、アンマネージリソースを持つ2つの型と、決定的に解放されるマネージリソースを持つ型を示します。

```cpp
// compile with: /clr
#include <vcclr.h>
#include <stdio.h>
using namespace System;
using namespace System::IO;

ref class SystemFileWriter {
   FileStream ^ file;
   array<Byte> ^ arr;
   int bufLen;

public:
   SystemFileWriter(String ^ name) : file(File::Open(name, FileMode::Append)),
                                     arr(gcnew array<Byte>(1024)) {}

   void Flush() {
      file->Write(arr, 0, bufLen);
      bufLen = 0;
   }

   ~SystemFileWriter() {
      Flush();
      delete file;
   }
};

ref class CRTFileWriter {
   FILE * file;
   array<Byte> ^ arr;
   int bufLen;

   static FILE * getFile(String ^ n) {
      pin_ptr<const wchar_t> name = PtrToStringChars(n);
      FILE * ret = 0;
      _wfopen_s(&ret, name, L"ab");
      return ret;
   }

public:
   CRTFileWriter(String ^ name) : file(getFile(name)), arr(gcnew array<Byte>(1024) ) {}

   void Flush() {
      pin_ptr<Byte> buf = &arr[0];
      fwrite(buf, 1, bufLen, file);
      bufLen = 0;
   }

   ~CRTFileWriter() {
      this->!CRTFileWriter();
   }

   !CRTFileWriter() {
      Flush();
      fclose(file);
   }
};

int main() {
   SystemFileWriter w("systest.txt");
   CRTFileWriter ^ w2 = gcnew CRTFileWriter("crttest.txt");
}
```

## <a name="see-also"></a>関連項目

[クラスと構造体](../extensions/classes-and-structs-cpp-component-extensions.md)
