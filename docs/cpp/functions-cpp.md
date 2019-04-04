---
title: 関数 (C++)
ms.date: 11/19/2018
helpviewer_keywords:
- defaults, arguments
- function definitions
- function definitions, about function definitions
- default arguments
- declarators, functions
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
ms.openlocfilehash: aafd3be3b27fbe134b380a29083b4ca36177e702
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176485"
---
# <a name="functions-c"></a>関数 (C++)

関数とは、何らかの操作を実行するコードのブロックです。 関数には、呼び出し元が関数に引数を渡すのに使用する入力パラメーターを必要に応じて定義できます。 関数は、必要に応じて値を出力として返すことができます。 関数は、一般的な操作を 1 つの再利用可能なブロックでカプセル化するのに役立ちます。関数には、その動作を明確に説明する名前を付けることが理想的です。 次の関数が呼び出し元から 2 つの整数に受け取り; その合計を返します *、* と*b*は*パラメーター*型の**int**します。

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

関数を呼び出すことができます、または*と呼ばれる*、プログラム内の場所の任意の数から。 関数に渡される値は、*引数*、関数定義でパラメーターの型と互換性のある型を持つ必要があります。

```cpp
int main()
{
    int i = sum(10, 32);
    int j = sum(i, 66);
    cout << "The value of j is" << j << endl; // 108
}
```

関数の長さに事実上制限はありませんが、優れた設計では、適切に定義された 1 つのタスクを実行する関数を目標にします。 複雑なアルゴリズムは、可能な場合は常に、理解しやすい簡潔な関数に分割することをお勧めします。

クラス スコープで定義されている関数はメンバー関数と呼ばれます。 C++ では、他の言語とは異なり、名前空間スコープ (暗黙的なグローバル名前空間を含む) でも関数を定義できます。 このような関数が呼び出される*の free 関数*または*非メンバー関数*。 標準ライブラリで広く使用されています。

関数があります*オーバー ロードされた*数や仮パラメーターの型が異なる場合、同じ名前を共有関数の異なるバージョンのことを意味する可能性があります。 詳細については、[関数のオーバー ロード](../cpp/function-overloading.md)を参照してください。

## <a name="parts-of-a-function-declaration"></a>関数宣言部分

最小限の関数*宣言*戻り値の型、関数名、およびパラメーター リスト (空にすることがあります)、コンパイラに追加の指示を提供する省略可能なキーワードとから成ります。 次の例では、関数の宣言を示します。

```cpp
int sum(int a, int b);
```

関数定義は、宣言だけでなく、*本文*、中かっこの間のすべてのコードは。

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

関数宣言の後にはセミコロンが続きます。1 つのプログラムの複数個所で、関数宣言がなされる場合があります。 関数宣言は、翻訳単位ごとに関数に対する呼び出しの前に記述される必要があります。 関数定義は、単一定義規則 (ODR) に従い、プログラム内で 1 回だけ記述する必要があります。

関数宣言に必要な部分は次のとおりです。

1. 関数が返す値の型を指定するには、戻り値の型または**void**値が返されない場合。 C++ 11 で**自動**は return ステートメントから型を推論するようにコンパイラに指示する有効な戻り値の型。 C++14 では、"decltype(auto)" も使用できます。 詳細については、以下の「戻り値の型の型推論」を参照してください。

1. 関数名は文字かアンダースコアで始まる必要があり、スペースを含めることはできません。 一般に、標準ライブラリ関数名で先頭にアンダースコアがあるものは、プライベート メンバー関数であるか、コードでの使用が意図されていない非メンバー関数であることを意味しています。

1. パラメーター リストとは、中かっこに挟まれ、コンマで区切られた 0 個以上のパラメーターのセットです。パラメーターで、型を指定し、関数本体内で値にアクセスする際に使用するローカル名も必要に応じて指定できます。

関数宣言の省略可能な部分は次のとおりです。

1. `constexpr`。関数の戻り値がコンパイル時に計算できる定数値であることを示します。

    ```cpp
    constexpr float exp(float x, int n)
    {
        return n == 0 ? 1 :
            n % 2 == 0 ? exp(x * x, n / 2) :
            exp(x * x, (n - 1) / 2) * x;
    };
    ```

1. そのリンケージ指定**extern**または**静的**します。

    ```cpp
    //Declare printf with C linkage.
    extern "C" int printf( const char *fmt, ... );

    ```

   詳細については、[プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)を参照してください。

