---
title: コンパイラ エラー C2010 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2010
dev_langs:
- C++
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c1f1a042881420c85670020e05ded3684a91268
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2010"></a>コンパイラ エラー C2010
'character': マクロの仮パラメーター リストに予期しません。  
  
 マクロ定義の仮パラメーター リストの中で、文字が正しくない方法で使用されています。 エラーを解決するのには、文字を削除します。  
  
 次の例では、C2010 が生成されます。  
  
```  
// C2010.cpp  
// compile with: /c  
#define mymacro(a|) (2*a)   // C2010  
#define mymacro(a) (2*a)   // OK  
```