---
title: コンパイラの警告 (レベル 4) C4937 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4937
dev_langs:
- C++
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ed7b33889677a304d303873799f36430c38129a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294932"
---
# <a name="compiler-warning-level-4-c4937"></a>コンパイラの警告 (レベル 4) C4937
'text1' と 'text2' を、'directive' への引数として区別できません  
  
 コンパイラがディレクティブへの引数を処理するしくみにより、複数のテキスト表現 (単一および二重のアンダースコア形式) を持つキーワードなど、コンパイラにとって意味を持つ名前は区別することができません。  
  
 このような文字列の例としては、_ _cdecl と\__forceinline です。  /Za の下では、二重アンダースコア形式のみが有効であることに注意してください。  
  
 次の例では C4937 が生成されます。  
  
```  
// C4937.cpp  
// compile with: /openmp /W4  
#include "omp.h"  
int main() {  
   #pragma omp critical ( __leave )   // C4937  
   ;  
  
   // OK  
   #pragma omp critical ( leave )  
   ;  
}  
```