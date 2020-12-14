---
description: 詳細については、「コンパイラエラー C2013」を参照してください。
title: コンパイラ エラー C2013
ms.date: 11/04/2016
f1_keywords:
- C2013
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
ms.openlocfilehash: 2f883c24be5e02c58553ca6f7abe4f588ae8a2da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220969"
---
# <a name="compiler-error-c2013"></a>コンパイラ エラー C2013

'>' がありません。

`#include` ディレクティブに終わりの山かっこがありません。 エラーを解決するには、終わりの山かっこを追加します。

次の例では C2013 が生成されます。

```cpp
// C2013.cpp
#include <stdio.h    // C2013
```

考えられる解決策:

```cpp
// C2013b.cpp
// compile with: /c
#include <stdio.h>
```
