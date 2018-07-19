---
title: コンパイラの警告 (レベル 1) C4218 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4218
dev_langs:
- C++
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88b27af84c390760274bb20665eec4452c8e7072
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279751"
---
# <a name="compiler-warning-level-1-c4218"></a>コンパイラの警告 (レベル 1) C4218
使用される標準の拡張機能: ストレージ クラスまたは型を指定する必要があります  
  
 既定 Microsoft 拡張機能 (/Ze)、型やストレージ クラスを指定することがなく変数を宣言することができます。 既定の型は `int` です。  
  
## <a name="example"></a>例  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 このような宣言があります。 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。