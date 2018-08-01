---
title: break ステートメント (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- break_cpp
dev_langs:
- C++
helpviewer_keywords:
- break keyword [C++]
ms.assetid: 63739928-8985-4b05-93ce-016322e6da3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30910f6850fc3728ee101ab0662638fdebcd3775
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405445"
---
# <a name="break-statement-c"></a>break ステートメント (C++)
**Break**ステートメントは、最も外側の実行を終了ループまたは条件付きステートメントが表示されます。 このステートメントの終了の後ろにステートメントがある場合は、そこに制御が移動します。  
  
## <a name="syntax"></a>構文  
  
```  
break;  
```  
  
## <a name="remarks"></a>Remarks  
 **Break** 、条件付きステートメントを使用[切り替える](../cpp/switch-statement-cpp.md)ステートメントを使用して、[は](../cpp/do-while-statement-cpp.md)、[の](../cpp/for-statement-cpp.md)、および[中に](../cpp/while-statement-cpp.md)ステートメントをループします。  
  
 **切り替える**ステートメントでは、 **break**ステートメントは、外にある次のステートメントを実行するプログラム、**切り替える**ステートメント。 なし、 **break**ステートメントでは、すべてのステートメントから、一致する**ケース**の末尾にラベル、**切り替える**ステートメントを含む、**既定**句が実行されます。  
  
 、ループで、 **break**ステートメントが最も近い外側の実行が終了**は**、**の**、または**中**ステートメント。 終了したステートメントの次にステートメントがある場合は、そこに制御が移動します。  
  
 入れ子になったステートメント内で、**中断**だけステートメントを終了、**は**、**の**、**スイッチ**、または**中に**をすぐにそれを囲むステートメント。 使用することができます、**返す**または**goto**入れ子構造のレベルが深複数から制御を転送するステートメント。  
  
## <a name="example"></a>例  
 次のコードを使用する方法を示しています、 **break**内のステートメントを**の**ループします。  
  
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
  
 次のコードを使用する方法を示します**break**で、**中に**ループと**は**ループします。  
  
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
  
 次のコードは、使用する方法を示しています。 **break** switch ステートメントでします。 使用する必要があります**break**を使用しない場合は各ケースを個別に処理する場合、すべてのケースで**break**コードの実行が次の case にフォール スルーします。  
  
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
 [ジャンプ ステートメント](../cpp/jump-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [continue ステートメント](../cpp/continue-statement-cpp.md)