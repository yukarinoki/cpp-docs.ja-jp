---
title: コンパイラの警告 (レベル 1) C4556 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- C4556
dev_langs:
- C++
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22d10f7dc73e0d5e39fcad8975114f7cb176b24d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4556"></a>コンパイラの警告 (レベル 1) C4556
組み込みイミディ エイト引数 'value' の値が '下限の上限値' の範囲外  
  
 組み込み関数では、ハードウェア命令と一致します。 ハードウェアの命令には、固定数の定数をエンコードするビットがあります。 場合***値***が範囲外には正常にエンコードされません。 コンパイラは、余分なビットを切り捨てます。  
  
 次の例では、C4556 が生成されます。  
  
```  
// C4556.cpp  
// compile with: /W1  
// processor: x86 IPF  
#include <xmmintrin.h>  
void test()  
{  
   __m64 m;  
   _m_pextrw(m, 5);   // C4556  
}  
int main()  
{  
}  
```