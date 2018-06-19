---
title: コンパイラ エラー C2153 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2153
dev_langs:
- C++
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6d288434cce1e1584a61040145b07d26defd9dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169726"
---
# <a name="compiler-error-c2153"></a>コンパイラ エラー C2153
16 進型定数は 16 進数には、少なくとも 1 つをいる必要があります。  
  
 16 進定数 0 0 X、x と \x が有効ではありません。 16 進数には、少なくとも 1 つが従う必要があります x または X。  
  
 次の例では、C2153 が生成されます。  
  
```  
// C2153.cpp  
int main() {  
   int a= 0x;    // C2153  
   int b= 0xA;   // OK  
}  
```