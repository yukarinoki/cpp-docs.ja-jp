---
title: コンパイラの警告 (レベル 4) C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: 61a6d3090355c9bda8aa11c041b302e4ec77ec8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557285"
---
# <a name="compiler-warning-level-4-c4400"></a>コンパイラの警告 (レベル 4) C4400

'type': この型での const/volatile 修飾子はサポートされていません

[Const](../../cpp/const-cpp.md)と[揮発性](../../cpp/volatile-cpp.md)修飾子は、共通言語ランタイム型の変数では動作しません。

## <a name="example"></a>例

次の例では、C4400 が生成されます。

```
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```