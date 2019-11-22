---
title: Type conversions and type safety
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 629b361a-2ce1-4700-8b5d-ab4f57b245d5
ms.openlocfilehash: dbca9057622ab1a92b74e2958b8dfbe8d810fede
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246113"
---
# <a name="type-conversions-and-type-safety"></a>Type conversions and type safety

このドキュメントでは、共通型の変換に伴う問題を識別し、C++ コードでそれらを回避する方法を説明します。

C ++.のプログラムを作成するときは、そのプログラムがタイプ セーフであることを確認することが重要です。 これは、すべての変数、関数の引数、および関数の戻り値が適切な種類のデータを格納すること、異なる型の値が関係する操作が "意味のある" 処理を行うこと、さらにデータ損失、ビット パターンの誤った解釈、メモリ破損を発生させないことを意味します。 プログラムが、明示的または暗黙的に、ある型の値を他の型に変換しないことが、定義上のタイプ セーフです。 ただし、型の変換、また場合によっては安全でない変換が必須になることもあります。 For example, you might have to store the result of a floating point operation in a variable of type **int**, or you might have to pass the value in an unsigned **int** to a function that takes a signed **int**. Both examples illustrate unsafe conversions because they may cause data loss or re-interpretation of a value.

コンパイラが安全ではない変換を検出した場合は、エラーまたは警告を発行します。 エラーが生じた場合はコンパイルが中止されます。警告が生じた場合は、コンパイルは続行されますが、コード内にエラーが存在する可能性が示されます。 ただし、警告なしでプログラムがコンパイルされた場合でも、正しくない結果を生成する暗黙の型変換につながるコードが存在している可能性があります。 型エラーは、コード内の明示的な変換、またはキャストによって発生する可能性があります。

## <a name="implicit-type-conversions"></a>暗黙的な型変換

When an expression contains operands of different built-in types, and no explicit casts are present, the compiler uses built-in *standard conversions* to convert one of the operands so that the types match. コンパイラはいずれかが成功するまで、適切に定義された一連の変換を試みます。 選択した変換が上位変換である場合は、コンパイラは警告を発行しません。 変換が縮小変換である場合は、コンパイラは、データ損失の可能性に関する警告を発行します。 実際のデータ損失が発生するかどうかは、関与する実際の値に依存しますが、この警告をエラーとして扱うことをお勧めします。 ユーザー定義型が関与している場合は、コンパイラは、ユーザーがクラス定義の中で指定した変換を使用しようとします。 受け入れ可能な変換が見つからない場合は、コンパイラはエラーを発行し、プログラムをコンパイルしません。 For more information about the rules that govern the standard conversions, see [Standard Conversions](../cpp/standard-conversions.md). For more information about user-defined conversions, see [User-Defined Conversions (C++/CLI)](../dotnet/user-defined-conversions-cpp-cli.md).

### <a name="widening-conversions-promotion"></a>拡大変換 (上位変換)

拡大変換では、より小さい変数内の値が、より大きい変数に代入され、データは失われません。 拡大変換は常に安全であるため、コンパイラはこの変換を自動的に実行し、警告を発行しません。 次の変換は、拡大変換です。

|変換元|終了|
|----------|--------|
|Any signed or unsigned integral type except **long long** or **__int64**|**double**|
|**bool** or **char**|他のすべての組み込み型|
|**short** or **wchar_t**|**int**, **long**, **long long**|
|**int**, **long**|**long long**|
|**float**|**double**|

### <a name="narrowing-conversions-coercion"></a>縮小変換 (強制型)

コンパイラは、暗黙的に縮小変換を実行しますが、データ損失の可能性に関する警告を発行します。 これらの警告を重大なものとして受け止めてください。 大きい変数の中にある値が、小さい変数の中に必ず収容でき、データ損失が発生しないことが確実な場合は、コンパイラが今後警告を発行しないように、明示的なキャストを追加してください。 変換が安全かどうか自信がない場合は、コード内になんらかの種類の実行時チェックを追加し、発生する可能性のあるデータ損失に対処できるようにしてください。その結果、プログラムが誤った結果を生成することはありません。

浮動小数点型から整数型へのあらゆる変換は、浮動小数点値の小数部が破棄されて失われるため、縮小変換です。

