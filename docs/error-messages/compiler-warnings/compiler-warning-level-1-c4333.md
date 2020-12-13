---
description: '詳細情報: コンパイラの警告 (レベル 1) C4333'
title: コンパイラの警告 (レベル 1) C4333
ms.date: 11/04/2016
f1_keywords:
- C4333
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
ms.openlocfilehash: 7a9384ad9dad8b17e6541256c71d28066d557df5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340036"
---
# <a name="compiler-warning-level-1-c4333"></a>コンパイラの警告 (レベル 1) C4333

' operator ': 右シフトが大きすぎるため、データが失われる

右シフト演算が大きすぎて、容量が大きすぎます。  すべての重要なビットがシフトされ、結果は常に0になります。

## <a name="example"></a>例

次の例では、C4333 が生成されます。

```cpp
// C4333.cpp
// compile with: /c /W1
unsigned shift8 (unsigned char c) {
   return c >> 8;   // C4333

   // try the following line instead
   // return c >> 4;   // OK
}
```
