---
title: コンパイラの警告 (レベル 1) C4544 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4544
dev_langs:
- C++
helpviewer_keywords:
- C4544
ms.assetid: 11ee04df-41ae-435f-af44-881e801315a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc07340c0b8c9cc513e8b10910ccee21152328f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4544"></a>コンパイラの警告 (レベル 1) C4544
'declaration': このテンプレート宣言の既定のテンプレート引数が無視されました  
  
 既定のテンプレート引数は誤った場所で指定されたため、無視されました。 クラス テンプレートの既定のテンプレート引数を指定できるのは、クラス テンプレートのメンバーではなく、クラス テンプレートの宣言または定義でのみです。  
  
 次の例では、C4545 を生成し、その修正方法を示しています。  
  
```  
// C4544.cpp  
// compile with: /W1 /LD  
template <class T>   
struct S  
{  
   template <class T1>   
      struct S1;  
   void f();  
};  
  
template <class T=int>  
template <class T1>  
struct S<T>::S1 {};   // C4544  
```  
  
 次の例では、既定のパラメーターがクラス テンプレート `S` に適用されます。  
  
```  
// C4544b.cpp  
// compile with: /LD  
template <class T = int>   
struct S  
{  
   template <class T1>   
      struct S1;  
   void f();  
};  
  
template <class T>  
template <class T1>  
struct S<T>::S1 {};  
```