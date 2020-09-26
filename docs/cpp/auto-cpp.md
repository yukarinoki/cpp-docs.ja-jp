---
title: auto (C++)
ms.date: 12/10/2019
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: be268635e61005efbdb01ed8c4eec79c7cb9b800
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "91353039"
---
# <a name="auto-c"></a>`auto` (C++)

宣言された変数の型を、その初期化式から推測します。

> [!NOTE]
> C++ 標準では、このキーワードの元の意味と改訂された意味が定義されています。 Visual Studio 2010 より前では、キーワードは、 **`auto`** *自動* ストレージクラスの変数、つまりローカルの有効期間を持つ変数を宣言しています。 Visual Studio 2010 以降では、 **`auto`** キーワードは、宣言の初期化式から推測される型を持つ変数を宣言します。 [ `/Zc:auto`&#91; &#93;](../build/reference/zc-auto-deduce-variable-type.md)コンパイラオプションは、キーワードの意味を制御し **`auto`** ます。

## <a name="syntax"></a>構文

> **`auto`***宣言**子の初期化子***`;`**

> **`[](auto`***param1* **`, auto`***param2***`) {};`**

## <a name="remarks"></a>解説

キーワードは、宣言された **`auto`** 変数の初期化式、またはラムダ式のパラメーターを使用してその型を推測するようにコンパイラに指示します。

変換が必要な場合を除き、ほとんどの状況でキーワードを使用することをお勧めし **`auto`** ます。これには、次のような利点があります。

- **堅牢性:** 式の型が変更された場合は、関数の戻り値の型が変更されたときにのみ機能します。

- **パフォーマンス:** 変換が行われないことは保証されています。

- **使いやすさ:** 型名のスペルの問題や誤字を心配する必要はありません。

- **効率:** コーディングの方が効率的です。

以下を使用する必要がない変換ケース **`auto`** :

- 特定の型が必要であり、他の型を使用できない場合。

- 式テンプレートヘルパー型 (たとえば、) `(valarray+valarray)` 。

キーワードを使用するには、 **`auto`** 変数を宣言するために型の代わりに使用し、初期化式を指定します。 また、、 **`auto`** **`const`** **`volatile`** 、pointer ( **`*`** )、reference ( **`&`** )、右辺値参照 () などの指定子と宣言子を使用して、キーワードを変更することもでき **`&&`** ます。 コンパイラは初期化式を評価し、その情報を使用して変数の型を推測します。

初期化式には、代入 (等号の構文)、直接の初期化 (関数形式の構文)、 [`operator new`](new-operator-cpp.md) 式、または、[範囲ベースの `for` ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)ステートメントで*の範囲宣言*のパラメーターを指定できます。 詳細については、このドキュメントで後述する「 [初期化子](../cpp/initializers.md) とコード例」を参照してください。

キーワードは、 **`auto`** 型のプレースホルダーですが、それ自体は型ではありません。 そのため、キーワードは、やなどの **`auto`** キャストまたは演算子では使用できません [`sizeof`](../cpp/sizeof-operator.md) (C++/cli の場合) [`typeid`](../extensions/typeid-cpp-component-extensions.md) 。

## <a name="usefulness"></a>実用性

**`auto`** キーワードは、複雑な型を持つ変数を宣言する簡単な方法です。 たとえば、を使用して、 **`auto`** 初期化式にテンプレート、関数へのポインター、またはメンバーへのポインターが含まれる変数を宣言できます。

また、を使用し **`auto`** て、変数を宣言し、ラムダ式に初期化することもできます。 ラムダ式の型を認識できるのはコンパイラのみであるため、プログラマが変数の型を宣言することはできません。 詳細については、「 [ラムダ式の例](../cpp/examples-of-lambda-expressions.md)」を参照してください。

## <a name="trailing-return-types"></a>後続の戻り値の型

を型指定子と共に使用すると、 **`auto`** **`decltype`** テンプレートライブラリを記述するのに役立ちます。 とを使用し **`auto`** て、 **`decltype`** 戻り値の型がテンプレート引数の型に依存するテンプレート関数を宣言します。 または、とを使用して、 **`auto`** **`decltype`** 別の関数の呼び出しをラップするテンプレート関数を宣言し、その他の関数の戻り値の型を返します。 詳細については、[`decltype`](../cpp/decltype-cpp.md) を参照してください。

## <a name="references-and-cv-qualifiers"></a>参照と cv 修飾子

を使用する **`auto`** と、参照、修飾子、および修飾子が削除されることに注意 **`const`** **`volatile`** してください。 次に例を示します。

```cpp
// cl.exe /analyze /EHsc /W4
#include <iostream>

using namespace std;

int main( )
{
    int count = 10;
    int& countRef = count;
    auto myAuto = countRef;

    countRef = 11;
    cout << count << " ";

    myAuto = 12;
    cout << count << endl;
}
```

前の例では、myAuto は **`int`** 参照ではなくです **`int`** 。そのため、 `11 11` `11 12` 参照修飾子がによって削除されていない場合のように、出力はになり **`auto`** ます。

## <a name="type-deduction-with-braced-initializers-c14"></a>かっこ付き初期化子を使用した型推論 (C++ 14)

次のコード例は、 **`auto`** 中かっこを使用して変数を初期化する方法を示しています。 B と C の違いと A と E の違いに注意してください。

```cpp
#include <initializer_list>

int main()
{
    // std::initializer_list<int>
    auto A = { 1, 2 };

    // std::initializer_list<int>
    auto B = { 3 };

    // int
    auto C{ 4 };

    // C3535: cannot deduce type for 'auto' from initializer list'
    auto D = { 5, 6.7 };

    // C3518 in a direct-list-initialization context the type for 'auto'
    // can only be deduced from a single initializer expression
    auto E{ 8, 9 };

    return 0;
}
```

## <a name="restrictions-and-error-messages"></a>制限事項とエラー メッセージ

次の表に、キーワードの使用に関する制限 **`auto`** と、コンパイラによって生成される対応する診断エラーメッセージの一覧を示します。

|エラー番号|説明|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|**`auto`** キーワードを他の型指定子と組み合わせることはできません。|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|キーワードで宣言されたシンボルには **`auto`** 初期化子が必要です。|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|キーワードを誤って使用して **`auto`** 型を宣言した。 たとえば、メソッドの戻り値の型または配列を宣言しました。|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md)、 [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|パラメーターまたはテンプレート引数をキーワードで宣言することはできません **`auto`** 。|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|メソッドまたはテンプレートパラメーターをキーワードで宣言することはできません **`auto`** 。|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|シンボルは初期化前に使用することはできません。 実際には、変数はその変数自体を初期化するために使用できないことを意味します。|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|キーワードで宣言された型にキャストすることはできません **`auto`** 。|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|キーワードを使用して宣言されている宣言子リスト内のすべてのシンボルは、 **`auto`** 同じ型に解決する必要があります。 詳細については、「 [宣言と定義](declarations-and-definitions-cpp.md)」を参照してください。|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md)、 [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|[Sizeof](../cpp/sizeof-operator.md)および[typeid](../extensions/typeid-cpp-component-extensions.md)演算子は、キーワードで宣言されたシンボルには適用できません **`auto`** 。|

## <a name="examples"></a>例

これらのコードフラグメントは、キーワードを使用するいくつかの方法を示して **`auto`** います。

次の宣言は同等です。 最初のステートメントでは、変数 `j` が型として宣言されてい **`int`** ます。 2番目のステートメントで `k` は、 **`int`** 初期化式 (0) が整数であるため、変数は型と推測されます。

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

次の宣言は同じ意味を持ちますが、2 番目の宣言の方が最初の宣言より単純です。 キーワードを使用する最も説得力のある理由の1つ **`auto`** は、単純であることです。

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

次のコード片では、変数の型 `iter` と、 `elem` 範囲のループが開始されるタイミングを宣言し **`for`** **`for`** ます。

```cpp
// cl /EHsc /nologo /W4
#include <deque>
using namespace std;

int main()
{
    deque<double> dqDoubleData(10, 0.1);

    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)
    { /* ... */ }

    // prefer range-for loops with the following information in mind
    // (this applies to any range-for with auto, not just deque)

    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples
    { /* ... */ }

    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE
    { /* ... */ }

    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE
    { /* ... */ }
}
```

次のコード片では、 **`new`** 演算子とポインターの宣言を使用してポインターを宣言しています。

```cpp
double x = 12.34;
auto *y = new auto(x), **z = new auto(&x);
```

次のコード片は各宣言ステートメントで複数のシンボルを宣言します。 各ステートメントのすべてのシンボルが同じ型に解決されることに注意してください。

```cpp
auto x = 1, *y = &x, **z = &y; // Resolves to int.
auto a(2.01), *b (&a);         // Resolves to double.
auto c = 'a', *d(&c);          // Resolves to char.
auto m = 1, &n = m;            // Resolves to int.
```

次のコード片は、値が 200 の整数として変数 `?:` を宣言するために、条件演算子 (`x`) を使用します。

```cpp
int v1 = 100, v2 = 200;
auto x = v1 > v2 ? v1 : v2;
```

次のコードフラグメントは、変数を型に、変数を型への参照に、変数を型を `x` **`int`** `y` **`const int`** `fp` 返す関数へのポインターに初期化し **`int`** ます。

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto& y = f(1);
    int (*p)(int x);
    p = f;
    auto fp = p;
    //...
}
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[`/Zc:auto` (変数の型の推測)](../build/reference/zc-auto-deduce-variable-type.md)<br/>
[`sizeof` 演算子](../cpp/sizeof-operator.md)<br/>
[`typeid`](../extensions/typeid-cpp-component-extensions.md)<br/>
[`operator new`](new-operator-cpp.md)<br/>
[宣言と定義](declarations-and-definitions-cpp.md)<br/>
[ラムダ式の例](../cpp/examples-of-lambda-expressions.md)<br/>
[初期化子](../cpp/initializers.md)<br/>
[`decltype`](../cpp/decltype-cpp.md)
