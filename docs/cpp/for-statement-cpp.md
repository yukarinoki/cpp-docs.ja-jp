---
title: for ステートメント (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- for keyword [C++]
ms.assetid: 6c7d01b3-c4c1-4c6a-aa58-e2d198f33d4a
ms.openlocfilehash: e3dfdb45bdf8a508eca9d29e90b3f7c05e7b147d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179914"
---
# <a name="for-statement-c"></a>for ステートメント (C++)

条件が偽 (false) になるまでステートメントを繰り返し実行します。 範囲ベースの for ステートメントの詳細については、「[範囲ベースの ForC++ステートメント ()](../cpp/range-based-for-statement-cpp.md)」を参照してください。

## <a name="syntax"></a>構文

```
for ( init-expression ; cond-expression ; loop-expression )
    statement;
```

## <a name="remarks"></a>解説

**For**ステートメントを使用して、指定された回数だけ実行する必要があるループを構築します。

**For**ステートメントは、次の表に示すように、3つの省略可能な部分で構成されています。

### <a name="for-loop-elements"></a>for ループ要素

|構文の名前|実行タイミング|説明|
|-----------------|-------------------|-----------------|
|`init-expression`|**For**ステートメントの他の要素の前には、`init-expression` が1回だけ実行されます。 その後、制御は `cond-expression` に渡されます。|ループ インデックスを初期化するためによく使用されます。 式または宣言を含めることができます。|
|`cond-expression`|最初のイテレーションを含む `statement` の各イテレーションの実行前。 `statement` は、`cond-expression` が true (0 以外) に評価された場合にのみ実行されます。|整数型に評価される式、または整数型へのあいまいでない変換が行われるクラス型。 通常、for ループの終了条件をテストするために使用します。|
|`loop-expression`|`statement` の各イテレーションの終了時。 `loop-expression` の実行後に `cond-expression` が実行されます。|通常、ループ インデックスのインクリメントに使用します。|

次の例では、 **for**ステートメントを使用するさまざまな方法を示します。

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

**For**ループは、`statement` 内の[break](../cpp/break-statement-cpp.md)、 [return](../cpp/return-statement-cpp.md)、または[goto](../cpp/goto-statement-cpp.md) (for ループの外側**の**ラベル付きステートメントに対する) が実行されると終了します。 **For**ループ内の[continue](../cpp/continue-statement-cpp.md)ステートメントは、現在のイテレーションのみを終了します。

`cond-expression` を省略すると、true と見なされ、 **for**ループは、 **break**、 **return**、または**goto**を使用せずに `statement`内に終了しません。

通常、 **for**ステートメントの3つのフィールドは初期化、終了のテスト、および増分のために使用されますが、これらのフィールドはこれらの使用に限定されません。 たとえば、次のコードは、数値 0 ～ 4 を出力します。 この場合、`statement` は null ステートメントです。

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

標準C++では、 **for ループで**宣言された変数が**for**ループの終了後にスコープ外に出るということが示されています。 次に例を示します。

```cpp
for (int i = 0 ; i < 5 ; i++) {
   // do something
}
// i is now out of scope under /Za or /Zc:forScope
```

既定では、 [/ze](../build/reference/za-ze-disable-language-extensions.md)では**for ループで**宣言された変数は、 **for**ループの外側のスコープが終了するまでスコープ内に残ります。

[/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)は、for ループで宣言された変数の標準動作を有効にします。 `/Za`を指定する必要はありません。

For ループのスコープの違いを使用して、次**の**ように `/Ze` で変数を再宣言することもできます。

```cpp
// for_statement5.cpp
int main(){
   int i = 0;   // hidden by var with same name declared in for loop
   for ( int i = 0 ; i < 3; i++ ) {}

   for ( int i = 0 ; i < 3; i++ ) {}
}
```

これは、for ループで宣言された変数の標準動作をよりよく模倣しています。**そのために**は、ループの完了後に**for**ループで宣言された変数がスコープ外に出る必要があります。 変数が**for**ループで宣言されている場合、同じ名前を持つローカル変数が既に存在する場合でも、コンパイラは内部**的に for ループの**外側のスコープ内のローカル変数にその変数を昇格させます。

## <a name="see-also"></a>参照

[繰り返しステートメント](../cpp/iteration-statements-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)<br/>
[while ステートメント (C++)](../cpp/while-statement-cpp.md)<br/>
[do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)<br/>
[範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)
