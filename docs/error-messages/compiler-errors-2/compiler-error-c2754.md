---
title: コンパイラ エラー C2754 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2754
dev_langs:
- C++
helpviewer_keywords:
- C2754
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d1b12eb7b091c2566235239f5c9b929e4e881ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233916"
---
# <a name="compiler-error-c2754"></a>コンパイラ エラー C2754
'specialization': 部分的特殊化は、依存非型テンプレート パラメーターを持つことはできません  
  
 依存非型テンプレート パラメーターを持つテンプレート クラスの部分的な特化しようとしました。 これは認められていません。  
  
 次の例では、C2754 が生成されます。  
  
```  
// C2754.cpp  
// compile with: /c  
  
template<class T, T t>  
struct A {};  
  
template<class T, int N>  
struct B {};  
  
template<class T> struct A<T,5> {};   // C2754  
template<> struct A<int,5> {};   // OK  
template<class T> struct B<T,5> {};   // OK  
```