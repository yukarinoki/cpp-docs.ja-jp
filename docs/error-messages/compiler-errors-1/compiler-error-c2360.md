---
title: コンパイラ エラー C2360 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2360
dev_langs:
- C++
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c24a44222a01d66c57aab340c5a06469f212e285
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33196286"
---
# <a name="compiler-error-c2360"></a>コンパイラ エラー C2360
'identifier' の初期化が 'case' ラベルによって行われませんでした。  
  
 初期化`identifier`でスキップすることができます、`switch`ステートメントです。 宣言がブロックで囲まれている場合を除き、初期化子を含む宣言ジャンプすることはできません。 (ブロック内で宣言されている場合を除き、変数はスコープ内で最後までの`switch`ステートメントです)。  
  
 次の例では、C2360 が生成されます。  
  
```  
// C2360.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   case 1 :   // C2360  
      int k = 1;  
   }  
}  
```  
  
 考えられる解決方法:  
  
```  
// C2360b.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   case 1 :  
      int k = 1;  
   }  
}  
```