---
description: '詳細情報: コンパイラの警告 (レベル 1) C4077'
title: コンパイラの警告 (レベル 1) C4077
ms.date: 11/04/2016
f1_keywords:
- C4077
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
ms.openlocfilehash: 96e611db6d36dfa62d96561deb2f4c4d57638c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208711"
---
# <a name="compiler-warning-level-1-c4077"></a>コンパイラの警告 (レベル 1) C4077

check_stack プラグマに不明なオプションが与えられました。

以前の形式の **check_stack** プラグマが不明な引数と共に使用されています。 引数は `+`、 `-`、 `(on)`、 `(off)`、または空である必要があります。

コンパイラはプラグマを無視し、スタック チェックを変更しません。

## <a name="example"></a>例

```cpp
// C4077.cpp
// compile with: /W1 /LD
#pragma check_stack yes // C4077
#pragma check_stack +    // Correct old form
#pragma check_stack (on) // Correct new form
```
