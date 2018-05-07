---
title: コンパイラの警告 (レベル 3) C4161 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4161
dev_langs:
- C++
helpviewer_keywords:
- C4161
ms.assetid: 03d3be61-83f1-4009-8310-8758ab67055f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c81072c5121bea4a323c3eb16cc58c6f28c06f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4161"></a>コンパイラの警告 (レベル 3) C4161
\#プラグマ pragma(pop...): ポップがプッシュ  
  
 ソース コードのポップが、プラグマ ***pragma***のプッシュを 1 回上回っているため、スタックが期待どおりに動作しない可能性があります。 警告を回避するには、ポップの数がプッシュの数を超えないようにします。  
  
## <a name="example"></a>例  
 次の例では、C4161 が生成されます。  
  
```  
// C4161.cpp  
// compile with: /W3 /LD  
#pragma pack(push, id)  
#pragma pack(pop, id)  
#pragma pack(pop, id)   // C4161, an extra pop  
  
#pragma bss_seg(".my_data1")  
int j;  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;  
  
#pragma bss_seg(pop, stack1)  
int m;  
  
#pragma bss_seg(pop, stack1)   // C4161  
```