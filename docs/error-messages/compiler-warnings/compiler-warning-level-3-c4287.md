---
title: コンパイラの警告 (レベル 3) C4287 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4287
dev_langs:
- C++
helpviewer_keywords:
- C4287
ms.assetid: 1bf3bff8-6402-4d06-95ba-431678a790a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6adea398c1e4f9383cbbf6f828562bf1ea63c9eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289797"
---
# <a name="compiler-warning-level-3-c4287"></a>コンパイラの警告 (レベル 3) C4287
'operator': 符号なし/負の定数が一致しません  
  
 符号なしの変数は、負の数値の操作で使用されました。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C4287 が生成されます。  
  
```  
// C4287.cpp  
// compile with: /W3  
#pragma warning(default : 4287)  
#include <stdio.h>  
  
int main()  
{  
    unsigned int u = 1;  
    if (u < -1)   // C4287  
        printf_s("u LT -1");  
    else  
        printf_s("u !LT -1");  
    return 0;  
}  
```