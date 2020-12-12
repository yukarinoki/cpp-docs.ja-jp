---
description: 詳細については、「コンパイラエラー C2012」を参照してください。
title: コンパイラ エラー C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: 82f2a5660ec3920c9ff3db57c6ed0b70516c4531
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221008"
---
# <a name="compiler-error-c2012"></a>コンパイラ エラー C2012

' < ' の後に名前がありません

`#include` ディレクティブに必要なファイル名がありません。

次の例では C2012 エラーが生成されます。

```cpp
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

考えられる解決策:

```cpp
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```
