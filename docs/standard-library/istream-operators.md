---
description: 詳細については、「 &lt; istream 演算子」を参照してください。 &gt;
title: '&lt;istream&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 68bf59480af68248533f55ef32de4525a4d900d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277883"
---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; 演算子

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a> operator&gt;&gt;

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

### <a name="remarks"></a>解説

`basic_istream` クラスもいくつかの抽出演算子を定義します。 詳細については、「[basic_istream::operator >>](../standard-library/basic-istream-class.md#op_gt_gt)」を参照してください。

関数テンプレート:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

は、最大の要素を抽出 `N - 1` し、 *str* から始まる配列に格納します。 `Istr.` [Width](../standard-library/ios-base-class.md#width)が0より大きい場合、 *N* はです。それ以外の場合は、 `Istr.width` 宣言できるの最大配列のサイズです `Elem` 。 関数は、格納する抽出された要素の後に常に値を格納 `Elem()` します。 抽出は、ファイルの終わり、値 (抽出されて `Elem(0)` いない)、または [ws](../standard-library/istream-functions.md#ws)によって破棄される任意の要素 (抽出されていない) に対して早期に停止します。 関数が要素を抽出しなかった場合は、を呼び出し `Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` ます。 いずれの場合も、を呼び出し、 `Istr.width(0)` *istr* を返します。

**セキュリティ** に関する注意入力ストリームから抽出される null で終わる文字列は、コピー先のバッファー *str* のサイズを超えないようにする必要があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

関数テンプレート:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

可能な場合は要素を抽出し、 *Ch* に格納します。 それ以外の場合は、を呼び出し `is.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` ます。 どのような場合でも、 *Istr* が返されます。

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

を返し `Istr >> val` ます (右辺値参照を `Istr` プロセス内の左辺値に変換します)。

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
