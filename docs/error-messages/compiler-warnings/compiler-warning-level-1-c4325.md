---
title: コンパイラの警告 (レベル 1) C4325 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 936433987f823ae7d5d22cfd075f188dd5d4b1e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277645"
---
# <a name="compiler-warning-level-1-c4325"></a>コンパイラの警告 (レベル 1) C4325
**標準のセクションの属性 '**   
 ***セクション*' は無視されます**  
  
 標準のセクションの属性は変更できません。 例えば:  
  
```  
#pragma section(".sdata", long)  
```  
  
 これは、上書き、`.sdata`標準のセクションを使用して、**短い**データ型、**長い**データ型。  
  
 変更することがありますいない属性を含めるには、標準のセクション  
  
-   .data  
  
-   .sdata  
  
-   .bss  
  
-   .sbss  
  
-   .text  
  
-   .const  
  
-   .sconst  
  
-   .rdata  
  
-   .srdata  
  
 その他のセクションでは、後で追加可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [section](../../preprocessor/section.md)