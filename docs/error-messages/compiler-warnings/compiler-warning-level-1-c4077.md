---
title: コンパイラの警告 (レベル 1) C4077
ms.date: 11/04/2016
f1_keywords:
- C4077
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
ms.openlocfilehash: 90797463595cda07c5b37e1530964b23c656b027
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200281"
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