1. **インライン**に関数を呼び出すたびに関数コード自体を置き換えるコンパイラに指示します。 パフォーマンスが重要なコード セクションで関数が迅速に実行され、繰り返し呼び出されるシナリオでは、インライン展開を使用すると、パフォーマンスが向上します。

    ```cpp
    inline double Account::GetBalance()
    {
        return balance;
    }
    ```

   詳細については、[インライン関数](../cpp/inline-functions-cpp.md)を参照してください。

1. A`noexcept`式で、関数が例外をスローできるかどうかを指定します。 次の例では、関数は例外をスローしない場合、`is_pod`式に評価される**true**します。

    ```cpp
    #include <type_traits>

    template <typename T>
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}
    ```

   詳細については、[noexcept](../cpp/noexcept-cpp.md)を参照してください。

1. (メンバー関数のみ)Cv 修飾子、関数は、かどうかを指定する**const**または**揮発性**します。

1. (メンバー関数のみ)**仮想**、 `override`、または`final`します。 **仮想**関数を派生クラスでオーバーライドできることを示します。 `override` は、派生クラス内の関数が仮想関数をオーバーライドすることを意味します。 `final` は、いかなる派生クラス内でも関数がオーバーライドされないことを意味します。 詳細については、[仮想関数](../cpp/virtual-functions.md)を参照してください。

1. (メンバー関数のみ)**静的**適用関数が、関数がクラスのすべてのオブジェクト インスタンスに関連付けられていないことを意味するメンバー。

1. (非静的メンバー関数のみ)Ref 修飾子、ときに選択する関数のオーバー ロードをコンパイラに指定する暗黙的オブジェクト パラメーター (\*この) が左辺値参照と右辺値参照。 詳細については、[関数のオーバー ロード](function-overloading.md#ref-qualifiers)を参照してください。

次の図では、関数定義の一部を示しています。 網かけされた部分は関数本体です。

![関数定義部分](../cpp/media/vc38ru1.gif "関数定義部分") <br/>
関数定義部分

## <a name="function-definitions"></a>関数定義

A*関数の定義*宣言と関数本体の中かっこで囲まれた変数の宣言、ステートメントと式を含むで構成されます。 次の例では、完全な関数の定義を示しています。

```cpp
    int foo(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       if(strcmp(s, "default") != 0)
       {
            value = mc.do_something(i);
       }
       return value;
    }
```

本体内で宣言された変数は、ローカル変数またはローカルと呼ばれます。 これらは関数の終了時にスコープ外に出るため、関数がローカルに参照を返すことはありません。

```cpp
    MyClass& boom(int i, std::string s)
    {
       int value {i};
       MyClass mc;
       mc.Initialize(i,s);
       return mc;
    }
```

## <a name="const-and-constexpr-functions"></a>const 変数と constexpr 関数

メンバー関数として宣言できます**const**クラスのデータ メンバーの値を変更する関数が許可されないことを指定します。 メンバー関数として宣言することで**const**、役立つようにコンパイラで強制*const の正確*します。 だれかが誤って、として宣言された関数を使用して、オブジェクトを変更するにはかどうか**const**、コンパイラ エラーが発生します。 詳細については、[const](const-cpp.md)を参照してください。

関数として宣言`constexpr`コンパイル時に決定される値を生成できますが可能性があります。 Constexpr 関数は一般に通常の関数よりも高速実行します。 詳細については、[constexpr](constexpr-cpp.md)を参照してください。

## <a name="function-templates"></a>関数テンプレート

関数テンプレートはクラス テンプレートに似ており、テンプレート引数に基づく具体的な関数を生成します。 多くの場合、テンプレートは型の引数を推測できるので、型の引数を明示的に指定する必要はありません。

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs;
}

auto a = Add2(3.13, 2.895); // a is a double
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string
```

詳細については、次を参照してください[関数テンプレート。](../cpp/function-templates.md)

## <a name="function-parameters-and-arguments"></a>関数のパラメーターと引数

関数にはコンマで区切られた 0 個以上の型のパラメーター リストがあり、それぞれに関数本体内でアクセスする際に使用する名前があります。 関数テンプレートで、追加の型や値のパラメーターを指定できます。 呼び出し元は引数を渡します。引数は、パラメーター リストと互換性のある型を持つ具体的な値です。

既定では、引数は関数に値渡しで渡されます。このことは、関数が渡されるオブジェクトのコピーを受け取ることを意味します。 大きなオブジェクトの場合、コピーの作成は負荷が高く、必ずしも必要ではありません。 (具体的には左辺値参照) を参照渡しで渡される引数には、パラメーターに量指定子、参照を追加します。

```cpp
void DoSomething(std::string& input){...}
```

関数が参照によって渡される引数を変更すると、ローカル コピーではなく元のオブジェクトが変更されます。 関数がこのような引数を変更しないようにするには、パラメーターを const& として修飾します。

```cpp
void DoSomething(const std::string& input){...}
```

**C++ 11:** 右辺値参照または左辺値参照によって渡される引数を明示的に処理するには、ユニバーサルの参照を示すために、パラメーターで二重アンパサンドを使用します。

```cpp
void DoSomething(const std::string&& input){...}
```

1 つのキーワードで宣言された関数**void**パラメーターの宣言でリスト引数を受け取らない限り、キーワードとして**void**が最初と引数宣言リストのメンバーだけです。 型の引数**void**別の場所の一覧でエラーを生成します。 例えば:

```cpp

