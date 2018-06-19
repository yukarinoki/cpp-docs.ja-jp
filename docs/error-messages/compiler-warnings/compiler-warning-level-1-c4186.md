---
title: コンパイラの警告 (レベル 1) C4186 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4186
dev_langs:
- C++
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cc40d2b9f43d041c7b04ba2bc77a0aba0630274c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277593"
---
# <a name="compiler-warning-level-1-c4186"></a>コンパイラの警告 (レベル 1) C4186
\#インポート属性 'attribute' には、数の引数が必要です。無視されます。  
  
 `#import` 属性に指定されている引数の数が正しくありません。  
  
## <a name="example"></a>例  
  
```  
// C4186.cpp  
// compile with: /W1 /c  
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186  
```  
  
 `no_namespace` 属性は引数を受け取りません。 **rename** 属性は 2 つの引数のみを受け取ります。