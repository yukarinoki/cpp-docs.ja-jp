---
title: for ステートメント (C++)
description: Microsoft Visual Studio C++ の標準 C++ for ステートメントへの参照。
f1_keywords:
- for_cpp
ms.date: 07/31/2020
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: b32a50e376113f9f9d550d4984d05fc8c675f14d
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520850"
---
# <a name="for-statement-c"></a>`for`ステートメント (C++)

条件が偽 (false) になるまでステートメントを繰り返し実行します。 範囲ベースのステートメントの詳細につい **`for`** ては、「[範囲ベースの `for` ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)」を参照してください。

## <a name="syntax"></a>構文

> **`for (`** *`init-expression`* **`;`** *`cond-expression`* **`;`** *`loop-expression`* **`)`**\
> &emsp;*`statement`*

## <a name="remarks"></a>Remarks

ステートメントを使用し **`for`** て、指定された回数だけ実行する必要があるループを構築します。

ステートメントは、 **`for`** 次の表に示すように、3つの省略可能な部分で構成されています。

### <a name="for-loop-elements"></a>for ループ要素

| 構文名 | 実行時 | 説明 |
|--|--|--|
| *`init-expression`* | ステートメントの他の要素の前に **`for`** 、 *`init-expression`* が1回だけ実行されます。 次に、コントロールがに渡さ *`cond-expression`* れます。 | ループ インデックスを初期化するためによく使用されます。 式または宣言を含めることができます。 |
| *`cond-expression`* | 最初のイテレーションを含め、の各イテレーションの実行前 *`statement`* 。 *`statement`* が *`cond-expression`* true (0 以外) に評価される場合にのみ、が実行されます。 | 整数型に評価される式、または整数型へのあいまいでない変換が行われるクラス型。 通常、for ループの終了条件をテストするために使用します。 |
| *`loop-expression`* | 各イテレーションの終了時 *`statement`* 。 *`loop-expression`* が実行されると、 *`cond-expression`* が評価されます。 | 通常、ループ インデックスのインクリメントに使用します。 |

次の例では、ステートメントを使用するさまざまな方法を示し **`for`** ます。

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
    // Output: 01
}
```

*`init-expression`* と *`loop-expression`* には、コンマで区切られた複数のステートメントを含めることができます。 次に例を示します。

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

*`loop-expression`* インクリメントまたはデクリメントしたり、他の方法で変更したりできます。

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

ループは、内の、、、 **`for`** [`break`](../cpp/break-statement-cpp.md) または[return](../cpp/return-statement-cpp.md) [`goto`](../cpp/goto-statement-cpp.md) (ループの外側のラベル付きステートメントに対する **`for`** ) が実行されると終了 *`statement`* します。 [`continue`](../cpp/continue-statement-cpp.md)ループ内のステートメントは **`for`** 、現在のイテレーションのみを終了します。

を省略した場合は、と見なされ、 *`cond-expression`* **`true`** **`for`** **`break`** **`return`** 内で、、またはがないとループは終了しません **`goto`** *`statement`* 。

ステートメントの3つのフィールドは **`for`** 通常、初期化、終了のテスト、および増分のために使用されますが、これらのフィールドはこれらの使用に限定されません。 たとえば、次のコードは、数値 0 ～ 4 を出力します。 この場合、 *`statement`* は null ステートメントです。

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

## <a name="for-loops-and-the-c-standard"></a>`for`ループと C++ 標準

C++ 標準では、ループの終了後に、ループで宣言された変数がスコープ外に出てくるということが示されて **`for`** **`for`** います。 次に例を示します。

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

既定では、 [/ze](../build/reference/za-ze-disable-language-extensions.md)では、ループ内で宣言された変数は、 **`for`** ループの外側のスコープが終了するまでスコープ内に残り **`for`** ます。

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)を使用すると、for ループで宣言された変数の標準動作が有効になりますが、を指定する必要は `/Za` ありません。

次のように、ループのスコープの違いを使用して、で変数を再宣言することもでき **`for`** `/Ze` ます。

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

この動作は、ループで宣言された変数の標準動作をよりよく模倣して **`for`** います。ループの完了後、ループで宣言された変数がスコープ外に出る必要があり **`for`** ます。 変数がループ内で宣言されている場合、 **`for`** コンパイラは内部的にループの外側のスコープ内のローカル変数にその変数を昇格させ **`for`** ます。 同じ名前のローカル変数が既に存在する場合でも昇格されます。

## <a name="see-also"></a>関連項目

[繰り返しステートメント](../cpp/iteration-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[while ステートメント (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)<br/>
[範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)
