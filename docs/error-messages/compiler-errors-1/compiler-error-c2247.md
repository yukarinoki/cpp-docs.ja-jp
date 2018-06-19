---
title: コンパイラ エラー C2247 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2247
dev_langs:
- C++
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed27398ea1f51ccc2ef0d3339446b422c7a503c0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172314"
---
# <a name="compiler-error-c2247"></a>コンパイラ エラー C2247
' identifier' の 'class' では、'specifier' を使用して、'class' から継承するためアクセスできません。  
  
 `identifier` プライベートまたはプロテクトのアクセスで宣言されたクラスから継承されます。  
  
 次の例では、C2247 が生成されます。  
  
```  
// C2247.cpp  
class A {  
public:  
   int i;  
};  
class B : private A {};    // B inherits a private A  
class C : public B {} c;   // so even though C's B is public  
int j = c.i;               // C2247, i not accessible  
```  
  
 このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成することもできます。 プロテクト メンバーのアクセスを制御します。 プロテクト メンバー (n) は、(A) (n) がメンバーである、クラスから継承するクラス (B) のメンバー関数からのみアクセスできます。  
  
 Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C の両方で有効であるコードでは、型のフレンドであるメンバーを宣言します。 パブリック継承も使用できます。  
  
```  
// C2247b.cpp  
// compile with: /c  
// C2247 expected  
class A {  
public:  
   void f();  
   int n;  
};  
  
class B: protected A {  
   // Uncomment the following line to resolve.  
   // friend void A::f();  
};  
  
void A::f() {  
   B b;  
   b.n;  
}  
```  
  
 C2247 が Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成されることもできます: プライベート基本クラスはアクセスできないようになりました。 プライベート基底クラスを型には、クラス (A) は、(C)、基底クラスとして B を使用する型にアクセスできない (B) 必要があります。  
  
 Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C の両方で有効であるコードでは、スコープ演算子を使用します。  
  
```  
// C2247c.cpp  
// compile with: /c  
struct A {};  
  
struct B: private A {};  
  
struct C : B {  
   void f() {  
      A *p1 = (A*) this;   // C2247  
      // try the following line instead  
      // ::A *p2 = (::A*) this;  
   }  
};  
```