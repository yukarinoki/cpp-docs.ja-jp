---
description: '詳細情報: 宣言と定義 (C++)'
title: 宣言と定義 (C++)
ms.date: 12/12/2019
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
ms.openlocfilehash: 00d86e4df70e150a2e9f2417050b47b943a054ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339515"
---
# <a name="declarations-and-definitions-c"></a>宣言と定義 (C++)

C++ プログラムは、変数、関数、型、名前空間などのさまざまなエンティティで構成されています。 これらの各エンティティは、使用する前に *宣言* する必要があります。 宣言は、エンティティの一意の名前と、その型およびその他の特性に関する情報を指定します。 C++ では、名前が宣言されているポイントは、コンパイラに表示される位置です。 コンパイル単位の後の時点で宣言されている関数またはクラスを参照することはできません。 変数は、使用されるポイントの前にできるだけ近いものとして宣言する必要があります。

次の例は、いくつかの宣言を示しています。

```cpp
#include <string>

void f(); // forward declaration

int main()
{
    const double pi = 3.14; //OK
    int i = f(2); //OK. f is forward-declared
    std::string str; // OK std::string is declared in <string> header
    C obj; // error! C not yet declared.
    j = 0; // error! No type specified.
    auto k = 0; // OK. type inferred as int by compiler.
}

int f(int i)
{
    return i + 42;
}

namespace N {
   class C{/*...*/};
}
```

5行目で `main` は、関数が宣言されています。 7行目では、と **`const`** いう名前の変数 `pi` が宣言され、 *初期化* されます。 8行目では、整数 `i` が宣言され、関数によって生成された値で初期化され `f` ます。 名前は、 `f` 3 行目の *事前宣言* によってコンパイラから参照できます。

9行目では、型のという名前 `obj` の変数 `C` が宣言されています。 ただし、がプログラムの後半まで宣言されておらず、前方宣言されていないため、この宣言ではエラーが発生 `C` します。 このエラーを修正するには、の *定義* 全体を移動するか、事前 `C` `main` 宣言を追加します。 この動作は、C# などの他の言語とは異なり、関数とクラスは、ソースファイル内の宣言のポイントの前に使用できます。

10行目では、型のという名前 `str` の変数 `std::string` が宣言されています。 名前 `std::string` は、ヘッダーファイルに導入されて `string` [](header-files-cpp.md)おり、1行目のソースファイルにマージされるため、表示されます。 `std` は、 `string` クラスが宣言されている名前空間です。

11行目では、名前 `j` が宣言されていないため、エラーが発生します。 宣言は、javaScript などの他の言語とは異なり、型を提供する必要があります。 12行目で **`auto`** は、キーワードが使用されます。これは、 `k` 初期化された値に基づいて、の型を推論するようにコンパイラに指示します。 この場合、コンパイラは **`int`** 型を選択します。  

## <a name="declaration-scope"></a>宣言のスコープ

宣言によって導入される名前は、宣言が行われる *スコープ* 内で有効です。 前の例では、関数内で宣言されている変数 `main` は *ローカル変数* です。 Main の外部にあるという名前の別の変数を `i` *グローバルスコープ* で宣言し、完全に独立したエンティティにすることができます。 ただし、このような名前の重複によって、プログラマの混乱やエラーが発生する可能性があるため、回避する必要があります。 21行目では、クラスは `C` 名前空間のスコープ内で宣言されてい `N` ます。 名前空間を使用すると、 *名前の競合* を回避できます。 ほとんどの C++ 標準ライブラリ名は、名前空間内で宣言されてい `std` ます。 スコープ規則と宣言の相互作用の詳細については、「 [スコープ](../cpp/scope-visual-cpp.md)」を参照してください。

## <a name="definitions"></a>定義

関数、クラス、列挙型、定数変数を含む一部のエンティティは、宣言されるだけでなく、定義する必要があります。 *定義* により、プログラムの中でエンティティが使用されている場合にコンピューターコードを生成するために必要なすべての情報がコンパイラに提供されます。 前の例では、行3に関数の宣言が含まれてい `f` ますが、関数の *定義* は 15 ~ 18 行目に用意されています。 21行目では、クラス `C` が宣言および定義されています (定義されているように、クラスは何も実行しません)。 定数変数は、その変数が宣言されているのと同じステートメント内で、値が割り当てられている他の単語に定義されている必要があります。 などの組み込み型の宣言 **`int`** は自動的に定義されます。これは、コンパイラが割り当てられる領域の量を認識するためです。

次の例は、定義でもある宣言を示しています。

```cpp
// Declare and define int variables i and j.
int i;
int j = 10;

// Declare enumeration suits.
enum suits { Spades = 1, Clubs, Hearts, Diamonds };

// Declare class CheckBox.
class CheckBox : public Control
{
public:
    Boolean IsChecked();
    virtual int     ChangeState() = 0;
};
```

定義ではない宣言をいくつか次に示します。

```cpp
extern int i;
char *strchr( const char *Str, const char Target );
```

## <a name="typedefs-and-using-statements"></a>Typedef と using ステートメント

以前のバージョンの C++ では、キーワードを使用して、 [`typedef`](aliases-and-typedefs-cpp.md) 別の名前の *エイリアス* である新しい名前を宣言しています。 たとえば、型 `std::string` はの別の名前です `std::basic_string<char>` 。 プログラマは、実際の名前ではなく typedef 名を使用するのが明らかです。 最新の C++ では、キーワードはよりも優先されますが、考え方は同じです。 [`using`](aliases-and-typedefs-cpp.md) **`typedef`** 新しい名前は、既に宣言および定義されているエンティティに対して宣言されています。

## <a name="static-class-members"></a>静的クラスメンバー

静的クラスのデータメンバーは、クラスのすべてのオブジェクトによって共有される個別の変数であるため、クラス定義の外部で定義および初期化する必要があります。 (詳細については、「 [クラス](../cpp/classes-and-structs-cpp.md)」を参照してください)。

## <a name="extern-declarations"></a>extern 宣言

C++ プログラムには、複数の [コンパイル単位](header-files-cpp.md)が含まれる場合があります。 個別のコンパイル単位で定義されたエンティティを宣言するには、キーワードを使用し [`extern`](extern-cpp.md) ます。 宣言内の情報はコンパイラに対して十分ですが、リンク手順でエンティティの定義が見つからない場合は、リンカーによってエラーが発生します。

## <a name="in-this-section"></a>このセクションの内容

[ストレージ クラス](storage-classes-cpp.md)<br/>
[`const`](const-cpp.md)<br/>
[`constexpr`](constexpr-cpp.md)<br/>
[`extern`](extern-cpp.md)<br/>
[初期化子](initializers.md)<br/>
[エイリアスと typedef](aliases-and-typedefs-cpp.md)<br/>
[`using` 定義](using-declaration.md)<br/>
[`volatile`](volatile-cpp.md)<br/>
[`decltype`](decltype-cpp.md)<br/>
[C++ の属性](attributes.md)<br/>

## <a name="see-also"></a>関連項目

[基本的な概念](../cpp/basic-concepts-cpp.md)<br/>
