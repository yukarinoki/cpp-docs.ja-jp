---
title: コンパイラ エラー C2448 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2448
dev_langs:
- C++
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc62d7aeba0a128c9b736586e6c1502227de717
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2448"></a>コンパイラ エラー C2448
'identifier': 関数スタイルの初期化子は、関数の定義が表示されます  
  
 関数の定義が正しくありません。  
  
 このエラーは、旧式の C 言語仮引数リストによって発生することができます。  
  
 次の例では、C2448 が生成されます。  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```