---
title: 致命的なエラー C1094 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1094
dev_langs:
- C++
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15e722c6a74490a5fbb26e4e367f7f1b4cbcc932
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109250"
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