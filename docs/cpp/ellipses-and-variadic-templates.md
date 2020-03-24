---
title: 楕円および可変値引数テンプレート
ms.date: 11/04/2016
ms.assetid: f20967d9-c967-4fd2-b902-2bb1d5ed87e3
ms.openlocfilehash: 9c9294089b9f0a144946b7f6b81da2a71ca710bc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189261"
---
# <a name="ellipses-and-variadic-templates"></a>楕円および可変値引数テンプレート

ここでは、C++ の可変個引数テンプレートを使用して省略記号 (`...`) を指定する方法を示します。 省略記号は、C および C++ で多くの用途に使用されてきました。 たとえば、関数の可変個引数リストなどです。 C ランタイム ライブラリの `printf()` 関数は、最も一般的な例の 1 つです。

*可変個引数テンプレート*は、任意の数の引数をサポートするクラスまたは関数テンプレートです。 この機構はクラス テンプレートと関数テンプレートの両方に適用でき、それによって広範なタイプ セーフと非自明の機能や柔軟性が提供されるため、C++ ライブラリの開発者に特に役立ちます。

## <a name="syntax"></a>構文

可変個引数テンプレートでは、省略記号が 2 とおりの方法で使用されます。 パラメーター名の左側には、パラメーター*パック*が示されます。パラメーター名の右側には、パラメーターパックが個別の名前で展開されます。

*可変個引数テンプレートクラス*定義の構文の基本的な例を次に示します。

```cpp
template<typename... Arguments> class classname;
```

パラメーター パックとその展開のいずれの場合でも、次の例に示すように、必要に応じて省略記号の前後に空白を追加できます。

```cpp
template<typename ...Arguments> class classname;
```

または

```cpp
template<typename ... Arguments> class classname;
```

この記事では最初の例に示している規約を使用する (省略記号を `typename` に接続する) ことに注目してください。

前の例では、*引数*はパラメーターパックです。 `classname` クラスには、次の例のように、可変個の引数を指定できます。

```cpp
template<typename... Arguments> class vtclass;

vtclass< > vtinstance1;
vtclass<int> vtinstance2;
vtclass<float, bool> vtinstance3;
vtclass<long, std::vector<int>, std::string> vtinstance4;
```

可変個引数テンプレート クラス定義を使用して、1 つ以上のパラメーターを要求することもできます。

```cpp
template <typename First, typename... Rest> class classname;
```

*可変個引数 template 関数*の構文の基本的な例を次に示します。

```cpp
template <typename... Arguments> returntype functionname(Arguments... args);
```

次のセクション「**可変個引数テンプレートについ**て」で説明しているように、*引数*parameter pack が使用できるように展開されます。

可変個引数テンプレート関数の構文は、他の形式を使用することもできます。いくつかの例を次に示します。

```cpp
template <typename... Arguments> returntype functionname(Arguments&... args);
template <typename... Arguments> returntype functionname(Arguments&&... args);
template <typename... Arguments> returntype functionname(Arguments*... args);
```

**Const**などの指定子も使用できます。

```cpp
template <typename... Arguments> returntype functionname(const Arguments&... args);
```

可変個引数テンプレート クラス定義を使用して、1 つ以上のパラメーターを要求する関数を作成することができます。

```cpp
template <typename First, typename... Rest> returntype functionname(const First& first, const Rest&... args);
```

可変個引数テンプレートでは、`sizeof...()` 演算子が使用されます (従来の `sizeof()` 演算子とは無関係です)。

```cpp
template<typename... Arguments>
void tfunc(const Arguments&... args)
{
    constexpr auto numargs{ sizeof...(Arguments) };

    X xobj[numargs]; // array of some previously defined type X

    helper_func(xobj, args...);
}
```

## <a name="more-about-ellipsis-placement"></a>省略記号の配置の詳細

以前にこの記事で、パラメーター パックとその展開を定義する省略記号の配置について、パラメーター名の左に配置すると、パラメーター パックを意味し、パラメーター名の右に配置すると、パラメーター パックの展開を意味する (パラメーター パックが個々の名前に展開される) と説明しました。 これは技術的には事実ですが、コードへの変換の点では混乱することがあります。 以下を検討してください。

- テンプレートパラメーターリスト (`template <parameter-list>`) では、`typename...` テンプレートパラメーターパックが導入されています。

- パラメーター宣言句 (`func(parameter-list)`) では、"最上位" の省略記号によって関数パラメーターパックが導入され、省略記号の配置が重要になります。

    ```cpp
    // v1 is NOT a function parameter pack:
    template <typename... Types> void func1(std::vector<Types...> v1);

    // v2 IS a function parameter pack:
    template <typename... Types> void func2(std::vector<Types>... v2);
    ```

- 省略記号がパラメーター名の直後にある場合、パラメーター パックの展開を示します。

## <a name="example"></a>例

可変個引数テンプレート関数の機構について説明するには、これを使用して `printf` の機能の一部を変更するのが最も適切です。

```cpp
#include <iostream>

using namespace std;

void print() {
    cout << endl;
}

template <typename T> void print(const T& t) {
    cout << t << endl;
}

template <typename First, typename... Rest> void print(const First& first, const Rest&... rest) {
    cout << first << ", ";
    print(rest...); // recursive call using pack expansion syntax
}

int main()
{
    print(); // calls first overload, outputting only a newline
    print(1); // calls second overload

    // these call the third overload, the variadic template,
    // which uses recursion as needed.
    print(10, 20);
    print(100, 200, 300);
    print("first", 2, "third", 3.14159);
}
```

## <a name="output"></a>Output

```Output
1
10, 20
100, 200, 300
first, 2, third, 3.14159
```

> [!NOTE]
>  可変個引数テンプレート関数を組み込むほとんどの実装では、何らかの形式の再帰が使用されますが、従来の再帰とは少し異なります。  従来の再帰には、同じシグネチャを使用して関数自体を呼び出す関数が含まれています。 (オーバーロードまたはテンプレート化されている場合もありますが、毎回同じ署名が選択されます)。可変個引数の再帰では、異なる (ほとんどの場合には減少する) 引数の数を使用して可変個引数関数テンプレートを呼び出すことができます。これにより、毎回異なる署名がスタンプされます。 "基本ケース" が必要なのは同じですが、再帰の性質は異なります。
