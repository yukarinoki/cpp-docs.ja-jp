---
title: do-while ステートメント (C++)
ms.date: 11/04/2016
f1_keywords:
- do_cpp
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
ms.openlocfilehash: 014012166f3a659d71b2e3212d63a523f2b87b8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656134"
---
# <a name="do-while-statement-c"></a>do-while ステートメント (C++)

実行、*ステートメント*指定された終了条件まで繰り返し (、*式*) 0 に評価します。

## <a name="syntax"></a>構文

```
do
   statement
while ( expression ) ;
```

## <a name="remarks"></a>Remarks

終了条件のテストがループの各実行後に行われました。そのため、**は-中**ループは終了式の値に応じて、1 つまたは複数回実行されます。 **do-while** ステートメントは、[break](../cpp/break-statement-cpp.md)、[goto](../cpp/goto-statement-cpp.md)、または [return](../cpp/return-statement-cpp.md) ステートメントがステートメントの本体で実行されたときにも終了できます。

*expression* は演算型またはポインター型であることが必要です。 次のように実行されます。

1. ステートメントの本体が実行されます。

1. 次に、*expression* が評価されます。 *expression* が false の場合、**do-while** ステートメントは終了し、プログラムの次のステートメントに制御が渡されます。 *式*が true (0 以外) の場合、プロセスは手順 1 から繰り返されます。

## <a name="example"></a>例

次のサンプルでは、**は-中**ステートメント。

```cpp
// do_while_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        printf_s("\n%d",i++);
    } while (i < 3);
}
```

## <a name="see-also"></a>関連項目

[繰り返しステートメント](../cpp/iteration-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[while ステートメント (C++)](../cpp/while-statement-cpp.md)<br/>
[for ステートメント (C++)](../cpp/for-statement-cpp.md)<br/>
[範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)