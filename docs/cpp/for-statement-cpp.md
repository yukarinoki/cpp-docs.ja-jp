---
title: for ステートメント (C++)
description: ステートメントの標準 C++ への参照です。
f1_keywords:
- for_cpp
ms.date: 04/14/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: 92f7ae4b1f2fbaaf710cd5a8739b78cb98a0accb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375383"
---
# <a name="for-statement-c"></a>for ステートメント (C++)

条件が偽 (false) になるまでステートメントを繰り返し実行します。 範囲ベースの for ステートメントについては、「ステートメントの[範囲ベース (C++)」](../cpp/range-based-for-statement-cpp.md)を参照してください。

## <a name="syntax"></a>構文

> **`for (`***init 式***`;`***の cond 式***`;`***ループ式***`)`**\
> &nbsp;&nbsp;&nbsp;&nbsp;_ステートメント_**`;`**

## <a name="remarks"></a>解説

**for**ステートメントを使用して、指定した回数実行する必要があるループを構築します。

**for**ステートメントは、次の表に示すように、3 つの省略可能な部分で構成されます。

### <a name="for-loop-elements"></a>for ループ要素

|構文の名前|実行タイミング|説明|
|-----------------|-------------------|-----------------|
|`init-expression`|**for**ステートメントの他の要素の前`init-expression`に、1 回だけ実行されます。 その後、制御は `cond-expression` に渡されます。|ループ インデックスを初期化するためによく使用されます。 式または宣言を含めることができます。|
|`cond-expression`|最初のイテレーションを含む `statement` の各イテレーションの実行前。 `statement` は、`cond-expression` が true (0 以外) に評価された場合にのみ実行されます。|整数型に評価される式、または整数型へのあいまいでない変換が行われるクラス型。 通常、for ループの終了条件をテストするために使用します。|
|`loop-expression`|`statement` の各イテレーションの終了時。 `loop-expression` の実行後に `cond-expression` が実行されます。|通常、ループ インデックスのインクリメントに使用します。|

次の例は **、for**ステートメントを使用するさまざまな方法を示しています。

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

`init-expression` と `loop-expression` には、コンマで区切った複数のステートメントを含めることができます。 次に例を示します。

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

**for**ループは[、for](../cpp/break-statement-cpp.md)**ループの**外側にあるラベル付きのステートメントに対してブレーク 、[リターン](../cpp/return-statement-cpp.md)、または`statement`[goto](../cpp/goto-statement-cpp.md)が実行されると終了します。 **for**ループ内の[continue](../cpp/continue-statement-cpp.md)ステートメントは、現在の反復のみを終了します。

省略`cond-expression`すると、 と`true`見なされ、 **for**ループは、 が**中断**、**戻り**、または 内の`statement`**goto**なしで終了しません。

**for**ステートメントの 3 つのフィールドは、通常、初期化、終了のテスト、インクリメントに使用されますが、これらの使用に限定されません。 たとえば、次のコードは、数値 0 ～ 4 を出力します。 この場合、`statement` は null ステートメントです。

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

C++ 標準では **、for**ループで宣言された変数は **、for**ループの終了後にスコープ外に出ると言います。 次に例を示します。

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

デフォルトでは[、/Ze](../build/reference/za-ze-disable-language-extensions.md)の下で **、for**ループで宣言された変数は **、for**ループの外側のスコープが終了するまでスコープ内に残ります。

[/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)を使用すると、 を指定`/Za`しなくても for ループで宣言された変数の標準動作が可能になります。

for**ループの**スコープの違いを使用して、次`/Ze`のように変数を再宣言することもできます。

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

この動作は **、for**ループで宣言された変数の標準動作をより厳密に模倣します。 **for** **for**ループで変数が宣言されると、コンパイラは内部的に**for**ループの外側のスコープ内のローカル変数に変数を昇格します。 同じ名前のローカル変数が既に存在する場合でも、昇格されます。

## <a name="see-also"></a>関連項目

[繰り返しステートメント](../cpp/iteration-statements-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)<br/>
[while ステートメント (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)<br/>
[範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)
