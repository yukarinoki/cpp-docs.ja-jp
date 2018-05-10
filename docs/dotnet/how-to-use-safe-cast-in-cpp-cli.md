---
title: '方法: safe_cast を使用して、C + + CLI |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++], upcasting
ms.assetid: 0fbc87d8-ecdf-4cd5-81f4-0d8cc18e2aff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0f695c45d5202f376a4ce4daf14c37a7fd9a1904
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-safecast-in-ccli"></a>方法: C++/CLI で safe_cast を使用する
この記事は、C + で safe_cast を使用する方法を示しています。 + CLI アプリケーションです。 Safe_cast について[!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]を参照してください[safe_cast](../windows/safe-cast-cpp-component-extensions.md)です。  
  
## <a name="upcasting"></a>アップ キャスト  
 アップ キャストは、派生型からその基本クラスのいずれかへのキャストです。 このキャストは、安全な明示的なキャスト表記は必要ありません。 次の例を使用して、アップ キャストを実行する方法を示しています。`safe_cast`と指定されていない場合。  
  
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
  
## <a name="downcasting"></a>ダウン キャスト  
 ダウン キャストには、基底クラスから基底クラスから派生したクラスへのキャストを示します。  ダウン キャストは実行時にアドレス指定されるオブジェクトは、派生クラス オブジェクト実際に対処している場合にのみ安全です。  異なり`static_cast`、`safe_cast`動的チェックを実行し、スロー<xref:System.InvalidCastException>場合は、変換は失敗します。  
  
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
  
## <a name="safecast-with-user-defined-conversions"></a>ユーザー定義の変換と safe_cast  
 次の例は、使用する方法を示しています。`safe_cast`をユーザー定義の変換を呼び出します。  
  
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
  
## <a name="safecast-and-boxing-operations"></a>safe_cast およびボックス化の操作  
  
### <a name="boxing"></a>ボックス化  
  
 ボックス化は、コンパイラが挿入された、ユーザー定義の変換として定義されます。  したがって、使用することができます`safe_cast`CLR ヒープに値をボックス化します。  
  
 次の例では、単純なとユーザー定義の値の型をボックス化を示します。  A`safe_cast`がガベージ コレクトされたヒープに変数に割り当て、ネイティブ スタックには値型の変数をボックスします。  
  
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
  
 [次へ] 例は、ボックス化が経由でユーザー定義の変換で優先順位を持つ、`safe_cast`操作します。  
  
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
  
 ボックス化解除は、コンパイラが挿入された、ユーザー定義の変換として定義されます。  したがって、使用することができます`safe_cast`CLR ヒープに値をボックス化解除します。  
  
 ユーザー定義の変換は、ボックス化解除は、ボックス化とは異なりボックス化解除する必要がありますは明示的にする-によっては、実行する必要があります、 `static_cast`、C スタイル キャスト、または`safe_cast`; ボックス化解除し、暗黙的に実行できません。  
  
```cpp  
// safe_cast_unboxing.cpp  
// compile with: /clr  
int main() {  
   System::Object ^ o = 42;  
   int x = safe_cast<int>(o);  
}  
```  
  
 次のサンプルは、値型とのプリミティブ型をボックス化解除を示しています。  
  
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
  
## <a name="safecast-and-generic-types"></a>safe_cast 型およびジェネリック型  
 次の例は、使用する方法を示しています。`safe_cast`ジェネリック型にキャストを実行します。  
  
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
 [safe_cast](../windows/safe-cast-cpp-component-extensions.md)