---
title: 列挙型 [C++]
ms.date: 06/01/2018
f1_keywords:
- enum_cpp
helpviewer_keywords:
- declarations, enumerations
- enumerators, declaring
- enum keyword [C++]
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
ms.openlocfilehash: d4511ed7d09ff280d01214a2a177148956580ee5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221615"
---
# <a name="enumerations-c"></a>列挙型 [C++]

列挙体は、列挙子と呼ばれる一連の名前付き整数定数で構成されるユーザー定義型です。

> [!NOTE]
> この記事では、 **`enum`** c++ 11 で導入された ISO 標準 C++ 言語の型とスコープを持つ (または厳密に型指定された)**列挙型クラス**型について説明します。 C++/CLI および C++/CX の**パブリック列挙型クラス**または**プライベート列挙**型クラスの詳細については、「 [enum クラス](../extensions/enum-class-cpp-component-extensions.md)」を参照してください。

## <a name="syntax"></a>構文

```
// unscoped enum:
enum [identifier] [: type]
{enum-list};

// scoped enum:
enum [class|struct]
[identifier] [: type]
{enum-list};
```

```cpp
// Forward declaration of enumerations  (C++11):
enum A : int; // non-scoped enum must have type specified
enum class B; // scoped enum defaults to int but ...
enum class C : short;  // ... may have any integral underlying type
```

## <a name="parameters"></a>パラメーター

*identifier*<br/>
列挙体に渡す型名。

*type*<br/>
列挙子の基になる型であり、すべての列挙子は同じ型を基にしています。 任意の整数型を指定できます。

*列挙型リスト*<br/>
列挙体に含まれる列挙子のコンマ区切りのリスト。 スコープ内のすべての列挙子または変数名は一意である必要があります。 ただし、値は複製できます。 対象範囲外の列挙型では、スコープは周囲のスコープです。スコープを持つ列挙型では、スコープは*列挙型リスト*自体です。  スコープを持つ列挙型では、リストは空になることがあります。これは、有効な場合は新しい整数型を定義します。

*class*<br/>
このキーワードを宣言で使用すると、列挙型のスコープを指定し、*識別子*を指定する必要があります。 キーワードは、 **`struct`** **`class`** このコンテキストでは意味的に等価であるため、の代わりに使用することもできます。

## <a name="enumerator-scope"></a>列挙子のスコープ

列挙型を使用すると、名前付き定数として表される値の範囲 (列挙子) を記述できます。 元の C と C++ の列挙型では、修飾なしの列挙子は列挙型が宣言されているスコープ内で可視です。 スコープを持つ列挙型では、列挙子の名前は列挙型の名前で修飾する必要があります。 次の例に、2 種類の列挙型のこの基本的な相違点を示します。

```cpp
namespace CardGame_Scoped
{
    enum class Suit { Diamonds, Hearts, Clubs, Spades };

    void PlayCard(Suit suit)
    {
        if (suit == Suit::Clubs) // Enumerator must be qualified by enum type
        { /*...*/}
    }
}

namespace CardGame_NonScoped
{
    enum Suit { Diamonds, Hearts, Clubs, Spades };

    void PlayCard(Suit suit)
    {
        if (suit == Clubs) // Enumerator is visible without qualification
        { /*...*/
        }
    }
}
```

列挙型の各値の名前には、列挙型の値の順序に対応する場所の整数値が割り当てられます。 既定では、最初の値には 0、その次の値には 1 などのように割り当てられますが、次に示すように、列挙体の値を明示的に設定することもできます。

```cpp
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };
```

`Diamonds` 列挙子に値 `1` を割り当てます。 明示的な値を指定しない場合、後続の列挙子は前の列挙子の値に 1 を加えた数値が指定されます。 前の例では、`Hearts` の値が 2、`Clubs` の値が 3 などのようになります。

すべての列挙子は定数として扱われ、が定義されているスコープ (対象範囲 **`enum`** 外の列挙型の場合) またはそれ自体 (スコープが指定されている列挙型の場合) で、一意の名前を持つ必要があり **`enum`** ます。 列挙子の名前に対応する値は一意である必要はありません。 たとえば、スコープを持たない列挙型 `Suit` が次のように宣言されているとします。

```cpp
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };
```

この場合、`Diamonds`、`Hearts`、`Clubs`、`Spades` の値はそれぞれ 5、6、4、5 になります。 5 つが複数回使用されています。これは意図した値と異なる可能性がありますが、それ自体は問題ありません。 これらの規則はスコープを持つ列挙型でも同じです。

## <a name="casting-rules"></a>キャストの規則

対象範囲外の列挙定数はに暗黙的に変換でき **`int`** ますが、 **`int`** 列挙値に暗黙的に変換することはできません。 次の例では、`hand` に `Suit` 型でない値を代入しようとするとどうなるかを示します。

```cpp
int account_num = 135692;
Suit hand;
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'
```

を **`int`** スコープ内または対象範囲外の列挙子に変換するには、キャストが必要です。 ただし、スコープを持たない列挙子はキャストなしで整数値に上位変換できます。

```cpp
int account_num = Hearts; //OK if Hearts is in a unscoped enum
```

このような暗黙の型変換を使用すると、意図しない副作用につながることがあります。 スコープを持たない列挙型に関連するプログラミング エラーをなくすために役立つように、スコープを持つ列挙型の値は厳密に型指定します。 次の例に示すように、スコープを持つ列挙子は列挙型の名前 (識別子) で修飾する必要があり、暗黙的に変換されることはありません。

```cpp
namespace ScopedEnumConversions
{
    enum class Suit { Diamonds, Hearts, Clubs, Spades };

    void AttemptConversions()
    {
        Suit hand;
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier
        hand = Suit::Clubs; //Correct.
        int account_num = 135692;
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!

        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'
        account_num = static_cast<int>(Suit::Hearts); // OK
    }
}
```

`hand = account_num;` 行では、前に示したように、スコープを持たない列挙型に関連するエラーが発生することに注意してください。 これは、明示的にキャストすることでエラーを回避できます。 ただし、スコープを持つ列挙型を使用しても、次のステートメント、`account_num = Suit::Hearts;` での変換の試みは、明示的なキャストなしではエラーが発生します。

## <a name="enums-with-no-enumerators"></a><a name="no_enumerators"></a>列挙子のない列挙型

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): 明示的な基になる型と列挙子がない列挙型 (regular またはスコープ) を定義することで、他の型への暗黙の型変換を持たない新しい整数型が導入されます。 組み込みの基になる型の代わりにこの型を使用することにより、誤った暗黙的な変換によって発生する軽度のエラーの可能性を排除できます。

```cpp
enum class byte : unsigned char { };
```

新しい型は、基になる型の正確なコピーであるため、同じ呼び出し規約を持ちます。つまり、ABIs 全体で使用でき、パフォーマンスが低下することはありません。 直接リスト初期化を使用して型の変数を初期化する場合、キャストは必要ありません。 次の例は、さまざまなコンテキストで列挙子を含まない列挙型を初期化する方法を示しています。

```cpp
enum class byte : unsigned char { };

enum class E : int { };
E e1{ 0 };
E e2 = E{ 0 };

struct X
{
    E e{ 0 };
    X() : e{ 0 } { }
};

E* p = new E{ 0 };

void f(E e) {};

int main()
{
    f(E{ 0 });
    byte i{ 42 };
    byte j = byte{ 42 };

    // unsigned char c = j; // C2440: 'initializing': cannot convert from 'byte' to 'unsigned char'
    return 0;
}
```

## <a name="see-also"></a>関連項目

[C 列挙体の宣言](../c-language/c-enumeration-declarations.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
