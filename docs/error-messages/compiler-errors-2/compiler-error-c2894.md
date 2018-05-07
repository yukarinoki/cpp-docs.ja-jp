---
title: コンパイラ エラー C2894 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2894
dev_langs:
- C++
helpviewer_keywords:
- C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92c412aa753d4440a25f8123b4b25e40360b7a3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2894"></a>コンパイラ エラー C2894
テンプレートは、'C' リンケージがあるために宣言することはできません。  
  
 このエラーは、内部で定義されたテンプレートによって発生することができます、 `extern` "C"ブロックします。  
  
 次の例では、C2894 が生成されます。  
  
```  
// C2894.cpp  
extern "C" {  
   template<class T> class stack {};   // C2894 fail  
  
   template<class T> void f(const T &aT) {}   // C2894  
}  
```  
  
 次の例では、C2894 が生成されます。  
  
```  
// C2894b.cpp  
// compile with: /c  
extern "C" template<class T> void f(const T &aT) {}   // C2894  
  
template<class T> void f2(const T &aT) {}   // OK  
```