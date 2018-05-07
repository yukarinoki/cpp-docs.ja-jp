---
title: コンパイラ エラー C2267 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2267
dev_langs:
- C++
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc117bd692408773a2ef93ed319221b78646ba4b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2267"></a>コンパイラ エラー C2267
'function': ブロック スコープを持つ静的関数は無効  
  
 ローカルの関数が宣言されて`static`です。 静的関数には、グローバル スコープを設定する必要があります。  
  
 次の例では、C2267 が生成されます。  
  
```  
// C2267.cpp  
static int func2();   // OK  
int main() {  
    static int func1();   // C2267  
}  
```