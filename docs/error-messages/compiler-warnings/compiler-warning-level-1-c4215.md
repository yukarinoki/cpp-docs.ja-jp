---
title: コンパイラの警告 (レベル 1) C4215 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4215
dev_langs:
- C++
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d5e07b9382c24f82f3e7d84fe82aee9dd91ca19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277606"
---
# <a name="compiler-warning-level-1-c4215"></a>コンパイラの警告 (レベル 1) C4215
使用される標準の拡張機能: long float  
  
 既定の Microsoft 拡張機能 (/Ze) が扱う**long float**として**二重**です。 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) はありません。 使用して**二重**互換性を維持します。  
  
 次の例では、C4215 が生成されます。  
  
```  
// C4215.cpp  
// compile with: /W1 /LD  
long float a;   // C4215  
  
// use the line below to resolve the warning  
// double a;  
```