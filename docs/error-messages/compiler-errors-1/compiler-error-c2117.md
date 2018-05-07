---
title: コンパイラ エラー C2117 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2117
dev_langs:
- C++
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a51bebc1edf7398d91356adb16f35443820cef2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2117"></a>コンパイラ エラー C2117
'identifier': 配列の境界オーバーフロー  
  
 配列は、初期化子が多すぎますがあります。  
  
-   配列の要素と初期化子は、サイズと数は一致しません。  
  
-   文字列に null 終端文字用の領域がありません。  
  
 次の例では、C2117 が生成されます。  
  
```  
// C2117.cpp  
int main() {  
   char abc[4] = "abcd";   // C2117  
   char def[4] = "abd";   // OK  
}  
```