---
title: コンパイラの警告 (レベル 1) C4939 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4939
dev_langs:
- C++
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 459674bb4e6899563a18943f7ba510a6168d0e28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4939"></a>コンパイラの警告 (レベル 1) C4939
\#プラグマ vtordisp は廃止されており、Visual C の将来のリリースで削除される予定  
  
 [vtordisp](../../preprocessor/vtordisp.md) プラグマは今後の Visual C++ バージョンからは削除されます  
  
## <a name="example"></a>例  
 次の例では C4939 警告が生成されます。  
  
```  
// C4939.cpp  
// compile with: /c /W1  
#pragma vtordisp(off)   // C4939  
```