---
title: '&lt;istream&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 3b9521fde1b5a03389bfc1ad3e35fa407d9d6ac0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363040"
---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; 演算子

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a>演算子&gt;&gt;

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

*Ch*\
単一の文字。

*イストル*\
ストリーム。

*Str*\
文字列。

*ヴァル*\
型。

### <a name="return-value"></a>戻り値

ストリーム

### <a name="remarks"></a>解説

`basic_istream` クラスもいくつかの抽出演算子を定義します。 詳細については、「[basic_istream::operator >>](../standard-library/basic-istream-class.md#op_gt_gt)」を参照してください。

関数テンプレート:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

要素まで`N - 1`抽出し *、str*から始まる配列に格納します。 `Istr.`[幅](../standard-library/ios-base-class.md#width)がゼロより大きい場合 *、N*は`Istr.width`;それ以外の場合は、宣言できる最大の配列の`Elem`サイズです。 関数は、抽出された要素`Elem()`が格納した後に常に値を格納します。 抽出は、ファイルの終わり、値`Elem(0)`を持つ文字 (抽出されない文字)、または[ws](../standard-library/istream-functions.md#ws)によって破棄される要素 (抽出されない要素) で、早い段階で停止します。 関数が要素を抽出しない場合は、`Istr.`[`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`を呼び出します。 いずれにしても`Istr.width(0)`*、Istr*を呼び出して返します。

**セキュリティに関する注意事項**入力ストリームから抽出される null で終わる文字列は、宛先 buffer *str*のサイズを超えてはなりません。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

関数テンプレート:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

要素を抽出し、可能であれば Ch*に格納*します。 それ以外の場合`is.`[`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`は、 を呼び出します。 いずれにしても *、Istr*が返されます。

関数テンプレート:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

`Istr >> ( char * ) str` が返されます。

関数テンプレート:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

`Istr >> ( char& ) Ch` が返されます。

関数テンプレート:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

`Istr >> ( char * ) str` が返されます。

関数テンプレート:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

`Istr >> ( char& ) Ch` が返されます。

関数テンプレート:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

を`Istr >> val`返します (および、プロセス内の`Istr`右辺値参照を左辺値に変換します)。

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

[\<i流>](../standard-library/istream.md)
