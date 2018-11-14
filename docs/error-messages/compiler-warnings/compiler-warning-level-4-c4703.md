---
title: コンパイラの警告 (レベル 4) C4703
ms.date: 11/04/2016
f1_keywords:
- C4703
helpviewer_keywords:
- C4703
ms.assetid: 5dad454e-69e3-4931-9168-050a861c05f8
ms.openlocfilehash: ab0e4ef0024446f51f7ee1e50480c1ab2b277652
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518036"
---
# <a name="compiler-warning-level-4-c4703"></a>コンパイラの警告 (レベル 4) C4703

可能性のあるローカル ポインター変数 'name' が使用される初期化されていません。

ローカル ポインター変数*名前*値を割り当てられることがなく使用される可能性があります。 これは、予期しない結果につながりますでした。

## <a name="example"></a>例

次のコードには、C4701 と C4703 が生成されます。

```cpp
#include <malloc.h>

void func(int size)
{
    void* p;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr) // C4701 and C4703
        free(p);
}

void main()
{
    func(9);
}
```

```Output
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used
```

この警告を解決するには、この例で示すように、変数を初期化します。

```cpp
#include <malloc.h>

void func(int size)
{
    void* p = nullptr;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr)
        free(p);
}

void main()
{
    func(9);
}
```

## <a name="see-also"></a>関連項目

[コンパイラの警告 (レベル 4) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)<br/>
[警告、/sdl、および初期化されていない変数の検出の向上](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)