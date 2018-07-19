---
title: コンパイラ エラー C2007 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2007
dev_langs:
- C++
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 159a4b8f9dffc4f6ee96b0bb1935682f9f6db281
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163538"
---
# <a name="compiler-error-c2007"></a>コンパイラ エラー C2007
\#構文を定義します。  
  
 後に識別子が表示されない、`#define`です。 エラーを解決するには、識別子を使用します。  
  
 次の例では、C2007 が生成されます。  
  
```  
// C2007.cpp  
#define   // C2007  
```  
  
 考えられる解決方法:  
  
```  
// C2007b.cpp  
// compile with: /c  
#define true 1  
```