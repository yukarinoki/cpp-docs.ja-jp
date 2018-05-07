---
title: コンパイラ エラー C2791 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2791
dev_langs:
- C++
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65a3d399ed6c7f25b849335328550526ecf7a816
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2791"></a>コンパイラ エラー C2791
'super' の不正な使用: 'class' には、基本クラスはありません。  
  
 キーワード[super](../../cpp/super.md)を任意の基本クラスを持たないクラスのメンバー関数のコンテキスト内で使用されました。  
  
 次の例では、C2791 が生成されます。  
  
```  
// C2791.cpp  
struct D {  
   void mf() {  
      __super::mf();   // C2791  
   }  
};  
```