---
title: コンパイラ エラー C2571 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96dea582cf5d1211d57eac94a7f70458a51542ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2571"></a>コンパイラ エラー C2571
'function': 仮想関数は、'union' 共用体にすることはできません  
  
 仮想関数を持つ共用体が宣言されています。 クラスまたは構造体でのみ仮想関数を宣言することができます。  考えられる解決策:  
  
1.  クラスまたは構造体、共用体を変更します。  
  
2.  非仮想関数を作成します。  
  
 次の例では、C2571 が生成されます。  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```