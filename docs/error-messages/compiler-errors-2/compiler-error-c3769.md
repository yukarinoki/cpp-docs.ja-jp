---
title: コンパイラ エラー C3769 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3769
dev_langs:
- C++
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5258c3dadd7ede384520b76e95c1b8e691882f8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266973"
---
# <a name="compiler-error-c3769"></a>コンパイラ エラー C3769
'type': 入れ子になったクラスは、すぐ外側のクラスと同じ名前を持つことはできません  
  
 入れ子になったクラスは、すぐ外側のクラスと同じ名前を持つことはできません。  
  
## <a name="example"></a>例  
 次の例では、C3769 を生成します。  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```