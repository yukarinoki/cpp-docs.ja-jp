---
title: コンパイラ エラー C2681 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2681
dev_langs:
- C++
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e35cf6effdbb5aaed5a898bf19a6b42c3df519e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2681"></a>コンパイラ エラー C2681
'type': 無効な式の型名  
  
 キャスト演算子は、無効な型から変換しようとしました。 たとえば、使用する場合、 [dynamic_cast](../../cpp/dynamic-cast-operator.md)ポインター型では、元の式を式に変換する演算子をポインターである必要があります。  
  
 次の例では、C2681 が生成されます。  
  
```  
// C2681.cpp  
class A { virtual void f(); };  
  
void g(int i) {  
    A* pa;  
    pa = dynamic_cast<A*>(i);  // C2681  
}  
```