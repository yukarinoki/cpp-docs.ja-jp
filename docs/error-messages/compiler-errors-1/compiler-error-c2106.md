---
title: コンパイラ エラー C2106 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2106
dev_langs:
- C++
helpviewer_keywords:
- C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0d8b55bed4b86e44ada9f81dc2bf0269af604ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164815"
---
# <a name="compiler-error-c2106"></a>コンパイラ エラー C2106
'operator': 左のオペランドが左辺値にする必要があります  
  
 演算子の左側のオペランドとして左辺値が必要です。  
  
 次の例では、C2106 が生成されます。  
  
```  
// C2106.cpp  
int main() {  
   int a;  
   1 = a;   // C2106  
   a = 1;   // OK  
}  
```