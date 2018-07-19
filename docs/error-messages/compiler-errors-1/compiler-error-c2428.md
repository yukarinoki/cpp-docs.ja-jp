---
title: コンパイラ エラー C2428 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2428
dev_langs:
- C++
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2468e20265de6558464a493f49439f1766effa5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33223557"
---
# <a name="compiler-error-c2428"></a>コンパイラ エラー C2428
'operation': 型 'bool' のオペランドでは使用できません  
  
 型のオブジェクトにデクリメント演算子を適用することはできません`bool`です。  
  
 次の例では、C2428 が生成されます。  
  
```  
// C2428.cpp  
void g(bool fFlag) {  
   --fFlag;   // C2428  
   fFlag--;   // C2428  
}  
```