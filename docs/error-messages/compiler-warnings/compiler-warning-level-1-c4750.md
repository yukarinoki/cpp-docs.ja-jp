---
title: コンパイラの警告 (レベル 1) C4750
description: スタックオーバーフローの可能性についての MSVC compiler warning C4750 について説明します。
ms.date: 07/08/2020
f1_keywords:
- C4750
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
ms.openlocfilehash: a02b69981d3cf1d35a6700261fc5142cfa8ec8e6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225359"
---
# <a name="compiler-warning-level-1-c4750"></a>コンパイラの警告 (レベル 1) C4750

> '*identifier*': ループにインライン展開される _alloca () の関数

## <a name="remarks"></a>解説

'*Identifier*' 関数は [`_alloca`](../../c-runtime-library/reference/alloca.md) ループ内で関数のインライン展開を強制します。ループが実行されると、スタックオーバーフローが発生する可能性があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. '*Identifier*' 関数が指定子を使用して変更されていないことを確認してください [`__forceinline`](../../cpp/inline-functions-cpp.md) 。

1. '*Identifier*' 関数に、 [`_alloca`](../../c-runtime-library/reference/alloca.md) ループに含まれている関数が含まれていないことを確認してください。

1. [`/O1`](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、、 [`/O2`](../../build/reference/o1-o2-minimize-size-maximize-speed.md) [`/Ox`](../../build/reference/ox-full-optimization.md) 、またはコンパイルスイッチを指定しないで [`/Og`](../../build/reference/og-global-optimizations.md) ください。

1. [`_alloca`](../../c-runtime-library/reference/alloca.md)スタックオーバーフローをキャッチする[try except ステートメント](../../cpp/try-except-statement.md)に関数を配置します。

## <a name="example"></a>例

次のコード例はループ内で `MyFunction` を呼び出し、 `MyFunction` は `_alloca` 関数を呼び出します。 **`__forceinline`** 修飾子により、関数のインライン展開が発生し `_alloca` ます。

```cpp
// c4750.cpp
// compile with: /O2 /W1 /c
#include <intrin.h>

char * volatile newstr;

__forceinline void myFunction(void) // C4750 warning
{
// The _alloca function does not require a __try/__except
// block because the example uses compiler option /c.
    newstr = (char * volatile) _alloca(1000);
}

int main(void)
{
    for (int i=0; i<50000; i++)
       myFunction();
    return 0;
}
```

## <a name="see-also"></a>関連項目

[_alloca](../../c-runtime-library/reference/alloca.md)
