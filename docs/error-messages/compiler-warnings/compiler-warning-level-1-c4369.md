---
title: コンパイラの警告 (レベル 1) C4369 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4369
dev_langs:
- C++
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63445f0713b43ce7fde418ebd9d65403965c07ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4369"></a>コンパイラの警告 (レベル 1) C4369
'列挙子': 列挙子の値 'value' を 'type' として表現できず、値は 'new_value'  
  
 列挙子を計算すると、指定した基になる型の最大値よりも大きい値を指定します。  これによって、オーバーフローが発生し、コンパイラが型の最小値を列挙子の値をラップします。  
  
## <a name="example"></a>例  
 次の例では、C4369 を生成します。  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```