---
title: コンパイラ エラー C3140 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3140
dev_langs:
- C++
helpviewer_keywords:
- C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2c8c9e47020fe53e87b985b5db6192cd26098fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246905"
---
# <a name="compiler-error-c3140"></a>コンパイラ エラー C3140
同じコンパイル単位内の複数の 'module' 属性を持つことはできません。  
  
 [モジュール](../../windows/module-cpp.md)属性がプロジェクトごと 1 回定義するのみできます。  
  
 次の例では、c3140 エラーが生成されます。  
  
```  
// C3140.cpp  
// compile with: /c  
[emitidl];  
[module(name = "MyLibrary")];  
[module(name = "MyLibrary2")];   // C3140  
```