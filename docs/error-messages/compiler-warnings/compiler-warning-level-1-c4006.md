---
title: コンパイラの警告 (レベル 1) C4006 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4006
dev_langs:
- C++
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9b6cb37e383f4bfb9dd7f070344141b49ddf4f54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4006"></a>コンパイラの警告 (レベル 1) C4006
\#undef 識別子  
  
 `#undef` ディレクティブは未定義にする識別子を指定しませんでした。 ディレクティブは無視されます。 この警告を解決するには、必ず識別子を指定します。 次の例では C4006 が生成されます。  
  
```  
// C4006.cpp  
// compile with: /W1  
#undef   // C4006  
  
// try..  
// #undef TEST  
  
int main() {  
}  
```