// OK same as GetTickCount()
long GetTickCount( void );
```

指定することはできませんが、注意してください、 **void**を除く引数をますが、ここでは、型から派生した**void** (へのポインターなど**void** の配列と **。void**) 引数宣言リストを任意の場所に表示できます。

### <a name="default-arguments"></a>既定の引数

関数のシグネチャの最後のパラメーターに既定の引数を割り当てることができます。このことは、他の値を指定する必要がない場合は、関数を呼び出すときに呼び出し元が引数を省略できることを意味します。

```cpp
int DoSomething(int num,
    string str,
    Allocator& alloc = defaultAllocator)
{ ... }

// OK both parameters are at end
int DoSomethingElse(int num,
    string str = string{ "Working" },
    Allocator& alloc = defaultAllocator)
{ ... }

// C2548: 'DoMore': missing default parameter for parameter 2
int DoMore(int num = 5, // Not a trailing parameter!
    string str,
    Allocator& = defaultAllocator)
{...}
```

詳細については、[既定の引数](../cpp/default-arguments.md)を参照してください。

## <a name="function-return-types"></a>関数の戻り値の型

関数が別の関数または組み込みの配列を返さないただし、これらの型へのポインターを返すまたは*ラムダ*、関数オブジェクトが作成されます。 ような場合、関数は、スコープ内の任意の型の値を返す可能性がありますまたは値を返すありません、ただし場合、戻り値の型が**void**します。

### <a name="trailing-return-types"></a>後続の戻り値の型

"通常" の戻り値の型は、関数のシグネチャの左側にあります。 A*後続の戻り値の型*署名の右端にあるし、前に、-> 演算子。 後続の戻り値の型は、関数テンプレートにおいて、戻り値の種類がテンプレート パラメーターに依存する場合、特に便利です。

```cpp
template<typename Lhs, typename Rhs>
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)
{
    return lhs + rhs;
}
```

ときに**自動**される後続の戻り値の型と共に、それだけのプレースホルダとして使用、decltype 式によって生成されるのとは自体は型の推論を実行します。

## <a name="function-local-variables"></a>関数のローカル変数

関数本体内で宣言されている変数と呼ばれる、*ローカル変数*または単に*ローカル*します。 非静的ローカルは関数本体内でのみ認識され、スタックで宣言されている場合は、関数の終了時にスコープ外に出ます。 ローカル変数を作成して値渡しで値を返す場合、通常、コンパイラで戻り値の最適化を実行し、不要なコピー操作を回避できます。 ローカル変数を参照渡しで返す場合、呼び出し元がその参照を使用するために実行する試行がローカルの破棄後に発生するため、コンパイラは警告を発行します。

C++ では、ローカル変数を "静的" として宣言することがあります。 変数は関数本体内でのみ認識されますが、関数のすべてのインスタンスに対して変数の 1 つのコピーが存在します。 ローカルな静的オブジェクトは、`atexit` によって指定された終了時に破棄されます。 プログラムの制御フローが宣言をバイパスしたために静的オブジェクトが構築されなかった場合、そのオブジェクトの破棄は試みられません。

##  <a name="type_deduction"></a> 戻り値の型 (c++ 14) の型の推論

C++ 14 で使用できます**自動**を後続の戻り値の型を提供しなくても、関数本体からの戻り値の型を推測するようコンパイラに指示します。 なお**自動**値渡しの戻り値を常にあると推測します。 `auto&&` を使用すると、参照を推測するようにコンパイラに指示できます。

この例で**自動**lhs と rhs の合計の非定数の値のコピーとして推測されます。

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs; //returns a non-const object by value
}
```

なお**自動**推測した型の const 性は保持されません。 Const 性または ref 性、引数を保持するために必要な戻り値を返す関数を転送するには、使用することができます、 **decltype (auto)** キーワードを使用して、 **decltype**推論規則を入力し、すべての型情報を保持します。 **decltype (auto)** 、左側にある通常の戻り値または後続の戻り値として使用する可能性があります。

