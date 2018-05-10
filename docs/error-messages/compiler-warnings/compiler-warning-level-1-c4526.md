---
title: コンパイラの警告 (レベル 1) C4526 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5a38d629d61e16b038701522d4bb27a4de7391d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4526"></a>コンパイラの警告 (レベル 1) C4526
'function': 静的メンバー関数は仮想関数をオーバーライドできません ' 仮想 function'override が無視されます、仮想関数を非表示には  
  
 静的メンバー関数では、仮想と静的メンバー関数は、仮想関数をオーバーライドする条件を満たしています。  
  
 次のコードには、C4526 が生成されます。  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 考えられる修正方法を次に示します。  
  
-   関数が基底クラスの仮想関数をオーバーライドするためのもので、静的な指定子を削除します。  
  
-   関数は、静的メンバー関数を意図した場合、基底クラスの仮想関数とも競合しないように変更します。