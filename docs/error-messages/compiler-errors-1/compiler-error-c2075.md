---
title: コンパイラ エラー C2075 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2075
dev_langs:
- C++
helpviewer_keywords:
- C2075
ms.assetid: 8b1865d2-540b-4117-b982-e7a58a0b6cf7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 689cce77da2193cf4864e46df050287d98b6e46e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165429"
---
# <a name="compiler-error-c2075"></a>コンパイラ エラー C2075
'identifier' : 配列の初期化には中かっこ ({}) が必要です  
  
 指定した配列初期化子の周囲に中かっこがありませんでした。  
  
 次の例では C2075 エラーが生成されます。  
  
```  
// C2075.c  
int main() {  
   int i[] = 1, 2, 3 };   // C2075  
}  
```  
  
 考えられる解決方法:  
  
```  
// C2075b.c  
int main() {  
   int j[] = { 1, 2, 3 };  
}  
```