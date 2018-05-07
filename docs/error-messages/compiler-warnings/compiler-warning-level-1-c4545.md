---
title: コンパイラの警告 (レベル 1) C4545 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4545
dev_langs:
- C++
helpviewer_keywords:
- C4545
ms.assetid: 43f8f34f-ed46-4661-95c0-c588c577ff73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5f34dbdb420fffefdd07f79ae651002cfe67598
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4545"></a>コンパイラの警告 (レベル 1) C4545
コンマ前の式は、引数リストのない関数として評価します。  
  
 正しい形式でコンマ式が検出されました。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
 次の例では、C4545 を生成します。  
  
```  
// C4545.cpp  
// compile with: /W1  
#pragma warning (default : 4545)  
  
void f() { }  
  
int main()  
{  
   *(&f), 10;   // C4545  
   // try the following line instead  
   // (*(&f))(), 10;  
}  
```