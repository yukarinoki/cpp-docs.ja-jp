---
title: コンパイラの警告 (レベル 4) C4629 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4629
dev_langs:
- C++
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d77f0d5343952919577845bb5c20ef4f8cb14cca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4629"></a>コンパイラの警告 (レベル 4) C4629
digraph が使用されました。文字のシーケンス 'digraph' はトークン 'char' として解釈されます。(これが意図でない場合は、2 文字の間にスペースを挿入してください)  
  
 コンパイラで [/Za](../../build/reference/za-ze-disable-language-extensions.md)を使用すると、digraph の検出時に警告が表示されます。  
  
 次の例では C4629 が生成されます。  
  
```  
// C4629.cpp  
// compile with: /Za /W4  
int main()  
<%   // C4629 <% digraph for {  
}  
```