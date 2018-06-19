---
title: '&lt;istream&gt; 演算子 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::operator&gt;&gt;
dev_langs:
- C++
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5068c0bd540b1c44d2cdc484c2e511276bd12666
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853061"
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

`Ch` 文字です。

`Istr` ストリームです。

`str` 文字列。

`val` 型。

### <a name="return-value"></a>戻り値

ストリーム

### <a name="remarks"></a>コメント

`basic_istream` クラスもいくつかの抽出演算子を定義します。 詳細については、「[basic_istream::operator >>](../standard-library/basic-istream-class.md#op_gt_gt)」を参照してください。

下記のテンプレート関数は

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

最大で *N* - 1 の要素を抽出し、_ *Str* から始まる配列にこれらを格納します。 `Istr`. [width](../standard-library/ios-base-class.md#width) が 0 より大きい場合、*N* は `Istr`. **width** です。そうでない場合は、宣言できる **Elem** の最大の配列のサイズになります。 この関数は常に、格納する抽出された要素の後に値 **Elem()** を格納します。 抽出は、ファイルの最後の早い段階で、値 **Elem**(0) (これは抽出されません) を持つ文字、または [ws](../standard-library/istream-functions.md#ws) によって破棄される任意の要素 (これは抽出されません) で停止します。 関数が要素を抽出しなかった場合、`Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) が呼び出されます。 いずれの場合も、`Istr`. **width**(0) が呼び出され、`Istr` が返されます。

**セキュリティに関するメモ** 入力ストリームから抽出された、null で終わる文字列が、コピー先バッファー `str` のサイズを超えないようにする必要があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。

下記のテンプレート関数は

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

可能な場合は要素を抽出し、この要素を `Ch` に格納します。 そうでない場合は、**is**. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) を呼び出します。 いずれの場合も、`Istr` を返します。

下記のテンプレート関数は

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

`Istr` >> ( `char`**\***) `str` を返します。

下記のテンプレート関数は

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

`Istr` >> ( **char&**) `Ch` を返します。

下記のテンプレート関数は

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

`Istr` >> ( **char \***) `str` を返します。

下記のテンプレート関数は

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

`Istr` >> ( **char&**) `Ch` を返します。

下記のテンプレート関数は

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

`Istr` `>>` `val` を返します (さらに、その過程で `Istr` に対する `rvalue reference` を `lvalue` に変換します)。

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

[\<istream>](../standard-library/istream.md)<br/>
