---
title: テンプレート (C++)
ms.date: 11/04/2016
f1_keywords:
- template_cpp
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
ms.openlocfilehash: f1532b5aa4ea712feab08b49b7c035187ca0d042
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330493"
---
# <a name="templates-c"></a>テンプレート (C++)

テンプレートは、C++ での汎用のプログラミングの基礎です。 厳密に型指定された言語として C++ にはすべての変数を明示的にプログラマが宣言されている、またはコンパイラが推論し、特定の種類を持つ必要があります。 ただし、多くのデータ構造とアルゴリズムの種類にかかわらず同じに見えます。 これらの操作の種類のクラスや関数の操作を定義し、ユーザーがどのような具象型を指定できるテンプレートの有効化に取り組む必要があります。

## <a name="defining-and-using-templates"></a>定義とテンプレートの使用

テンプレートは、ユーザーはテンプレートのパラメーターを提供する引数に基づいた、コンパイル時に、通常の型または関数を生成するコンストラクトです。 たとえば、このような関数テンプレートを定義できます。

```cpp
template <typename T>
T minimum(const T& lhs, const T& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

上記のコードが 1 つの型パラメーターを持つジェネリック関数のテンプレートについて説明します*T*値を返し、パラメーター (lhs と rhs) の呼び出し元はこの型のすべて。 型パラメーターは、最も一般的に使用すると同様が、規則の 1 つの大文字の文字で何も名前をことができます。 *T*テンプレート パラメーターは、 **typename**キーワードは、このパラメーターは、型のプレース ホルダー。 コンパイラでのすべてのインスタンスを交換して、関数が呼び出されると、`T`されるか、ユーザーが指定したコンパイラによって推測された具象型引数を持つ。 コンパイラは、クラスを生成しますまたは、テンプレートからの関数と呼びますプロセス*テンプレートのインスタンス化*;。`minimum<int>`テンプレートをインスタンス化は、`minimum<T>`します。

他の場所で、ユーザーが int の特化したテンプレートのインスタンスを宣言できます。Get_a() と get_b() が int を返す関数であると仮定します。

```cpp
int a = get_a();
int b = get_b();
int i = minimum<int>(a, b);
```

ただし、これが関数テンプレートと、コンパイラの型を推測`T`引数から *、* と*b*、通常の関数と同じように呼び出すことができます。

```cpp
int i = minimum(a, b);
```

コンパイラには、その最後のステートメントが検出されると、新しい関数を生成 すべてのオカレンス*T*テンプレートでに置き換えられます**int**:

```cpp
int minimum(const int& lhs, const int& rhs)
{
    return lhs < rhs ? lhs : rhs;
}
```

関数テンプレートで、コンパイラが型の推論を実行する方法のルールは、通常の関数の規則に基づいています。 詳細については、次を参照してください。[オーバー ロード解決の関数テンプレート呼び出し](../cpp/overload-resolution-of-function-template-calls.md)します。

## <a id="type_parameters"></a> 型パラメーター

`minimum`なお、上記のテンプレート型パラメーター *T*定数と参照修飾子が追加される関数呼び出しのパラメーターで使用されるまで任意の方法では修飾されません。

型パラメーターの数に事実上制限はありません。 複数のパラメーターをコンマで区切ります。

```cpp
template <typename T, typename U, typename V> class Foo{};
```

キーワード**class**と等価**typename**このコンテキストでします。 前の例として表すことができます。

```cpp
template <class T, class U, class V> class Foo{};
```

省略記号演算子 (...) を使用して、任意の数の 0 個以上の型パラメーターを受け取るテンプレートを定義できます。

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
```

任意の組み込みまたはユーザー定義型は、型引数として使用できます。 Int、double 型、文字列を格納する標準ライブラリで std::vector を使用するなど、MyClass、MyClass const *、MyClass (& a)。 テンプレートを使用する場合は、重要な制限は、型引数が型パラメーターに適用されるすべての操作をサポートする必要があります。 たとえば、最小値と呼んで MyClass を使用して、この例のように。

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

MyClass がのオーバー ロードを提供しないために、コンパイラ エラーが発生、< 演算子。

このような制限を適用するテンプレートを定義できますが、特定のテンプレートのすべての型引数が、同じオブジェクトの階層に属する固有の要件はありません。 テンプレートでオブジェクト指向の手法を組み合わせることができます。たとえば、格納できます派生 * ベクターに\<ベース\*>。    引数はポインターである必要がありますに注意してください。