次のコード例では、いくつかの暗黙的な縮小変換と、それらに関してコンパイラが発行する警告を示します。

```cpp
int i = INT_MAX + 1; //warning C4307:'+':integral constant overflow
wchar_t wch = 'A'; //OK
char c = wch; // warning C4244:'initializing':conversion from 'wchar_t'
              // to 'char', possible loss of data
unsigned char c2 = 0xfffe; //warning C4305:'initializing':truncation from
                           // 'int' to 'unsigned char'
int j = 1.9f; // warning C4244:'initializing':conversion from 'float' to
              // 'int', possible loss of data
int k = 7.7; // warning C4244:'initializing':conversion from 'double' to
             // 'int', possible loss of data
```

### <a name="signed---unsigned-conversions"></a>符号付き - 符号なしの変換

符号付き整数型と符号なし整数型は常に同じサイズですが、値変換の目的でビット パターンを解釈する方法が異なります。 次のコード例は、同じビット パターンが符号付きの値、および符号なしの値として解釈されるときの動作を示します。 `num` と `num2` の両方に格納されているビット パターンは、前の図から決して変化していません。

```cpp
using namespace std;
unsigned short num = numeric_limits<unsigned short>::max(); // #include <limits>
short num2 = num;
cout << "unsigned val = " << num << " signed val = " << num2 << endl;
// Prints: unsigned val = 65535 signed val = -1

// Go the other way.
num2 = -1;
num = num2;
cout << "unsigned val = " << num << " signed val = " << num2 << endl;
// Prints: unsigned val = 65535 signed val = -1
```

値の再解釈が双方向で発生することに注意してください。 期待される値に対して、符号が反転したように思える奇妙な結果をプログラムが返した場合は、符号付き整数型と符号なし整数型の間で暗黙的な変換が実行された可能性に注目してください。 In the following example, the result of the expression ( 0 - 1) is implicitly converted from **int** to **unsigned int** when it's stored in `num`. この結果、ビット パターンの再解釈が発生します。

```cpp
unsigned int u3 = 0 - 1;
cout << u3 << endl; // prints 4294967295
```

符号付きと符号なし整数型の間の暗黙的な変換について、コンパイラは警告を発行しません。 したがって、符号付きから符号なしへの変換を決して実施しないことをお勧めします。 このような変換を回避できない場合は、変換されようとしている値が 0 以上であるかどうか、および符号付きの型の最大値以下であるかどうかを検出する実行時チェックをコードに追加してください。 この範囲内にある値は、再解釈なしで、符号付きから符号なし、および符号なしから符号付きへと変換されます。

### <a name="pointer-conversions"></a>ポインター変換

多くの式では、C 形式の配列は、配列内の最初の要素へのポインターに暗黙的に変換され、また定数変換が警告なしで実施される可能性があります。 これは便利ですが、場合によってはエラーが発生しやすくなります。 For example, the following badly designed code example seems nonsensical, and yet it will compile and produces a result of 'p'. まず、"Help" 文字列定数リテラルは `char*` に変換されます。このポインターは 配列の最初の要素を指し、3 つの要素によってインクリメントされます。その結果、最後の要素 'p' を指すようになります。

```cpp
char* s = "Help" + 3;
```

## <a name="explicit-conversions-casts"></a>明示的な変換 (キャスト)

キャスト操作を使用すると、ある型の値を別の型に変換するようにコンパイラに指示できます。 2 つの方が完全に無関係である場合はコンパイラはエラーを生成しますが、操作がタイプ セーフでない場合でもエラーを生成しない状況が存在します。 キャストは控えめに使用してください。ある型から別の型への変換は、プログラム エラーの原因となる可能性があるためです。 ただし、時にはキャストが必須であり、すべてのキャストが等しく危険というわけでもありません。 キャストの 1 つの効率的な使用方法は、コードが縮小変換を実行し、その変換により、プログラムが不適切な結果をもたらさないことがわかっている場合です。 実際には、何を実行するかを開発者が理解していて、その点に関する警告を発行しないようにコンパイラに指示することになります。 別の使用法は、ポインターから派生クラス、およびポインターから基底クラスへのキャストです。 Another use is to cast away the **const**-ness of a variable to pass it to a function that requires a non-**const** argument. これらのキャスト操作のほとんどには、ある程度のリスクが存在します。

