---
description: 詳細については、「コンパイラエラー C2092」を参照してください。
title: コンパイラエラー C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: 3f89d735d44b3cc0b2c28013ab957bf433159afb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251883"
---
# <a name="compiler-error-c2092"></a>コンパイラエラー C2092

' array name ' 配列要素型を関数にすることはできません

関数の配列は使用できません。 関数へのポインターの配列を使用します。

## <a name="examples"></a>例

次の例では、C2092 が生成されます。

```cpp
// C2092.cpp
typedef void (F) ();
typedef F AT[10];   // C2092
```

考えられる解決策:

```cpp
// C2092b.cpp
// compile with: /c
typedef void (F) ();
typedef F * AT[10];
```
