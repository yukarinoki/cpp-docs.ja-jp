---
description: '詳細情報: do while ステートメント (C++)'
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
ms.openlocfilehash: fed7dc3300651dd35326c1eb28e3078538db1301
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195490"
---
# <a name="do-while-statement-c"></a>do-while ステートメント (C++)

指定された終了条件 (*式*) が0に評価されるまで、*ステートメント* を繰り返し実行します。

## <a name="syntax"></a>構文

```
do
   statement
while ( expression ) ;
```

## <a name="remarks"></a>解説

終了条件のテストは、ループの各実行後に行われます。したがって、 **do while** ループは、終了式の値に応じて1回以上実行されます。 **do-while** ステートメントは、[break](../cpp/break-statement-cpp.md)、[goto](../cpp/goto-statement-cpp.md)、または [return](../cpp/return-statement-cpp.md) ステートメントがステートメントの本体で実行されたときにも終了できます。

*expression* は演算型またはポインター型であることが必要です。 次のように実行されます。

1. ステートメントの本体が実行されます。

1. 次に、*expression* が評価されます。 *expression* が false の場合、**do-while** ステートメントは終了し、プログラムの次のステートメントに制御が渡されます。 *式* が true (0 以外) の場合、プロセスは手順 1 から繰り返されます。

## <a name="example"></a>例

次のサンプルは、 **do while** ステートメントを示しています。

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
