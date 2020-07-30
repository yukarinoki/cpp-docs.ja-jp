---
title: return ステートメント (C++)
ms.date: 11/04/2016
f1_keywords:
- return_cpp
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
ms.openlocfilehash: 6a1ed4f374f133abd0233826d1b58896d49576cf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225866"
---
# <a name="return-statement-c"></a>return ステートメント (C++)

関数の実行を終了し、呼び出し元の関数 (`main` 関数から制御を転送する場合はオペレーティング システム) に制御を返します。 呼び出し直後の位置から、呼び出し元の関数で実行が再開します。

## <a name="syntax"></a>構文

```
return [expression];
```

## <a name="remarks"></a>解説

`expression` 句は、存在する場合、初期化が実行されたときと同様に、関数宣言で指定された型に変換されます。 式の型から関数の型への変換で **`return`** は、一時オブジェクトを作成できます。 一時要素を作成する方法とタイミングの詳細については、「[一時オブジェクト](../cpp/temporary-objects.md)」を参照してください。

`expression` 句の値が呼び出し元の関数に返されます。 expression が省略されている場合、関数の戻り値は未定義です。 コンストラクターとデストラクター、および型の関数 **`void`** は、ステートメントで式を指定することはできません **`return`** 。 他のすべての型の関数は、ステートメントで式を指定する必要があり **`return`** ます。

制御のフローが関数定義を囲むブロックを終了すると、 **`return`** 式のないステートメントが実行された場合と同じ結果になります。 これは、値を返すように宣言された関数では無効です。

関数には、任意の数のステートメントを含めることができ **`return`** ます。

次の例では、ステートメントで式を使用して **`return`** 、2つの整数のうち最大の値を取得します。

## <a name="example"></a>例

```cpp
// return_statement2.cpp
#include <stdio.h>

int max ( int a, int b )
{
   return ( a > b ? a : b );
}

int main()
{
    int nOne = 5;
    int nTwo = 7;

    printf_s("\n%d is bigger\n", max( nOne, nTwo ));
}
```

## <a name="see-also"></a>関連項目

[ジャンプ ステートメント](../cpp/jump-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
