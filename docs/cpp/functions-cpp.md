---
title: 関数 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/25/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- defaults, arguments
- function definitions
- function definitions, about function definitions
- default arguments
- declarators, functions
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 720147992540b53c51e731db361cd9946a7a5313
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418417"
---
# <a name="functions-c"></a>関数 (C++)

関数とは、何らかの操作を実行するコードのブロックです。 関数には、呼び出し元が関数に引数を渡すのに使用する入力パラメーターを必要に応じて定義できます。 関数は、必要に応じて値を出力として返すことができます。 関数は、一般的な操作を 1 つの再利用可能なブロックでカプセル化するのに役立ちます。関数には、その動作を明確に説明する名前を付けることが理想的です。 次の関数の呼び出し元から 2 つの整数を受け付けるその合計を返します。`a`と`b`は*パラメーター*型の**int**です。

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

関数を呼び出すことができます、または*と呼ばれる*プログラム内の場所の任意の数からです。 関数に渡される値は、*引数*、関数定義のパラメーターの型と互換性のある型を持つ必要があります。

```cpp
int main()
{
    int i = sum(10, 32);
    int j = sum(i, 66);
    cout << "The value of j is" << j << endl; // 108
}
```

関数の長さに事実上制限はありませんが、優れた設計では、適切に定義された 1 つのタスクを実行する関数を目標にします。 複雑なアルゴリズムは、可能な場合は常に、理解しやすい簡潔な関数に分割することをお勧めします。

クラス スコープで定義されている関数はメンバー関数と呼ばれます。 C++ では、他の言語とは異なり、名前空間スコープ (暗黙的なグローバル名前空間を含む) でも関数を定義できます。 このような関数が呼び出される*の free 関数*または*非メンバー関数*; 標準ライブラリで広く使用されています。

関数があります*オーバー ロードされた*、仮パラメーターの型や数が異なる場合、同じ名前を共有関数の異なるバージョンを意味する可能性があります。 詳細については、次を参照してください。[関数のオーバー ロード](../cpp/function-overloading.md)です。

## <a name="parts-of-a-function-declaration"></a>関数宣言部分

最小限の関数*宣言*戻り値の型、関数名、およびパラメーター リスト (空にすることがあります)、コンパイラに追加の指示を提供する省略可能なキーワードと共に構成されます。 次の例では、関数の宣言を示します。

```cpp
int sum(int a, int b);
```

関数定義は、宣言と*本文*、中かっこの間のすべてのコードは。

```cpp
int sum(int a, int b)
{
    return a + b;
}
```

関数宣言の後にはセミコロンが続きます。1 つのプログラムの複数個所で、関数宣言がなされる場合があります。 関数宣言は、翻訳単位ごとに関数に対する呼び出しの前に記述される必要があります。 関数定義は、単一定義規則 (ODR) に従い、プログラム内で 1 回だけ記述する必要があります。

関数宣言に必要な部分は次のとおりです。

1. 関数が返す値の型を指定するには、戻り値の型または**void**値が返されない場合。 C++ 11、**自動**は、コンパイラは return ステートメントから型を推論するように指示する有効な戻り値の型。 C++14 では、"decltype(auto)" も使用できます。 詳細については、以下の「戻り値の型の型推論」を参照してください。

1. 関数名は文字かアンダースコアで始まる必要があり、スペースを含めることはできません。 一般に、標準ライブラリ関数名で先頭にアンダースコアがあるものは、プライベート メンバー関数であるか、コードでの使用が意図されていない非メンバー関数であることを意味しています。

1. パラメーター リストとは、中かっこに挟まれ、コンマで区切られた 0 個以上のパラメーターのセットです。パラメーターで、型を指定し、関数本体内で値にアクセスする際に使用するローカル名も必要に応じて指定できます。

関数宣言の省略可能な部分は次のとおりです。

1. **constexpr**コンパイル時に、関数の戻り値が定数値を計算できます。

    ```cpp
    constexpr float exp(float x, int n)
    {
        return n == 0 ? 1 :
            n % 2 == 0 ? exp(x * x, n / 2) :
            exp(x * x, (n - 1) / 2) * x;
    };
    ```

1. そのリンケージ指定**extern**または**静的**です。

    ```cpp
    //Declare printf with C linkage.
    extern "C" int printf( const char *fmt, ... );

    ```

     詳細については、次を参照してください。[プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)です。

1. **インライン**、関数コード自体で、関数へのすべての呼び出しを置き換えるコンパイラに指示します。 パフォーマンスが重要なコード セクションで関数が迅速に実行され、繰り返し呼び出されるシナリオでは、インライン展開を使用すると、パフォーマンスが向上します。

    ```cpp
    inline double Account::GetBalance()
    {
        return balance;
    }
    ```

     詳細については、次を参照してください。[インライン関数](../cpp/inline-functions-cpp.md)です。

