---
title: コンパイラの警告 (レベル 1 およびレベル 4) C4949 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f806912188ada3a4f97f0b1500e811d1271f40fe
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077309"
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