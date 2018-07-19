---
title: コンパイラ エラー C2006 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2006
dev_langs:
- C++
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93880e7d767de3101cd7a292af5fa2874cae86bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165572"
---
# <a name="compiler-error-c2006"></a>コンパイラ エラー C2006
'directive' 'token' が見つかりません、ファイル名を想定します。  
  
 などのディレクティブ[#include](../../preprocessor/hash-include-directive-c-cpp.md)または[#import](../../preprocessor/hash-import-directive-cpp.md)ファイル名を必要とします。 エラーを解決するには、確認*トークン*は有効なファイル名。 また、ファイル名を二重引用符や山かっこで配置します。  
  
 次の例では、C2006 が生成されます。  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 考えられる解決方法:  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```