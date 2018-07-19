---
title: ユーザー定義変換 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 721f7135814db0421165fed74e124a7a8fe58e99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170649"
---
# <a name="user-defined-conversions-ccli"></a>ユーザー定義変換 (C++/CLI)
このセクションでは、参照または値型または参照型のインスタンスには、変換内の型のいずれかの場合、ユーザー定義の変換 (UDC) がについて説明します。  
  
## <a name="implicit-and-explicit-conversions"></a>暗黙的および明示的な変換  
 ユーザー定義の変換は暗黙的または明示的なのか、できます。  UDC 暗黙の変換が情報の損失にならない場合があります。 それ以外の場合、明示的な UDC を定義する必要があります。  
  
 ネイティブ クラスのコンス トラクターは、ネイティブ クラスに参照または値の型を変換に使用できます。  
  
 変換の詳細については、次を参照してください。[ボックス化](../windows/boxing-cpp-component-extensions.md)と[標準変換](../cpp/standard-conversions.md)です。  
  
```  
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
 変換元演算子は、他のクラスのオブジェクトから、演算子が定義されているクラスのオブジェクトを作成します。  
  
 標準の C++ では、変換元演算子; をサポートしていません標準 C++ では、この目的のコンス トラクターを使用します。 ただし、CLR 型を使用する場合、Visual C は、変換元演算子を呼び出すため構文のサポートを提供します。  
  
 他の CLS 準拠の言語とも相互運用、対応する変換元演算子で特定のクラスの各単項のユーザー定義のコンス トラクターをラップする場合します。  
  
 変換元演算子:  
  
-   静的関数として定義するものとします。  
  
-   いずれかのできます (短い形式の int などの有効桁数が失われない変換) の暗黙的または明示的な有効桁数の損失が存在する場合。  
  
-   クラスを含むオブジェクトを返します。  
  
-   含まれていては唯一のパラメーターの種類として"from"の型。  
  
 次の例では、暗黙的および明示的な「変換元」、ユーザー定義変換 (UDC) 演算子を使用しています。  
  
```  
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
  
## <a name="convert-to-operators"></a>変換先演算子  
 変換先演算子は、その他のオブジェクトを演算子が定義されているクラスのオブジェクトを変換します。 次の例は、暗黙的な変換先、ユーザー定義変換演算子は示しています。  
  
```  
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
  
 明示的なユーザー定義変換先の変換演算子は、何らかの方法でデータが失われる可能性のある変換に適しています。 明示的な変換先演算子を呼び出すには、キャストを使用する必要があります。  
  
```  
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
  
## <a name="to-convert-generic-classes"></a>ジェネリック クラスを変換するには  
 ジェネリック クラスを T に変換することができます。  
  
```  
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
  
 変換コンス トラクターは、型を受け取り、およびオブジェクトの作成に使用します。  直接の初期化のみで、変換されるコンス トラクターが呼び出されますキャストでは、変換コンス トラクターは呼び出されません。 既定では、変換コンス トラクターは、CLR 型の明示的なは。  
  
```  
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
  
 このサンプル コードでは、暗黙的な静的変換関数は、明示的な変換コンス トラクターと同じ動作を行います。  
  
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
 [クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)