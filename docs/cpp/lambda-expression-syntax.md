---
description: '詳細情報: ラムダ式の構文'
title: ラムダ式の構文
ms.date: 05/07/2019
helpviewer_keywords:
- lambda expressions [C++], syntax
ms.assetid: 5d6154a4-f34d-4a15-970d-7e7de45f54e9
ms.openlocfilehash: 522f9afd1b4d500e42bd5a5ff2adb4ae25cb7c19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333943"
---
# <a name="lambda-expression-syntax"></a>ラムダ式の構文

この記事では、ラムダ式の構文と構造体要素を説明します。 ラムダ式の詳細については、「 [ラムダ式](../cpp/lambda-expressions-in-cpp.md)」を参照してください。

## <a name="function-objects-vs-lambdas"></a>関数オブジェクトとラムダ

コードを記述する場合、特に [C++ 標準ライブラリアルゴリズム](../standard-library/algorithms.md)を使用する場合は、関数ポインターと関数オブジェクトを使用して問題を解決し、計算を実行します。 関数ポインターと関数オブジェクトには、それぞれに利点と欠点があります。たとえば、関数ポインターは、最小限の構文オーバーヘッドで済みますが、スコープ内の状態を保持しません。関数オブジェクトは、状態を保持できますが、クラス定義の構文オーバーヘッドが必要となります。

ラムダは、関数ポインターと関数オブジェクトの両方の利点を持ち、それらの欠点を回避できます。 ラムダは、関数オブジェクトのように柔軟性があり状態を保持できますが、関数オブジェクトとは異なり、その簡潔な構文には明示的なクラス定義は必要ありません。 ラムダを使用すると、同等の関数オブジェクトのコードよりも使いやすくエラーが発生しにくいコードを作成できます。

次の例では、ラムダの使用と関数オブジェクトの使用を比較しています。 最初の例では、ラムダを使用して `vector` オブジェクト内の各要素が偶数か奇数であるかをコンソールに出力します。 2 番目の例では、関数オブジェクトを使用して同じタスクを行っています。

## <a name="example-1-using-a-lambda"></a>例 1: ラムダの使用

この例では、ラムダを **for_each** 関数に渡します。 ラムダは、`vector` オブジェクト内の各要素が偶数か奇数かを示す結果を出力します。

### <a name="code"></a>コード

```cpp
// even_lambda.cpp
// compile with: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
   // Create a vector object that contains 9 elements.
   vector<int> v;
   for (int i = 1; i < 10; ++i) {
      v.push_back(i);
   }

   // Count the number of even numbers in the vector by
   // using the for_each function and a lambda.
   int evenCount = 0;
   for_each(v.begin(), v.end(), [&evenCount] (int n) {
      cout << n;
      if (n % 2 == 0) {
         cout << " is even " << endl;
         ++evenCount;
      } else {
         cout << " is odd " << endl;
      }
   });

   // Print the count of even numbers to the console.
   cout << "There are " << evenCount
        << " even numbers in the vector." << endl;
}
```

```Output
1 is odd
2 is even
3 is odd
4 is even
5 is odd
6 is even
7 is odd
8 is even
9 is odd
There are 4 even numbers in the vector.
```

### <a name="comments"></a>説明

この例では、 **for_each** 関数の3番目の引数はラムダです。 `[&evenCount]` の部分は、式の capture 句を指定します。`(int n)` はパラメーター リストを指定します。残りの部分は、式の本体を指定します。

## <a name="example-2-using-a-function-object"></a>例 2: 関数オブジェクトの使用

ラムダは、前の例よりも拡張するのがはるかに複雑になる場合があります。 次の例では、ラムダの代わりに関数オブジェクトを **for_each** 関数と共に使用して、例1と同じ結果を生成します。 どちらの例でも `vector` オブジェクトに含まれる偶数の数を格納します。 操作の状態を保持するために、`FunctorClass` クラスはメンバー変数の参照として `m_evenCount` 変数を格納します。 操作を実行するために、は `FunctorClass` 関数呼び出し演算子である **operator ()** を実装します。 Microsoft C++ コンパイラは、サイズとパフォーマンスに匹敵するコードを例1のラムダコードに生成します。 ここで紹介したような基本的な問題の場合は、おそらく、より単純なラムダのデザインの方が関数オブジェクトよりも適切です。 ただし、後で大幅な機能拡張が必要となる可能性がある場合は、コードの保守が容易になるように、関数オブジェクトのデザインを使用します。

**演算子 ()** の詳細については、「[関数呼び出し](../cpp/function-call-cpp.md)」を参照してください。 **For_each** 関数の詳細については、「 [for_each](../standard-library/algorithm-functions.md#for_each)」を参照してください。

### <a name="code"></a>コード

```cpp
// even_functor.cpp
// compile with: /EHsc
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

class FunctorClass
{
public:
    // The required constructor for this example.
    explicit FunctorClass(int& evenCount)
        : m_evenCount(evenCount) { }

    // The function-call operator prints whether the number is
    // even or odd. If the number is even, this method updates
    // the counter.
    void operator()(int n) const {
        cout << n;

        if (n % 2 == 0) {
            cout << " is even " << endl;
            ++m_evenCount;
        } else {
            cout << " is odd " << endl;
        }
    }

private:
    // Default assignment operator to silence warning C4512.
    FunctorClass& operator=(const FunctorClass&);

    int& m_evenCount; // the number of even variables in the vector.
};

int main()
{
    // Create a vector object that contains 9 elements.
    vector<int> v;
    for (int i = 1; i < 10; ++i) {
        v.push_back(i);
    }

    // Count the number of even numbers in the vector by
    // using the for_each function and a function object.
    int evenCount = 0;
    for_each(v.begin(), v.end(), FunctorClass(evenCount));

    // Print the count of even numbers to the console.
    cout << "There are " << evenCount
        << " even numbers in the vector." << endl;
}
```

```Output
1 is odd
2 is even
3 is odd
4 is even
5 is odd
6 is even
7 is odd
8 is even
9 is odd
There are 4 even numbers in the vector.
```

## <a name="see-also"></a>関連項目

[ラムダ式](../cpp/lambda-expressions-in-cpp.md)<br/>
[ラムダ式の例](../cpp/examples-of-lambda-expressions.md)<br/>
[生み](../standard-library/algorithm-functions.md#generate)<br/>
[generate_n](../standard-library/algorithm-functions.md#generate_n)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)<br/>
[例外の指定 (throw)](../cpp/exception-specifications-throw-cpp.md)<br/>
[コンパイラの警告 (レベル 1) C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md)<br/>
[Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)
