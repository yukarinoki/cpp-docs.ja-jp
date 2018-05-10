---
title: コンパイラ エラー C2460 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2460
dev_langs:
- C++
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4220be654f93ecd79d196efc14657ca7346411f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2460"></a>コンパイラ エラー C2460
'identifier1': は 'identifier2' で宣言されています。  
  
 クラスまたは構造体 (`identifier2`) がそれ自体のメンバーとして宣言されている (`identifier1`)。 クラスと構造体の再帰的な定義を指定することはできません。  
  
 次の例では、C2460 が生成されます。  
  
```  
// C2460.cpp  
class C {  
   C aC;    // C2460  
};  
```  
  
 代わりに、クラスのポインターの参照を使用します。  
  
```  
// C2460.cpp  
class C {  
   C * aC;    // OK  
};  
```