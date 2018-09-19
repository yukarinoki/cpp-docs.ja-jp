---
title: コンパイラの警告 (レベル 1) C4750 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c77c46daf30b6e0238345d9b2be3c6c5362c192
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026622"
---
# <a name="compiler-warning-level-1-c4750"></a>コンパイラの警告 (レベル 1) C4750

'identifier': ループにインライン展開されている _alloca() を含む関数です

'identifier' 関数はループ内に [_alloca](../../c-runtime-library/reference/alloca.md) 関数のインライン展開を強制するため、ループが実行されるときにスタック オーバーフローの可能性があります。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 'identifier' 関数が [__forceinline](../../cpp/inline-functions-cpp.md) 指定子で変更されないことを確認します。

1. 'identifier' 関数が、ループに含まれている [_alloca](../../c-runtime-library/reference/alloca.md) 関数を含まないことを確認します。

1. [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、 [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、 [/Ox](../../build/reference/ox-full-optimization.md)、または [/Og](../../build/reference/og-global-optimizations.md) コンパイル スイッチを指定しないでください。

1. [_alloca](../../c-runtime-library/reference/alloca.md) 関数を、スタック オーバーフローをキャッチする [try-except ステートメント](../../cpp/try-except-statement.md) 内に配置します。

## <a name="example"></a>例

次のコード例はループ内で `MyFunction` を呼び出し、 `MyFunction` は `_alloca` 関数を呼び出します。 `__forceinline` 修飾子により、 `_alloca` 関数のインライン展開が発生します。

```
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