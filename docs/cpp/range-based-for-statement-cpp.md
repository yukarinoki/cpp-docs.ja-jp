---
title: 範囲ベースの for ステートメント (C++)
ms.date: 11/04/2016
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
ms.openlocfilehash: 1197080e2e96e0e5c51bc06e93026567a33c7842
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223617"
---
# <a name="range-based-for-statement-c"></a>範囲ベースの for ステートメント (C++)

`statement` 内の各要素に対して `expression` を繰り返し順番に実行します。

## <a name="syntax"></a>構文

> **`for (`***範囲内の宣言* **`:`***式***`)`**\
&emsp;*ステートメント*

## <a name="remarks"></a>解説

範囲ベースのステートメントを使用して、範囲を **`for`** 通じて実行*range*する必要があるループを構築します。これは、、などの反復処理可能なものとして定義され `std::vector` ます。また、範囲がとで定義されているその他の C++ 標準ライブラリシーケンスとして定義され `begin()` `end()` ます。 部分で宣言されている名前 `for-range-declaration` は、ステートメントに対してローカルで **`for`** あり、またはで再宣言することはできません `expression` `statement` 。 キーワードは、 [`auto`](../cpp/auto-cpp.md) ステートメントの部分で優先されることに注意して `for-range-declaration` ください。

**Visual Studio 2017 の新方法:** 範囲ベース **`for`** のループでは、が `begin()` `end()` 同じ型のオブジェクトを返す必要がなくなりました。 これにより、は、 `end()` 範囲-V3 の提案で定義されている範囲によって使用されるなど、sentinel オブジェクトを返すことができます。 詳細については、「[範囲ベースの `For` ループの一般化](https://wg21.link/p0184r0)」と、 [GitHub の範囲-v3 ライブラリ](https://github.com/ericniebler/range-v3)を参照してください。

このコードは、範囲ベースの **`for`** ループを使用して配列とベクターを反復処理する方法を示しています。

```cpp
// range-based-for.cpp
// compile by using: cl /EHsc /nologo /W4
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    // Basic 10-element integer array.
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

    // Range-based for loop to iterate through the array.
    for( int y : x ) { // Access by value using a copy declared as a specific type.
                       // Not preferred.
        cout << y << " ";
    }
    cout << endl;

    // The auto keyword causes type inference to be used. Preferred.

    for( auto y : x ) { // Copy of 'x', almost always undesirable
        cout << y << " ";
    }
    cout << endl;

    for( auto &y : x ) { // Type inference by reference.
        // Observes and/or modifies in-place. Preferred when modify is needed.
        cout << y << " ";
    }
    cout << endl;

    for( const auto &y : x ) { // Type inference by const reference.
        // Observes in-place. Preferred when no modify is needed.
        cout << y << " ";
    }
    cout << endl;
    cout << "end of integer array test" << endl;
    cout << endl;

    // Create a vector object that contains 10 elements.
    vector<double> v;
    for (int i = 0; i < 10; ++i) {
        v.push_back(i + 0.14159);
    }

    // Range-based for loop to iterate through the vector, observing in-place.
    for( const auto &j : v ) {
        cout << j << " ";
    }
    cout << endl;
    cout << "end of vector test" << endl;
}
```

出力内容は次のとおりです。

```Output
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
1 2 3 4 5 6 7 8 9 10
end of integer array test

0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159
end of vector test
```

範囲ベース **`for`** のループは、の、、 `statement` [`break`](../cpp/break-statement-cpp.md) またはが、 [`return`](../cpp/return-statement-cpp.md) [`goto`](../cpp/goto-statement-cpp.md) 範囲ベースのループの外側のラベル付きステートメントに対して実行 **`for`** されると終了します。 [`continue`](../cpp/continue-statement-cpp.md)範囲ベースのループ内のステートメントは、 **`for`** 現在のイテレーションのみを終了します。

範囲ベースについては、次の点に注意してください **`for`** 。

- 自動的に配列を認識します。

- `.begin()` と `.end()` を持つコンテナーを認識します。

- それ以外については `begin()` および `end()` の引数依存の参照を使用します。

## <a name="see-also"></a>関連項目

[`auto`](../cpp/auto-cpp.md)<br/>
[繰り返しステートメント](../cpp/iteration-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[`while` ステートメント (C++)](../cpp/while-statement-cpp.md)<br/>
[`do-while` ステートメント (C++)](../cpp/do-while-statement-cpp.md)<br/>
[`for` ステートメント (C++)](../cpp/for-statement-cpp.md)
