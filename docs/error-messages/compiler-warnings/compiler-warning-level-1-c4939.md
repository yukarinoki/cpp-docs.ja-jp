---
title: コンパイラの警告 (レベル 1) C4939 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4939
dev_langs:
- C++
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e13cab2d5277cca0a1962b8ec254aaef10cfc98
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118766"
---
# <a name="compiler-warning-level-1-c4939"></a>コンパイラの警告 (レベル 1) C4939

\#プラグマ vtordisp は非推奨し、Visual C の将来のリリースで削除される予定

[vtordisp](../../preprocessor/vtordisp.md) プラグマは今後の Visual C++ バージョンからは削除されます

## <a name="example"></a>例

次の例では C4939 警告が生成されます。

```
// C4939.cpp
// compile with: /c /W1
#pragma vtordisp(off)   // C4939
```