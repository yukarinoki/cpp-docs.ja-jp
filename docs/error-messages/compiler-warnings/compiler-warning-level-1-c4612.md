---
title: コンパイラの警告 (レベル 1) C4612 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0983f5d0bb89eaf1daee94468b318557bc83cd05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4612"></a>コンパイラの警告 (レベル 1) C4612
インクルード ファイル名にエラーがあります  
  
 この警告は、ファイル名が正しくないか、不足している場合に、 **#pragma include_alias** で発生します。  
  
 引数、 **#pragma include_alias**ステートメントから引用符を使用できます (**"***filename***"**) または山かっこ形式 ( **\< ***filename***>**)、両方とも同じ形式を使用する必要がありますが、します。  
  
## <a name="example"></a>例  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```