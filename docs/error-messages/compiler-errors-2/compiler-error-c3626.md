---
title: コンパイラ エラー C3626 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3626
dev_langs:
- C++
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ede2ec42b3afc581126d2591cba072817dcc8748
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266169"
---
# <a name="compiler-error-c3626"></a>コンパイラ エラー C3626
'keyword': '_ _event' キーワードは、COM インターフェイス、メンバー関数およびデリゲートへのポインターであるデータ メンバーでのみ使用できます  
  
 キーワードが正しく使用されていません。  
  
 次の例では、C3626 が生成されます。  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```