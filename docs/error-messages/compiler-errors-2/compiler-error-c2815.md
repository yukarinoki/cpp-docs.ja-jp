---
title: コンパイラ エラー C2815 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2815
dev_langs:
- C++
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43eadfe636250c0acab9bcb2cd09323292f26a43
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2815"></a>コンパイラ エラー C2815
'operator delete': 仮引数の最初のパラメーターである必要があります ' void *'、'param' が使用されましたが、  
  
 ユーザー定義[演算子 delete](../../standard-library/new-operators.md#op_delete)関数は、型の最初の仮パラメーターを受け取る必要があります`void *`です。  
  
 次の例では、C2815 が生成されます。  
  
```  
// C2815.cpp  
// compile with: /c  
class CMyClass {  
public:  
   void mf1(int *a);  
   void operator delete(CMyClass *);   // C2815  
   void operator delete(void *);   
};  
```