---
title: dynamic_cast 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- dynamic_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- dynamic_cast keyword [C++]
ms.assetid: f380ada8-6a18-4547-93c9-63407f19856b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a87105ad2d52ebbb7749deafadedcd510314038f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="dynamiccast-operator"></a>dynamic_cast 演算子
オペランド `expression` を `type-id` 型のオブジェクトに変換します。  
  
## <a name="syntax"></a>構文  
  
```  
  
dynamic_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>コメント  
 `type-id` は、以前に定義されたクラス型への参照またはポインター、または "void 型へのポインター" である必要があります。 `expression` の型は、`type-id` がポインターの場合はポインター、`type-id` が参照の場合は左辺値である必要があります。  
  
 参照してください[static_cast](../cpp/static-cast-operator.md)と各を使用する適切な静的および動的なキャスト変換では、間の違いの説明。  
  
 マネージ コードの `dynamic_cast` の動作には、次の 2 つの大きな変更があります。  
  
-   ボックス化された列挙体の基になる型へのポインターへの `dynamic_cast` は、実行時に失敗し、変換されたポインターではなく 0 を返します。  
  
-   `dynamic_cast` は、`type-id` が値型への内部ポインターであり、キャストが実行時に失敗した場合に、例外をスローしなくなりました。  キャストは、スローする代わりに、ポインター値 0 を返します。  
  
 `type-id` が `expression` の明確でアクセス可能な直接または間接的な基底クラスへのポインターである場合、結果は `type-id` 型の一意のサブオブジェクトへのポインターになります。 例えば:  
  
```  
// dynamic_cast_1.cpp  
// compile with: /c  
class B { };  
class C : public B { };  
class D : public C { };  
  
void f(D* pd) {  
   C* pc = dynamic_cast<C*>(pd);   // ok: C is a direct base class  
                                   // pc points to C subobject of pd   
   B* pb = dynamic_cast<B*>(pd);   // ok: B is an indirect base class  
                                   // pb points to B subobject of pd  
}  
```  
  
 このような変換は "アップキャスト" と呼ばれます。理由は、クラスの階層構造で、派生したクラスから上位に (つまり、そのクラスの派生元のクラスに) ポインターを移動するためです。 アップキャストは暗黙の変換です。  
  
 `type-id` が void* の場合、`expression` の実際の型を確認するためにランタイム チェックが行われます。 結果は `expression` によってポイントされた完全なオブジェクトへのポインターです。 例えば:  
  
```  
// dynamic_cast_2.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
  
void f() {  
   A* pa = new A;  
   B* pb = new B;  
   void* pv = dynamic_cast<void*>(pa);  
   // pv now points to an object of type A  
  
   pv = dynamic_cast<void*>(pb);  
   // pv now points to an object of type B  
}  
```  
  
 `type-id` が void* でない場合は、`expression` によって指し示されるオブジェクトが `type-id` 型によって指し示される型に変換できるかどうかを確認するランタイム チェックが行われます。  
  
 `expression` の型が `type-id` の型の基底クラスである場合は、ランタイム チェックが実行されて、`expression` が `type-id` の型の完全なオブジェクトを実際に指し示しているかどうかが確認されます。 実際に指し示している場合、結果は `type-id` の型の完全なオブジェクトへのポインターになります。 例えば:  
  
```  
// dynamic_cast_3.cpp  
// compile with: /c /GR  
class B {virtual void f();};  
class D : public B {virtual void f();};  
  
