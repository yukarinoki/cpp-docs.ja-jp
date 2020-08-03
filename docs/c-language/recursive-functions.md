---
title: 再帰関数
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
ms.openlocfilehash: 8979d386c6fc3415cd50159250db8488cb917cee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87199517"
---
# <a name="recursive-functions"></a>再帰関数

C プログラムのどの関数も、再帰的に、つまり、その関数自体を呼び出すことができます。 再帰呼び出しの数は、スタックのサイズに制限されます。 スタック サイズを設定するリンカー オプションについては、「[`/STACK` (スタック割り当て)](../build/reference/stack-stack-allocations.md)」リンカー オプションを参照してください。 関数が呼び出されるたびに、以前の未完了の呼び出しの値が上書きされないように、新しいストレージがパラメーター、変数 **`auto`** および **`register`** 変数に割り当てられます。 パラメーターは、作成元の関数のインスタンスにのみ直接アクセスできます。 前のパラメーターは、関数のその後のインスタンスに直接アクセスできません。

**`static`** ストレージで宣言された変数は、再帰呼び出しごとに新しいストレージを必要としないことに注意してください。 このようなストレージは、プログラムの有効期間にわたって存続します。 このような変数への各参照は、同じストレージ領域にアクセスします。

## <a name="example"></a>例

この例は、再帰呼び出しを示しています。

```C
int factorial( int num );      /* Function prototype */

int main()
{
    int result, number;
    .
    .
    .
    result = factorial( number );
}

int factorial( int num )      /* Function definition */
{
    .
    .
    .
    if ( ( num > 0 ) || ( num <= 10 ) )
        return( num * factorial( num - 1 ) );
}
```

## <a name="see-also"></a>関連項目

[関数呼び出し](../c-language/function-calls.md)
