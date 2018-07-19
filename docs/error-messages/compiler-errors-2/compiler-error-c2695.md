---
title: コンパイラ エラー C2695 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2695
dev_langs:
- C++
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 67dc97688dddde37323f25b96bd8bbc596660e2f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231218"
---
# <a name="compiler-error-c2695"></a>コンパイラ エラー C2695
'function1': 仮想関数をオーバーライドする唯一の相違点から 'function2' 呼び出し規約  
  
 派生クラスで関数のシグネチャは、基本クラスで関数をオーバーライドし、呼び出し規則を変更できません。  
  
 次の例では、C2695 が生成されます。  
  
```  
// C2695.cpp  
class C {  
   virtual void __fastcall func();  
};  
  
class D : public C {  
   virtual void __clrcall func();   // C2695  
};  
```