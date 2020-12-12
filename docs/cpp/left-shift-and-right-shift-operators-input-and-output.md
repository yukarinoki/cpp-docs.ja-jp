---
description: 詳細については、左シフト演算子と右シフト演算子 ( &gt; &gt; および &lt; &lt; ) に関するページを参照してください。
title: 左シフト演算子と右シフト演算子 ( &gt; &gt; および &lt; &lt; )
ms.date: 08/13/2018
f1_keywords:
- <<
- '>>'
helpviewer_keywords:
- << operator [C++], with specific objects
- left shift operators [C++]
- right shift operators [C++]
- bitwise-shift operators [C++]
- '>> operator'
- shift operators [C++]
- operators [C++], shift
ms.assetid: 25fa0cbb-5fdd-4657-8745-b35f7d8f1606
ms.openlocfilehash: e13333d178fdfbb44631b9a2aced9ed2a48ad871
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321019"
---
# <a name="left-shift-and-right-shift-operators-gtgt-and-ltlt"></a>左シフト演算子と右シフト演算子 ( &gt; &gt; および &lt; &lt; )

ビットごとのシフト演算子は、右シフト演算子 ( **&gt;&gt;** ) であり、 *シフト式* のビットを右に移動し、左シフト演算子 () を使用して、 **&lt;&lt;** *シフト式* のビットを左に移動します。 <sup>1</sup>

## <a name="syntax"></a>構文

> *シフト式* `<<`*加法-式*\
> *shift-expression* `>>` *additive-expression*

## <a name="remarks"></a>解説

> [!IMPORTANT]
> 次の説明と例は、x86 および x64 アーキテクチャの Windows で有効です。 ARM デバイスの場合、左シフト演算子と右シフト演算子の実装は大きく異なります。 詳細については、 [HELLO ARM](https://devblogs.microsoft.com/cppblog/hello-arm-exploring-undefined-unspecified-and-implementation-defined-behavior-in-c/) のブログ記事の「シフト演算子」セクションを参照してください。

## <a name="left-shifts"></a>左シフト

左シフト演算子を使用すると、 *シフト式* のビットが、 *加法式* で指定された位置の数だけ左にシフトされます。 シフト演算により空いたビット位置はゼロで埋められます。 左シフトは論理シフトです (符号ビットを含めてシフトし、溢れたビットは捨てます)。 ビットごとのシフトの種類の詳細については、「 [ビットごとのシフト](https://en.wikipedia.org/wiki/Bitwise_shift)」を参照してください。

次の例では、符号なし数値を使用した左シフト演算を示しています。 値をビットセットとして表すことでビットがどうなるかを示しています。 詳細については、「 [ビットセットクラス](../standard-library/bitset-class.md)」を参照してください。

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned short short1 = 4;
    bitset<16> bitset1{short1};   // the bitset representation of 4
    cout << bitset1 << endl;  // 0b00000000'00000100

    unsigned short short2 = short1 << 1;     // 4 left-shifted by 1 = 8
    bitset<16> bitset2{short2};
    cout << bitset2 << endl;  // 0b00000000'00001000

    unsigned short short3 = short1 << 2;     // 4 left-shifted by 2 = 16
    bitset<16> bitset3{short3};
    cout << bitset3 << endl;  // 0b00000000'00010000
}
```

符号付き数値をシフトして符号ビットが影響を受ける場合、結果は未定義です。 次の例では、1ビットが符号ビット位置に左シフトされたときの動作を示します。

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short short1 = 16384;
    bitset<16> bitset1(short1);
    cout << bitset1 << endl;  // 0b01000000'00000000

    short short3 = short1 << 1;
    bitset<16> bitset3(short3);  // 16384 left-shifted by 1 = -32768
    cout << bitset3 << endl;  // 0b10000000'00000000

    short short4 = short1 << 14;
    bitset<16> bitset4(short4);  // 4 left-shifted by 14 = 0
    cout << bitset4 << endl;  // 0b00000000'00000000
}
```

## <a name="right-shifts"></a>右シフト

右シフト演算子を使用すると、 *シフト式* のビットパターンが *加法式* で指定された位置の数だけ右にシフトされます。 符号なし数値の場合、シフト演算により空いたビット位置はゼロで埋められます。 符号付き数値の場合、その空いたビット位置は符号ビットで埋められます。 つまり、数値が正である場合は 0 を使用し、数値が負である場合は 1 を使用します。

> [!IMPORTANT]
> 符号付きの負の数値の右シフトの結果は実装に依存します。 Microsoft C++ コンパイラでは、空いたビット位置を埋めるために符号ビットが使用されますが、他の実装もこれを実行するという保証はありません。

次の例では、符号なし数値を使用した左シフト演算を示しています。

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned short short11 = 1024;
    bitset<16> bitset11{short11};
    cout << bitset11 << endl;     // 0b00000100'00000000

    unsigned short short12 = short11 >> 1;  // 512
    bitset<16> bitset12{short12};
    cout << bitset12 << endl;     // 0b00000010'00000000

    unsigned short short13 = short11 >> 10;  // 1
    bitset<16> bitset13{short13};
    cout << bitset13 << endl;     // 0b00000000'00000001

    unsigned short short14 = short11 >> 11;  // 0
    bitset<16> bitset14{short14};
    cout << bitset14 << endl;     // 0b00000000'00000000
}
```

次の例では、正の符号付き数値を使用した右シフト演算を示しています。

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short short1 = 1024;
    bitset<16> bitset1(short1);
    cout << bitset1 << endl;     // 0b00000100'00000000

    short short2 = short1 >> 1;  // 512
    bitset<16> bitset2(short2);
    cout << bitset2 << endl;     // 0b00000010'00000000

    short short3 = short1 >> 11;  // 0
    bitset<16> bitset3(short3);
    cout << bitset3 << endl;     // 0b00000000'00000000
}
```

