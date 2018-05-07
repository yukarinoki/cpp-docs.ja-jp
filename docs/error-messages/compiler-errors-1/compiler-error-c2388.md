---
title: コンパイラ エラー C2388 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2388
dev_langs:
- C++
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38ce3de47355dea18f2c2deca8cfe07cde4d313f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2388"></a>コンパイラ エラー C2388
'symbol': シンボルは、両方 __declspec(appdomain) で宣言することはできませんと\__declspec(process)  
  
 `appdomain` および `process` `__declspec` 修飾子は、同じシンボルでは使用できません。 変数のストレージは、プロセスごとまたはアプリケーション ドメインごとに存在します。  
  
 詳細については、「 [appdomain](../../cpp/appdomain.md) 」および「 [process](../../cpp/process.md)」を参照してください。  
  
 次の例では C2388 が生成されます。  
  
```  
// C2388.cpp  
// compile with: /clr /c  
__declspec(process) __declspec(appdomain) int i;   // C2388  
__declspec(appdomain) int i;   // OK  
```