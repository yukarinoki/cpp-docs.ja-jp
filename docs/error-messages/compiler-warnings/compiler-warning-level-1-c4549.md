---
title: コンパイラの警告 (レベル 1) C4549 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4549
dev_langs:
- C++
helpviewer_keywords:
- C4549
ms.assetid: 81a07676-625b-4f58-9b0c-3ee22830b04a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a31a2aec4753cf0cd800ca22ea1e997a5929bf3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284330"
---
# <a name="compiler-warning-level-1-c4549"></a>コンパイラの警告 (レベル 1) C4549
'operator': コンマも何も起こりません前の演算子。'operator' を意図しましたか。  
  
 正しい形式でコンマ式が検出されました。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
 次の例では、C4549 が生成されます。  
  
```  
// C4549.cpp  
// compile with: /W1  
#pragma warning (default : 4549)  
  
int main() {  
   int i = 0, k = 0;  
  
   if ( i == 0, k )   // C4549  
   // try the following line instead  
   // if ( i == 0 )  
      i++;  
}  
```