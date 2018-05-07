---
title: コンパイラ エラー C2676 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2676
dev_langs:
- C++
helpviewer_keywords:
- C2676
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ffda876d8f399d3953a592d3c157b0957c7cb9a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2676"></a>コンパイラ エラー C2676
二項演算子 'operator' : 'type' は、この演算子または定義済の演算子に適切な型への変換の定義を行いません。  
  
 この演算子を使うには、型を指定してこの演算子をオーバーロードするか、この演算子が定義された型への変換を定義する必要があります。  
  
## <a name="example"></a>例  
 次の例では、C2676 を生成します。  
  
```  
// C2676.cpp  
// C2676 expected  
struct C {  
   C();  
} c;  
  
struct D {  
   D();  
   D operator >>( C& ){return * new D;}  
   D operator <<( C& ){return * new D;}  
} d;  
  
struct E {  
   // operator int();  
};  
  
int main() {  
   d >> c;  
   d << c;  
   E e1, e2;  
   e1 == e2;   // uncomment operator int in class E, then  
               // it is OK even though neither E::operator==(E) nor   
               // operator==(E, E) defined. Uses the conversion to int   
               // and then the builtin-operator==(int, int)  
}  
```  
  
## <a name="example"></a>例  
 C2676 は、参照型の `this` ポインターでポインター演算を試行した場合にも発生することがあります。  
  
 `this` ポインターは、参照型の型ハンドルのポインターです。 詳細については、次を参照してください。[このセマンティクス ポインター](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)です。  
  
 次の例では、C2676 を生成します。  
  
```  
// C2676_a.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct A {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
  
   A() {  
      Console::WriteLine("{0}", this + 3.3);   // C2676  
      Console::WriteLine("{0}", this[3.3]);   // OK  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
}  
```