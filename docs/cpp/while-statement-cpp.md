---
description: '詳細情報: while ステートメント (C++)'
title: while ステートメント (C++)
ms.date: 11/04/2016
f1_keywords:
- while_cpp
helpviewer_keywords:
- while keyword [C++]
- while keyword [C++], syntax
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
ms.openlocfilehash: 3001760372410222651366416ac74d0cba59f23b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302830"
---
# <a name="while-statement-c"></a>while ステートメント (C++)

*Expression* が0に評価されるまで、*ステートメント* を繰り返し実行します。

## <a name="syntax"></a>構文

```
while ( expression )
   statement
```

## <a name="remarks"></a>解説

*式* のテストは、ループの各実行の前に行われます。したがって、 **`while`** ループは0回以上実行されます。 *式* は整数型、ポインター型、または整数型またはポインター型への明確な変換を持つクラス型である必要があります。

ループは、 **`while`** ステートメント本体内で [break](../cpp/break-statement-cpp.md)、 [goto](../cpp/goto-statement-cpp.md)、または [return](../cpp/return-statement-cpp.md) が実行されたときにも終了できます。 ループを終了せずに現在のイテレーションを終了するには、 [continue](../cpp/continue-statement-cpp.md) を使用し **`while`** ます。 **`continue`** ループの次の反復処理に制御を渡し **`while`** ます。

次のコードでは、ループを使用して **`while`** 文字列から末尾のアンダースコアを削除しています。

```cpp
// while_statement.cpp

#include <string.h>
#include <stdio.h>
char *trim( char *szSource )
{
    char *pszEOS = 0;

    //  Set pointer to character before terminating NULL
    pszEOS = szSource + strlen( szSource ) - 1;

    //  iterate backwards until non '_' is found
    while( (pszEOS >= szSource) && (*pszEOS == '_') )
        *pszEOS-- = '\0';

    return szSource;
}
int main()
{
    char szbuf[] = "12345_____";

    printf_s("\nBefore trim: %s", szbuf);
    printf_s("\nAfter trim: %s\n", trim(szbuf));
}
```

終了条件はループの先頭で評価されます。 末尾のアンダースコアがない場合、ループは実行されません。

## <a name="see-also"></a>関連項目

[繰り返しステートメント](../cpp/iteration-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)<br/>
[for ステートメント (C++)](../cpp/for-statement-cpp.md)<br/>
[範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)
