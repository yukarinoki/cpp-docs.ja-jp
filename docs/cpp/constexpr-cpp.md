---
title: ':::no-loc(constexpr)::: (C++)'
description: 'C++ 言語キーワードのガイド :::no-loc(constexpr)::: 。'
ms.date: 01/28/2020
f1_keywords:
- :::no-loc(constexpr):::_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- ':::no-loc(constexpr):::'
- ':::no-loc(const):::'
- ':::no-loc(inline):::'
- ':::no-loc(goto):::'
- ':::no-loc(try):::'
- ':::no-loc(if):::'
- ':::no-loc(switch):::'
- ':::no-loc(for):::'
- ':::no-loc(while):::'
ms.openlocfilehash: d66dc333b7ac9fba94221dc4efa723c7919ef88f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229026"
---
# <a name="no-locconstexpr-c"></a>:::no-loc(constexpr)::: (C++)

キーワードは **`:::no-loc(constexpr):::`** c++ 11 で導入され、c++ 14 で改良されました。 これは、 * :::no-loc(const)::: ant 式*を意味します。 と同様 **`:::no-loc(const):::`** に、変数に適用できます。コードが :::no-loc(if)::: 値を mod しようとしたときにコンパイラエラーが発生します。 とは異なり **`:::no-loc(const):::`** 、は **`:::no-loc(constexpr):::`** 関数およびクラス :::no-loc(const)::: ructors も適用できます。 **`:::no-loc(constexpr):::`** 値 (戻り値) が ant であり :::no-loc(const)::: 、可能であればコンパイル時に計算されることを示します。

**`:::no-loc(constexpr):::`** 整数値は、 :::no-loc(const)::: テンプレート引数や配列宣言など、整数が必要な場所で使用できます。 また、値が実行時ではなくコンパイル時に計算されると、プログラムの実行速度が向上し、使用するメモリが少なくなります。

コンパイル時の ant 計算の複雑さと、コンパイル時の潜在的な影響を制限するために、 :::no-loc(const)::: c++ 14 標準では、ant 式の型がリテラル型である必要があり :::no-loc(const)::: ます。 [literal types](trivial-standard-layout-and-pod-types.md#literal_types)

## <a name="syntax"></a>構文

> **`:::no-loc(constexpr):::`***リテラル型* *ident :::no-loc(if)::: ier* **=** * :::no-loc(const)::: * **;**\
> **`:::no-loc(constexpr):::`***リテラル型* *ident :::no-loc(if)::: ier* **{** * :::no-loc(const)::: ant 式* **}** **;**\
> **`:::no-loc(constexpr):::`***リテラル型* *ident :::no-loc(if)::: ier* **(** *params* **)** **;**\
> **`:::no-loc(constexpr):::`***.ctor* **(** *params* **)** **;**

## <a name="parameters"></a>パラメーター

*params*\
1つ以上のパラメーター。それぞれがリテラル型である必要があり、それ自体が ant 式でなければなりません :::no-loc(const)::: 。

## <a name="return-value"></a>戻り値

**`:::no-loc(constexpr):::`** 変数または関数は、[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)を返す必要があります。

## <a name="no-locconstexpr-variables"></a>:::no-loc(constexpr)::: 変数

変数 :::no-loc(if)::: と変数の間の主な d f) **`:::no-loc(const):::`** は、 **`:::no-loc(constexpr):::`** 変数の初期化を **`:::no-loc(const):::`** 実行時まで遅らせることができることです。 変数は、 **`:::no-loc(constexpr):::`** コンパイル時に初期化する必要があります。  すべて **`:::no-loc(constexpr):::`** の変数は **`:::no-loc(const):::`** です。

- 変数は **`:::no-loc(constexpr):::`** 、リテラル型を持ち、初期化されている場合、で宣言できます。 Ructor によって1つずつ初期化される場合は、 :::no-loc(for)::: :::no-loc(const)::: ructor をとし :::no-loc(const)::: て宣言する必要があり **`:::no-loc(constexpr):::`** ます。

- 参照は、 **`:::no-loc(constexpr):::`** 両方の条件が満たされたときにとして宣言できます。参照されるオブジェクトは、ant 式によって初期化されます。また、 :::no-loc(const)::: 初期化中に呼び出された暗黙の変換も :::no-loc(const)::: ant 式になります。

- **`:::no-loc(constexpr):::`** 変数または関数のすべての宣言には、spec ier を指定する必要があり **`:::no-loc(constexpr):::`** :::no-loc(if)::: ます。

```cpp
:::no-loc(constexpr)::: float x = 42.0;
:::no-loc(constexpr)::: float y{108};
:::no-loc(constexpr)::: float z = exp(5, 3);
:::no-loc(constexpr)::: int i; // Error! Not initialized
int j = 0;
:::no-loc(constexpr)::: int k = j + 1; //Error! j not a :::no-loc(const):::ant expression
```

## <a name="no-locconstexpr-functions"></a><a name=":::no-loc(constexpr):::_functions"></a>:::no-loc(constexpr):::関数

**`:::no-loc(constexpr):::`** 関数は、コンパイル時にコードを使用する必要がある場合に、戻り値が計算できるである関数です。 コードを使用するには、コンパイル時に変数を初期化する **`:::no-loc(constexpr):::`** か、非型テンプレート引数を指定する必要があります。 引数が値の場合 **`:::no-loc(constexpr):::`** 、 **`:::no-loc(constexpr):::`** 関数はコンパイル時に ant を生成 :::no-loc(const)::: します。 引数以外のを使用して呼び出された場合 **`:::no-loc(constexpr):::`** 、またはコンパイル時に値が必要ない場合は、実行時に通常の関数のように値が生成されます。 (このデュアル動作で **`:::no-loc(constexpr):::`** は、同じ関数の非バージョンを書き込む必要がなく **`:::no-loc(constexpr):::`** なります)。

