---
title: コンパイラの警告 (レベル 1) C4618
ms.date: 11/04/2016
f1_keywords:
- C4618
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
ms.openlocfilehash: b8f24df7465525b24ecd3871447bd873889b1e23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406393"
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