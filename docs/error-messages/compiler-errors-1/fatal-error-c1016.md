---
title: 致命的なエラー C1016 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1016
dev_langs:
- C++
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8a07f1fc36293b483772087b3325c7e0d0529e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1016"></a>致命的なエラー C1016
\#ifdef 予想識別子 #ifndef には、識別子が必要です。  
  
 条件付きコンパイル ディレクティブ ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) または `#ifndef`) に、評価する識別子が指定されていません。 このエラーを解決するには、識別子を指定してください。  
  
 次の例では C1016 が生成されます。  
  
```  
// C1016.cpp  
#ifdef   // C1016  
#define FC1016  
#endif  
  
int main() {}  
```  
  
 考えられる解決方法:  
  
```  
// C1016b.cpp  
#ifdef X  
#define FC1016  
#endif  
  
int main() {}  
```