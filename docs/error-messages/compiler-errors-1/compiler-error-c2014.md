---
description: 詳細については、「コンパイラエラー C2014」を参照してください。
title: コンパイラエラー C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 2f8de1d2b9ea8ef680826cfbfc189dbe2617c9f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220982"
---
# <a name="compiler-error-c2014"></a>コンパイラエラー C2014

プリプロセッサコマンドは最初のシャープ空白 space として起動する必要があります

`#`プリプロセッサディレクティブの符号は、空白ではない行の最初の文字である必要があります。

次の例では、C2014 が生成されます。

```cpp
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

考えられる解決策:

```cpp
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```
