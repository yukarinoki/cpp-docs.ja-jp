---
description: 詳細については、「コンパイラエラー C2006」を参照してください。
title: コンパイラエラー C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: 5747f5417db60bd3c1f7bc1420c257552a9b42c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298514"
---
# <a name="compiler-error-c2006"></a>コンパイラエラー C2006

' ディレクティブ ' にはファイル名が必要ですが、' token ' が見つかりました。

[#Include](../../preprocessor/hash-include-directive-c-cpp.md)や[#import](../../preprocessor/hash-import-directive-cpp.md)などのディレクティブにはファイル名が必要です。 このエラーを解決するには、 *トークン* が有効なファイル名であることを確認します。 また、ファイル名を二重引用符または山かっこで囲みます。

次の例では、C2006 が生成されます。

```cpp
// C2006.cpp
#include stdio.h   // C2006
```

考えられる解決策:

```cpp
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```
