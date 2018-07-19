---
title: コンパイラ エラー C2764 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2764
dev_langs:
- C++
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd07a00e701804a56f74c86e8a0aedf67e470320
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236454"
---
# <a name="compiler-error-c2764"></a>コンパイラ エラー C2764
'param': テンプレート パラメーターは使用されている、または部分的特殊化 'specialization' を推論できません。  
  
 テンプレート パラメーターは、部分的特殊化では使用されません。 これにより、部分的特殊化をテンプレート パラメーターを推測できないため使用できなくなります。  
  
## <a name="example"></a>例  
 次の例では、C2764 が生成されます。  
  
```  
// C2764.cpp  
#include <stdio.h>  
template <class T1, class T2>  
struct S  {  
   int m_i;  
};  
  
template <class T1, class T2>  
struct S<int, T2*> {   // C2764  
// try the following line instead  
// struct S<T1(*)(T2), T2*> {  
   char m_c;  
};  
  
int main() {  
   S<int, char> s1;  
   S<void (*)(short), short *> s2;  
   s2.m_c = 10;  
   s1.m_i = s2.m_c;  
   printf_s("%d\n", s1.m_i);  
}  
```