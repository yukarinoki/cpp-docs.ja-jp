---
title: break ステートメント (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 30ca602ecc65099adff7300f730c500a31fe0ed5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227609"
---
# <a name="break-statement-c"></a>break ステートメント (C++)

ステートメントは、 **`break`** 最も近い外側のループまたは条件付きステートメントの実行を終了します。 このステートメントの終了の後ろにステートメントがある場合は、そこに制御が移動します。

## <a name="syntax"></a>構文

```
break;
```

## <a name="remarks"></a>解説

ステートメントは、 **`break`** 条件付き[スイッチ](../cpp/switch-statement-cpp.md)ステートメントと、 [do](../cpp/do-while-statement-cpp.md)、 [for](../cpp/for-statement-cpp.md)、および[while](../cpp/while-statement-cpp.md)ループステートメントと共に使用します。

ステートメントでは、ステートメントに **`switch`** **`break`** よってプログラムがステートメントの外部で次のステートメントを実行し **`switch`** ます。 ステートメントを使用しない **`break`** 場合、句を含め、一致するラベルからステートメントの最後までのすべてのステートメント **`case`** **`switch`** **`default`** が実行されます。

ループでは、 **`break`** ステートメントは、最も近い、 **`do`** **`for`** 、またはステートメントの実行を終了し **`while`** ます。 終了したステートメントの次にステートメントがある場合は、そこに制御が移動します。

入れ子になったステートメント内では、 **`break`** ステートメントは **`do`** 、 **`for`** その直後にある、、 **`switch`** 、またはステートメントのみを終了し **`while`** ます。 またはステートメントを使用して、 **`return`** **`goto`** より深い入れ子構造から制御を移すことができます。

## <a name="example"></a>例

次のコードは、ループ内でステートメントを使用する方法を示して **`break`** **`for`** います。

```cpp
#include <iostream>
using namespace std;

int main()
{
    // An example of a standard for loop
    for (int i = 1; i < 10; i++)
    {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }

    // An example of a range-based for loop
int nums []{1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

    for (int i : nums) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
    }
}
```

```Output
In each case:
1
2
3
```

次のコードは、ループとループでを使用する方法を示して **`break`** **`while`** **`do`** います。

```cpp
#include <iostream>
using namespace std;

int main() {
    int i = 0;

    while (i < 10) {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    }

    i = 0;
    do {
        if (i == 4) {
            break;
        }
        cout << i << '\n';
        i++;
    } while (i < 10);
}
```

```Output
In each case:
0123
```

次のコードは、switch ステートメントでを使用する方法を示して **`break`** います。 **`break`** 各ケースを個別に処理する場合は、すべてのケースでを使用する必要があります。を使用しない場合は、 **`break`** コードの実行が次のケースにフォールスルーされます。

```cpp
#include <iostream>
using namespace std;

enum Suit{ Diamonds, Hearts, Clubs, Spades };

int main() {

    Suit hand;
    . . .
    // Assume that some enum value is set for hand
    // In this example, each case is handled separately
    switch (hand)
    {
    case Diamonds:
        cout << "got Diamonds \n";
        break;
    case Hearts:
        cout << "got Hearts \n";
        break;
    case Clubs:
        cout << "got Clubs \n";
        break;
    case Spades:
        cout << "got Spades \n";
        break;
    default:
          cout << "didn't get card \n";
    }
    // In this example, Diamonds and Hearts are handled one way, and
    // Clubs, Spades, and the default value are handled another way
    switch (hand)
    {
    case Diamonds:
    case Hearts:
        cout << "got a red card \n";
        break;
    case Clubs:
    case Spades:
    default:
        cout << "didn't get a red card \n";
    }
}
```

## <a name="see-also"></a>関連項目

[ジャンプ ステートメント](../cpp/jump-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[continue ステートメント](../cpp/continue-statement-cpp.md)
