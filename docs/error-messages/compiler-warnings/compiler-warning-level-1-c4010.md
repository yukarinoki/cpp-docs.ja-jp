---
title: コンパイラの警告 (レベル 1) C4010 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06ab6307a34887fe2d8a8719e20c31da9728664b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4010"></a>コンパイラの警告 (レベル 1) C4010
単一行コメントには、行連結文字が含まれています。  
  
 導入された、単一行のコメント//、円記号が含まれています (\\) 行連結文字として機能します。 コンパイラでは、継続タスクを次の行を考慮し、コメントとして扱われます。  
  
 一部の構文向けエディターは、コメントとして連結文字の次の行を示していません。 構文の色分けでこの警告が発生した行を無視します。  
  
 次の例では、C4010 が生成されます。  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```