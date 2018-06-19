---
title: コンパイラ エラー C2910 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2910
dev_langs:
- C++
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fec2baafae0647964a56afaed3286140f8b9f759
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242716"
---
# <a name="compiler-error-c2910"></a>コンパイラ エラー C2910
'function': 明示的特殊化できません  
  
 コンパイラでは、明示的に特殊化関数を 2 回の試行が検出されました。  
  
 次の例では、C2910 が生成されます。  
  
```  
// C2910.cpp  
// compile with: /c  
template <class T>  
struct S;  
  
template <> struct S<int> { void f() {} };  
template <> void S<int>::f() {}   // C2910 delete this specialization  
```  
  
 C2910 は、テンプレートでないメンバーを明示的に特殊化しようとする場合にも生成できます。 つまり、関数テンプレートを明示的にのみ特殊化することができます。  
  
 次の例では、C2910 が生成されます。  
  
```  
// C2910b.cpp  
// compile with: /c  
template <class T> struct A {  
   A(T* p);  
};  
  
template <> struct A<void> {  
   A(void* p);  
};  
  
template <class T>  
inline A<T>::A(T* p) {}  
  
template <> A<void>::A(void* p){}   // C2910  
// try the following line instead  
// A<void>::A(void* p){}  
```  
  
 このエラーは Visual Studio .NET 2003 で行われたコンパイラ準拠作業の結果として生成することも: です。  
  
 コードは、Visual Studio .NET 2003 バージョンと Visual Studio .NET バージョンの Visual C では無効になります、削除`template <>`です。  
  
 次の例では、C2910 が生成されます。  
  
```  
// C2910c.cpp  
// compile with: /c  
template <class T> class A {  
   void f();  
};  
  
template <> class A<int> {  
   void f();  
};  
  
template <> void A<int>::f() {}   // C2910  
// try the following line instead  
// void A<int>::f(){}   // OK  
```