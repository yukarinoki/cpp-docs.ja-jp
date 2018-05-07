---
title: コンパイラ エラー C2040 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2040
dev_langs:
- C++
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6b19a5dd647e51efb46ef9798b7f7cdff5339b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2040"></a>コンパイラ エラー C2040
'operator' : 間接参照のレベルが 'identifier1' と 'identifier2' で異なっています。  
  
 指定したオペランドを含む式に、互換性がないオペランド型または暗黙的に変換されるオペランド型が含まれています。 オペランドが両方とも数値型である場合や、両方とも数値型でない場合 (つまり配列やポインターの場合)、オペランドは変更されずに使用されます。 片方がオペランドであるのにもう片方が数値型でない場合、オペランドの方はオペランドでない方の型に変換されます。  
  
 この例では C2040 が生成され、その修正方法が示されています。  
  
```  
// C2040.cpp  
// Compile by using: cl /c /W3 C2040.cpp  
bool test() {  
   char c = '3';  
   return c == "3"; // C2446, C2040  
   // return c == '3'; // OK  
}  
```