---
title: テンプレート (C++)
ms.date: 12/27/2019
f1_keywords:
- template_cpp
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
ms.openlocfilehash: e47f00c7e387974c7d1756cf3ee3865f892e6951
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032344"
---
# <a name="templates-c"></a>テンプレート (C++)

テンプレートは、C++ のジェネリック プログラミングの基礎となります。 C++ では、厳密に型指定された言語として、すべての変数が、プログラマによって明示的に宣言されるか、コンパイラによって推測される特定の型を持つ必要があります。 ただし、多くのデータ構造とアルゴリズムは、操作している型に関係なく同じように見えます。 テンプレートを使用すると、クラスまたは関数の操作を定義し、ユーザーがそれらの操作を処理する具体的な型を指定できます。

## <a name="defining-and-using-templates"></a>テンプレートの定義と使用

テンプレートは、ユーザーがテンプレート パラメーターに指定した引数に基づいて、コンパイル時に通常の型または関数を生成するコンストラクトです。 たとえば、次のように関数テンプレートを定義できます。

```cpp
template <typename T>
T minimum(const T& lhs, const T& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

上記のコードは、単一の型パラメーター *T*を持つジェネリック関数のテンプレートを記述し、戻り値と呼び出しパラメーター (lhs と rhs) がこの型のすべてです。 型パラメーターには好きな名前を付けることができますが、通常は大文字で 1 文字が最も多く使用されます。 *T*はテンプレート パラメーターです。**typename**キーワードは、このパラメーターが型のプレースホルダーであることを示します。 関数が呼び出されると、コンパイラは、ユーザーによって指定`T`されるか、コンパイラによって推定される具象型引数で、すべてのインスタンスを置き換えます。 コンパイラがテンプレートからクラスまたは関数を生成するプロセスは、*テンプレートのインスタンス化*と呼ばれます。`minimum<int>`は、テンプレート`minimum<T>`のインスタンス化です。

他の場所では、int に特化したテンプレートのインスタンスを宣言できます get_b get_a。

```cpp
int a = get_a();
int b = get_b();
int i = minimum<int>(a, b);
```

ただし、これは関数テンプレートであり、コンパイラは引数*a*と*b*から`T`型を推測できるため、通常の関数と同じように呼び出すことができます。

```cpp
int i = minimum(a, b);
```

コンパイラは、その最後のステートメントを検出すると、テンプレート内の*T*の出現箇所をすべて**int**に置き換える新しい関数を生成します。

```cpp
int minimum(const int& lhs, const int& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

コンパイラが関数テンプレートで型の推論を実行する方法の規則は、通常の関数の規則に基づいています。 詳細については、「[関数テンプレート呼び出しのオーバーロード解決](../cpp/overload-resolution-of-function-template-calls.md)」を参照してください。

## <a name="type-parameters"></a><a id="type_parameters"></a>型パラメーター

上記の`minimum`テンプレートでは、型パラメーター *T*は、const および参照修飾子が追加される関数呼び出しパラメーターで使用されるまで、何らかの修飾されないことに注意してください。

型パラメータの数に実質的な制限はありません。 複数のパラメータをカンマで区切ります。

```cpp
template <typename T, typename U, typename V> class Foo{};
```

キーワード**クラス**は、このコンテキストで**の型名**と同じです。 前の例を次のように表現できます。

```cpp
template <class T, class U, class V> class Foo{};
```

省略記号演算子 (..) を使用して、任意の数の 0 個以上の型パラメーターを受け取るテンプレートを定義できます。

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
```

組み込み型またはユーザー定義型は、型引数として使用できます。 たとえば、標準ライブラリで[std::vector](../standard-library/vector-class.md)を使用して **、int**型、**ダブル**変数、[標準変数::文字列](../standard-library/basic-string-class.md)型、`MyClass`変数、**定数**`MyClass` `MyClass&`*、などなどを格納できます。 テンプレートを使用する場合の主な制限は、型引数が型パラメーターに適用される操作をサポートする必要があるというものです。 たとえば、次の例のように`minimum`呼`MyClass`び出すとします。

```cpp
class MyClass
{
public:
    int num;
    std::wstring description;
};

int main()
{
    MyClass mc1 {1, L"hello"};
    MyClass mc2 {2, L"goodbye"};
    auto result = minimum(mc1, mc2); // Error! C2678
}
```

演算子にオーバーロードが指定`MyClass`されていないため、コンパイラ エラーが**<** 生成されます。

特定のテンプレートの型引数がすべて同じオブジェクト階層に属しているという要件はありませんが、そのような制限を適用するテンプレートを定義できます。 オブジェクト指向の手法をテンプレートと組み合わせることができます。たとえば、派生* をベクター\<ベース\*>に格納できます。    引数はポインタでなければならないことに注意してください

```cpp
vector<MyClass*> vec;
   MyDerived d(3, L"back again", time(0));
   vec.push_back(&d);

   // or more realistically:
   vector<shared_ptr<MyClass>> vec2;
   vec2.push_back(make_shared<MyDerived>());
```

の要素に対`std::vector`して標準ライブラリ コンテナが課す基本的`T`な要件`T`は、コピー代入可能でコピー構築可能な要素です。

## <a name="non-type-parameters"></a>非型パラメーター

C# や Java などの他の言語のジェネリック型とは異なり、C++ テンプレートは*非型パラメーター*をサポートしています。 たとえば、標準ライブラリの[std::array](../standard-library/array-class-stl.md)クラスに似た次の例のように、配列の長さを指定する定数整数値を指定できます。

```cpp
template<typename T, size_t L>
class MyArray
{
    T arr[L];
public:
    MyArray() { ... }
};
```

テンプレート宣言の構文に注意してください。 値`size_t`はコンパイル時にテンプレート引数として渡され **、const**または**constexpr**式でなければなりません。 次のように使用します。

```cpp
MyArray<MyClass*, 10> arr;
```

ポインターや参照を含む他の種類の値は、非型パラメーターとして渡すことができます。 たとえば、関数または関数オブジェクトへのポインターを渡して、テンプレート コード内の操作をカスタマイズできます。

### <a name="type-deduction-for-non-type-template-parameters"></a>非型テンプレート パラメーターの型の控除

Visual Studio 2017 以降では **、/std:c++17**モードでは、コンパイラは**auto**で宣言された非型テンプレート引数の型を推測します。

```cpp
template <auto x> constexpr auto constant = x;

auto v1 = constant<5>;      // v1 == 5, decltype(v1) is int
auto v2 = constant<true>;   // v2 == true, decltype(v2) is bool
auto v3 = constant<'a'>;    // v3 == 'a', decltype(v3) is char
```

## <a name="templates-as-template-parameters"></a><a id="template_parameters"></a>テンプレート パラメーターとしてのテンプレート

テンプレートはテンプレート パラメーターにできます。 この例では、MyClass2 には、型名パラメーター *T*とテンプレート パラメーター *Arr*の 2 つのテンプレート パラメーターがあります。

```cpp
template<typename T, template<typename U, int I> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
    U u; //Error. U not in scope
};
```

*Arr*パラメータ自体には本体がないため、パラメータ名は不要です。 実際、の本体から*Arr*の型名またはクラス パラメータ名を参照するとエラーになります`MyClass2`。 このため *、Arr*の型パラメータ名は、次の例のように省略できます。

```cpp
template<typename T, template<typename, int> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
};
```

## <a name="default-template-arguments"></a>既定のテンプレート引数

クラステンプレートと関数テンプレートには、デフォルトの引数を指定できます。 テンプレートに既定の引数がある場合は、テンプレートを使用するときに、指定されていないままにしておくことができます。 たとえば、std::vector テンプレートには、アロケーターのデフォルト引数があります。

```cpp
template <class T, class Allocator = allocator<T>> class vector;
```

ほとんどの場合、デフォルトの std::allocator クラスは受け入れられるので、次のようなベクトルを使用します。

```cpp
vector<int> myInts;
```

しかし、必要に応じて、次のようなカスタムアロケーターを指定できます。

```cpp
vector<int, MyAllocator> ints;
```

テンプレート引数が複数ある場合、最初の既定の引数の後は、すべての引数に既定の引数が必要です。

パラメータがすべてデフォルトになっているテンプレートを使用する場合は、空の山かっこを使用します。

```cpp
template<typename A = int, typename B = double>
class Bar
{
    //...
};
...
int main()
{
    Bar<> bar; // use all default type arguments
}
```

## <a name="template-specialization"></a>テンプレートの特殊化

テンプレートがどの型にもまったく同じコードを定義できない場合もあります。 たとえば、型引数がポインター、std::wstring、または特定の基本クラスから派生した型である場合にのみ実行されるコード パスを定義できます。  そのような場合は、特定のタイプに対するテンプレートの*特殊化*を定義できます。 ユーザーがその型を使用してテンプレートをインスタンス化すると、コンパイラは特殊化を使用してクラスを生成し、その他のすべての型に対して、より一般的なテンプレートを選択します。 すべてのパラメータが特殊化されている専門分野は*完全な特殊化です*。 一部のパラメータだけが特殊化されている場合は、*部分特化*と呼ばれます。

```cpp
template <typename K, typename V>
class MyMap{/*...*/};

// partial specialization for string keys
template<typename V>
class MyMap<string, V> {/*...*/};
...
MyMap<int, MyClass> classes; // uses original template
MyMap<string, MyClass> classes2; // uses the partial specialization
```

テンプレートは、特殊化された各型パラメーターが一意である限り、任意の数の特殊化を持つことができます。 クラス テンプレートのみが、部分的に特化されている場合があります。 テンプレートの完全な特殊化と部分的な特殊化はすべて、元のテンプレートと同じ名前空間で宣言する必要があります。

詳細については、「[テンプレートの特化](../cpp/template-specialization-cpp.md)」を参照してください。
