---
title: コンパイラ エラー C2846 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2846
dev_langs:
- C++
helpviewer_keywords:
- C2846
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b217e37cf1eb9ed94f6b0a1e2a3ec01d82731f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2846"></a>コンパイラ エラー C2846
'constructor': インターフェイスは、コンス トラクターを持つことはできません  
  
 Visual C[インターフェイス](../../cpp/interface.md)コンス トラクターを持つことはできません。  
  
 次の例では、C2846 が生成されます。  
  
```  
// C2846.cpp  
// compile with: /c  
__interface C {  
   C();   // C2846 constructor not allowed in an interface  
};  
```