---
title: プログラム終了時の return ステートメント (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
ms.openlocfilehash: 9c7b6130ee1a0b49ab75a70d84764d3a1f8c5ef0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267614"
---
# <a name="return-statement-in-program-termination-c"></a>プログラム終了時の return ステートメント (C++)

発行、**返す**ステートメントから`main`呼び出しと同じ機能が、`exit`関数。 次に例を示します。

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

`exit`と**返す**前の例のステートメントは機能的に同じです。 ただし、C++ を持つ関数が以外の型を返す必要**void**値を返します。 **返す**ステートメントを使用するから値を返す`main`します。

## <a name="see-also"></a>関連項目

[プログラムの終了](../cpp/program-termination.md)