---
title: コンパイラの警告 (レベル 1) C4103 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4103
dev_langs:
- C++
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1942acc2d9c5c274806e06127f9f98d4bfcb5077
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085538"
---
# <a name="compiler-warning-level-1-c4103"></a>コンパイラの警告 (レベル 1) C4103

'filename': #pragma pack (pop) がないため配置がヘッダーを含めた後に変更されましたがあります。

パッキング、クラスのレイアウトに影響し、一般的には、ヘッダー ファイル間で変更をパッキングする場合は問題があります。

#Pragma[パック](../../preprocessor/pack.md)(pop) この警告を解決するのには、ヘッダー ファイルを終了する前にします。

次の例では、C4103 が生成されます。

```
// C4103.h
#pragma pack(push, 4)

// defintions and declarations

// uncomment the following line to resolve
// #pragma pack(pop)
```

この場合、次のようになります。

```
// C4103.cpp
// compile with: /LD /W1
#include "c4103.h"   // C4103
```