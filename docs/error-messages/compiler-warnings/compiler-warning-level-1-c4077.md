---
title: コンパイラの警告 (レベル 1) C4077
ms.date: 11/04/2016
f1_keywords:
- C4077
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
ms.openlocfilehash: 5171ee79c3afd32e847483568fbbf90222747509
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208351"
---
# <a name="compiler-warning-level-1-c4077"></a>コンパイラの警告 (レベル 1) C4077

check_stack プラグマに不明なオプションが与えられました。

以前の形式の **check_stack** プラグマが不明な引数と共に使用されています。 引数は `+`、 `-`、 `(on)`、 `(off)`、または空である必要があります。

コンパイラはプラグマを無視し、スタック チェックを変更しません。

## <a name="example"></a>例

```
// C4077.cpp
// compile with: /W1 /LD
#pragma check_stack yes // C4077
#pragma check_stack +    // Correct old form
#pragma check_stack (on) // Correct new form
```