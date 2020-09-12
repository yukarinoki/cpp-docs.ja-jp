---
title: '&lt;ビット &gt; 関数'
description: 個々のビットとビットシーケンスのアクセス、操作、および処理を行う関数
ms.date: 08/28/2020
f1_keywords:
- bit/std::bit_cast
- bit/std::has_single_bit
- bit/std::bit_ceil
- bit/std::bit_floor
- bit/std::bit_width
- bit/std::rotl
- bit/std::rotr
- bit/std::countl_zero
- bit/std::countl_one
- bit/std::countr_zero
- bit/std::countr_one
- bit/std::popcount
helpviewer_keywords:
- std::bit [C++], bit_cast
- std::bit [C++], has_single_bit
- std::bit [C++], bit_ceil
- std::bit [C++], bit_floor
- std::bit [C++], bit_width
- std::bit [C++], rotl
- std::bit [C++], rotr
- std::bit [C++], countl_zero
- std::bit [C++], countl_one
- std::bit [C++], countr_zero
- std::bit [C++], countr_one
- std::bit [C++], popcount
ms.openlocfilehash: a2408df9aa13c6e714f615561871397be17fc4a3
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039814"
---
# <a name="ltbitgt-functions"></a>&lt;ビット &gt; 関数

ヘッダーには、 \<bit> 次の非メンバーテンプレート関数が含まれています。

