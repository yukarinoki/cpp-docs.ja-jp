---
title: for ステートメント (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38181a43134c35c4db1db3d78a79d3338934b7d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417185"
---
# <a name="for-statement-c"></a>for ステートメント (C++)
条件が偽 (false) になるまでステートメントを繰り返し実行します。 範囲ベースの for ステートメントについては、次を参照してください。[ステートメント (C++) の範囲に基づく](../cpp/range-based-for-statement-cpp.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
for ( init-expression ; cond-expression ; loop-expression )   
    statement;  
```  
  
## <a name="remarks"></a>コメント  
 指定された回数だけ実行する必要のあるループの構築に `for` ステートメントを使用します。  
  
 次の表に示すように、`for` ステートメントは 3 つのオプション部分から構成されます。  
  
### <a name="for-loop-elements"></a>for ループ要素  
  
|構文の名前|実行タイミング|説明|  
|-----------------|-------------------|-----------------|  
|`init-expression`|その他の要素の前に、**の**ステートメントでは、`init-expression`は一度だけ実行します。 その後、制御は `cond-expression` に渡されます。|ループ インデックスを初期化するためによく使用されます。 式または宣言を含めることができます。|  
|`cond-expression`|最初のイテレーションを含む `statement` の各イテレーションの実行前。 `statement` は、`cond-expression` が true (0 以外) に評価された場合にのみ実行されます。|整数型に評価される式、または整数型へのあいまいでない変換が行われるクラス型。 通常、for ループの終了条件をテストするために使用します。|  
|`loop-expression`|`statement` の各イテレーションの終了時。 `loop-expression` の実行後に `cond-expression` が実行されます。|通常、ループ インデックスのインクリメントに使用します。|  
  
 次の例では、`for` ステートメントを使用するさまざまな方法を示しています。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main() {  
    // The counter variable can be declared in the init-expression.  
    for (int i = 0; i < 2; i++ ){   
       cout << i;  
    }  
    // Output: 01  
    // The counter variable can be declared outside the for loop.  
    int i;  
    for (i = 0; i < 2; i++){  
        cout << i;  
    }  
    // Output: 01  
    // These for loops are the equivalent of a while loop.  
    i = 0;  
    while (i < 2){  
        cout << i++;  
    }  
}  
    // Output: 012  
```  
  
 `init-expression` と `loop-expression` には、コンマで区切った複数のステートメントを含めることができます。 例えば:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
    int i, j;  
    for ( i = 5, j = 10 ; i + j < 20; i++, j++ ) {  
        cout << "i + j = " << (i + j) << '\n';  
    }  
}  
    // Output:  
    i + j = 15  
    i + j = 17  
    i + j = 19  
```  
  
 `loop-expression` はインクリメントまたはデクリメントするか、他の方法で変更することができます。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main(){  
for (int i = 10; i > 0; i--) {  
        cout << i << ' ';  
    }  
    // Output: 10 9 8 7 6 5 4 3 2 1  
    for (int i = 10; i < 20; i = i+2) {  
        cout << i << ' ';  
    }  
    // Output: 10 12 14 16 18  
```  
  
 A`for`ループが終了したときに、 [break](../cpp/break-statement-cpp.md)、[返す](../cpp/return-statement-cpp.md)、または[goto](../cpp/goto-statement-cpp.md) (ラベル付きステートメントの外側に、**の**ループ) 内で`statement`を実行します。 A[続行](../cpp/continue-statement-cpp.md)内のステートメント、`for`ループは、現在のイテレーションのみを終了します。  
  
 場合`cond-expression`は省略すると、これが true と見なされます、**の**せずループは終了しません、 `break`、 `return`、または`goto`内`statement`です。  
  
 通常、`for` ステートメントの 3 種類のフィールドは初期化、終了のテスト、およびインクリメントのためによく使用されますが、これらの使用に限定されません。 たとえば、次のコードは、数値 0 ～ 4 を出力します。 この場合、`statement` は null ステートメントです。  
  
```cpp  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    int i;  
    for( i = 0; i < 5; cout << i << '\n', i++){  
        ;  
    }  
}  
```  
  
## <a name="for-loops-and-the-c-standard"></a>for ループおよび C++ 標準  
 C++ 標準では `for` ループの終了後に `for` ループ内で宣言された変数がスコープ外に出ることを通知します。 例えば:  
  
```cpp  
for (int i = 0 ; i < 5 ; i++) {  
   // do something  
}  
// i is now out of scope under /Za or /Zc:forScope  
```  
  
 既定では、下にある[/Ze](../build/reference/za-ze-disable-language-extensions.md)で宣言された変数、`for`までスコープ内にループが残り、`for`ループの外側のスコープが終了します。  
  
 [/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)を/Za を指定せずに for ループで宣言された変数の標準動作を有効にします。  
  
 また、次のように、/Ze の下で変数を再宣言するために `for` ループのスコープの相違点を使用することも可能です。  
  
```cpp  
// for_statement5.cpp  
int main(){  
   int i = 0;   // hidden by var with same name declared in for loop  
   for ( int i = 0 ; i < 3; i++ ) {}  
  
   for ( int i = 0 ; i < 3; i++ ) {}  
}  
```  
  
 これにより、`for` ループで宣言された変数の標準動作がより正確に模倣されます。その場合、ループの終了後にスコープ外に出るために `for` ループで宣言された変数が必要です。 変数が `for` ループで宣言される場合、既に同じ名前のローカル変数がある場合でも、コンパイラは `for` ループの外側のスコープでローカル変数に内部的に引き上げます。  
  
## <a name="see-also"></a>関連項目  
 [繰り返しステートメント](../cpp/iteration-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [while ステートメント (C++)](../cpp/while-statement-cpp.md)   
 [do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)   
 [範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)