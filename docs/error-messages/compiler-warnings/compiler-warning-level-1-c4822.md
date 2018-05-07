---
title: コンパイラの警告 (レベル 1) C4822 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4822
dev_langs:
- C++
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9491d522c65eba3599c3618d510c57b55682876
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4822"></a>コンパイラの警告 (レベル 1) C4822
'member': ローカル クラスのメンバー関数は本体がありません  
  
 ローカル クラス メンバー関数が宣言されましたが、クラスに定義されていません。 ローカル クラス メンバー関数を使用するには、その関数をクラスに定義する必要があります。 クラスで宣言する関数をクラス外に定義することはできません。  
  
 ローカル クラス メンバー関数をクラス外に定義すると、エラーになります。  
  
 次の例では C4822 が生成されます。  
  
```  
// C4822.cpp  
// compile with: /W1  
int main() {  
   struct C {  
      void func1(int);   // C4822  
      // try the following line instead  
      // void func1(int){}  
  };  
}  
```