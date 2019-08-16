---
title: '&lt;istream&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: f5da7c6805d10e919255ce301dae5618ef58e76d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501925"
---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; 演算子

## <a name="op_gt_gt"></a>  演算子&gt;&gt;

ストリームから文字と文字列を抽出します。

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>パラメーター

*ハーフ*\
単一の文字。

*Istr*\
ストリーム。

*引数*\
文字列。

*val*\
型。

### <a name="return-value"></a>戻り値

ストリーム

### <a name="remarks"></a>Remarks

`basic_istream` クラスもいくつかの抽出演算子を定義します。 詳細については、「[basic_istream::operator >>](../standard-library/basic-istream-class.md#op_gt_gt)」を参照してください。

下記のテンプレート関数は

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

最大で *N* - 1 の要素を抽出し、_ *Str* から始まる配列にこれらを格納します。 `Istr`. [width](../standard-library/ios-base-class.md#width) が 0 より大きい場合、*N* は `Istr`. **width**;それ以外の場合は、宣言できるの`Elem`最大配列のサイズです。 関数は、格納する抽出`Elem()`された要素の後に常に値を格納します。 抽出は、ファイルの最後の早い段階で、値 **Elem**(0) (これは抽出されません) を持つ文字、または [ws](../standard-library/istream-functions.md#ws) によって破棄される任意の要素 (これは抽出されません) で停止します。 関数が要素を抽出しなかった場合、`Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**)。 いずれの場合も、`Istr`. **幅**(0) とは*Istr*を返します。

**セキュリティ**に関する注意入力ストリームから抽出される null で終わる文字列は、コピー先のバッファー *str*のサイズを超えないようにする必要があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

下記のテンプレート関数は

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

可能な場合は要素を抽出し、 *Ch*に格納します。 そうでない場合は、**is**. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) を呼び出します。 どのような場合でも、 *Istr*が返されます。

下記のテンプレート関数は

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

`Istr >> ( char * ) str` が返されます。

下記のテンプレート関数は

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

`Istr >> ( char& ) Ch` が返されます。

下記のテンプレート関数は

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

`Istr >> ( char * ) str` が返されます。

下記のテンプレート関数は

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

`Istr >> ( char& ) Ch` が返されます。

下記のテンプレート関数は

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

を`Istr >> val`返します (右辺値`Istr`参照をプロセス内の左辺値に変換します)。

### <a name="example"></a>例

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>関連項目

[\<istream>](../standard-library/istream.md)
