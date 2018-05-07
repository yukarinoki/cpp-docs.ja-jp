---
title: コンパイラの警告 (レベル 2) C4307 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4307
dev_langs:
- C++
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52914fc5825bda5647308c006b853538f3d6225e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-2-c4307"></a>コンパイラの警告 (レベル 2) C4307
'operator': 整数定数がオーバーフローしました  
  
 演算子は、それに割り当てられた領域がオーバーフローしたため整数の定数に評価される式で使用されます。 定数のより大きい型を使用する必要があります。 A **int を署名**よりも小さい値を保持する、`unsigned int`ため、 **int を署名**1 ビットを使用して、記号を表します。  
  
 次の例では、C4307 が生成されます。  
  
```  
// C4307.cpp  
// compile with: /W2  
int i = 2000000000 + 2000000000;   // C4307  
int j = (unsigned)2000000000 + 2000000000;   // OK  
  
int main()  
{  
}  
```