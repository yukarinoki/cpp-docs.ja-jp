---
title: コンパイラの警告 (レベル 1) C4393 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4393
dev_langs:
- C++
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59a1022f54d22e97a11c0970cad6bcd8918c7190
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4393"></a>コンパイラの警告 (レベル 1) C4393
'var': const リテラル データ メンバーに影響を与えません無視されます。  
  
 A[リテラル](../../windows/literal-cpp-component-extensions.md)データ メンバーを定数としても指定されました。  リテラル データ メンバーには、const からわかるように、のでする必要はありませんを追加する宣言に定数。  
  
 次の例では、C4393 が生成されます。  
  
```  
// C4393.cpp  
// compile with: /clr /W1 /c  
ref struct Y1 {  
   literal const int staticConst = 10;   // C4393  
   literal int staticConst2 = 10;   // OK  
};  
```