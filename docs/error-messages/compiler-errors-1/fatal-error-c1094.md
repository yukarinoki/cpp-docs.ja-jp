---
title: 致命的なエラー C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: 23891a783a018f6d84ea820af98992f61632984c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469655"
---
# <a name="fatal-error-c1094"></a>致命的なエラー C1094

'-Zmval1': コマンド ライン オプションはプリコンパイル済みヘッダーを構築するために使用する値と一致しません ('-Zmval2')

渡される値[/Yc](../../build/reference/yc-create-precompiled-header-file.md)に渡される値と同じである必要があります[/Yu](../../build/reference/yu-use-precompiled-header-file.md) (**/Zm**値は同じプリコンパイル済みの作成またはを使用するすべてのコンパイルで同じである必要がありますヘッダー ファイルの場合)。

次の例では、C1094 が生成されます。

```
// C1094.h
int func1();
```

この場合、次のようになります。

```
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

この場合、次のようになります。

```
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```