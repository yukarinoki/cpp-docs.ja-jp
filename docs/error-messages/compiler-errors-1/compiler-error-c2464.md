---
title: コンパイラ エラー C2464 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98949ba463f432666753cb39de37bb4bf8f7276f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2464"></a>コンパイラ エラー C2464
'identifier': 参照の割り当てに 'new' を使用することはできません  
  
 参照識別子がで割り当てられた、`new`演算子。 参照ではないメモリ オブジェクトのため`new`にポインターを返すことはできません。 参照を宣言するのにには、標準の変数宣言の構文を使用します。  
  
 次の例では、C2464 が生成されます。  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```