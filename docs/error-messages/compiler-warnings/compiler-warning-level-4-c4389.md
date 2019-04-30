---
title: コンパイラの警告 (レベル 4) C4389
ms.date: 11/04/2016
f1_keywords:
- c4389
helpviewer_keywords:
- C4389
ms.assetid: fc0e3a8e-f766-437c-b7f1-e61abb2a8765
ms.openlocfilehash: 7490218c0af61ef3b2346fc1bee9806d87d02294
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391583"
---
# <a name="compiler-warning-level-4-c4389"></a>コンパイラの警告 (レベル 4) C4389

'operator': signed/unsigned が一致しません

操作には、符号付きと符号なしの変数が関係します。 これは、データが失われるなる可能性があります。

次の例では、C4389 が生成されます。

```
// C4389.cpp
// compile with: /W4
#pragma warning(default: 4389)

int main()
{
   int a = 9;
   unsigned int b = 10;
   if (a == b)   // C4389
      return 0;
   else
      return 0;
};
```