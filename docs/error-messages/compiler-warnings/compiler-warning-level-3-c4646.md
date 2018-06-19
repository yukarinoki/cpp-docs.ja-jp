---
title: コンパイラの警告 (レベル 3) C4646 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4646
dev_langs:
- C++
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36ff770877333042319b2a91dc5006e2ceb4118f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291217"
---
# <a name="compiler-warning-level-3-c4646"></a>コンパイラの警告 (レベル 3) C4646
__declspec(noreturn) で宣言された関数に、non-void 戻り値の型があります。  
  
 [noreturn](../../cpp/noreturn.md) `__declspec` 修飾子でマークされた関数は [void](../../cpp/void-cpp.md) 型が必要です。  
  
 次の例では C4646 が生成されます。  
  
```  
// C4646.cpp  
// compile with: /W3 /WX  
int __declspec(noreturn) TestFunction()  
{   // C4646  make return type void  
}  
```