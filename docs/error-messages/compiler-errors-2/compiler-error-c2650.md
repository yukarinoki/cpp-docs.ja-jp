---
title: コンパイラ エラー C2650 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2650
dev_langs:
- C++
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee76b2d80ff76033f6776b91ee90e52ef5e200cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232236"
---
# <a name="compiler-error-c2650"></a>コンパイラ エラー C2650
'operator': 仮想関数をすることはできません  
  
 A`new`または`delete`演算子が宣言されて`virtual`です。 これらの演算子は`static`メンバー関数し、することはできません`virtual`です。  
  
## <a name="example"></a>例  
 次の例では、C2650 が生成されます。  
  
```  
// C2650.cpp  
// compile with: /c  
class A {  
   virtual void* operator new( unsigned int );   // C2650  
   // try the following line instead  
   // void* operator new( unsigned int );  
};  
```