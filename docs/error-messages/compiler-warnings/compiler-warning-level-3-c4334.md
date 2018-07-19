---
title: コンパイラの警告 (レベル 3) C4334 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4334
dev_langs:
- C++
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f26749c968c3cac18b509046633ba3d91d15a4be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292686"
---
# <a name="compiler-warning-level-3-c4334"></a>コンパイラの警告 (レベル 3) C4334
'operator': 64 ビットに 32 ビット シフトの結果が暗黙的に変換 (されました 64 ビット シフト目的としていますか?)  
  
 32 ビット シフトの結果は、64 ビットおよび 64 ビット シフトされたものである、コンパイラを疑いますに暗黙的に変換されました。  この警告を解決するには、64 ビット シフトを使用するか 64 ビットをシフトの結果を明示的にキャストします。  
  
## <a name="example"></a>例  
 次の例では、C4334 を生成します。  
  
```  
// C4334.cpp  
// compile with: /W3 /c  
void SetBit(unsigned __int64 *p, int i) {  
   *p |= (1 << i);   // C4334  
   *p |= (1i64 << i);   // OK  
}  
```