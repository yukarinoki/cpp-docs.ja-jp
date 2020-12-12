---
description: '詳細情報: コンパイラの警告 (レベル 4) C4937'
title: コンパイラの警告 (レベル 4) C4937
ms.date: 11/04/2016
f1_keywords:
- C4937
helpviewer_keywords:
- C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
ms.openlocfilehash: fa614e9f93cf83afbe3ff46e624f13b5199a28d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251246"
---
# <a name="compiler-warning-level-4-c4937"></a>コンパイラの警告 (レベル 4) C4937

'text1' と 'text2' を、'directive' への引数として区別できません

コンパイラがディレクティブへの引数を処理するしくみにより、複数のテキスト表現 (単一および二重のアンダースコア形式) を持つキーワードなど、コンパイラにとって意味を持つ名前は区別することができません。

このような文字列の例としては、__cdecl および \_ _forceinline があります。  /Za の下では、二重アンダースコア形式のみが有効であることに注意してください。

次の例では C4937 が生成されます。

```cpp
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
