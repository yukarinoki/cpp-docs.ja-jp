---
title: コンパイラ エラー C2563 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85a4de195c681ce8d11b789a9aca102629cc2bac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2563"></a>コンパイラ エラー C2563
正式なパラメーター リストが一致しません  
  
 関数 (または関数へのポインター) の仮パラメーター リストには、別の関数 (またはメンバー関数へのポインター) のものと一致しません。 その結果、または関数ポインターの代入を行うことはできません。  
  
 次の例では、C2563 が生成されます。  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```