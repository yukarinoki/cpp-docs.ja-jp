---
title: コンパイラの警告 (レベル 1) C4616 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4616
dev_langs:
- C++
helpviewer_keywords:
- C4616
ms.assetid: 71e15265-c5bc-42ce-a6a9-4879892472b1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6cf59fa32b45215cc29c1cc500cc0bef3378b51e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4616"></a>コンパイラの警告 (レベル 1) C4616
\#pragma 警告: 警告番号 'number' 有効なコンパイラ警告ではありません  
  
 指定された警告番号、[警告](../../preprocessor/warning.md)プラグマを再割り当てすることはできません。 プラグマは無視されました。  
  
 次の例では、C4616 が生成されます。  
  
```  
// C4616.cpp  
// compile with: /W1 /c  
#pragma warning( disable : 0 )   // C4616  
#pragma warning( disable : 999 )   // OK  
#pragma warning( disable : 4998 )   // OK  
```