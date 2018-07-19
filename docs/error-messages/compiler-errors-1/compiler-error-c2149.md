---
title: コンパイラ エラー C2149 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2149
dev_langs:
- C++
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e02d69aa89c77c72685ef0db3125dab2cbf1898b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167825"
---
# <a name="compiler-error-c2149"></a>コンパイラ エラー C2149
'identifier': 名前付きビットフィールドの幅が 0 です  
  
 名前を指定しない場合にのみ、ビット フィールドの幅を 0 にできます。  
  
 次の例では C2149 が生成されます。  
  
```  
// C2149.cpp  
// compile with: /c  
struct C {  
   int i : 0;   // C2149  
   int j : 2;   // OK  
};  
```