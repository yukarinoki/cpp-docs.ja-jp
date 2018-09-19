---
title: while ステートメント (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- do_cpp
dev_langs:
- C++
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37155be11caaee9c609a0e11ddbfeb5d62856903
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071199"
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

終了条件のテストがループの各実行後に行われました。そのため、**は-中**ループは終了式の値に応じて、1 つまたは複数回実行されます。 **は-中に**ステートメントがときに終了することできますも、 [break](../cpp/break-statement-cpp.md)、 [goto](../cpp/goto-statement-cpp.md)、または[返す](../cpp/return-statement-cpp.md)ステートメントがステートメント本体で実行されます。

*expression* は演算型またはポインター型であることが必要です。 次のように実行されます。

1. ステートメントの本体が実行されます。

1. 次に、*expression* が評価されます。 場合*式*が false の場合、**は-中**ステートメントが終了し、プログラムの次のステートメントに制御が移ります。 *式*が true (0 以外) の場合、プロセスは手順 1 から繰り返されます。

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