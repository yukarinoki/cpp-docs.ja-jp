---
description: '詳細については、次を参照してください: Reference-Type 関数の引数'
title: Reference-Type Function Arguments (参照型関数の引数)
ms.date: 08/27/2018
helpviewer_keywords:
- arguments [C++], function
- functions [C++], parameters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
ms.openlocfilehash: 2e290160b1b897eadbf77f0c8a805f927a26c02f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260333"
---
# <a name="reference-type-function-arguments"></a>Reference-Type Function Arguments (参照型関数の引数)

多くの場合、大きなオブジェクトよりも、関数への参照を渡す方が効率的です。 これにより、コンパイラは、オブジェクトへのアクセスに使用される構文を保持しつつ、オブジェクトのアドレスを渡すことができます。 `Date` 構造体を使用する次の例について考えます。

```cpp
// reference_type_function_arguments.cpp
#include <iostream>

struct Date
{
    short Month;
    short Day;
    short Year;
};

// Create a date of the form DDDYYYY (day of year, year)
// from a Date.
long DateOfYear( Date& date )
{
    static int cDaysInMonth[] = {
        31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31
    };
    long dateOfYear = 0;

    // Add in days for months already elapsed.
    for ( int i = 0; i < date.Month - 1; ++i )
        dateOfYear += cDaysInMonth[i];

    // Add in days for this month.
    dateOfYear += date.Day;

    // Check for leap year.
    if ( date.Month > 2 &&
        (( date.Year % 100 != 0 || date.Year % 400 == 0 ) &&
        date.Year % 4 == 0 ))
        dateOfYear++;

    // Add in year.
    dateOfYear *= 10000;
    dateOfYear += date.Year;

    return dateOfYear;
}

int main()
{
    Date date{ 8, 27, 2018 };
    long dateOfYear = DateOfYear(date);
    std::cout << dateOfYear << std::endl;
}
```

前のコードでは、参照によって渡される構造体のメンバーに、ポインターメンバー選択演算子 () ではなく、メンバー選択演算子 (**.**) を使用してアクセスすることを示してい **->** ます。

参照型として渡される引数は非ポインター型の構文を観察しますが、ポインター型の1つの重要な特性を保持します。として宣言しない限り、変更 **`const`** できます。 前のコードの意図は `date` オブジェクトを変更することではないため、より適切な関数プロトタイプは次のとおりです。

```cpp
long DateOfYear( const Date& date );
```

このプロトタイプによって、関数 `DateOfYear` が引数を変更しないことが保証されます。

参照型を受け取るようにプロトタイプ宣言された関数は、 *typename* から *typename* への標準変換があるため、その代わりに同じ型のオブジェクトを受け取ることができ <strong>&</strong> ます。

## <a name="see-also"></a>関連項目

[参照](../cpp/references-cpp.md)<br/>
