---
title: コンパイラ エラー C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: 85c3ad1d127dcabeeed0c5727ba6bbbca86f7898
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499659"
---
# <a name="compiler-error-c2012"></a>コンパイラ エラー C2012

'<' の後にファイル名がありません。

`#include` ディレクティブに必要なファイル名がありません。

次の例では C2012 エラーが生成されます。

```
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

考えられる解決方法:

```
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```