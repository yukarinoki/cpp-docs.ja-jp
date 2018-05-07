---
title: コンパイラ エラー C2652 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 576aef31268c0cdce09162fc367358e0ed044429
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2652"></a>コンパイラ エラー C2652
'identifier': コピー コンス トラクター: 最初のパラメーターが 'identifier' することはできません  
  
 コピー コンス トラクターの最初のパラメーターは、クラス、構造体、または共用体が定義されているのと同じ型を持ちます。 最初のパラメーターは、型が型自体ではなくへの参照を指定できます。  
  
 次の例では、C2651 が生成されます。  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```