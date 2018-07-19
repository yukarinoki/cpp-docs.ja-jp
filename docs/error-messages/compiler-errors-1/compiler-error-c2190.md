---
title: コンパイラ エラー C2190 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2190
dev_langs:
- C++
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8a40aa3ae2169233874ae806d65a63d1644283e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169869"
---
# <a name="compiler-error-c2190"></a>コンパイラ エラー C2190
2 番目を超える最初のパラメーター リスト  
  
 C の関数は、パラメーター一覧を短くしてもう一度で宣言されました。 C では、オーバー ロードされた関数はサポートされません。  
  
 次の例では、C2190 が生成されます。  
  
```  
// C2190.c  
// compile with: /Za /c  
void func( int, float );  
void func( int  );   // C2190, different parameter list  
void func2( int  );   // OK  
```