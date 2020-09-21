---
title: コンパイラエラー C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: 8f2b83b4099308ea1d0bb127d8cea377ab65da96
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741892"
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
