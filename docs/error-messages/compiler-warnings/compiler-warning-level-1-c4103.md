---
title: コンパイラの警告 (レベル 1) C4103
ms.date: 11/04/2016
f1_keywords:
- C4103
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
ms.openlocfilehash: 15d7403d461467e33b7e89957821a311179d33a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577815"
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