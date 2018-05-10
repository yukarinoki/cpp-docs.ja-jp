---
title: コンパイラの警告 (レベル 1) C4530 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4530
dev_langs:
- C++
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74804aa3ea0450c08710a5d0818eae67ce9b556e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4530"></a>コンパイラの警告 (レベル 1) C4530
C++ 例外処理を使っていますが、アンワインド セマンティクスが有効になっていません。 /EHsc を指定してください。  
  
 C++ 例外処理が使用されましたが、 [/EHsc](../../build/reference/eh-exception-handling-model.md)が選択されていません。  
  
 /EHsc オプションが有効になっていない場合、関数のスローを行うと、スローをキャッチ関数の間、フレームに自動ストレージを持つオブジェクトは破棄されません。 ただしで自動ストレージを持つオブジェクトを作成、**再試行**または**キャッチ**ブロックは破棄されます。  
  
 次の例では、C4530 が生成されます。  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 警告を解決する/EHsc でサンプルをコンパイルします。