---
title: constexpr (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- constexpr_cpp
dev_langs:
- C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f95f6c98138ff1eb52750c1b8593795ca28c784
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417998"
---
# <a name="constexpr-c"></a>constexpr (C++)

キーワード**constexpr**が c++ 11 で導入され、c++ 14 で改良されました。 意味*定数式*です。 同様に**const**、任意のコード値を変更しようとすると、コンパイラ エラーが発生するようには、変数に適用することができます。 異なり**const**、 **constexpr**関数にも適用でき、クラスのコンス トラクターです。 **constexpr**があること示し、値、または戻り値は、定数、可能な場合は、コンパイル時に計算されます。

A **constexpr** const の整数がなど、必要に応じてテンプレート引数や配列の宣言で場所で、整数値を使用することができます。 実行時ではなくコンパイル時に値を計算することができる場合、に、実行速度が向上しより少ないメモリを使用して、プログラムが役立ちます。

コンピューティングのコンパイル時定数の複雑さと、コンパイル時の潜在的な影響を制限するため、c++ 14 標準できる必要があります定数式に含まれる型に制限[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)です。

## <a name="syntax"></a>構文

```
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);
```

## <a name="parameters"></a>パラメーター

 *params*  
リテラルの型にする必要があるあり、自体をする必要がある 1 つまたは複数のパラメーターには、定数式があります。

## <a name="return-value"></a>戻り値


 Constexpr 変数または関数が返す必要があります、[リテラルの型](trivial-standard-layout-and-pod-types.md#literal_types)です。

## <a name="constexpr-variables"></a>constexpr 変数

 const 変数と constexpr 変数の主な違いとして、const 変数の初期化は実行時まで遅延できるのに対し、constexpr 変数はコンパイル時に初期化する必要があります。  すべての constexpr 変数は、const です。

- 変数を宣言できる**constexpr**が初期化され、リテラル型を持ち、します。 コンス トラクターによって初期化が実行される場合、コンス トラクターとして宣言されなければなりません**constexpr**です。

- 参照するオブジェクトが定数式で初期化され、初期化中に呼び出される暗黙の変換もすべて定数式である場合には、参照を constexpr と宣言することができます。

- すべての宣言、 **constexpr**変数または関数があります、 **constexpr**指定子。

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="constexpr_functions"></a> constexpr 関数

A **constexpr**関数は、1 つ使用コードで要求されたとき、コンパイル時戻り値を返すを計算できます。  ときに、引数が**constexpr**値、および利用側のコードを初期化する例については、コンパイル時に、戻り値が必要です、 **constexpr**変数や、非型テンプレート引数がコンパイル時定数を生成します。 以外で呼び出されると**constexpr**引数、またはその値がコンパイル時に必要ない場合に、正規関数と同様に実行時に値を生成します。  (この 2 重の動作を記述する必要がなくなります**constexpr**と非-**constexpr**同じ関数のバージョンです)。

A **constexpr**関数またはコンス トラクターは暗黙的に**インライン**です。

Constexpr 関数に、次の規則が適用されます。

- A **constexpr**関数がそのまま使用し、のみを返す必要があります[リテラル型](trivial-standard-layout-and-pod-types.md#literal_types)です。

- A **constexpr**関数が再帰的なをすることができます。

- できません[仮想](../cpp/virtual-cpp.md)です。 A、外側のクラスが仮想基底クラス コンス トラクターは constexpr として定義できません。

- として本文を定義することができます **= 既定**または **= delete**です。

- 本文は、いいえを含めることができます**goto**ステートメントまたは try ブロックします。

- 非 constexpr のテンプレートの明示的な特殊化として宣言できます**constexpr**:

- 明示的な特殊化、 **constexpr**テンプレートにもする必要はありません**constexpr**:

次の規則を適用する**constexpr**以降では、Visual Studio 2017 関数。

- 含まれて**場合**と**切り替える**ステートメント、およびすべてのループ ステートメントを含む**の**、範囲に基づく、**中**、および**操作の中に**です。
 
- ローカル変数の宣言を含めることがありますが、変数の初期化する必要があります、リテラルの型にする必要があります、および静的あるいはスレッド ローカルにすることはできません。 ローカルに宣言された変数は const を指定する必要はありませんし、変更可能性があります。

- Constexpr 静的でないメンバー関数は、暗黙的に const を指定する必要はありません。


```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
};
```

> [!TIP]
> 注意: Visual Studio デバッガーでビルド、デバッグ非最適化のデバッグとわかるかどうか、 **constexpr**中にブレークポイントを設定することによって関数がコンパイル時に評価されています。 ブレークポイントにヒットすると、実行時に関数が呼び出されます。  ヒットしなければ、コンパイル時に関数が呼び出されます。

## <a name="extern-constexpr"></a>extern constexpr

[/Zc:externConstexpr](../build/reference/zc-externconstexpr.md)コンパイラ オプションは、適用するコンパイラ[外部リンケージ]()を使用して宣言される変数に**extern constexpr**です。 以前のバージョンの Visual Studio で、既定の場合、または **/Zc:externConstexpr-** を指定すると、Visual Studio に内部リンケージを適用する**constexpr**変数場合であっても、 **extern**キーワードを使用します。 **/Zc:externConstexpr**オプションは、Visual Studio 2017 更新 15.6 以降を使用します。 既定では無効になっているとします。 /Permissive-option に/Zc:externConstexpr が有効にできません。

## <a name="example"></a>例

 次の例は**constexpr**変数、関数およびユーザー定義の型。 なお、main() の最後のステートメントで、 **constexpr**値がコンパイル時に既知である必要はないために、メンバー関数 GetValue() は実行時の呼び出しです。

```cpp
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

// Compile time computation of array length
template<typename T, int N>
constexpr int length(const T(&ary)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n*fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue()
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    //foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    //Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    //Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;

}

```

## <a name="requirements"></a>要件

Visual Studio 2015

## <a name="see-also"></a>関連項目

- [宣言と定義](../cpp/declarations-and-definitions-cpp.md)
- [const](../cpp/const-cpp.md)
