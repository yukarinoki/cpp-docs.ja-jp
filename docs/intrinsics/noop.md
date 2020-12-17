---
description: 'Microsoft C/c + + 組み込みの詳細情報: __noop'
title: __noop
ms.date: 12/16/2020
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 5fd300ca8d68305a12e6b5540be05aa60a042a44
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645086"
---
# `__noop`

**Microsoft 固有** の組み込みは、 **`__noop`** 関数を無視する必要があることを指定します。 引数リストは解析されますが、引数のコードは生成されません。 コンパイラは、コンパイラの警告 C4100 と同様の分析のために、引数を参照されているものと見なします。 `__noop`組み込みは、可変個の引数を受け取るグローバルデバッグ関数で使用することを目的としています。

コンパイラは、 **`__noop`** コンパイル時に組み込みを0に変換します。

## <a name="example"></a>例

次のコードは、の使用方法を示して **`__noop`** います。

```cpp
// compiler_intrinsics__noop.cpp
// compile using: cl /EHsc /W4 compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

#define IGNORE(x) { __noop(x); }

int main(int argv, char ** argc)
{
   IGNORE(argv);
   IGNORE(argc);
   PRINT("\nDEBUG is defined\n");
}
```

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[キーワード](../cpp/keywords-cpp.md)
