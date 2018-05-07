---
title: コンパイラ エラー C2014 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2014
dev_langs:
- C++
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 839fececb10897c799473ae328afb9f422b4c390
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2014"></a>コンパイラ エラー C2014
最初の空白としてプリプロセッサ コマンドを起動する必要があります。  
  
 `#`プリプロセッサ ディレクティブの記号が空白ではない行の最初の文字にする必要があります。  
  
 次の例では、C2014 が生成されます。  
  
```  
// C2014.cpp  
int k; #include <stdio.h>   // C2014  
```  
  
 考えられる解決方法:  
  
```  
// C2014b.cpp  
// compile with: /c  
int k;   
#include <stdio.h>  
```