---
title: コンパイラの警告 (レベル 4) C4408 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4408
dev_langs:
- C++
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 640a3de24921186bd441b8f8b9bc5f3dcd7e5810
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297581"
---
# <a name="compiler-warning-level-4-c4408"></a>コンパイラの警告 (レベル 4) C4408
anonymousstruct または共用体宣言がありません。 すべてのデータ メンバー  
  
 匿名構造体または匿名共用体には、少なくとも 1 つのデータ メンバーが必要です。  
  
 次の例では C4408 が生成されます。  
  
```  
// C4408.cpp  
// compile with: /W4 /LD  
static union  
{  
   // int i;  
};  
// a named union can have no data members  
// } MyUnion;  
```