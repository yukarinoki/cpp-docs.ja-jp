---
title: コンパイラの警告 (レベル 1 およびレベル 4) C4949 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3dbf80f85db7334d4bcb46402851cac601d258f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279647"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>コンパイラの警告 (レベル 1 およびレベル 4) C4949
マネージおよびアンマネージのプラグマはコンパイルしたときにのみ意味のある '/clr [: オプション]'  
  
 コンパイラは無視、[マネージ](../../preprocessor/managed-unmanaged.md)と、ソース コードがコンパイルされていない場合は、プラグマをアンマネージ[/clr](../../build/reference/clr-common-language-runtime-compilation.md)です。 これは、情報提供の警告です。  
  
 次の例では、C4949 が生成されます。  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 ときに **#pragma をアンマネージ**なしで使われた **/clr**C4949 はレベル 4 の警告です。  
  
 次の例では、C4949 が生成されます。  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```