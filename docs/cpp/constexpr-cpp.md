---
title: constexpr (C++)
description: C++ 言語キーワードのガイド constexpr 。
ms.date: 01/28/2020
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- constexpr
- const
- inline
- goto
- try
- if
- switch
- for
- while
ms.openlocfilehash: 57ebf4bf69c768bfcd2e4d26a5c3334ca788b08f
ms.sourcegitcommit: a6b97f5d78299ad93675de2fe0f0561f528d26c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90569565"
---
# <a name="no-locconstexpr-c"></a>constexpr (C++)

キーワードは **`constexpr`** c++ 11 で導入され、c++ 14 で改良されました。 これは、 * const ant 式*を意味します。 と同様 **`const`** に、変数に適用できます。コードが if 値を mod しようとしたときにコンパイラエラーが発生します。 とは異なり **`const`** 、は **`constexpr`** 関数およびクラス const ructors も適用できます。 **`constexpr`** 値 (戻り値) が ant であり const 、可能であればコンパイル時に計算されることを示します。

**`constexpr`** 整数値は、 const テンプレート引数や配列宣言など、整数が必要な場所で使用できます。 また、値が実行時ではなくコンパイル時に計算されると、プログラムの実行速度が向上し、使用するメモリが少なくなります。

コンパイル時の ant 計算の複雑さと、コンパイル時の潜在的な影響を制限するために、 const c++ 14 標準では、ant 式の型がリテラル型である必要があり const ます。 [literal types](trivial-standard-layout-and-pod-types.md#literal_types)

## <a name="syntax"></a>構文

> **`constexpr`***リテラル型* *ident if ier* **=** * const * **;**\
> **`constexpr`***リテラル型* *ident if ier* **{** * const ant 式* **}** **;**\
> **`constexpr`***リテラル型* *ident if ier* **(** *params* **)** **;**\
> **`constexpr`***.ctor* **(** *params* **)** **;**

## <a name="parameters"></a>パラメーター

*params*\
1つ以上のパラメーター。それぞれがリテラル型である必要があり、それ自体が ant 式でなければなりません const 。

## <a name="return-value"></a>戻り値

**`constexpr`** 変数または関数は、[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)を返す必要があります。

## <a name="no-locconstexpr-variables"></a>constexpr 変数

変数 if と変数の間の主な d f) **`const`** は、 **`constexpr`** 変数の初期化を **`const`** 実行時まで遅らせることができることです。 変数は、 **`constexpr`** コンパイル時に初期化する必要があります。  すべて **`constexpr`** の変数は **`const`** です。

- 変数は **`constexpr`** 、リテラル型を持ち、初期化されている場合、で宣言できます。 Ructor によって1つずつ初期化される場合は、 for const ructor をとし const て宣言する必要があり **`constexpr`** ます。

- 参照は、 **`constexpr`** 両方の条件が満たされたときにとして宣言できます。参照されるオブジェクトは、ant 式によって初期化されます。また、 const 初期化中に呼び出された暗黙の変換も const ant 式になります。

- **`constexpr`** 変数または関数のすべての宣言には、spec ier を指定する必要があり **`constexpr`** if ます。

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="no-locconstexpr-functions"></a><a name="constexpr_functions"></a> constexpr 関数

**`constexpr`** 関数は、コンパイル時にコードを使用する必要がある場合に、戻り値が計算できるである関数です。 コードを使用するには、コンパイル時に変数を初期化する **`constexpr`** か、非型テンプレート引数を指定する必要があります。 引数が値の場合 **`constexpr`** 、 **`constexpr`** 関数はコンパイル時に ant を生成 const します。 引数以外のを使用して呼び出された場合 **`constexpr`** 、またはコンパイル時に値が必要ない場合は、実行時に通常の関数のように値が生成されます。 (このデュアル動作で **`constexpr`** は、同じ関数の非バージョンを書き込む必要がなく **`constexpr`** なります)。

**`constexpr`** 関数または const ructor は暗黙的に **`inline`** です。

関数には、次の規則が適用され constexpr ます。

- 関数は、 **`constexpr`** [リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)のみを受け入れて返す必要があります。

- **`constexpr`** 関数は再帰的に使用できます。

- [仮想](../cpp/virtual-cpp.md)にすることはできません。 Ructor は、 const **`constexpr`** 外側のクラスに仮想基底クラスがある場合として定義することはできません。

- 本体は `= default` または `= delete` として定義できます。

- 本文に **`goto`** は、ステートメントまたはブロックを含めることはできません **`try`** 。

- 以外のテンプレートの明示的な特殊化は、 **`constexpr`** 次のように宣言でき **`constexpr`** ます。

- テンプレートの明示的な特殊化は、 **`constexpr`** 次のようにする必要もありません **`constexpr`** 。

次の規則は、 **`constexpr`** Visual Studio 2017 以降の関数に適用されます。

- これには **`if`** 、 **`switch`** ステートメントとステートメント、および **`for`** 、範囲ベース **`for`** の、 **`while`** 、および**do while -** を含むすべてのループステートメントを含めることができます。

- ローカル変数宣言が含まれている場合がありますが、変数を初期化する必要があります。 リテラル型である必要があり、 **`static`** またはスレッドローカルにすることはできません。 ローカルで宣言された変数は、である必要はなく、変化する **`const`** 可能性があります。

- **`constexpr`** 非 **`static`** メンバー関数は、暗黙的に指定する必要はありません **`const`** 。

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
}
```

> [!TIP]
> Visual Studio デバッガーで、最適化されていないデバッグビルドをデバッグする場合、コンパイル時に関数が評価されているかどうかを判断するには、 **`constexpr`** その中にブレークポイントを配置します。 ブレークポイントにヒットすると、実行時に関数が呼び出されます。  ヒットしなければ、コンパイル時に関数が呼び出されます。

## <a name="extern-no-locconstexpr"></a>不十分 constexpr

[/Zc: externConstexpr](../build/reference/zc-externconstexpr.md)コンパイラオプションを使用すると、コンパイラは** constexpr extern**を使用して宣言された変数に[外部リンケージ](../c-language/external-linkage.md)を適用します。 以前のバージョンの Visual Studio では、既定で、または **/zc: externConstexpr** が仕様になっている場合 if 、 **`constexpr`** キーワードが使用されている場合でも、visual studio は変数への内部リンケージを適用 **`extern`** します。 **/Zc: externConstexpr**オプションは、Visual Studio 2017 更新プログラム15.6 以降で使用でき、既定ではオフになっています。 [/Permissive-](../build/reference/permissive-standards-conformance.md)オプションでは **/zc: externConstexpr**が有効になっていません。

## <a name="example"></a>例

次の例は、 **`constexpr`** 変数、関数、およびユーザー定義型を示しています。 の最後のステートメントで `main()` は、 **`constexpr`** `GetValue()` コンパイル時に値が認識される必要がないため、メンバー関数はランタイム呼び出しです。

```cpp
// constexpr.cpp
// Compile with: cl /EHsc /W4 constexpr.cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
}

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
}

// Compile-time computation of array length
template<typename T, int N>
constexpr int length(const T(&)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue() const
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>必要条件

Visual Studio 2015 以降。

## <a name="see-also"></a>関連項目

[宣言と定義](../cpp/declarations-and-definitions-cpp.md)\
[const](../cpp/const-cpp.md)
