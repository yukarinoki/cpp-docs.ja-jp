---
title: コンパイラ エラー C2252 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2252
dev_langs:
- C++
helpviewer_keywords:
- C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d54e99fb1e4d3fb168b6b48a8cb6b1d0707281da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172396"
---
# <a name="compiler-error-c2252"></a>コンパイラ エラー C2252
現在のスコープ内のテンプレートを明示的にインスタンス化できません。  
  
 テンプレートの明示的なインスタンス化に問題が検出されました。  たとえば、関数にテンプレートを明示的にインスタンス化できません。  
  
 次の例では、C2252 が生成されます。  
  
```  
// C2252.cpp  
class A {  
public:  
   template <class T>  
   int getit(int i , T * it ) {  
      return i;  
   }  
   template int A::getit<double>(int i, double * it);   // C2252  
   // try the following line instead  
   // template <> int A::getit<double>(int i, double * it);  
  
};  
  
int main() {  
   // cannot explicitly instantiate in function  
   template int A::getit<long>(int i, long * it);   // C2252  
}  
```