| **非メンバー関数** | **説明** |
|--------|---------|
|[bit_cast](#bit_cast) | オブジェクト表現を1つの型から別の型に再解釈します。 |
|[bit_ceil](#bit_ceil) | 値以上の2の最小指数を求めます。 |
|[bit_floor](#bit_floor) | 値を超えない2の最大の累乗を求めます。 |
|[bit_width](#bit_width) | 値を表すために必要な最小ビット数を求めます。 |
|[countl_zero](#countl_zero) | 最上位ビットから開始して、連続するビットの数を0に設定します。 |
|[countl_one](#countl_one) | 最上位ビットから順に1に設定される連続ビットの数をカウントします。 |
|[countr_zero](#countr_zero) | 最下位ビットから開始して、連続するビットの数を0に設定します。 |
|[countr_one](#countl_one) | 最下位ビットから順に1に設定される連続ビットの数をカウントします。 |
|[has_single_bit](#has_single_bit) | 値に1ビットだけが設定されているかどうかを確認します。 これは、値が2の累乗であるかどうかをテストすることと同じです。 |
|[popcount](#popcount) | 1に設定されたビット数をカウントします。 |
|[rotl](#rotl) | ビットごとの左回転の結果を計算します。 |
|[rotr](#rotr) | ビットごとの右回転の結果を計算します。 |

## <a name="bit_cast"></a>`bit_cast`

型のオブジェクトから `From` 型の新しいオブジェクトにビットパターンをコピー `To` します。

```cpp
template <class To, class From>
[[nodiscard]] constexpr To bit_cast(const From& from) noexcept;
```

### <a name="parameters"></a>パラメーター

*宛先*\
出力の型。

*差出人*\
変換する値の型。

*差出人*\
変換する値。

### <a name="return-value"></a>戻り値

`To` 型のオブジェクト。

に埋め込みビットが存在しない場合、結果の各ビットがの対応するビットと一致し `from` `To` ます。この場合、結果のビットは指定されません。

### <a name="example"></a>例

```cpp
#include <bit>
#include <iostream>

int main()
{
    float f = std::numeric_limits<float>::infinity();
    int i = std::bit_cast<int>(f);
    std::cout << "float f = " << std::hex << f
              << "\nstd::bit_cat<int>(f) = " << std::hex << i << '\n';
    return 0;
}
```

```Output
float f = inf
std::bit_cat<int>(f) = 7f800000
```

### <a name="remarks"></a>注釈

多くの場合、下位レベルのコードでは、ある型のオブジェクトを別の型として解釈する必要があります。 再解釈されたオブジェクトは元のと同じビット表現を持ちますが、型は異なります。

`reinterpret_cast`、、またはを使用する代わりに、これらの `memcpy()` `bit_cast()` 変換を行う方がより適切な方法です。 次のような場合に適しています。
- `bit_cast()` は `constexpr` です
- `bit_cast()` 型は、普通にコピー可能で、同じサイズである必要があります。 これにより、およびを使用して発生する可能性のある潜在的な問題を回避でき `reinterpret_cast` `memcpy` ます。これは、不注意によるコピーが可能な型を誤って変換するために使用される可能性があるためです。 また、 `memcpy()` 同じサイズではない型を誤ってコピーする場合にも使用できます。 たとえば、double (8 バイト) が符号なし整数 (4 バイト)、またはその逆になります。

このオーバーロードは、次の場合にのみ、オーバーロードの解決に関与します。
-  `sizeof(To) == sizeof(From)`
- `To` および `From` は [is_trivially_copyable](is-trivially-copyable-class.md)です。

この関数テンプレートは `constexpr` `To` 、、 `From` 、およびサブオブジェクトの型がである場合にのみ、次のようになります。
- 共用体型またはポインター型ではありません
- メンバー型へのポインターではありません
- volatile で修飾されていません
- 参照型の非静的データメンバーはありません

## <a name="bit_ceil"></a>`bit_ceil`

値以上の2の最小指数を求めます。 たとえば、が指定されている場合、は `3` を返し `4` ます。

```cpp
template<class T>
[[nodiscard]] constexpr T bit_ceil(T value);
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

 次の2つ以上の最小のべき乗 `value` 。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (auto i = 0u; i < 6u; ++i) // bit_ceil() takes an unsigned integer type
    {
        auto nextClosestPowerOf2 = std::bit_ceil(i);
        std::cout << "\nbit_ceil(0b" << std::bitset<4>(i) << ") = "
                  << "0b" << std::bitset<4>(nextClosestPowerOf2);
    }
    return 0;
}
```

```Output
bit_ceil(0b0000) = 0b0001
bit_ceil(0b0001) = 0b0001
bit_ceil(0b0010) = 0b0010
bit_ceil(0b0011) = 0b0100
bit_ceil(0b0100) = 0b0100
bit_ceil(0b0101) = 0b1000
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="bit_floor"></a>`bit_floor`

値を超えない2の最大の累乗を求めます。 たとえば、が指定されている場合、は `5` を返し `4` ます。

```cpp
template< class T >
[[nodiscard]] constexpr T bit_floor(T value) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

次の値より大きくない2の最大のべき乗 `value` 。
`value`が0の場合、は0を返します。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (auto i = 0u; i < 6u; ++i) // bit_floor() takes an unsigned integer type
    {
        auto previousPowerOf2 = std::bit_floor(i);
        std::cout << "\nbit_floor(0b" << std::bitset<4>(i) << ") = 0b"
                  << std::bitset<4>(previousPowerOf2);
    }
    return 0;
}
```

```Output
bit_floor(0b0000) = 0b0000
bit_floor(0b0001) = 0b0001
bit_floor(0b0010) = 0b0010
bit_floor(0b0011) = 0b0010
bit_floor(0b0100) = 0b0100
bit_floor(0b0101) = 0b0100
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="bit_width"></a>`bit_width`

値を表すために必要な最小ビット数を求めます。

たとえば、5 (0b101) が指定されている場合、値5を表す3つのバイナリビットを受け取るため、は3を返します。

```cpp
template<class T>
[[nodiscard]] constexpr T bit_width(T value) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

を表すために必要なビット数 `value` 。
`value`が0の場合、は0を返します。

### <a name="example"></a>例

```cpp
#include <bit>
#include <iostream>

int main()
{
    for (unsigned i=0u; i <= 8u; ++i)
    {
        std::cout << "\nbit_width(" << i << ") = "
                  << std::bit_width(i);
    }
    return 0;
}
```

```Output
bit_width(0) = 0
bit_width(1) = 1
bit_width(2) = 2
bit_width(3) = 2
bit_width(4) = 3
bit_width(5) = 3
bit_width(6) = 3
bit_width(7) = 3
bit_width(8) = 4
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="countl_zero"></a>`countl_zero`

最上位ビットから開始して、連続するビットの数を0に設定します。

```cpp
template<class T>
[[nodiscard]] constexpr int countl_zero(T value) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

最上位ビットから始まる、連続した0ビットの数。 \
`value`が0の場合、の型のビット数 `value` 。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (unsigned char result = 0, i = 0; i < 9; i++)
    {
        std::cout << "\ncountl_zero(0b" << std::bitset<8>(result) << ") = " << std::countl_zero(result);
        result = result == 0 ? 1 : result * 2;
    }
    return 0;
}
```

```Output
countl_zero(0b00000000) = 8
countl_zero(0b00000001) = 7
countl_zero(0b00000010) = 6
countl_zero(0b00000100) = 5
countl_zero(0b00001000) = 4
countl_zero(0b00010000) = 3
countl_zero(0b00100000) = 2
countl_zero(0b01000000) = 1
countl_zero(0b10000000) = 0
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="countl_one"></a>`countl_one`

最上位ビットから順に1に設定される連続ビットの数をカウントします。

```cpp
template<class T>
[[nodiscard]] constexpr int countl_one(T value) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

最上位ビットから順に1に設定される連続ビットの数。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char value = 0;
    for (unsigned char bit = 128; bit > 0; bit /= 2)
    {
        value |= bit;
        std::cout << "\ncountl_one(0b" << std::bitset<8>(value) << ") = "
                  << std::countl_one(value);
    }
    return 0;
}
```

```Output
countl_one(0b10000000) = 1
countl_one(0b11000000) = 2
countl_one(0b11100000) = 3
countl_one(0b11110000) = 4
countl_one(0b11111000) = 5
countl_one(0b11111100) = 6
countl_one(0b11111110) = 7
countl_one(0b11111111) = 8
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="countr_zero"></a>`countr_zero`

最下位ビットから開始して、連続するビットの数を0に設定します。

```cpp
template<class T>
[[nodiscard]] constexpr int countr_zero(T value) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

最下位ビットから始まる、連続した0ビットの数。 \
`value`が0の場合、の型のビット数 `value` 。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    for (unsigned char result = 0, i = 0; i < 9; i++)
    {
        std::cout << "\ncountr_zero(0b" << std::bitset<8>(result) << ") = "
                  << std::countr_zero(result);
        result = result == 0 ? 1 : result * 2;
    }
    return 0;
}
```

```Output
countr_zero(0b00000000) = 8
countr_zero(0b00000001) = 0
countr_zero(0b00000010) = 1
countr_zero(0b00000100) = 2
countr_zero(0b00001000) = 3
countr_zero(0b00010000) = 4
countr_zero(0b00100000) = 5
countr_zero(0b01000000) = 6
countr_zero(0b10000000) = 7
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="countr_one"></a>`countr_one`

最下位ビットから順に1に設定される連続ビットの数をカウントします。

```cpp
template<class T>
[[nodiscard]] constexpr int countr_one(T value) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

最下位ビットから順に1に設定される連続ビットの数。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char value = 0;
    for (int bit = 1; bit <= 128; bit *= 2)
    {
        value |= bit;
        std::cout << "\ncountr_one(0b" << std::bitset<8>(value) << ") = "
                  << std::countr_one(value);
    }
    return 0;
}
```

```Output
countr_one(0b00000001) = 1
countr_one(0b00000011) = 2
countr_one(0b00000111) = 3
countr_one(0b00001111) = 4
countr_one(0b00011111) = 5
countr_one(0b00111111) = 6
countr_one(0b01111111) = 7
countr_one(0b11111111) = 8
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="has_single_bit"></a>`has_single_bit`

値にビットセットが1つだけ含まれているかどうかを確認します。これは、値が2の累乗であるかどうかをテストすることと同じです。
 
```cpp
template <class T>
[[nodiscard]] constexpr bool has_single_bit(T value) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

`true``value`のビットセットが1つしかない場合は、が2の累乗であることも意味 `value` します。 それ以外の場合は `false`。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>
#include <iomanip>

int main()
{
    for (auto i = 0u; i < 10u; ++i)
    {
        std::cout << "has_single_bit(0b" << std::bitset<4>(i) << ") = "
                  << std::boolalpha << std::has_single_bit(i) << '\n';
    }
    return 0;
}
```

```Output
has_single_bit(0b0000) = false
has_single_bit(0b0001) = true
has_single_bit(0b0010) = true
has_single_bit(0b0011) = false
has_single_bit(0b0100) = true
has_single_bit(0b0101) = false
has_single_bit(0b0110) = false
has_single_bit(0b0111) = false
has_single_bit(0b1000) = true
has_single_bit(0b1001) = false
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="popcount"></a>`popcount`

符号なし整数値で1に設定されたビット数をカウントします。
 
```cpp
template<class T>
[[nodiscard]] constexpr int popcount(T value) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
テストする符号なし整数値。

### <a name="return-value"></a>戻り値

の1に設定されたビット数 `value` 。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
   for (unsigned char value = 0; value < 16; value++)
    {
        std::cout << "\npopcount(0b" << std::bitset<4>(value) << ") = "
                  << std::popcount(value);
    }
    return 0;
}
```

```Output
popcount(0b0000) = 0
popcount(0b0001) = 1
popcount(0b0010) = 1
popcount(0b0011) = 2
popcount(0b0100) = 1
popcount(0b0101) = 2
popcount(0b0110) = 2
popcount(0b0111) = 3
popcount(0b1000) = 1
popcount(0b1001) = 2
popcount(0b1010) = 2
popcount(0b1011) = 3
popcount(0b1100) = 2
popcount(0b1101) = 3
popcount(0b1110) = 3
popcount(0b1111) = 4
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="rotl"></a>`rotl`

符号なし整数値のビットを、指定した回数だけ左に回転します。 左端のビットの "フォールアウト" されるビットは、右端のビットに回転されます。
 
```cpp
template<class T>
[[nodiscard]] constexpr T rotl(T value, int s) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
回転する符号なし整数値。

*2$s*\
実行する左の回転の数。

### <a name="return-value"></a>戻り値

左に回転した結果 `value` `s` 。 \
`s`が0の場合、はを返し `value` ます。
`s`が負の場合、はを行い `rotr(value, -s)` ます。 右端のビットの "フォールアウト" されるビットは、一番左のビットに回転します。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char bits = 1;
    for (int i = 0; i < 8; ++i)
    {
        std::cout << "rotl(0b" << std::bitset<8>(bits) << ", 1) = ";
        bits = std::rotl(bits, 1);
        std::cout << "0b" << std::bitset<8>(bits) << '\n';
    }
    std::cout << "rotl(0b" << std::bitset<8>(bits) << ",-1) = ";
    bits = std::rotl(bits, -1);
    std::cout << "0b" << std::bitset<8>(bits);
    return 0;
}
```

```Output
rotl(0b00000001, 1) = 0b00000010
rotl(0b00000010, 1) = 0b00000100
rotl(0b00000100, 1) = 0b00001000
rotl(0b00001000, 1) = 0b00010000
rotl(0b00010000, 1) = 0b00100000
rotl(0b00100000, 1) = 0b01000000
rotl(0b01000000, 1) = 0b10000000
rotl(0b10000000, 1) = 0b00000001
rotl(0b00000001,-1) = 0b10000000
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="rotr"></a>`rotr`

`value`指定した回数だけ右のビットを回転させます。 右端のビットの "フォールアウト" されたビットは、左端のビットに戻ります。
 
```cpp
template<class T>
[[nodiscard]] constexpr T rotr(T value, int s) noexcept;
```

### <a name="parameters"></a>パラメーター

*数値*\
回転する符号なし整数値。

*2$s*\
実行する右回転数。

### <a name="return-value"></a>戻り値

右に回転した結果 `value` `s` 。 \
`s`が0の場合、はを返し `value` ます。
`s`が負の場合、はを行い `rotl(value, -s)` ます。 左端のビットの "フォールアウト" するビットは、右端のビットに戻されます。

### <a name="example"></a>例

```cpp
#include <bit>
#include <bitset>
#include <iostream>

int main()
{
    unsigned char bits = 128;
    for (int i = 0; i < 8; ++i)
    {
        std::cout << "rotr(0b" << std::bitset<8>(bits) << ", 1) = ";
        bits = std::rotr(bits, 1);
        std::cout << "0b" << std::bitset<8>(bits) << '\n';
    }
    std::cout << "rotr(0b" << std::bitset<8>(bits) << ",-1) = ";
    bits = std::rotr(bits, -1);
    std::cout << "0b" << std::bitset<8>(bits);
    return 0;
}
```

```Output
rotr(0b10000000, 1) = 0b01000000
rotr(0b01000000, 1) = 0b00100000
rotr(0b00100000, 1) = 0b00010000
rotr(0b00010000, 1) = 0b00001000
rotr(0b00001000, 1) = 0b00000100
rotr(0b00000100, 1) = 0b00000010
rotr(0b00000010, 1) = 0b00000001
rotr(0b00000001, 1) = 0b10000000
rotr(0b10000000,-1) = 0b00000001
```

### <a name="remarks"></a>注釈

このテンプレート関数 `T` は、が符号なし整数型である場合にのみ、オーバーロードの解決に関与します。 たとえば、、、、 `unsigned int` `unsigned long` などです `unsigned short` `unsigned char` 。

## <a name="requirements"></a>要件

**ヘッダー:**\<bit>

**名前空間:** std

[/std: c + + latest](../build/reference/std-specify-language-standard-version.md) が必要です。

## <a name="see-also"></a>関連項目

[\<bit>](bit.md)