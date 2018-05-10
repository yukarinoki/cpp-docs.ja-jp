---
title: コンパイラ エラー C2698 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c466e39702f1e408ad96d79c16c4a5953fa373f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2698"></a>コンパイラ エラー C2698
using 宣言の '1' の宣言と共存できません既存 using 宣言の' 2' の宣言。  
  
 作成したら、[宣言を使用して](../../cpp/using-declaration.md)データ メンバーを使用しているすべての名前を使用するものと同じスコープ内の宣言は使用できません、のみの関数をオーバー ロードすることができます。  
  
 次の例では、C2698 が生成されます。  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```