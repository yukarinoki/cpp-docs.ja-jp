---
title: constexpr (C++)
ms.date: 08/05/2019
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
ms.openlocfilehash: 5c98436f537b34b1c9050e057971938d48792db1
ms.sourcegitcommit: c3bf94210bdb73be80527166264d49e33784152c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "68821101"
---
# <a name="constexpr-c"></a>constexpr (C++)

キーワード**constexpr**は c++ 11 で導入され、c++ 14 で改良されました。 これは、*定数式*を意味します。 **Const**と同様に、値を変更しようとしたコードがある場合にコンパイラエラーが発生するように、変数に適用できます。 **Const**とは異なり、 **constexpr**は関数およびクラスコンストラクターにも適用できます。 **constexpr**は、値または戻り値が定数であることを示します。可能であれば、コンパイル時に計算されます。

**Constexpr**整数値は、テンプレート引数や配列宣言など、const 整数が必要な場所で使用できます。 また、値を実行時ではなくコンパイル時に計算できる場合は、プログラムの実行速度を向上させ、使用するメモリを減らすことができます。

コンパイル時の定数計算の複雑さと、コンパイル時の潜在的な影響を制限するために、C++ 14 標準では定数式の型が[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)である必要があります。

## <a name="syntax"></a>構文

> **constexpr** *リテラル型* *識別子* **=** *定数式* **;** 
>  **constexpr** *リテラル型* *識別子* **{** *定数式* **}** **;** 
>  **constexpr** *リテラル型* *識別子* **(** *params* **)** **;** 
>  **constexpr** *ctor* **(** *params* **)** **;**

## <a name="parameters"></a>パラメーター

*params*<br/>
1つ以上のパラメーター。それぞれがリテラル型である必要があり、それ自体が定数式である必要があります。

## <a name="return-value"></a>戻り値

Constexpr 変数または関数は、[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)を返す必要があります。

## <a name="constexpr-variables"></a>constexpr 変数

Const 変数と constexpr 変数の主な違いは、const 変数の初期化を実行時まで遅らせることができることです。 Constexpr 変数は、コンパイル時に初期化する必要があります。  すべての constexpr 変数は、const です。

- 変数は、リテラル型を持ち、初期化されている場合、 **constexpr**を使用して宣言できます。 初期化がコンストラクターによって実行される場合、コンストラクターは**constexpr**として宣言されている必要があります。

- 参照するオブジェクトが定数式で初期化され、初期化中に呼び出される暗黙の変換もすべて定数式である場合には、参照を constexpr と宣言することができます。

- **Constexpr**変数または関数のすべての宣言には、 **constexpr**指定子が必要です。

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a>constexpr 関数

**Constexpr**関数は、コンパイル時にコードを必要とするときに戻り値を計算できる関数です。 コードを使用するには、コンパイル時に戻り値が必要です。たとえば、 **constexpr**変数を初期化したり、非型テンプレート引数を指定したりすることができます。 引数が**constexpr**値の場合、 **constexpr**関数はコンパイル時の定数を生成します。 非**constexpr**引数を使用して呼び出された場合、またはコンパイル時に値が必要ない場合は、実行時に通常の関数のように値が生成されます。 (この2つの動作により、同じ関数の**constexpr**と**constexpr**以外のバージョンを記述する必要がなくなります)。

**constexpr**関数またはコンストラクターが暗黙的に**inline**化されています。

Constexpr 関数には、次の規則が適用されます。

- **Constexpr**関数は、[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)のみを受け入れて返す必要があります。

- **Constexpr**関数は再帰的に使用できます。

- [仮想](../cpp/virtual-cpp.md)にすることはできません。 外側のクラスに仮想基底クラスがある場合、コンストラクターを constexpr として定義することはできません。

- 本体は `= default` または `= delete` として定義できます。

- 本文には、 **goto**ステートメントや try ブロックを含めることはできません。

- 非 constexpr テンプレートの明示的な特殊化は、 **constexpr**として宣言できます。

- **Constexpr**テンプレートの明示的な特殊化でも、 **constexpr**である必要はありません。

次の規則は、Visual Studio 2017 以降の**constexpr**関数に適用されます。

- **if**および**switch**文、ならびに **for**、range based for、 **while**、 **do while**を含むすべてのループ文を持つことができます。

- ローカル変数宣言が含まれている場合がありますが、変数は初期化する必要があり、リテラル型である必要があり、静的またはスレッドローカルにすることはできません。 ローカルで宣言された変数は、const である必要はなく、変化する可能性があります。

- Constexpr でない非静的メンバー関数は、暗黙的に const である必要はありません。

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> Visual Studio デバッガーでは、最適化されていないデバッグビルドをデバッグするときに、 **constexpr**関数がコンパイル時にブレークポイントを配置することで評価されているかどうかを判断できます。 ブレークポイントにヒットすると、実行時に関数が呼び出されます。  ヒットしなければ、コンパイル時に関数が呼び出されます。

## <a name="extern-constexpr"></a>extern constexpr

[/Zc: externConstexpr](../build/reference/zc-externconstexpr.md)コンパイラオプションにより、コンパイラは[外部リンケージ](../c-language/external-linkage.md)を**extern constexpr**を使用して宣言された変数に適用します。 以前のバージョンの Visual Studio では、既定では **/zc: externConstexpr**が指定されている場合、 **extern**キーワードが使用されている場合でも、visual studio は**constexpr**変数への内部リンケージを適用します。 **/Zc: externConstexpr**オプションは、Visual Studio 2017 更新プログラム15.6 以降で使用でき、既定ではオフになっています。 /Permissive-オプションでは、 **/zc: externConstexpr**は有効になりません。

## <a name="example"></a>例

次の例は、 **constexpr**変数、関数、およびユーザー定義型を示しています。 Main () の最後のステートメントでは、値がコンパイル時に認識される必要がないため、 **constexpr**メンバー関数 GetValue () はランタイム呼び出しです。

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
};

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
};

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
