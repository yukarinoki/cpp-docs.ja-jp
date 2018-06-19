---
title: コンパイラ エラー C2283 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2283
dev_langs:
- C++
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb602d1fa330876820cc7e1fe75fcfe7b736b81e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170857"
---
# <a name="compiler-error-c2283"></a>コンパイラ エラー C2283
'identifier' : 名前指定されていない struct が、純粋関数または抽象オーバーライド関数として指定されています  
  
 名前が指定されていないクラスまたは構造体のメンバー関数が、純粋指定子で宣言されていますが、これは許可されません。  
  
 次の例では C2283 が生成されます。  
  
```  
// C2283.cpp  
// compile with: /c  
struct {  
   virtual void func() = 0;   // C2283  
};  
struct T {  
   virtual void func() = 0;   // OK  
};  
```