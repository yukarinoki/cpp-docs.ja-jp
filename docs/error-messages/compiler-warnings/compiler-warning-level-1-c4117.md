---
title: コンパイラの警告 (レベル 1) C4117 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4117
dev_langs:
- C++
helpviewer_keywords:
- C4117
ms.assetid: c45aa281-4cc1-4dfd-bd32-bd7a60ddd577
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3087e7510e4a803d2a47de4a3c36eafdb86b8da8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4117"></a>コンパイラの警告 (レベル 1) C4117
マクロ名 'name' は予約されています。"Command" は無視されます  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  定義済みマクロを定義するか未定義にしようとしています。  
  
2.  プリプロセッサ演算子 **defined**を定義するか未定義にしようとしています。  
  
 次の例では C4117 が生成されます。  
  
```  
// C4117.cpp  
// compile with: /W1  
#define __FILE__ test         // C4117. __FILE__ is a predefined macro  
#define ValidMacroName test   // ok  
  
int main() {  
}  
```