C スタイルのプログラミングでは、同じ C スタイルのキャスト演算子が、あらゆる種類のキャストに使用されます。

```cpp
(int) x; // old-style cast, old-style syntax
int(x); // old-style cast, functional syntax
```

つまり、C スタイルのキャスト演算子は、呼び出し演算子 () と同じものであり、したがって、コードの中で目立たず、簡単に見過ごす可能性があります。 Both are bad because they're difficult to recognize at a glance or search for, and they're disparate enough to invoke any combination of **static**, **const**, and **reinterpret_cast**. 古いスタイルのキャストの実際の動作を理解するのは困難で、エラーが発生しやすくなります。 これらすべての理由により、キャストがどうしても必要な場合は、次の C++ スタイルのキャスト操作のいずれかを使用することをお勧めします。特定の状況では、かなりタイプ セーフであり、プログラミングの意図を非常に明確に表現できるからです。

- **static_cast**, for casts that are checked at compile time only. **static_cast** returns an error if the compiler detects that you are trying to cast between types that are completely incompatible. これを、基本型へのポインターと、派生形へのポインターの間でのキャストに使用することもできますが、コンパイラはこのような変換が実行時に安全かどうかを必ず判定できるわけではありません。

    ```cpp
    double d = 1.58947;
    int i = d;  // warning C4244 possible loss of data
    int j = static_cast<int>(d);       // No warning.
    string s = static_cast<string>(d); // Error C2440:cannot convert from
                                       // double to std:string

    // No error but not necessarily safe.
    Base* b = new Base();
    Derived* d2 = static_cast<Derived*>(b);
    ```

   For more information, see [static_cast](../cpp/static-cast-operator.md).

- **dynamic_cast**, for safe, runtime-checked casts of pointer-to-base to pointer-to-derived. A **dynamic_cast** is safer than a **static_cast** for downcasts, but the runtime check incurs some overhead.

    ```cpp
    Base* b = new Base();

    // Run-time check to determine whether b is actually a Derived*
    Derived* d3 = dynamic_cast<Derived*>(b);

    // If b was originally a Derived*, then d3 is a valid pointer.
    if(d3)
    {
       // Safe to call Derived method.
       cout << d3->DoSomethingMore() << endl;
    }
    else
    {
       // Run-time check failed.
       cout << "d3 is null" << endl;
    }

    //Output: d3 is null;
    ```

   For more information, see [dynamic_cast](../cpp/dynamic-cast-operator.md).

- **const_cast**, for casting away the **const**-ness of a variable, or converting a non-**const** variable to be **const**. Casting away **const**-ness by using this operator is just as error-prone as is using a C-style cast, except that with **const-cast** you are less likely to perform the cast accidentally. Sometimes you have to cast away the **const**-ness of a variable, for example, to pass a **const** variable to a function that takes a non-**const** parameter. その方法を次の例に示します。

    ```cpp
    void Func(double& d) { ... }
    void ConstCast()
    {
       const double pi = 3.14;
       Func(const_cast<double&>(pi)); //No error.
    }
    ```

   For more information, see [const_cast](../cpp/const-cast-operator.md).

- **reinterpret_cast**, for casts between unrelated types such as **pointer** to **int**.

    > [!NOTE]
    >  このキャスト演算子は、他のキャスト演算子ほどの頻度では使用されず、他のコンパイラへの移植性も保証されません。

   The following example illustrates how **reinterpret_cast** differs from **static_cast**.

    ```cpp
    const char* str = "hello";
    int i = static_cast<int>(str);//error C2440: 'static_cast' : cannot
                                  // convert from 'const char *' to 'int'
    int j = (int)str; // C-style cast. Did the programmer really intend
                      // to do this?
    int k = reinterpret_cast<int>(str);// Programming intent is clear.
                                       // However, it is not 64-bit safe.
    ```

   For more information, see [reinterpret_cast Operator](../cpp/reinterpret-cast-operator.md).

## <a name="see-also"></a>関連項目

[C++ type system](../cpp/cpp-type-system-modern-cpp.md)<br/>
[Welcome back to C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
