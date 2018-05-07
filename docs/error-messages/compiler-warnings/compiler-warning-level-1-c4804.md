---
title: コンパイラの警告 (レベル 1) C4804 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4804
dev_langs:
- C++
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 677899230b2475c80f9bdd461a0c79740c4d3bec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4804"></a>コンパイラの警告 (レベル 1) C4804
'operation': 型 'bool' の操作で安全でないを使用します。  
  
 この警告は、使用するときに、`bool`変数、または予期しない値です。 C4804 が生成された負の単項演算子などの演算子を使用する場合など (**-**) またはビットごとの補数演算子 (`~`)。 コンパイラは、式を評価します。  
  
## <a name="example"></a>例  
 次の例では、C4804 が生成されます。  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```