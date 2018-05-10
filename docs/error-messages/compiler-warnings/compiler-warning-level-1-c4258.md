---
title: コンパイラの警告 (レベル 1) C4258 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4258
dev_langs:
- C++
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08a182ed592119fd52247737988810f9ca66b45c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4258"></a>コンパイラの警告 (レベル 1) C4258
'variable': 定義から、ループが無視されます。外側のスコープから定義を使用すると"  
  
 [/Ze](../../build/reference/za-ze-disable-language-extensions.md)と[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)で定義された変数、[の](../../cpp/for-statement-cpp.md)ループが後にスコープ外に出る、**の**ループが終了します。 この警告を含むスコープの外側のループ内で定義された、ループ変数と同じ名前を持つ変数が再度使用される場合に発生、**の**ループします。 例えば:  
  
```  
// C4258.cpp  
// compile with: /Zc:forScope /W1  
int main()  
{  
   int i;  
   {  
      for (int i =0; i < 1; i++)  
         ;  
      i = 20;   // C4258 i (in for loop) has gone out of scope  
   }  
}  
```