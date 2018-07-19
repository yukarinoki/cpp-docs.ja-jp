---
title: コンパイラ エラー C2008 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88dcbc88b50ee46b406d383ec36e1fed167eca05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165520"
---
# <a name="compiler-error-c2008"></a>コンパイラ エラー C2008
'character' : マクロ定義内で指定された文字の使い方が間違っています。  
  
 マクロ名の直後の文字が表示されます。 エラーを解決するには、必要がありますスペース マクロ名の後。  
  
 次の例では、C2008 が生成されます。  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 考えられる解決方法:  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```