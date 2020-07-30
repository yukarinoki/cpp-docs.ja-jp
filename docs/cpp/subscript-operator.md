---
title: 添字演算子 []
ms.date: 11/04/2016
f1_keywords:
- '[]'
helpviewer_keywords:
- operators [C++], subscript
- postfix operators [C++]
- '[] operator'
- subscript operator [C++], syntax
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
ms.openlocfilehash: a4eb878a18aa38b7047104903d10d96d66cc6720
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231092"
---
# <a name="subscript-operator-"></a>添字演算子 []

## <a name="syntax"></a>構文

```
postfix-expression [ expression ]
```

## <a name="remarks"></a>解説

後置式 (プライマリ式でもかまいません) で、添字演算子 **[]** を指定すると、配列のインデックスが指定されます。

C++/CLI のマネージ配列の詳細については、「[配列](../extensions/arrays-cpp-component-extensions.md)」を参照してください。

通常、*後置式*によって表される値は、配列識別子などのポインター値で、 *expression*は整数値 (列挙型を含む) です。 ただし、構文上必要なのは、一方の式がポインター型で、もう一方が整数型であることです。 したがって、整数値が*後置式*の位置にあり、ポインター値が*式*または添字の位置の角かっこ内にある可能性があります。 次のコードがあるとします。

```cpp
int nArray[5] = { 0, 1, 2, 3, 4 };
cout << nArray[2] << endl;            // prints "2"
cout << 2[nArray] << endl;            // prints "2"
```

上の例では、式 `nArray[2]` は `2[nArray]` と同じです。 その理由は、添字式の結果は次のように指定されているためです `e1[e2]` 。

`*((e2) + (e1))`

式によって生成されたアドレスは、アドレス*e1*の*e2*バイトではありません。 代わりに、アドレスは配列*e2*内の次のオブジェクトを生成するようにスケーリングされます。 次に例を示します。

```cpp
double aDbl[2];
```

とのアドレス `aDb[0]` は `aDb[1]` 8 バイトで、型のオブジェクトのサイズ **`double`** です。 オブジェクト型に基づくこのスケーリングは、C++ 言語によって自動的に行われ、ポインター型のオペランドの加算および減算について説明する[加法演算子](../cpp/additive-operators-plus-and.md)で定義されます。

添字式には、次のように複数の添字がある場合があります。

*expression1* **[** *expression2* **] [** *expression3* **]** ...

添字式は、左から右へ関連付けられます。 左端の添字式、*expression1* **[** *expression2* **]** が最初に評価されます。 *expression1* と *expression2* を加算した結果として得られるアドレスからポインター式が形成され、次にこのポインター式に *expression3* が加算されて新しいポインター式が形成されます。このようにして、最後の添字式が加算されるまで処理が行われます。 間接演算子 () は、 <strong>\*</strong> 最終的なポインター値が配列型を指す場合を除き、最後の添字式が評価された後に適用されます。

複数の添字を持つ式は、多次元配列の要素を参照します。 多次元配列は、要素が配列である配列です。 たとえば、3 次元配列の最初の要素は 2 次元配列です。 次の例では、文字の単純な 2 次元配列を宣言して初期化しています。

```cpp
// expre_Subscript_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
#define MAX_ROWS 2
#define MAX_COLS 2

int main() {
  char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };
  for ( int i = 0; i < MAX_ROWS; i++ )
     for ( int j = 0; j < MAX_COLS; j++ )
        cout << c[ i ][ j ] << endl;
}
```

## <a name="positive-and-negative-subscripts"></a>正と負の添字

配列の最初要素は要素 0 です。 C++ 配列の範囲は、 *array*[0] から*array*[*size* -1] です。 ただし、C++ は、正の数の添字と負の数の添字をサポートします。 負の添字は配列の範囲内になる必要があり、そうでない場合、結果は予測不能となります。 次のコードは正および負の配列添字を示します。

```cpp
#include <iostream>
using namespace std;

int main() {
    int intArray[1024];
    for (int i = 0, j = 0; i < 1024; i++)
    {
        intArray[i] = j++;
    }

    cout << intArray[512] << endl;   // 512

    cout << 257[intArray] << endl;   // 257

    int *midArray = &intArray[512];  // pointer to the middle of the array

    cout << midArray[-256] << endl;  // 256

    cout << intArray[-256] << endl;  // unpredictable, may crash
}
```

最後の行の負の添字は、 **`int`** 配列の元よりもメモリの下位にあるアドレス256の位置を指しているため、実行時エラーが発生する可能性があります。 ポインター `midArray` はの中央に初期化されます `intArray` 。したがって、正の配列インデックスと負の配列インデックスの両方を使用することができます (ただし、これは危険です)。 配列添字のエラーは、コンパイル時のエラーを生成しませんが、予測できない結果になります。

添字演算子は可換です。 したがって、添字演算子がオーバーロードされていない限り、式*array*[*index*] と*index*[*array*] は等価であることが保証されます (「オーバーロードされた[演算子](../cpp/operator-overloading.md)」を参照してください)。 最初の形式は、共通のコーディングの推奨事項ですが、どちらの方法でも動作します。

## <a name="see-also"></a>関連項目

[後置式](../cpp/postfix-expressions.md)<br/>
[C++ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[配列](../cpp/arrays-cpp.md)<br/>
[1次元配列](../c-language/one-dimensional-arrays.md)<br/>
[多次元配列](../c-language/multidimensional-arrays-c.md)<br/>