```cpp
vector<MyClass*> vec;
   MyDerived d(3, L"back again", time(0));
   vec.push_back(&d);

   // or more realistically:
   vector<shared_ptr<MyClass>> vec2;
   vec2.push_back(make_shared<MyDerived>());
```

ベクターと他の標準ライブラリ コンテナーの要素に加えたの基本的な要件`T`です`T`コピー代入とコピー構築します。

## <a name="non-type-parameters"></a>非型パラメーター

C# や Java などの他の言語でジェネリック型とは異なりは、C++ テンプレートは、値パラメーターとも呼ばれます。 非型パラメーターをサポートします。 たとえば、この例では、標準ライブラリで std::array クラスと同様に、配列の長さを指定する定数整数値を行うことができます。

```cpp
template<typename T, size_t L>
class MyArray
{
    T arr[L];
public:
    MyArray() { ... }
};
```

テンプレート宣言の構文に注意してください。 Size_t 値では、コンパイル時にテンプレート引数として渡され、定数または式を constexpr にする必要があります。 次のように使用します。

```cpp
MyArray<MyClass*, 10> arr;
```

非型パラメーターとしてでその他のポインターと参照を含む値を渡すことができます。 たとえば、関数または関数オブジェクト、テンプレート コード内でいくつかの操作をカスタマイズするにポインターに渡します。

## <a id="template_parameters"></a> テンプレート パラメーターとしてテンプレート

テンプレートには、テンプレート パラメーターを指定できます。 この例で MyClass2 が 2 つのテンプレート パラメーター: typename パラメーター *T*とテンプレート パラメーター *Arr*:

```cpp
template<typename T, template<typename U, int I> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
    U u; //Error. U not in scope
};
```

*Arr*パラメーター自体には、本文がない、そのパラメーター名は必要ありません。 実際を参照するとエラーが*Arr*の typename またはクラス内のパラメーター名からの本文`MyClass2`します。 このため、 *Arr*のこの例で示すように、型パラメーター名を省略できます。

```cpp
template<typename T, template<typename, int> class Arr>
class MyClass2
{
    T t; //OK
    Arr<T, 10> a;
};
```

## <a name="default-template-arguments"></a>既定のテンプレート引数

クラスと関数テンプレートは、既定の引数でことができます。 テンプレートのままにすることができます、既定の引数がある使用すると、指定されません。 たとえば、std::vector テンプレートでは、アロケーターの既定の引数があります。

```cpp
template <class T, class Allocator = allocator<T>> class vector;
```

ほとんどの場合は、このようなベクトルを使用するようで既定の std::allocator クラスは、許容されます。

```cpp
vector<int> myInts;
```

かどうか必要に応じて指定することがカスタム アロケーターは、このような。

```cpp
vector<int, MyAllocator> ints;
```

テンプレート引数が複数ある場合、最初の既定の引数の後は、すべての引数に既定の引数が必要です。

パラメーターを持つ内容はすべて既定のテンプレートを使用する場合は、空の山かっこを使用します。

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

場合によっては、不可能であるか、または任意の型に対して正確に同じコードを定義するテンプレートに望ましくはありません。 たとえば、型引数がポインター、または、std::wstring または特定の基本クラスから派生した型の場合にのみに実行されるコード パスを定義することもできます。  このような場合を定義できますを*特殊化*の特定の種類のテンプレート。 ユーザーは、その型でテンプレートをインスタンス化、ときにコンパイラは、クラスを生成する、特殊化を使用し、他のすべての種類では、コンパイラがより一般的なテンプレートを選択します。 すべてのパラメーターが特殊化された特殊化は*特殊化を完了*します。 呼び出されたパラメーターの一部が特殊化された場合のみ、*部分的特殊化*します。

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

テンプレートには、それぞれの特殊化された型パラメーターが一意に任意の数の特殊化のことができます。 クラス テンプレートのみを部分的に特殊化することがあります。 テンプレートのすべての完全および部分的な特殊化は、元のテンプレートと同じ名前空間で宣言する必要があります。

詳細については、次を参照してください。[テンプレートの特殊化](../cpp/template-specialization-cpp.md)します。