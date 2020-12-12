---
description: '詳細情報: コンパイラの警告 (レベル 1) C4618'
title: コンパイラの警告 (レベル 1) C4618
ms.date: 11/04/2016
f1_keywords:
- C4618
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
ms.openlocfilehash: 824a55dab68fe45a94cacb1924bed46b87b7c0eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208685"
---
# <a name="compiler-warning-level-1-c4618"></a>コンパイラの警告 (レベル 1) C4618

プラグマパラメーターに空の文字列が含まれています。プラグマは無視されました

**#Pragma** の引数として null 文字列が指定されました。

プラグマは引数なしで処理されました。

次の例では、C4618 が生成されます。

```cpp
// C4618.cpp
// compile with: /W1 /LD
#pragma code_seg("")   // C4618
```
