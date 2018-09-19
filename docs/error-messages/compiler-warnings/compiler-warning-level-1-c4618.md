---
title: コンパイラの警告 (レベル 1) C4618 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4618
dev_langs:
- C++
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ff6080d6315156a1dbaeb89fae1d5cb10865405
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074267"
---
# <a name="compiler-warning-level-1-c4618"></a>コンパイラの警告 (レベル 1) C4618

プラグマのパラメーターに空の文字列。プラグマを無視

引数として null 文字列が指定された、 **#pragma**します。

プラグマは、引数なしに処理されました。

次の例では、C4618 が生成されます。

```
// C4618.cpp
// compile with: /W1 /LD
#pragma code_seg("")   // C4618
```