1. A **noexcept**式で、関数が例外をスローできるかどうかを指定します。 次の例では、関数が例外をスローしない場合、`is_pod`式に評価される**true**です。

    ```cpp
    #include <type_traits>

    template <typename T>
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}
    ```

     詳細については、次を参照してください。 [noexcept](../cpp/noexcept-cpp.md)です。

1. (メンバー関数のみ)Cv 修飾子を指定するかどうかは、関数は**const**または**揮発性**です。

1. (メンバー関数のみ)**仮想**、**オーバーライド**、または**最終**です。 **仮想**関数を派生クラスでオーバーライドできることを指定します。 **オーバーライド**派生クラスで関数が仮想関数をオーバーライドすることを意味します。 **最終的な**派生クラスの関数をさらにいずれかでオーバーライドできないことを意味します。 詳細については、次を参照してください。[仮想関数](../cpp/virtual-functions.md)です。

1. (メンバー関数のみ)**静的**適用関数が、関数がクラスのすべてのオブジェクト インスタンスに関連付けられていないことを意味、メンバーにします。

1. (非静的メンバー関数のみ)Ref 修飾子をクリックし、関数のどのオーバー ロードをコンパイラに指定する暗黙的オブジェクト パラメーター (\*この) は、左辺値参照と右辺値参照。 詳細については、次を参照してください。[関数のオーバー ロード](function-overloading.md#ref-qualifiers)です。

次の図では、関数定義の一部を示しています。 網かけされた部分は関数本体です。

 ![関数定義の一部](../cpp/media/vc38ru1.gif "vc38RU1")関数定義部分

## <a name="function-definitions"></a>関数定義

A*関数の定義*宣言と関数本体に、中かっこで囲まれたを含む変数を宣言し、ステートメント、式で構成されます。 次の例は、完全な関数の定義を示しています。

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

メンバー関数としてを宣言することができます**const**クラスの任意のデータ メンバーの値を変更する関数が使用できないことを指定します。 メンバー関数として宣言することによって**const**、コンパイラに強制できます*const の正確*です。 かどうか誤って何者かとして宣言された関数を使用して、オブジェクトを変更する**const**、コンパイラ エラーが発生します。 詳細については、次を参照してください。 [const](const-cpp.md)です。

関数として宣言**constexpr**コンパイル時に決定、値を生成できますが可能性があります。 Constexpr 関数は、一般に通常の関数よりも高速実行します。 詳細については、次を参照してください。 [constexpr](constexpr-cpp.md)です。

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

既定では、引数は関数に値渡しで渡されます。このことは、関数が渡されるオブジェクトのコピーを受け取ることを意味します。 大きなオブジェクトの場合、コピーの作成は負荷が高く、必ずしも必要ではありません。 参照渡し (具体的には左辺値参照) で渡される引数には、パラメーターに量指定子の参照を追加します。

```cpp
void DoSomething(std::string& input){...}
```

関数が参照によって渡される引数を変更すると、ローカル コピーではなく元のオブジェクトが変更されます。 関数がこのような引数を変更しないようにするには、パラメーターを const& として修飾します。

```cpp
void DoSomething(const std::string& input){...}
```

 **C++ 11:** 右辺値参照または左辺値参照によって渡される引数を明示的に処理するには、二重アンパサンド パラメーターで使用して、汎用参照を指定します。

```cpp
void DoSomething(const std::string&& input){...}
```

1 つのキーワードで宣言された関数**void**パラメーターの宣言でリスト引数を使用しない、キーワードと同じくらい**void**が最初では引数宣言リストのメンバーだけです。 型の引数**void**別の場所一覧にエラーが発生します。 例えば:

```cpp

// OK same as GetTickCount()
long GetTickCount( void );
```

なお、指定することはできません、 **void**記載されている以外の引数ここでは、型から派生した型**void** (へのポインターなど**void**およびの配列**void**) は引数宣言リストどこにも表示できます。

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

詳細については、次を参照してください。[既定の引数](../cpp/default-arguments.md)です。

## <a name="function-return-types"></a>関数の戻り値の型

別の関数、あるいは組み込み配列です。 関数が返していない可能性があります。これらの型へのポインターを返す、ただしまたは*ラムダ*、関数オブジェクトが生成されます。 このような場合は、関数がスコープ内にある任意の型の値を返す可能性があります値を返すありませんを除き、その場合は戻り値の型は**void**です。

### <a name="trailing-return-types"></a>後続の戻り値の型

"通常" の戻り値の型は、関数のシグネチャの左側にあります。 A*後続の戻り値の型*シグネチャの一番右端にあるし、は後に、-> 演算子。 後続の戻り値の型は、関数テンプレートにおいて、戻り値の種類がテンプレート パラメーターに依存する場合、特に便利です。

```cpp
template<typename Lhs, typename Rhs>
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)
{
    return lhs + rhs;
}
```

ときに**自動**使用は、後続の戻り値の型と組み合わせてののみ機能のプレース ホルダーとしてどのような decltype 式によって生成される値とは自体は型推論を実行します。


## <a name="function-local-variables"></a>関数のローカル変数

関数本体内で宣言されている変数と呼ばれる、*ローカル変数*または単に*ローカル*です。 非静的ローカルは関数本体内でのみ認識され、スタックで宣言されている場合は、関数の終了時にスコープ外に出ます。 ローカル変数を作成して値渡しで値を返す場合、通常、コンパイラで戻り値の最適化を実行し、不要なコピー操作を回避できます。 ローカル変数を参照渡しで返す場合、呼び出し元がその参照を使用するために実行する試行がローカルの破棄後に発生するため、コンパイラは警告を発行します。

C++ では、ローカル変数を "静的" として宣言することがあります。 変数は関数本体内でのみ認識されますが、関数のすべてのインスタンスに対して変数の 1 つのコピーが存在します。 によって指定された終了時にローカルな静的オブジェクトは破棄されます**atexit**です。 プログラムの制御フローが宣言をバイパスしたために静的オブジェクトが構築されなかった場合、そのオブジェクトの破棄は試みられません。

##  <a name="type_deduction"></a> 戻り値の型 (c++ 14) 型の推論

C++ 14 で使用できます**自動**に後続の戻り値の型を指定しない場合でも、関数本体からの戻り値の型を推測するようコンパイラに指示します。 なお**自動**値渡しの戻り値を常にあると推測します。 使用して**自動 (& a) (& a)** への参照を推測するようコンパイラに指示します。

この例では**自動**lhs と rhs の合計の非定数の値のコピーとして推測されます。

```cpp
template<typename Lhs, typename Rhs>
auto Add2(const Lhs& lhs, const Rhs& rhs)
{
    return lhs + rhs; //returns a non-const object by value
}
```

なお**自動**推測した型の const 性は保持されません。 Const 性または ref 性、引数を保持する必要がある戻り値を返す関数を転送するには、使用できます、 **decltype (auto)** キーワードを使用して、 **decltype**推論規則を入力し、すべての型情報を保持します。 **decltype (auto)** 左側にある、通常の戻り値または後続の戻り値として使用することがあります。

次の例 (コードに基づく[N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html))、表示**decltype (auto)** 関数の引数の戻り値の型がテンプレートになるまでの完全転送を有効にするために使用されています。インスタンス化されます。

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

## <a name="returning-multiple-values-from-a-function"></a>関数から複数の値を返す

さまざまな方法で、関数から 1 つ以上の値を返します。

1. 名前付きのクラスまたは構造体オブジェクト内の値をカプセル化します。 呼び出し元に表示するクラスまたは構造体の定義が必要です。

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
    
1. Std::tuple または std::pair オブジェクトを返します。

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

1. **Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 使用するバインディングを構造化します。 構造化されたバインドの場合は、戻り値を格納する変数は初期化は、宣言、同時にいくつかの場合がありますが大幅に効率的です。 次のステートメントで`auto[x, y, z] = f();`--角かっこを紹介し、関数全体のブロックのスコープ内にある名前を初期化します。

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
    
1. 戻り値自体を使用するだけでなくすることができます「値を返します」関数を変更または呼び出し元が提供するオブジェクトの値を初期化できるようにする、参照渡しを使用するパラメーターの任意の数を定義することで。 詳細については、次を参照してください。[参照型関数の引数](reference-type-function-arguments.md)です。

## <a name="function-pointers"></a>関数ポインター

C++ では、C 言語と同じ方法で、関数ポインターをサポートします。 ただし、通常、よりタイプ セーフな代替手段で関数オブジェクトが使用されます。

推奨**typedef**関数ポインター型を返す関数を宣言する場合、関数ポインター型のエイリアスの宣言に使用します。  次に例を示します。

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

- [関数のオーバーロード](../cpp/function-overloading.md)
- [可変個の引数リストを取る関数](../cpp/functions-with-variable-argument-lists-cpp.md)
- [明示的に既定された関数および削除された関数](../cpp/explicitly-defaulted-and-deleted-functions.md)
- [関数の引数依存名の参照 (Koenig 参照)](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)
- [既定の引数](../cpp/default-arguments.md)
- [インライン関数](../cpp/inline-functions-cpp.md)
