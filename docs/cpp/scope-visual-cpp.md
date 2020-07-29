---
title: スコープ (C)
ms.date: 11/19/2018
helpviewer_keywords:
- classes [C++], scope
- scope [C++]
- function prototypes [C++], scope
- class scope
- prototype scope
- functions [C++], scope
- scope, C++ names
ms.assetid: 81fecbb0-338b-4325-8332-49f33e716352
ms.openlocfilehash: 5cff7a4607201175c7095a87134850583b76d636
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227089"
---
# <a name="scope-c"></a>スコープ (C)

クラス、関数、または変数などのプログラム要素を宣言すると、その名前は "認識" されるだけで、プログラムの特定の部分で使用されます。 名前が表示されるコンテキストは、その*スコープ*と呼ばれます。 たとえば、関数内で変数を宣言した場合、 `x` `x` はその関数本体内でのみ表示されます。 *ローカルスコープ*を持ちます。 プログラムには、同じ名前の他の変数が含まれている場合があります。異なるスコープ内にある限り、1つの定義規則に違反することはなく、エラーは発生しません。

自動非静的変数の場合、スコープは、プログラムのメモリ内で作成および破棄されるタイミングも決定します。

スコープには、次の6種類があります。

- **グローバルスコープ**グローバル名は、クラス、関数、または名前空間の外部で宣言されている名前です。 ただし、C++ では、これらの名前は暗黙的なグローバル名前空間でも存在します。 グローバル名のスコープは、宣言の時点から、宣言されているファイルの末尾までを範囲としています。 グローバル名の場合、可視性は、プログラム内の他のファイルで名前が表示されるかどうかを決定する[リンケージ](program-and-linkage-cpp.md)の規則によっても制御されます。

- **名前空間のスコープ**名前[空間](namespaces-cpp.md)内でクラスまたは列挙型の定義または関数ブロックの外側で宣言された名前は、宣言の位置から名前空間の末尾まで参照できます。 名前空間は、さまざまなファイルにまたがる複数のブロックで定義できます。

- **ローカルスコープ**関数またはラムダ内で宣言された名前 (パラメーター名を含む) にはローカルスコープがあります。 多くの場合、"ローカル" と呼ばれます。 これらは、関数またはラムダの本体の最後まで、宣言の位置からのみ参照できます。 ローカルスコープは、この記事の後半で説明するブロックスコープの一種です。

- **クラススコープ**クラスメンバーの名前にはクラススコープがあり、宣言の位置に関係なくクラス定義全体で拡張されます。 クラスメンバーのアクセシビリティは、、、およびの各キーワードによってさらに制御され **`public`** **`private`** **`protected`** ます。 パブリックメンバーまたはプロテクトメンバーにアクセスするには、メンバー選択演算子 () を使用する必要があり**ます。** または **->** ) またはメンバーへのポインター演算子 (**.** <strong>\*</strong> または **->** <strong>\*</strong> )。

- **ステートメントのスコープ****`for`**、、 **`if`** **`while`** 、またはステートメントで宣言 **`switch`** された名前は、ステートメントブロックが終了するまで表示されます。

- **関数のスコープ**[ラベル](labeled-statements.md)には関数スコープがあります。つまり、宣言のポイントの前であっても、関数本体全体で参照できます。 関数スコープを使用すると `goto cleanup` 、 `cleanup` ラベルが宣言される前に、のようなステートメントを記述できます。

## <a name="hiding-names"></a>名前の隠ぺい

囲まれたブロック内で名前を宣言すると、その名前が非表示になります。 次の図では、内側のブロックで `i` が再宣言されています。そのため、外側のブロック スコープでは `i` に関連付けられた変数が隠し変数になります。

![&#45;スコープ名の非表示をブロックする](../cpp/media/vc38sf1.png "&#45;スコープ名の非表示をブロックする") <br/>
ブロックスコープと名前の非表示

このプログラムの出力を次の図に示します。

```cpp
i = 0
i = 7
j = 9
i = 0
```

> [!NOTE]
> `szWhat` 引数は、この関数のスコープ内にあると見なされます。 したがって、この関数の外側のブロックで宣言されたものとして処理されます。

## <a name="hiding-class-names"></a>クラス名の非表示

関数、オブジェクト、変数、または列挙子を同じスコープ内で宣言することで、クラス名を非表示にできます。 ただし、キーワードがプレフィックスとして使用されている場合でも、クラス名にアクセスでき **`class`** ます。

```cpp
// hiding_class_names.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

// Declare class Account at global scope.
class Account
{
public:
    Account( double InitialBalance )
        { balance = InitialBalance; }
    double GetBalance()
        { return balance; }
private:
    double balance;
};

double Account = 15.37;            // Hides class name Account

int main()
{
    class Account Checking( Account ); // Qualifies Account as
                                       //  class name

    cout << "Opening account with a balance of: "
         << Checking.GetBalance() << "\n";
}
//Output: Opening account with a balance of: 15.37
```

> [!NOTE]
> クラス名 ( `Account` ) が呼び出される場合は、グローバルスコープ変数アカウントと区別するためにキーワードクラスを使用する必要があります。 スコープ解決演算子 (::) の左側がクラス名の場合は、この規則が適用されません。 スコープ解決演算子の左側の名前は、常にクラス名と見なされます。

次の例は、 `Account` キーワードを使用して、型のオブジェクトへのポインターを宣言する方法を示してい **`class`** ます。

```cpp
class Account *Checking = new class Account( Account );
```

`Account`前のステートメントの初期化子 (かっこ内) のには、グローバルスコープがあります。これは型 **`double`** です。

> [!NOTE]
> この例のように、識別子名を再使用するのは適切なプログラミング方法ではありません。

クラスオブジェクトの宣言と初期化の詳細については、「[クラス、構造体、および共用体](../cpp/classes-and-structs-cpp.md)」を参照してください。 および自由ストア演算子の使用については **`new`** **`delete`** 、「 [new および delete 演算子](new-and-delete-operators.md)」を参照してください。

## <a name="hiding-names-with-global-scope"></a>グローバルスコープでの名前の非表示

ブロックスコープで同じ名前を明示的に宣言することにより、グローバルスコープの名前を非表示にすることができます。 ただし、スコープ解決演算子 () を使用してグローバルスコープ名にアクセスでき `::` ます。

```cpp
#include <iostream>

int i = 7;   // i has global scope, outside all blocks
using namespace std;

int main( int argc, char *argv[] ) {
   int i = 5;   // i has block scope, hides i at global scope
   cout << "Block-scoped i has the value: " << i << "\n";
   cout << "Global-scoped i has the value: " << ::i << "\n";
}
```

```Output
Block-scoped i has the value: 5
Global-scoped i has the value: 7
```

## <a name="see-also"></a>関連項目

[基本的な概念](../cpp/basic-concepts-cpp.md)
