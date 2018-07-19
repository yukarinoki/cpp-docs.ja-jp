---
title: コンパイラ エラー C2164 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2164
dev_langs:
- C++
helpviewer_keywords:
- C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23596fc25685adc155220de344adcd7d25827985
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171325"
---
# <a name="compiler-error-c2164"></a>コンパイラ エラー C2164
'function': 組み込み関数が宣言されていません  
  
 `intrinsic`プラグマは宣言されていない関数を使用して (でのみ発生 **/Oi**)。 または、そのヘッダー ファイルを含めずにコンパイラ組み込み関数のいずれかが使用されました。  
  
 次の例では、C2164 が生成されます。  
  
```  
// C2164.c  
// compile with: /c  
// processor: x86  
// Uncomment the following line to resolve.  
// #include "xmmintrin.h"  
void b(float *p) {  
   _mm_load_ss(p);   // C2164  
}  
```