次の例では、(コードに基づく[N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html))、表示**decltype (auto)** の戻り値の型がテンプレートになるまでの関数の引数の完全転送を有効にするために使用されています。インスタンス化します。

```cpp
template<typename F, typename Tuple = tuple<T...>, int... I>
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)
{
    return std::forward<F>(f)(std::get<I>(std::forward<Tuple>(args))...);
}

template<typename F, typename Tuple = tuple<T...>,
    typename Indices = make_index_sequence<tuple_size<Tuple>::value >>
   decltype( auto)
    apply(F&& f, Tuple&& args)
{
    return apply_(std::forward<F>(f), std::forward<Tuple>(args), Indices());
}
}
```

## <a name="multi_val"></a> 関数から複数の値を返す

関数から 1 つ以上の値を返すのさまざまな方法はあります。

1. 名前付きのクラスまたは構造体オブジェクトの値をカプセル化します。 呼び出し元に表示される、クラスまたは構造体の定義が必要です。

    ```cpp
    #include <string>
    #include <iostream>

    using namespace std;

    struct S
    {
        string name;
        int num;
    };

    S g()
    {
        string t{ "hello" };
        int u{ 42 };
        return { t, u };
    }

    int main()
    {
        S s = g();
        cout << s.name << " " << s.num << endl;
        return 0;
    }
    ```

1. Std::tuple または std::pair のオブジェクトを返します。

    ```cpp
    #include <tuple>
    #include <string>
    #include <iostream>

    using namespace std;

    tuple<int, string, double> f()
    {
        int i{ 108 };
        string s{ "Some text" };
        double d{ .01 };
        return { i,s,d };
    }

    int main()
    {
        auto t = f();
        cout << get<0>(t) << " " << get<1>(t) << " " << get<2>(t) << endl;

        // --or--

        int myval;
        string myname;
        double mydecimal;
        tie(myval, myname, mydecimal) = f();
        cout << myval << " " << myname << " " << mydecimal << endl;

        return 0;
    }
    ```

1. **Visual Studio 2017 バージョン 15.3 以降**(で使用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 構造化バインドを使用します。 構造化バインドの利点は、戻り値を格納する変数が初期化される、宣言されると同時に大幅に効率も指定できます。 次のステートメントで`auto[x, y, z] = f();`--角かっこを紹介し、関数全体のブロックのスコープ内の名前を初期化します。

    ```cpp
    #include <tuple>
    #include <string>
    #include <iostream>

    using namespace std;

    tuple<int, string, double> f()
    {
        int i{ 108 };
        string s{ "Some text" };
        double d{ .01 };
        return { i,s,d };
    }
    struct S
    {
        string name;
        int num;
    };

    S g()
    {
        string t{ "hello" };
        int u{ 42 };
        return { t, u };
    }

    int main()
    {
        auto[x, y, z] = f(); // init from tuple
        cout << x << " " << y << " " << z << endl;

        auto[a, b] = g(); // init from POD struct
        cout << a << " " << b << endl;
        return 0;
    }
    ```

1. 戻り値自体だけでなく、「値を返すできます」関数を変更したり、呼び出し元が提供するオブジェクトの値を初期化するために、参照渡しを使用するパラメーターの任意の数を定義することで。 詳細については、[参照型関数の引数](reference-type-function-arguments.md)を参照してください。

## <a name="function-pointers"></a>関数ポインター

C++ では、C 言語と同じ方法で、関数ポインターをサポートします。 ただし、通常、よりタイプ セーフな代替手段で関数オブジェクトが使用されます。

推奨されます**typedef**関数ポインター型を返す関数を宣言する場合、関数ポインター型のエイリアスの宣言に使用します。  次に例を示します。

```cpp
typedef int (*fp)(int);
fp myFunction(char* s); // function returning function pointer
```

このように記述していない場合でも、識別子 (上の例では `fp`) を関数名と引数リストで置き換えることで、関数ポインターの宣言構文から関数宣言の正しい構文を次のように導き出すことはできます。

```cpp
int (*myFunction(char* s))(int);
```

この宣言は、上記の typedef を使用した宣言と同等です。

## <a name="see-also"></a>関連項目

[関数のオーバーロード](../cpp/function-overloading.md)<br/>
[可変個の引数リストを取る関数](../cpp/functions-with-variable-argument-lists-cpp.md)<br/>
[明示的に既定された関数および削除された関数](../cpp/explicitly-defaulted-and-deleted-functions.md)<br/>
[関数の引数依存名の参照 (Koenig 参照)](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)<br/>
[既定の引数](../cpp/default-arguments.md)<br/>
[インライン関数](../cpp/inline-functions-cpp.md)
