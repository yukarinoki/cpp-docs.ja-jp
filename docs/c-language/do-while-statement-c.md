---
description: '詳細情報: do-while ステートメント (C)'
title: do-while ステートメント (C)
ms.date: 11/04/2016
f1_keywords:
- do
helpviewer_keywords:
- do-while keyword [C]
ms.assetid: f2ac20a6-10c7-4a08-b5e3-c3b3639dbeaf
ms.openlocfilehash: 9d80bb2aea047d0dc9cc2b7be417a7a44ced9050
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246995"
---
# <a name="do-while-statement-c"></a>do-while ステートメント (C)

*do-while* ステートメントを使用すると、指定した式が false になるまでステートメントまたは複合ステートメントを繰り返すことができます。

## <a name="syntax"></a>構文

*iteration-statement*: &nbsp;&nbsp;&nbsp;&nbsp; **`do`**  *statement*  **while (**  *expression*  **) ;**

*do-while* ステートメント内の *expression* は、ループの本体が実行された後で評価されます。 したがって、ループの本体は、常に少なくとも 1 回は実行されます。

*expression* は演算型またはポインター型であることが必要です。 次のように実行されます。

1. ステートメントの本体が実行されます。

1. 次に、*expression* が評価されます。 *expression* が false の場合、*do-while* ステートメントは終了し、プログラムの次のステートメントに制御が渡されます。 *式* が true (0 以外) の場合、プロセスは手順 1 から繰り返されます。

*do-while* ステートメントは、 **`break`** 、 **`goto`** 、または **`return`** ステートメントがステートメント本体で実行されたときにも終了できます。

*do-while* ステートメントの例を次に示します。

```C
do
{
    y = f( x );
    x--;
} while ( x > 0 );
```

この *do-while* ステートメントでは、`x` の初期値に関係なく、2 つのステートメント `y = f( x );` および `x--;` が実行されます。 次に、`x > 0` が評価されます。 `x` が 0 より大きい場合、ステートメント本体が再度実行され、`x > 0` が再評価されます。 `x` が 0 より大きい間、ステートメント本体が繰り返し実行されます。 *do-while* ステートメントの実行は、`x` が 0 または負になると終了します。 ループの本体は、少なくとも 1 回は実行されます。

## <a name="see-also"></a>関連項目

[do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)
