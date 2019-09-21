---
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 24ba85b1fbbba4491c03d5a81afae345228db3bd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217185"
---
# <a name="__noop"></a>__noop

**Microsoft 固有の仕様**

組み込み`__noop`は、関数を無視する必要があることを指定します。 引数リストは解析されますが、引数のコードは生成されません。 これは、可変個の引数を受け取るグローバルデバッグ関数で使用することを目的としています。

コンパイラは、 `__noop`コンパイル時に組み込みを0に変換します。

## <a name="example"></a>例

次のコードは、の使用`__noop`方法を示しています。

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

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
