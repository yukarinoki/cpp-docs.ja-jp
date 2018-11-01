---
title: コンパイラ エラー C2707
ms.date: 11/04/2016
f1_keywords:
- C2707
helpviewer_keywords:
- C2707
ms.assetid: 3deaf45c-74da-4c9d-acc6-b82412720b74
ms.openlocfilehash: ce86f69b36b915b3e757b5d18430c99cb288e4e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648176"
---
# <a name="compiler-error-c2707"></a>コンパイラ エラー C2707

'identifier': 組み込み関数のコンテキストが正しくありません

構造化例外処理の組み込み関数は、特定のコンテキストで有効でないです。

- `_exception_code()` 例外フィルター外または`__except`ブロック

- `_exception_info()` 例外フィルター外

- `_abnormal_termination()` 外側、`__finally`ブロック

エラーを解決するには、例外処理の組み込み関数が、適切なコンテキスト内に配置されることを確認します。

## <a name="example"></a>例

次の例では、C2707 が生成されます。

```
// C2707.cpp
#include <windows.h>
#include <stdio.h>

LONG MyFilter(LONG excode)
{
    return (excode == EXCEPTION_ACCESS_VIOLATION ?
        EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);   // OK
}

LONG func(void)
{
    int x, y;
    return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ?  // C2707
             EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);

    __try
    {
        y = 0;
        x = 4 / y;
        return 0;
     }

    __except(MyFilter(GetExceptionCode()))
    {
        return(GetExceptionCode() == EXCEPTION_ACCESS_VIOLATION ? // ok
               EXCEPTION_EXECUTE_HANDLER : EXCEPTION_CONTINUE_SEARCH);
    }
}

int main()
{
    __try
    {
        func();
    } __except(EXCEPTION_EXECUTE_HANDLER)
    {
        printf_s("Caught exception\n");
    }
}
```