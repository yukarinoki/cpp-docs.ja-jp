---
description: '詳細情報: 致命的なエラー C1094'
title: 致命的なエラー C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: af83c6fa80a6e1b115146ad05513539fea7d348c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145094"
---
# <a name="fatal-error-c1094"></a>致命的なエラー C1094

'-Zmval1 ': コマンドラインオプションは、プリコンパイル済みヘッダー ('-Zmval2 ') のビルドに使用される値と一致しません

[/Yc](../../build/reference/yc-create-precompiled-header-file.md)に渡される値は、 [/yu](../../build/reference/yu-use-precompiled-header-file.md)に渡される値と同じである必要があります (**/zm** 値は、を使用するか、同じプリコンパイル済みヘッダーファイルを作成するすべてのコンパイルで同じである必要があります)。

次の例では、C1094 が生成されます。

```
// C1094.h
int func1();
```

この場合、次のようになります。

```cpp
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

この場合、次のようになります。

```cpp
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```
