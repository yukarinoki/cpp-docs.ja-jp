---
title: コンパイラの警告 (レベル 1) C4618
ms.date: 11/04/2016
f1_keywords:
- C4618
helpviewer_keywords:
- C4618
ms.assetid: 6ff10d0a-6d5b-4373-8196-1d57bb6b1611
ms.openlocfilehash: 5e6c945932699119f97bca2d3d118a03665f6f9f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185881"
---
# <a name="compiler-warning-level-1-c4618"></a>コンパイラの警告 (レベル 1) C4618

プラグマパラメーターに空の文字列が含まれています。プラグマは無視されました

**#Pragma**の引数として null 文字列が指定されました。

プラグマは引数なしで処理されました。

次の例では、C4618 が生成されます。

```cpp
// C4618.cpp
// compile with: /W1 /LD
#pragma code_seg("")   // C4618
```