次の例では、負の符号付き整数を使用した右シフト演算を示しています。

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    short neg1 = -16;
    bitset<16> bn1(neg1);
    cout << bn1 << endl;  // 0b11111111'11110000

    short neg2 = neg1 >> 1; // -8
    bitset<16> bn2(neg2);
    cout << bn2 << endl;  // 0b11111111'11111000

    short neg3 = neg1 >> 2; // -4
    bitset<16> bn3(neg3);
    cout << bn3 << endl;  // 0b11111111'11111100

    short neg4 = neg1 >> 4; // -1
    bitset<16> bn4(neg4);
    cout << bn4 << endl;  // 0b11111111'11111111

    short neg5 = neg1 >> 5; // -1
    bitset<16> bn5(neg5);
    cout << bn5 << endl;  // 0b11111111'11111111
}
```

## <a name="shifts-and-promotions"></a>シフトと昇格

シフト演算子の両側の式は整数型であることが必要です。 整数の上位変換は、「 [標準変換](standard-conversions.md)」で説明されている規則に従って実行されます。 結果の型は、昇格させた *シフト式* の型と同じです。

次の例では、型の変数 **`char`** がに昇格され **`int`** ます。

```cpp
#include <iostream>
#include <typeinfo>

using namespace std;

int main() {
    char char1 = 'a';

    auto promoted1 = char1 << 1;   // 194
    cout << typeid(promoted1).name() << endl;  // int

    auto promoted2 = char1 << 10;  // 99328
    cout << typeid(promoted2).name() << endl;  // int
}
```

## <a name="additional-details"></a>追加の詳細

*加算式* が負の場合、または *加算式* が (昇格された)*シフト式* のビット数以上の場合、シフト演算の結果は未定義になります。 *加法式* が0の場合、シフト演算は実行されません。

```cpp
#include <iostream>
#include <bitset>

using namespace std;

int main() {
    unsigned int int1 = 4;
    bitset<32> b1{int1};
    cout << b1 << endl;    // 0b00000000'00000000'00000000'00000100

    unsigned int int2 = int1 << -3;  // C4293: '<<' : shift count negative or too big, undefined behavior
    unsigned int int3 = int1 >> -3;  // C4293: '>>' : shift count negative or too big, undefined behavior
    unsigned int int4 = int1 << 32;  // C4293: '<<' : shift count negative or too big, undefined behavior
    unsigned int int5 = int1 >> 32;  // C4293: '>>' : shift count negative or too big, undefined behavior
    unsigned int int6 = int1 << 0;
    bitset<32> b6{int6};
    cout << b6 << endl;    // 0b00000000'00000000'00000000'00000100 (no change)
}
```

## <a name="footnotes"></a>脚注

<sup>1</sup> 次に示すのは、C++ 11 ISO 仕様におけるシフト演算子の説明です (この例では、/ISO/IEC 14882-2011 [2012])、セクション5.8.2 と5.8.3。

`E1 << E2` の結果は、`E1` を `E2` ビット左にシフトした値であり、空いたビットはゼロで埋められる。 `E1`に符号なしの型がある場合、結果の値は **E1 × 2**<sup>**E2**</sup>になり、剰余が結果の型で表現可能な最大値を超えています。 それ以外の場合、 `E1` に符号付きの型と負でない値が含まれ、 **E1 × 2**<sup>**E2**</sup> が結果の型の対応する符号なしの型で表現できる場合、結果の型に変換された値が結果の値になります。それ以外の場合、動作は定義されません。

`E1 >> E2` の結果は、`E1` を `E2` ビット右にシフトした値である。 `E1`に符号なしの型がある場合、または `E1` に符号付きの型と負でない値が含まれている場合、結果の値は **E1/2**<sup>**E2**</sup>の商の整数部分になります。 `E1` が符号付きの型で値が負の場合、結果として得られる値は実装に依存する。

## <a name="see-also"></a>関連項目

[二項演算子を含む式](../cpp/expressions-with-binary-operators.md)<br/>
[C++ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