**`:::no-loc(constexpr):::`** 関数または :::no-loc(const)::: ructor は暗黙的に **`:::no-loc(inline):::`** です。

関数には、次の規則が適用され :::no-loc(constexpr)::: ます。

- 関数は、 **`:::no-loc(constexpr):::`** [リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)のみを受け入れて返す必要があります。

- **`:::no-loc(constexpr):::`** 関数は再帰的に使用できます。

- [仮想](../cpp/virtual-cpp.md)にすることはできません。 Ructor は、 :::no-loc(const)::: **`:::no-loc(constexpr):::`** 外側のクラスに仮想基底クラスがある場合として定義することはできません。

- 本体は `= default` または `= delete` として定義できます。

- 本文に **`:::no-loc(goto):::`** は、ステートメントまたはブロックを含めることはできません **`:::no-loc(try):::`** 。

- 以外のテンプレートの明示的な特殊化は、 **`:::no-loc(constexpr):::`** 次のように宣言でき **`:::no-loc(constexpr):::`** ます。

- テンプレートの明示的な特殊化は、 **`:::no-loc(constexpr):::`** 次のようにする必要もありません **`:::no-loc(constexpr):::`** 。

次の規則は、 **`:::no-loc(constexpr):::`** Visual Studio 2017 以降の関数に適用されます。

- これには **`:::no-loc(if):::`** 、 **`:::no-loc(switch):::`** ステートメントとステートメント、および **`:::no-loc(for):::`** 、範囲ベース **`:::no-loc(for):::`** の、 **`:::no-loc(while):::`** 、および**do :::no-loc(while)::: -** を含むすべてのループステートメントを含めることができます。

- ローカル変数宣言が含まれている場合がありますが、変数を初期化する必要があります。 リテラル型である必要があり、 **`static`** またはスレッドローカルにすることはできません。 ローカルで宣言された変数は、である必要はなく、変化する **`:::no-loc(const):::`** 可能性があります。

- **`:::no-loc(constexpr):::`** 非 **`static`** メンバー関数は、暗黙的に指定する必要はありません **`:::no-loc(const):::`** 。

```cpp
:::no-loc(constexpr)::: float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Visual Studio デバッガーで、最適化されていないデバッグビルドをデバッグする場合、コンパイル時に関数が評価されているかどうかを判断するには、 **`:::no-loc(constexpr):::`** その中にブレークポイントを配置します。 ブレークポイントにヒットすると、実行時に関数が呼び出されます。  ヒットしなければ、コンパイル時に関数が呼び出されます。

## <a name="extern-no-locconstexpr"></a>不十分:::no-loc(constexpr):::

[/Zc: externConstexpr](../build/reference/zc-extern:::no-loc(constexpr):::.md)コンパイラオプションを使用すると、コンパイラは** :::no-loc(constexpr)::: extern**を使用して宣言された変数に[外部リンケージ](../c-language/external-linkage.md)を適用します。 以前のバージョンの Visual Studio では、既定で、または **/zc: externConstexpr**が仕様になっている場合 :::no-loc(if)::: 、 **`:::no-loc(constexpr):::`** キーワードが使用されている場合でも、visual studio は変数への内部リンケージを適用 **`extern`** します。 **/Zc: externConstexpr**オプションは、Visual Studio 2017 更新プログラム15.6 以降で使用でき、既定ではオフになっています。 [/Permissive-](../build/reference/permissive-standards-con:::no-loc(for):::mance.md)オプションでは **/zc: externConstexpr**が有効になっていません。

## <a name="example"></a>例

次の例は、 **`:::no-loc(constexpr):::`** 変数、関数、およびユーザー定義型を示しています。 の最後のステートメントで `main()` は、 **`:::no-loc(constexpr):::`** `GetValue()` コンパイル時に値が認識される必要がないため、メンバー関数はランタイム呼び出しです。

```cpp
// :::no-loc(constexpr):::.cpp
// Compile with: cl /EHsc /W4 :::no-loc(constexpr):::.cpp
#include <iostream>

using namespace std;

// Pass by value
:::no-loc(constexpr)::: float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};

// Pass by reference
:::no-loc(constexpr)::: float exp2(:::no-loc(const)::: float& x, :::no-loc(const)::: int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

// Compile-time computation of array length
template<typename T, int N>
:::no-loc(constexpr)::: int length(:::no-loc(const)::: T(&)[N])
{
    return N;
}

// Recursive :::no-loc(constexpr)::: function
:::no-loc(constexpr)::: int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    :::no-loc(constexpr)::: explicit Foo(int i) : _i(i) {}
    :::no-loc(constexpr)::: int GetValue() :::no-loc(const):::
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is :::no-loc(const)::::
    :::no-loc(constexpr)::: Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    :::no-loc(constexpr)::: float x = exp(5, 3);
    :::no-loc(constexpr)::: float y { exp(2, 5) };
    :::no-loc(constexpr)::: int val = foo.GetValue();
    :::no-loc(constexpr)::: int f5 = fac(5);
    :::no-loc(const)::: int nums[] { 1, 2, 3, 4 };
    :::no-loc(const)::: int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>必要条件

Visual Studio 2015 以降。

## <a name="see-also"></a>関連項目

[宣言と定義](../cpp/declarations-and-definitions-cpp.md)\
[:::no-loc(const):::](../cpp/:::no-loc(const):::-cpp.md)
