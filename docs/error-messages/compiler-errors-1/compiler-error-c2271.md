---
title: コンパイラ エラー C2271 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2271
dev_langs:
- C++
helpviewer_keywords:
- C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f2f108d9f2f3ec6a1ba9f20a2937dee53297a4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170217"
---
# <a name="compiler-error-c2271"></a>コンパイラ エラー C2271
'operator': 新規/削除の仮引数リストの修飾子を設定することはできません  
  
 演算子 (`new`または`delete`) がメモリ モデル修飾子で宣言されています。  
  
 次の例では、C2271 が生成されます。  
  
```  
// C2271.cpp  
// compile with: /c  
void* operator new(size_t) const {   // C2271  
// try the following line instead  
// void* operator new(size_t) {  
   return 0;  
}  
  
struct X {  
   static void* operator new(size_t) const;   // C2271  
   // try the following line instead  
   // void * X::operator new(size_t) const;   // static member operator new  
};  
```