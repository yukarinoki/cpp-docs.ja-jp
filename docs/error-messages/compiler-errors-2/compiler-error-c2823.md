---
title: コンパイラ エラー C2823 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2823
dev_langs:
- C++
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ad7336834d38f7236b88debc28035d8f7d68e88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2823"></a>コンパイラ エラー C2823  
  
> typedef のテンプレートは無効です。  
  
テンプレートはでは許可されていない`typedef`定義します。  
  
## <a name="example"></a>例  
  
次の例では、C2823 を生成し、その修正方法を示しています。  
  
```cpp  
// C2823.cpp  
template<class T>  
typedef struct x {  
   T i;   // C2823 can't use T, specify data type and delete template  
   int i;   // OK  
} x1;  
```