---
title: コンパイラ エラー C3920 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3920
dev_langs:
- C++
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ced0a0f8fa2b6694de4dd901d71f6721e12493b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3920"></a>コンパイラ エラー C3920
' operator ': 後置インクリメント/デクリメントの WinRT または CLR 演算子の後置形式は定義できません WinRT または CLR 演算子には、対応するプレフィックスを呼び出す WinRT または CLR 演算子 (op_Increment/op_Decrement) が、後置形式のセマンティクスで  
  
 Windows Runtime および CLR は後置演算子をサポートしておらず、ユーザー定義後置演算子は許可されていません。  前置演算子は定義でき、プレ インクリメント演算でもポスト インクリメント演算でも前置演算子が使用されます。  
  
 次の例では、C3920 を生成し、その修正方法を示しています。  
  
```  
// C3920.cpp  
// compile with: /clr /LD  
public value struct V {  
   static V operator ++(V me, int)  
   // try the following line instead  
   // static V operator ++(V me)  
   {   // C3920  
      me.m_i++;  
      return me;  
   }  
  
   int m_i;  
};  
  
```