void f() {  
   B* pb = new D;   // unclear but ok  
   B* pb2 = new B;  
  
   D* pd = dynamic_cast<D*>(pb);   // ok: pb actually points to a D  
   D* pd2 = dynamic_cast<D*>(pb2);   // pb2 points to a B not a D  
}  
```  
  
 このような変換は "ダウンキャスト" と呼ばれます。理由は、クラスの階層構造で特定のクラスから下位に (つまり、そのクラスから派生したクラスに) ポインターを移動するためです。  
  
 多重継承の場合、あいまいさが生じる可能性があります。 次の図に示すクラスの階層構造の場合を考えてみましょう。  
  
 CLR 型の場合、`dynamic_cast` を実行すると、暗黙的な変換が可能な場合、何も行われません。変換が失敗した場合は、動的チェックを実行し、`isinst` を返す MSIL `nullptr` 命令が実行されます。  
  
 次のサンプルでは、クラスが特定の型のインスタンスであるかどうかを判断するために `dynamic_cast` を使用します。  
  
```  
// dynamic_cast_clr.cpp  
// compile with: /clr  
using namespace System;  
  
void PrintObjectType( Object^o ) {  
   if( dynamic_cast<String^>(o) )  
      Console::WriteLine("Object is a String");  
   else if( dynamic_cast<int^>(o) )  
      Console::WriteLine("Object is an int");  
}  
  
int main() {  
   Object^o1 = "hello";  
   Object^o2 = 10;  
  
   PrintObjectType(o1);  
   PrintObjectType(o2);  
}  
```  
  
 ![クラスの複数の継承を示す階層](../cpp/media/vc39011.gif "vc39011")  
複数の継承を示すクラスの階層構造  
  
 `D` 型のオブジェクトへのポインターは、`B` または `C` に安全にキャストできます。 しかし、`D` が `A` オブジェクトを指し示すようにキャストされる場合、結果は `A` のどのインスタンスになるでしょうか。 このような場合に、あいまいなキャスト エラーが発生します。 この問題を回避するには、2 種類の明確なキャストを実行します。 例えば:  
  
```  
// dynamic_cast_4.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
class D : public B {virtual void f();};  
  
void f() {  
   D* pd = new D;  
   B* pb = dynamic_cast<B*>(pd);   // first cast to B  
   A* pa2 = dynamic_cast<A*>(pb);   // ok: unambiguous  
}  
```  
  
 仮想基底クラスを使用するときに、あいまいさが発生する可能性もあります。 次の図に示すクラスの階層構造の場合を考えてみましょう。  
  
 ![クラスの仮想基底クラスを示す階層](../cpp/media/vc39012.gif "vc39012")  
仮想基底クラスを示すクラスの階層構造  
  
 この階層構造では、`A` は仮想基底クラスです。 `E` クラスのインスタンスと `A` サブオブジェクトへのポインターがある場合、`dynamic_cast` へのポインターへの `B` はあいまいさが原因で失敗します。 最初に、完全な `E` オブジェクトにキャストし、その後、明確な方法で階層を上へとたどり、正しい `B` オブジェクトに到達する必要があります。  
  
 次の図に示すクラスの階層構造の場合を考えてみましょう。  
  
 ![クラスの重複する基底クラスを示す階層](../cpp/media/vc39013.gif "vc39013")  
基底クラスの複製を示すクラスの階層構造  
  
 `E` 型のオブジェクトと `D` サブオブジェクトへのポインターがあるとして、`D` サブオブジェクトから左端の `A` サブオブジェクトに移動するには、変換を 3 回行います。 `dynamic_cast` ポインターから `D` ポインターへの `E` 変換を実行してから、`dynamic_cast` から `E` への変換 (`B` または暗黙の型変換) を実行し、最後に `B` から `A` への暗黙の型変換を実行することができます。 例えば:  
  
```  
// dynamic_cast_5.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B : public A {virtual void f();};  
class C : public A { };  
class D {virtual void f();};  
class E : public B, public C, public D {virtual void f();};  
  
