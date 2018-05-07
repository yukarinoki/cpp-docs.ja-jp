---
title: コンパイラ エラー C2537 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2537
dev_langs:
- C++
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6100f77d3a1487bfa1eb12a78ac8187cec43fe64
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2537"></a>コンパイラ エラー C2537
'specifier': リンケージ仕様  
  
 以下の原因が考えられます。  
  
1.  リンケージ指定子はサポートされていません。 "C"リンケージ指定子のみがサポートされています。  
  
2.  "C"リンケージは、一連のオーバー ロードされた関数の 1 つ以上の関数を指定します。 これは認められていません。  
  
 次の例では、C2537 が生成されます。  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```