---
title: コンパイラ エラー C2553 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2553
dev_langs:
- C++
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cfb09f2701b418ab5570641a78c465ff72ed943
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232535"
---
# <a name="compiler-error-c2553"></a>コンパイラ エラー C2553
'base_function': 仮想関数をオーバーライドするには、'override_function' とは異なる型が戻り値  
  
 派生クラス内の関数は、基底クラスの仮想関数をオーバーライドしようとしていますが、派生クラスの関数は基底クラス関数と同じ戻り値の型がありません。  オーバーライド関数のシグネチャは、オーバーライドされる関数のシグネチャと一致する必要があります。  
  
 次の例では、C2553 が生成されます。  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```