void f(D* pd) {  
   E* pe = dynamic_cast<E*>(pd);  
   B* pb = pe;   // upcast, implicit conversion  
   A* pa = pb;   // upcast, implicit conversion  
}  
```  
  
 `dynamic_cast` 演算子を使用して、"クロス キャスト" を実行することもできます。 同じクラス階層を使用すると、完全なオブジェクトが `B` 型であれば、たとえば `D` サブオブジェクトから `E` サブオブジェクトへのように、ポインターをキャストできます。  
  
 クロス キャストを考慮すると、`D` へのポインターから左端の `A` サブオブジェクトへのポインターへの変換は、実際には 2 ステップで行うことができます。 `D` から `B` にクロス キャストを実行してから、`B` から `A` への暗黙の型変換を実行できます。 例えば:  
  
```  
// dynamic_cast_6.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B : public A {virtual void f();};  
class C : public A { };  
class D {virtual void f();};  
class E : public B, public C, public D {virtual void f();};  
  
void f(D* pd) {  
   B* pb = dynamic_cast<B*>(pd);   // cross cast  
   A* pa = pb;   // upcast, implicit conversion  
}  
```  
  
 null ポインター値は、`dynamic_cast` によって変換先の型の null ポインター値に変換されます。  
  
 `dynamic_cast < type-id > ( expression )` を使用するときに、`expression` を型 `type-id` に安全に変換できない場合、ランタイム チェックにより、キャストは失敗します。 例えば:  
  
```  
// dynamic_cast_7.cpp  
// compile with: /c /GR  
class A {virtual void f();};  
class B {virtual void f();};  
  
void f() {  
   A* pa = new A;  
   B* pb = dynamic_cast<B*>(pa);   // fails at runtime, not safe;  
   // B not derived from A  
}  
```  
  
 ポインター型への失敗したキャストの値は、null ポインターです。 参照型をスローする失敗したキャスト、 [bad_cast 例外](../cpp/bad-cast-exception.md)です。   場合`expression`、有効なオブジェクトを参照または をポイントしません、`__non_rtti_object`例外がスローされます。  
  
 参照してください[typeid](../cpp/typeid-operator.md)の詳細について、`__non_rtti_object`例外。  
  
## <a name="example"></a>例  
 次のサンプルは、オブジェクト (構造体 C) への基底クラス (構造体 A) ポインターを作成します。  このことと、仮想関数があるという事実によって、実行時ポリモーフィズムが可能になります。  
  
 このサンプルでは、階層内の非仮想関数も呼び出します。  
  
```  
// dynamic_cast_8.cpp  
// compile with: /GR /EHsc  
#include <stdio.h>  
#include <iostream>  
  
struct A {  
    virtual void test() {  
        printf_s("in A\n");  
   }  
};  
  
struct B : A {  
    virtual void test() {  
        printf_s("in B\n");  
    }  
  
    void test2() {  
        printf_s("test2 in B\n");  
    }  
};  
  
struct C : B {  
    virtual void test() {  
        printf_s("in C\n");  
    }  
  
    void test2() {  
        printf_s("test2 in C\n");  
    }  
};  
  
void Globaltest(A& a) {  
    try {  
        C &c = dynamic_cast<C&>(a);  
        printf_s("in GlobalTest\n");  
    }  
    catch(std::bad_cast) {  
        printf_s("Can't cast to C\n");  
    }  
}  
  
int main() {  
    A *pa = new C;  
    A *pa2 = new B;  
  
    pa->test();  
  
    B * pb = dynamic_cast<B *>(pa);  
    if (pb)  
        pb->test2();  
  
    C * pc = dynamic_cast<C *>(pa2);  
    if (pc)  
        pc->test2();  
  
    C ConStack;  
    Globaltest(ConStack);  
  
   // will fail because B knows nothing about C  
    B BonStack;  
    Globaltest(BonStack);  
}  
```  
  
```Output  
in C  
test2 in B  
in GlobalTest  
Can't cast to C  
```  
  
## <a name="see-also"></a>関連項目  
 [キャスト演算子](../cpp/casting-operators.md)   
 [キーワード](../cpp/keywords-cpp.md)