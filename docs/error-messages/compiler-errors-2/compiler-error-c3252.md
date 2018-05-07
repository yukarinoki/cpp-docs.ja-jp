---
title: コンパイラ エラー C3252 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3252
dev_langs:
- C++
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bc7ca0ccf3c973363e4427c89ccf497c20d1791
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3252"></a>コンパイラ エラー C3252
'method': マネージ型または WinRT 型で、仮想メソッドのアクセシビリティを制限することはできません。  
  
 基底クラスの仮想メソッドまたはインターフェイスのいずれかのメソッドを実装するクラスは、そのメソッドのアクセスを制限することはできません。  
  
 インターフェイスのすべてのメソッドはパブリックです。  
  
 次の例では、C3252 を生成し、その修正方法を示しています。  
  
```  
// C3252.cpp  
// compile with: /clr /c  
ref class A {  
public:  
   virtual void f1() {}  
};  
  
ref class B : public A {  
// To fix, uncomment the following line:   
// public:      
   virtual void f1() override sealed {}   // C3252, make this method public  
};  
```