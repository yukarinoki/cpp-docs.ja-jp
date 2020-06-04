---
title: コンパイラの警告 (レベル 1) C4939
ms.date: 11/04/2016
f1_keywords:
- C4939
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
ms.openlocfilehash: 5c87dad744281464599ee6c28b5bcf6e350b9feb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199278"
---
# <a name="compiler-warning-level-1-c4939"></a>コンパイラの警告 (レベル 1) C4939

\#プラグマ vtordisp は非推奨とされており、今後の Visual リリースで削除される予定ですC++

[vtordisp](../../preprocessor/vtordisp.md) プラグマは今後の Visual C++ バージョンからは削除されます

## <a name="example"></a>例

次の例では C4939 警告が生成されます。

```cpp
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```
