---
title: '&lt;bitset&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- bitset/std::operator&amp;
- bitset/std::operator&gt;&gt;
- bitset/std::operator&lt;&lt;
- bitset/std::operator^
- bitset/std::operator|
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
helpviewer_keywords:
- std::operator&amp; (bitset)
- std::operator&gt;&gt; (bitset)
- std::operator&lt;&lt; (bitset)
ms.openlocfilehash: c51bc5ecf2bc3a74b25a06320f0ca8fd64749f5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531145"
---
# <a name="ltbitsetgt-operators"></a>&lt;bitset&gt; 演算子

||||
|-|-|-|
|[operator&amp;](#op_amp)|[operator&gt;&gt;](#op_gt_gt)|[operator&lt;&lt;](#op_lt_lt)|
|[operator^](#op_xor)|[operator|](#op_or)|

## <a name="op_amp"></a>  operator&amp;

2 つのビットセット間でビットごとの `AND` を実行します。

```cpp
template <size_t size>
bitset<size>
operator&(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
それぞれの要素が `AND` でビットごとに結合される 2 つのビットセットのうちの最初。

*right*<br/>
それぞれの要素が `AND` でビットごとに結合される 2 つの valarray のうちの 2 つ目。

### <a name="return-value"></a>戻り値

要素が実行した結果、ビットセット、`AND`の対応する要素を操作*左*と*右*します。

### <a name="example"></a>例

```cpp
// bitset_and.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 & b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0001
```

## <a name="op_lt_lt"></a>  演算子&lt;&lt;

ビット シーケンスのテキスト表現を出力ストリームに挿入します。

```

template <class CharType, class Traits, size_t N>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,
    const bitset<N>& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
文字列として出力ストリームに挿入する型 **bitset\<N>** のオブジェクト。

### <a name="return-value"></a>戻り値

ビット シーケンス内のテキスト表現`ostr`します。

### <a name="remarks"></a>Remarks

テンプレート関数のオーバー ロード`operator<<`、ビットセットを文字列に変換せずに書き出されます。 このテンプレート関数は、実質的に次の内容を実行します。

**ostr** << _ *Right*. [to_string](bitset-class.md) < **CharType**, **Traits**, **allocator**\< **CharType**> > ( )

### <a name="example"></a>例

```cpp
// bitset_op_insert.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 9 );

   // bitset inserted into output stream directly
   cout << "The ordered set of bits in the bitset<5> b1(9)"
        << "\n can be output with the overloaded << as: ( "
        << b1 << " )" << endl;

   // Compare converting bitset to a string before
   // inserting it into the output steam
   string s1;
   s1 =  b1.template to_string<char,
      char_traits<char>, allocator<char> >( );
   cout << "The string returned from the bitset b1"
        << "\n by the member function to_string( ) is: "
        << s1 << "." << endl;
}
```

## <a name="op_gt_gt"></a>  演算子&gt;&gt;

ビット文字の文字列をビットセットに読み込みます。

```

template <class CharType, class Traits, size_t Bits>
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>&
_Istr,
    bitset<N>&
    right);
```

### <a name="parameters"></a>パラメーター

*_Istr*<br/>
ビットセットに挿入する入力ストリームに入力される文字列。

*right*<br/>
入力ストリームからビットを受け取るビットセット。

### <a name="return-value"></a>戻り値

テンプレート関数は、文字列を返します *_Istr*します。

### <a name="remarks"></a>Remarks

テンプレート関数のオーバー ロード`operator>>`ビットセット _ に格納する*右*値ビットセット (`str`) ここで、`str`型のオブジェクトは、 [basic_string](basic-string-class.md)  < **CharType**、 **Traits**、**アロケーター** \< **CharType**>>  **&** から抽出された *_Istr*します。

要素を抽出するテンプレート関数は、 *_Istr*までビットセットに挿入するとします。

- すべてのビット要素が入力ストリームから抽出され、ビットセットに格納されています。

- ビットセットが入力ストリームからのビットでいっぱいになっています。

- 0 でも 1 でもない入力要素に遭遇しました。

### <a name="example"></a>例

```cpp
#include <bitset>
#include <iostream>
#include <string>

using namespace std;
int main()
{

   bitset<5> b1;
   cout << "Enter string of (0 or 1) bits for input into bitset<5>.\n"
        << "Try bit string of length less than or equal to 5,\n"
        << " (for example: 10110): ";
   cin >>  b1;

   cout << "The ordered set of bits entered from the "
        << "keyboard\n has been input into bitset<5> b1 as: ( "
        << b1 << " )" << endl;

   // Truncation due to longer string of bits than length of bitset
   bitset<2> b3;
   cout << "Enter string of bits (0 or 1) for input into bitset<2>.\n"
        << " Try bit string of length greater than 2,\n"
        << " (for example: 1011): ";
   cin >>  b3;

   cout << "The ordered set of bits entered from the "
        << "keyboard\n has been input into bitset<2> b3 as: ( "
        << b3 << " )" << endl;

   // Flushing the input stream
   char buf[100];
   cin.getline(&buf[0], 99);

   // Truncation with non-bit value
   bitset<5> b2;
   cout << "Enter a string for input into  bitset<5>.\n"
        << " that contains a character than is NOT a 0 or a 1,\n "
        << " (for example: 10k01): ";
   cin >>  b2;

   cout << "The string entered from the keyboard\n"
        << " has been input into bitset<5> b2 as: ( "
        << b2 << " )" << endl;
}
```

## <a name="op_xor"></a>  operator^

2 つのビットセット間でビットごとの `EXCLUSIVE-OR` を実行します。

```cpp
template <size_t size>
bitset<size>
operator^(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
それぞれの要素が `EXCLUSIVE-OR` でビットごとに結合される 2 つのビットセットのうちの最初。

*right*<br/>
それぞれの要素が `EXCLUSIVE-OR` でビットごとに結合される 2 つの valarray のうちの 2 つ目。

### <a name="return-value"></a>戻り値

要素が実行した結果、ビットセット、`EXCLUSIVE-OR`の対応する要素を操作*左*と*右*します。

### <a name="example"></a>例

```cpp
// bitset_xor.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 ^ b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0110
```

## <a name="op_or"></a>  operator|

2 つのビットセット間でビットごとの `OR` を実行します。

```cpp
template <size_t size>
bitset<size>
operator|(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
それぞれの要素が `OR` でビットごとに結合される 2 つのビットセットのうちの最初。

*right*<br/>
それぞれの要素が `OR` でビットごとに結合される 2 つの valarray のうちの 2 つ目。

### <a name="return-value"></a>戻り値

要素が実行した結果、ビットセット、`OR`の対応する要素を操作*左*と*右*します。

### <a name="example"></a>例

```cpp
// bitset_or.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 | b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0111
```

## <a name="see-also"></a>関連項目

[\<bitset>](../standard-library/bitset.md)<br/>
