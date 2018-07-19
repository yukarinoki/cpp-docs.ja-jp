---
title: コンパイラ エラー C2229 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2229
dev_langs:
- C++
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c61708e7e67db39f85b1ff782e8945facc2b9568
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172189"
---
# <a name="compiler-error-c2229"></a>コンパイラ エラー C2229
'identifier' の型が無効なサイズ 0 の配列  
  
 構造体またはビット フィールドのメンバーには、最後のメンバーではない、サイズが 0 の配列が含まれています。  
  
 サイズ 0 の配列は、構造体の最後のメンバーとして持つことができます、ため構造体を割り当てるときのサイズを指定する必要があります。  
  
 サイズ 0 の配列が構造体の最後のメンバーでない場合、コンパイラはその他のフィールドのオフセットを計算できません。  
  
 次の例では、C2229 が生成されます。  
  
```  
// C2229.cpp  
struct S {  
   int a[0];  // C2229  zero-sized array  
   int b[1];  
};  
  
struct S2 {  
   int a;  
   int b[0];  
};  
  
int main() {  
   // allocate 7 elements for b field  
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];  
   s2->b[6] = 100;  
}  
```