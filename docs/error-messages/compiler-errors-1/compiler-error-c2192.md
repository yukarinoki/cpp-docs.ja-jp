---
title: コンパイラ エラー C2192 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2192
dev_langs:
- C++
helpviewer_keywords:
- C2192
ms.assetid: a147197e-e72d-4620-939b-f9e08d7c7c12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a97b0885dd626c992ab55703038838aa743e30d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2192"></a>コンパイラ エラー C2192
パラメーター 'number' の宣言が異なる  
  
 C の関数は、異なるパラメーター リストで 2 番目の時間を宣言されました。 C では、オーバー ロードされた関数はサポートされません。  
  
 次の例では、C2192 が生成されます。  
  
```  
// C2192.c  
// compile with: /Za /c  
void func( float, int );  
void func( int, float );   // C2192, different parameter list  
void func2( int, float );   // OK  
```