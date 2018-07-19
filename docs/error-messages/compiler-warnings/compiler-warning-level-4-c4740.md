---
title: コンパイラの警告 (レベル 4) C4740 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4740
dev_langs:
- C++
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6260a923da9f48b869707480d64f9be13ef7e9c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293310"
---
# <a name="compiler-warning-level-4-c4740"></a>コンパイラの警告 (レベル 4) C4740
グローバルな最適化を抑制するまたはインライン asm コードの外部のフロー  
  
 またはのうちにジャンプ先がある場合に、`asm`ブロック、その関数に対してグローバルな最適化を無効にします。  
  
 次の例では、C4740 が生成されます。  
  
```  
// C4740.cpp  
// compile with: /O2 /W4  
// processor: x86  
int main() {  
   __asm jmp tester  
   tester:;  
}  
```