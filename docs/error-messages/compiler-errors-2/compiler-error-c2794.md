---
title: コンパイラ エラー C2794 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2794
dev_langs:
- C++
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2cee2ce072f3dfe106434443ba28047cf7b58284
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33237393"
---
# <a name="compiler-error-c2794"></a>コンパイラ エラー C2794
'function': 'class' の直接または間接基底クラスのメンバーではありません  
  
 使用しようとしています。 [super](../../cpp/super.md)存在しないメンバー関数を呼び出す。  
  
 次の例には、C2794 が生成されます。  
  
```  
// C2794.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::f();  // C2794  
   }  
};  
```