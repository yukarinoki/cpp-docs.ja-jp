---
title: コンパイラ エラー C3087 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3087
dev_langs:
- C++
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6e1446d8d062f97e9161e62fae5052580174c83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245310"
---
# <a name="compiler-error-c3087"></a>コンパイラ エラー C3087
'named_argument': 'attribute' の呼び出しは、既にこのメンバーを初期化しています  
  
 名前付き引数が、同じ値の名前なし引数と同じ属性ブロックに指定されました。 名前付引数か名前なし引数の、どちらか 1 つだけを指定します。  
  
## <a name="example"></a>例  
 次の例では C3087 が生成されます。  
  
```  
// C3087.cpp  
// compile with: /c  
[idl_quote("quote1", text="quote2")];   // C3087  
[idl_quote(text="quote3")];   // OK  
[idl_quote("quote4")];   // OK  
```