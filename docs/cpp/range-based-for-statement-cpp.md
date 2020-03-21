---
title: 範囲ベースの for ステートメント (C++)
ms.date: 11/04/2016
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
ms.openlocfilehash: af9811fd707d4dbc28158dba3b6b3fbfcc43e4fe
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077178"
---
# <a name="range-based-for-statement-c"></a>範囲ベースの for ステートメント (C++)

`statement` 内の各要素に対して `expression` を繰り返し順番に実行します。

## <a name="syntax"></a>構文

```
for ( for-range-declaration : expression )
   statement
```

## <a name="remarks"></a>解説

範囲ベース**の for**ステートメントを使用して、"範囲" を通じて実行する必要があるループを構築します。これは、反復処理できるものとして定義C++されます。たとえば、`std::vector`、または `begin()` と `end()`によって範囲が定義されているその他の標準ライブラリシーケンスです。 `for-range-declaration` 部分で宣言されている名前は for ステートメントに**対し**てローカルであり、`expression` または `statement`で再宣言することはできません。 [Auto](../cpp/auto-cpp.md)キーワードは、ステートメントの `for-range-declaration` 部分で優先されることに注意してください。

**Visual Studio 2017 の新方法:** 範囲ベースの for ループでは、begin () と end () が同じ型のオブジェクトを返す必要がなくなりました。 これにより、end() が、Ranges-V3 範囲で定義されている範囲で使用されるような sentinel オブジェクトを返すことができます。 詳細については、「[Generalizing the Range-Based For Loop](https://wg21.link/p0184r0)」 (範囲ベースの for loop の汎用化) と「[range-v3 library on GitHub](https://github.com/ericniebler/range-v3)」 (GitHub 上の range-v3 ライブラリ) を参照してください。

このコードは、範囲ベース**の for**ループを使用して、配列とベクターを反復処理する方法を示しています。

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

範囲**ベースの for ループは**、これらのいずれかの `statement` が実行されると終了します。つまり、 [break](../cpp/break-statement-cpp.md)、 [return](../cpp/return-statement-cpp.md)、または、範囲ベース**の for**ループの外側のラベル付きステートメントへの[移動](../cpp/goto-statement-cpp.md)です。 範囲ベース**の for**ループ内の[continue](../cpp/continue-statement-cpp.md)ステートメントは、現在のイテレーションのみを終了します。

範囲ベースのについては、次**の**点に注意してください。

- 自動的に配列を認識します。

- `.begin()` と `.end()` を持つコンテナーを認識します。

- それ以外については `begin()` および `end()` の引数依存の参照を使用します。

## <a name="see-also"></a>参照

[auto](../cpp/auto-cpp.md)<br/>
[繰り返しステートメント](../cpp/iteration-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[while ステートメント (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)<br/>
[for ステートメント (C++)](../cpp/for-statement-cpp.md)