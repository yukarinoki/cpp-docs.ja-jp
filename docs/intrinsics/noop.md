---
description: '詳細については、次を参照してください: __noop'
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 4b140141e0f773f01cd666dd67f77244d7aef8a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222464"
---
# <a name="__noop"></a>__noop

**Microsoft 固有の仕様**

組み込みは、 **`__noop`** 関数を無視する必要があることを指定します。 引数リストは解析されますが、引数のコードは生成されません。 これは、可変個の引数を受け取るグローバルデバッグ関数で使用することを目的としています。

コンパイラは、 **`__noop`** コンパイル時に組み込みを0に変換します。

## <a name="example"></a>例

次のコードは、の使用方法を示して **`__noop`** います。

```cpp
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
