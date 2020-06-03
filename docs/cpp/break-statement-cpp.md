---
title: break ステートメント (C++)
ms.date: 11/04/2016
f1_keywords:
- break_cpp
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
ms.openlocfilehash: 23d31e1456106d5f82c4a13079c72c231b8477bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190483"
---
# <a name="break-statement-c"></a>break ステートメント (C++)

**Break**ステートメントは、最も近い外側のループまたは条件付きステートメントの実行を終了します。 このステートメントの終了の後ろにステートメントがある場合は、そこに制御が移動します。

## <a name="syntax"></a>構文

```
break;
```

## <a name="remarks"></a>解説

**Break**ステートメントは、条件付き[スイッチ](../cpp/switch-statement-cpp.md)ステートメントと[do](../cpp/do-while-statement-cpp.md)、 [for](../cpp/for-statement-cpp.md)、および[while](../cpp/while-statement-cpp.md)ループステートメントで使用されます。

**Switch**ステートメントでは、 **break**ステートメントによってプログラムが**switch**ステートメントの外部で次のステートメントを実行します。 **Break**ステートメントを使用しない**場合**、一致した case ラベルのすべてのステートメントが**switch**ステートメントの最後 ( **default**句を含む) に実行されます。

ループでは、 **break**ステートメントは、最も近い外側の**do**、 **for**、または**while**ステートメントの実行を終了します。 終了したステートメントの次にステートメントがある場合は、そこに制御が移動します。

入れ子になったステートメント内では、 **break**ステートメントは、すぐに囲まれる**do**、 **for**、 **switch**、または**while**ステートメントのみを終了します。 **Return**ステートメントまたは**goto**ステートメントを使用して、より深い入れ子構造から制御を移すことができます。

## <a name="example"></a>例

次のコードは、 **for**ループで**break**ステートメントを使用する方法を示しています。

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

次のコードは、 **while**ループと**do**ループで**break**を使用する方法を示しています。

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

次のコードは、switch ステートメントで**break**を使用する方法を示しています。 各ケースを個別に処理する場合は、必ず**break**を使用する必要があります。**break**を使用しない場合、コードの実行は次のケースにフォールスルーされます。

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

## <a name="see-also"></a>参照

[ジャンプ ステートメント](../cpp/jump-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[continue ステートメント](../cpp/continue-statement-cpp.md)
