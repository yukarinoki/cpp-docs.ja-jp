---
title: コンパイラ エラー C2286 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2286
dev_langs:
- C++
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ddfb523252572fb985b660f1d4dbf5b1d790df1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171927"
---
# <a name="compiler-error-c2286"></a>コンパイラ エラー C2286
'identifier' の形式のメンバーへのポインターは、既に '継承の' 宣言は無視に設定します。  
  
 クラスには、次の 2 つの異なるメンバーへのポインター表現が存在します。  
  
 詳細については、次を参照してください。[継承キーワード](../../cpp/inheritance-keywords.md)です。  
  
## <a name="example"></a>例  
 次の例では C2286 が生成されます。  
  
```  
// C2286.cpp  
// compile with: /c  
class __single_inheritance X;  
class __multiple_inheritance X;   // C2286  
class  __multiple_inheritance Y;   // OK  
```