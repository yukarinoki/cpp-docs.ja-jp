---
description: '詳細情報: User-Defined 変換 (C++/CLI)'
title: ユーザー定義変換 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
ms.openlocfilehash: 0b07ab3201bfd379a17922f020486d0b17a59558
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204265"
---
# <a name="user-defined-conversions-ccli"></a>ユーザー定義変換 (C++/CLI)

このセクションでは、変換の型の1つが値型または参照型の参照またはインスタンスである場合の、ユーザー定義変換 (UDC) について説明します。

## <a name="implicit-and-explicit-conversions"></a>暗黙的な変換と明示的な変換

ユーザー定義の変換は、暗黙的または明示的に行うことができます。  変換によって情報が失われることがない場合は、UDC を暗黙的に指定する必要があります。 それ以外の場合は、明示的な UDC を定義する必要があります。

ネイティブクラスのコンストラクターを使用して、参照型または値型をネイティブクラスに変換できます。

変換の詳細については、「 [ボックス](../extensions/boxing-cpp-component-extensions.md) 化と [標準変換](../cpp/standard-conversions.md)」を参照してください。

```cpp
// mcpp_User_Defined_Conversions.cpp
// compile with: /clr
#include "stdio.h"
ref class R;
class N;

value class V {
   static operator V(R^) {
      return V();
   }
};

ref class R {
public:
   static operator N(R^);
   static operator V(R^) {
      System::Console::WriteLine("in R::operator N");
      return V();
   }
};

class N {
public:
   N(R^) {
      printf("in N::N\n");
   }
};

R::operator N(R^) {
   System::Console::WriteLine("in R::operator N");
   return N(nullptr);
}

int main() {
   // Direct initialization:
   R ^r2;
   N n2(r2);   // direct initialization, calls constructor
   static_cast<N>(r2);   // also direct initialization

   R ^r3;
   // ambiguous V::operator V(R^) and R::operator V(R^)
   // static_cast<V>(r3);
}
```

**出力**

```Output
in N::N
in N::N
```

## <a name="convert-from-operators"></a>変換元演算子

変換元演算子は、他のクラスのオブジェクトから演算子が定義されているクラスのオブジェクトを作成します。

標準 C++ では、変換元演算子はサポートされていません。標準 C++ では、コンストラクターがこの目的に使用します。 ただし、CLR 型を使用する場合は、Visual C++ 変換元演算子を呼び出すための構文サポートを提供します。

他の CLS 準拠の言語と相互運用するには、対応する変換元演算子を使用して、特定のクラスのユーザー定義の単項コンストラクターをラップすることが必要になる場合があります。

変換元演算子:

- は、静的な関数として定義する必要があります。

- は、有効桁数が失われる可能性がある場合に、暗黙的 (short から int などの有効桁数を失う変換の場合) または明示的な場合があります。

- は、含んでいるクラスのオブジェクトを返します。

- は、唯一のパラメーター型として "from" 型を持つ必要があります。

次のサンプルは、暗黙的および明示的な "変換元" のユーザー定義変換 (UDC) 演算子を示しています。

```cpp
// clr_udc_convert_from.cpp
// compile with: /clr
value struct MyDouble {
   double d;

   MyDouble(int i) {
      d = static_cast<double>(i);
      System::Console::WriteLine("in constructor");
   }

   // Wrap the constructor with a convert-from operator.
   // implicit UDC because conversion cannot lose precision
   static operator MyDouble (int i) {
      System::Console::WriteLine("in operator");
      // call the constructor
      MyDouble d(i);
      return d;
   }

   // an explicit user-defined conversion operator
   static explicit operator signed short int (MyDouble) {
      return 1;
   }
};

int main() {
   int i = 10;
   MyDouble md = i;
   System::Console::WriteLine(md.d);

   // using explicit user-defined conversion operator requires a cast
   unsigned short int j = static_cast<unsigned short int>(md);
   System::Console::WriteLine(j);
}
```

**出力**

```Output
in operator
in constructor
10
1
```

## <a name="convert-to-operators"></a>変換先の演算子

変換先演算子は、演算子が定義されているクラスのオブジェクトを他のオブジェクトに変換します。 次のサンプルは、暗黙的な変換先のユーザー定義変換演算子を示しています。

```cpp
// clr_udc_convert_to.cpp
// compile with: /clr
using namespace System;
value struct MyInt {
   Int32 i;

   // convert MyInt to String^
   static operator String^ ( MyInt val ) {
      return val.i.ToString();
   }

   MyInt(int _i) : i(_i) {}
};

int main() {
   MyInt mi(10);
   String ^s = mi;
   Console::WriteLine(s);
}
```

**出力**

```Output
10
```

明示的なユーザー定義変換変換演算子は、何らかの方法でデータが失われる可能性のある変換に適しています。 明示的な変換先演算子を呼び出すには、キャストを使用する必要があります。

```cpp
// clr_udc_convert_to_2.cpp
// compile with: /clr
value struct MyDouble {
   double d;
   // convert MyDouble to Int32
   static explicit operator System::Int32 ( MyDouble val ) {
      return (int)val.d;
   }
};

int main() {
   MyDouble d;
   d.d = 10.3;
   System::Console::WriteLine(d.d);
   int i = 0;
   i = static_cast<int>(d);
   System::Console::WriteLine(i);
}
```

**出力**

```Output
10.3
10
```

## <a name="to-convert-generic-classes"></a>ジェネリッククラスを変換するには

ジェネリッククラスを T に変換できます。

```cpp
// clr_udc_generics.cpp
// compile with: /clr
generic<class T>
public value struct V {
   T mem;
   static operator T(V v) {
      return v.mem;
   }

   void f(T t) {
      mem = t;
   }
};

int main() {
   V<int> v;
   v.f(42);
   int i = v;
   i += v;
   System::Console::WriteLine(i == (42 * 2) );
}
```

**出力**

```Output
True
```

変換コンストラクターは、型を受け取り、それを使用してオブジェクトを作成します。  変換コンストラクターは、直接初期化のみで呼び出されます。キャストは、変換コンストラクターを呼び出しません。 既定では、変換コンストラクターは CLR 型に対して明示的に使用されます。

```cpp
// clr_udc_converting_constructors.cpp
// compile with: /clr
public ref struct R {
   int m;
   char c;

   R(int i) : m(i) { }
   R(char j) : c(j) { }
};

public value struct V {
   R^ ptr;
   int m;

   V(R^ r) : ptr(r) { }
   V(int i) : m(i) { }
};

int main() {
   R^ r = gcnew R(5);

   System::Console::WriteLine( V(5).m);
   System::Console::WriteLine( V(r).ptr);
}
```

**出力**

```Output
5
R
```

このコードサンプルでは、暗黙的な静的変換関数は、明示的な変換コンストラクターと同じ処理を行います。

```
public value struct V {
   int m;
   V(int i) : m(i) {}
   static operator V(int i) {
      V v(i*100);
      return v;
   }
};

public ref struct R {
   int m;
   R(int i) : m(i) {}
   static operator R^(int i) {
      return gcnew R(i*100);
   }
};

int main() {
   V v(13);   // explicit
   R^ r = gcnew R(12);   // explicit

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);

   // explicit ctor can't be called here: not ambiguous
   v = 5;
   r = 20;

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);
}
```

**出力**

```Output
13
12
500
2000
```

## <a name="see-also"></a>関連項目

[クラスと構造体](../extensions/classes-and-structs-cpp-component-extensions.md)
