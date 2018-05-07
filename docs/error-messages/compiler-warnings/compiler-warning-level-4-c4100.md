---
title: コンパイラの警告 (レベル 4) C4100 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4100
dev_langs:
- C++
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d3cf831590af2e1f2f7cd13d93c9d13ba217e11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4100"></a>コンパイラの警告 (レベル 4) C4100
'identifier' : 未参照仮パラメーター  
  
 仮パラメーターが関数の本体で参照されていません。 未参照のパラメーターは無視されます。  
  
 また、コードがプリミティブ型の他の未参照パラメーターでデストラクターを呼び出すと C4100 が出される可能性があります。  これは、Visual C++ コンパイラの制限事項です。  
  
 次の例では、C4100 が生成されます。  
  
```  
// C4100.cpp  
// compile with: /W4  
void func(int i) {   // C4100, delete the unreferenced parameter to  
                     //resolve the warning  
   // i;   // or, add a reference like this  
}  
  
int main()  
{  
   func(1);  
}  
```