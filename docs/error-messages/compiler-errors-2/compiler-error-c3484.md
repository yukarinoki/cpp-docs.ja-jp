---
title: コンパイラ エラー C3484 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3484
dev_langs:
- C++
helpviewer_keywords:
- C3484
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5de302987e4ea56e9ee6f29bed1b5842579a8f5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3484"></a>コンパイラ エラー C3484
戻り値の型の前に '->' が必要です  
  
 ラムダ式の戻り値の型の前に `->` を指定する必要があります。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
-   戻り値の型の前に `->` を指定します。  
  
## <a name="example"></a>例  
 次の例では C3484 が生成されます。  
  
```  
// C3484a.cpp  
  
int main()  
{  
   return []() . int { return 42; }(); // C3484  
}  
```  
  
## <a name="example"></a>例  
 次の例では、ラムダ式の戻り値の型の前に `->` を指定して C3484 を解決します。  
  
```  
// C3484b.cpp  
  
int main()  
{  
   return []() -> int { return 42; }();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)