---
title: コンパイラの警告 (レベル 1) C4584 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4584
dev_langs:
- C++
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df3f92142fe42451ca7ae8272463d9347a263121
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4584"></a>コンパイラの警告 (レベル 1) C4584
'class1': 基底クラス 'class2' が 'class3' の基底クラスでは既に  
  
 定義したクラスから別の継承の 1 つ、2 つのクラスから継承されます。 例えば:  
  
```  
// C4584.cpp  
// compile with: /W1 /LD  
class A {  
};  
  
class B : public A {  
};  
  
class C : public A, public B { // C4584  
};  
```  
  
 ここでは、警告がクラス C に発行されます両方クラス A および B で、クラス A からも継承クラスから継承しているためこの警告は、アラームのこれらの基本クラスからのメンバーの使用を完全に修飾する必要がありますか、参照するクラスのメンバーがに関してあいまいなので、コンパイラ エラーが生成されることとして機能します。