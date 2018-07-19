---
title: コンパイラの警告 (レベル 1) C4129 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc095a32e5cb0d5a0bf240282e11c3fa3382ffe5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276644"
---
# <a name="compiler-warning-level-1-c4129"></a>コンパイラの警告 (レベル 1) C4129
'character': 認識できない文字エスケープ シーケンス  
  
 `character`次の円記号 (\\) の文字または文字列定数は認識されません、有効なエスケープ シーケンスとして。 バック スラッシュは無視され、印刷されません。 バック スラッシュの後ろの文字が出力されます。  
  
 1 つの円記号を印刷するには、二重の円記号を指定 (\\\\)。  
  
 C++ 標準で 2.13.2 セクションでは、エスケープ シーケンスをについて説明します。  
  
 次の例では、C4129 が生成されます。  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```