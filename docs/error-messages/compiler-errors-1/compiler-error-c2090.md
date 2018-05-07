---
title: コンパイラ エラー C2090 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2090
dev_langs:
- C++
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 718ed5ba8d422c2657dc58591ce285b0d85857cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2090"></a>コンパイラ エラー C2090
関数の配列を返します  
  
 関数は、配列を返すことはできません。 代わりに配列へのポインターを返します。  
  
 次の例では、C2090 が生成されます。  
  
```  
// C2090.cpp  
int func1(void)[] {}   // C2090  
```  
  
 考えられる解決方法:  
  
```  
// C2090b.cpp  
// compile with: /c  
int* func2(int * i) {  
   return i;  
}  
```