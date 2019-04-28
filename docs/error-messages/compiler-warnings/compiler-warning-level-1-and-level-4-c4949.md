---
title: コンパイラの警告 (レベル 1 およびレベル 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 8050edbd7a653776d046bc7b4155fd43094d9a5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187523"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>コンパイラの警告 (レベル 1 およびレベル 4) C4949

マネージドおよびアンマネージドのプラグマはコンパイルした場合にのみ意味のある '/clr [: オプション]'

コンパイラは無視、[マネージ](../../preprocessor/managed-unmanaged.md)でソース コードがコンパイルされていない場合は、プラグマを管理対象外と[/clr](../../build/reference/clr-common-language-runtime-compilation.md)します。 これは、情報提供の警告です。

次の例では、C4949 が生成されます。

```
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

ときに**アンマネージド #pragma**なし **/clr**C4949 はレベル 4 の警告。

次の例では、C4949 が生成されます。

```
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```