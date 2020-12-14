---
description: '詳細情報: goto ステートメント (C++)'
title: goto ステートメント (C++)
ms.date: 11/04/2016
f1_keywords:
- goto_cpp
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
ms.openlocfilehash: c8f94a5c2dfbd6ff3bd33223944180a4d1642b0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221385"
---
# <a name="goto-statement-c"></a>goto ステートメント (C++)

ステートメントは、 **`goto`** 指定された識別子によってラベル付けされたステートメントに、無条件で制御を転送します。

## <a name="syntax"></a>構文

```
goto identifier;
```

## <a name="remarks"></a>解説

`identifier` で指定されたラベル付きステートメントは、現在の関数内にある必要があります。 すべての `identifier` 名は内部の名前空間のメンバーであるため、他の識別子と干渉することはありません。

ステートメントラベルは、ステートメントに対してのみ意味があります。 **`goto`** それ以外の場合、ステートメントラベルは無視されます。 ラベルは再宣言できません。

**`goto`** ステートメントでは、その場所のスコープ内にある変数の初期化をスキップする場所への制御の転送は許可されていません。 次の例では、C2362 が発生します。

```cpp
int goto_fn(bool b)
{
    if (!b)
    {
        goto exit;  // C2362
    }
    else
    { /*...*/ }

    int error_code = 42;

exit:
    return error_code;
}
```

可能な限り **`break`** 、 **`continue`** **`return`** ステートメントの代わりに、、およびの各ステートメントを使用するのに適したプログラミングスタイルです **`goto`** 。 ただし、ステートメントは **`break`** ループの1つのレベルのみから終了するので、ステートメントを使用して **`goto`** 深い入れ子になったループを終了する必要がある場合があります。

ラベルとステートメントの詳細については **`goto`** 、「 [ラベル付きステートメント](../cpp/labeled-statements.md)」を参照してください。

## <a name="example"></a>例

この例では、 **`goto`** ステートメントによって、が3に等しい場合にラベルが付けられたポイントに制御が移り `stop` `i` ます。

```cpp
// goto_statement.cpp
#include <stdio.h>
int main()
{
    int i, j;

    for ( i = 0; i < 10; i++ )
    {
        printf_s( "Outer loop executing. i = %d\n", i );
        for ( j = 0; j < 2; j++ )
        {
            printf_s( " Inner loop executing. j = %d\n", j );
            if ( i == 3 )
                goto stop;
        }
    }

    // This message does not print:
    printf_s( "Loop exited. i = %d\n", i );

    stop:
    printf_s( "Jumped to stop. i = %d\n", i );
}
```

```Output
Outer loop executing. i = 0
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 1
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 2
Inner loop executing. j = 0
Inner loop executing. j = 1
Outer loop executing. i = 3
Inner loop executing. j = 0
Jumped to stop. i = 3
```

## <a name="see-also"></a>関連項目

[ジャンプ ステートメント](../cpp/jump-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
