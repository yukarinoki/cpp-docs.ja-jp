---
title: '&lt;string&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- string/std::operator!=
- string/std::operator&gt;
- string/std::operator&gt;&gt;
- string/std::operator&gt;=
- string/std::operator&lt;
- string/std::operator&lt;&lt;
- string/std::operator&lt;=
- string/std::operator+
- string/std::operator==
ms.assetid: 33ce8f05-06c7-45d3-a0cb-bcd27cf93910
helpviewer_keywords:
- std::operator!= (string)
- std::operator&gt; (string)
- std::operator&gt;&gt; (string)
- std::operator&gt;= (string)
- std::operator&lt; (string)
- std::operator&lt;&lt; (string)
- std::operator&lt;= (string), std::operator== (string)
ms.openlocfilehash: a3ca469058ba65f83b0df60a93c63895e34f916e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412359"
---
# <a name="ltstringgt-operators"></a>&lt;string&gt; 演算子

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;&gt;](#op_gt_gt)|
|[operator&gt;=](#op_gt_eq)|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|
|[operator&lt;=](#op_lt_eq)|[operator+](#op_add)|[operator==](#op_eq_eq)|

## <a name="op_add"></a>  operator+

2 つの文字列オブジェクトを連結します。

```cpp
template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    CharType left,
    const basic_string<CharType, Traits, Allocator>&& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
連結する C スタイルの文字列または型 `basic_string` のオブジェクト。

*right*<br/>
連結する C スタイルの文字列または型 `basic_string` のオブジェクト。

### <a name="return-value"></a>戻り値

入力文字列を連結した文字列。

### <a name="remarks"></a>Remarks

関数はそれぞれ `operator+` をオーバーロードして、テンプレート クラス [basic_string クラス](../standard-library/basic-string-class.md)の 2 つのオブジェクトを連結します。 すべては実質的に戻り`basic_string< CharType, Traits, Allocator>(Left).append(right)`します。 詳細については、次を参照してください。[追加](../standard-library/basic-string-class.md#append)します。

### <a name="example"></a>例

```cpp
// string_op_con.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "anti" );
   string s2 ( "gravity" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "heroine";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // Declaring a character constant
   char c1 = '!';
   cout << "The character constant c1 = " << c1 << "." << endl;

   // First member function: concatenates an  object
   // of type basic_string with an object of type basic_string
   string s12 = s1 + s2;
   cout << "The string concatenating s1 & s2 is: " << s12 << endl;

   // Second & fourth member functions: concatenate an object
   // of type basic_string with an object of C-syle string type
   string s1s3 = s1 + s3;
   cout << "The string concatenating s1 & s3 is: " << s1s3 << endl;

   // Third & fifth member functions: concatenate an object
   // of type basic_string with a character constant
   string s1s3c1 = s1s3 + c1;
   cout << "The string concatenating s1 & s3 is: " << s1s3c1 << endl;
}
```

```Output
The basic_string s1 = anti.
The basic_string s2 = gravity.
The C-style string s3 = heroine.
The character constant c1 = !.
The string concatenating s1 & s2 is: antigravity
The string concatenating s1 & s3 is: antiheroine
The string concatenating s1 & s3 is: antiheroine!
```

## <a name="op_neq"></a>  operator!=

演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと等しくないかどうかを調べます。

```cpp
template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

*right*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと辞書順で等しくない場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

文字列オブジェクト間の比較は、文字のペアの辞書順比較に基づいています。 2 つの文字列は、同じ数の文字を持ち、各文字の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// string_op_ne.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 != s2 )
      cout << "The strings s1 & s2 are not equal." << endl;
   else
      cout << "The strings s1 & s2 are equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 != s3 )
      cout << "The strings s1 & s3 are not equal." << endl;
   else
      cout << "The strings s1 & s3 are equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 != s2 )
      cout << "The strings s3 & s2 are not equal." << endl;
   else
      cout << "The strings s3 & s2 are equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="op_eq_eq"></a>  operator==

演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと等しいかどうかを調べます。

```cpp
template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

*right*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと辞書順で等しい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

文字列オブジェクト間の比較は、文字のペアの辞書順比較に基づいています。 2 つの文字列は、同じ数の文字を持ち、各文字の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

### <a name="example"></a>例

```cpp
// string_op_eq.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 == s2 )
      cout << "The strings s1 & s2 are equal." << endl;
   else
      cout << "The strings s1 & s2 are not equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 == s3 )
      cout << "The strings s1 & s3 are equal." << endl;
   else
      cout << "The strings s1 & s3 are not equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 == s2 )
      cout << "The strings s3 & s2 are equal." << endl;
   else
      cout << "The strings s3 & s2 are not equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="op_lt"></a>  operator&lt;

演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトより小さいかどうかを調べます。

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

*right*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の文字列オブジェクトが辞書順で右辺の文字列オブジェクト未満の場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

文字列間の辞書順比較は、次の条件を満たすまで文字ごとに比較します。

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

```cpp
// string_op_lt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 < s2 )
      cout << "The string s1 is less than the string s2." << endl;
   else
      cout << "The string s1 is not less than the string s2." << endl;

   // Second member function: comparison between left-hand object
   // of type basic_string & right-hand object of C-syle string type
   if ( s1 < s3 )
      cout << "The string s1 is less than the string s3." << endl;
   else
      cout << "The string s1 is not less than the string s3." << endl;

   // Third member function: comparison between left-hand object
   // of C-syle string type & right-hand object of type basic_string
   if ( s3 < s2 )
      cout << "The string s3 is less than the string s2." << endl;
   else
      cout << "The string s3 is not less than the string s2." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than the string s2.
The string s1 is not less than the string s3.
The string s3 is less than the string s2.
```

## <a name="op_lt_eq"></a>  演算子&lt;=

演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクト以下かどうかを調べます。

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

*right*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の文字列オブジェクトが辞書順で右辺の文字列オブジェクト以下の場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

文字列間の辞書順比較は、次の条件を満たすまで文字ごとに比較します。

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

```cpp
// string_op_le.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 <= s2 )
      cout << "The string s1 is less than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 <= s3 )
      cout << "The string s1 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s3." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type  & right-side object of type basic_string
   if ( s2 <= s3 )
      cout << "The string s2 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than or equal to the string s2.
The string s1 is less than or equal to the string s3.
The string s2 is greater than the string s3.
```

## <a name="op_lt_lt"></a>  演算子&lt;&lt;

出力ストリームに文字列を書き込むテンプレート関数。

```cpp
template <class CharType, class Traits, class Allocator>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr,
    const basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>パラメーター

*_Ostr*<br/>
書き込み先の出力ストリーム。

*str*<br/>
出力ストリームに入力される文字列。

### <a name="return-value"></a>戻り値

指定した文字列の値を出力ストリームに書き込みます *_Ostr*します。

### <a name="remarks"></a>Remarks

テンプレート関数のオーバー ロード**演算子 <<** オブジェクトを挿入する*str*テンプレート クラスの[basic_string](../standard-library/basic-string-class.md)ストリームに *\_Ostr*します。 関数は効果的に返します`_Ostr.write( str.c_str, str.size )`します。

## <a name="op_gt"></a>  operator&gt;

演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトより大きいかどうかを調べます。

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

*right*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の文字列オブジェクトが辞書順で右辺の文字列オブジェクトよりも大きい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

文字列間の辞書順比較は、次の条件を満たすまで文字ごとに比較します。

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

```cpp
// string_op_gt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 > s2 )
      cout << "The string s1 is greater than "
           << "the string s2." << endl;
   else
      cout << "The string s1 is not greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 > s1 )
      cout << "The string s3 is greater than "
           << "the string s1." << endl;
   else
      cout << "The string s3 is not greater than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 > s3 )
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
   else
      cout << "The string s2 is not greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is not greater than the string s2.
The string s3 is greater than the string s1.
The string s2 is greater than the string s3.
```

## <a name="op_gt_eq"></a>  演算子&gt;=

演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクト以上かどうかを調べます。

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*left*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

*right*<br/>
比較する C スタイルの文字列または `basic_string` 型のオブジェクト。

### <a name="return-value"></a>戻り値

演算子の左辺の文字列オブジェクトが辞書順で右辺の文字列オブジェクト以上の場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

文字列間の辞書順比較は、次の条件を満たすまで文字ごとに比較します。

- 2 つの対応する文字が等しくない場合、比較の結果は文字列間の比較の結果として取得されます。

- 不等が見つからなくても、1 つの文字列に他より多くの文字がある場合、短い文字列は長い文字列より小さいと見なされます。

- 不等が見つからず、各文字列の文字数が同じである場合、文字列が等しくなります。

### <a name="example"></a>例

```cpp
// string_op_ge.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 >= s2 )
      cout << "The string s1 is greater than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is less than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 >= s1 )
      cout << "The string s3 is greater than or equal to "
           << "the string s1." << endl;
   else
      cout << "The string s3 is less than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 >= s3 )
      cout << "The string s2 is greater than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is less than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is less than the string s2.
The string s3 is greater than or equal to the string s1.
The string s2 is greater than or equal to the string s3.
```

## <a name="op_gt_gt"></a>  演算子&gt;&gt;

入力ストリームから文字列を読み取るテンプレート関数。

```cpp
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,
    basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*_Istr*<br/>
シーケンスを抽出するために使用する入力ストリーム

*right*<br/>
入力ストリームから抽出される文字列。

### <a name="return-value"></a>戻り値

指定した文字列の値を読み取ります *_Istr*にそれを返しますと*右*します。

### <a name="remarks"></a>Remarks

`skipws` フラグが設定されていない場合、演算子は先頭の余白をスキップします。 次の文字が余白か、ファイルの終わりに到達するまでは、次のすべての文字を読み取ります。

テンプレート関数のオーバー ロード**演算子 >>** によって制御されるシーケンスを置き換える*右*ストリームから抽出された要素のシーケンスを持つ *_Istr*します。 抽出は、次で停止します。

- ファイルの終わり。

- 関数が `_Istr` を抽出した後。 **width** 要素 (その値が 0 以外の場合)。

関数が `_Istr` を抽出した後。 [max_size](../standard-library/basic-string-class.md#max_size) 要素。

- 関数が [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **CharType**> >( `getloc`) の要素 *ch* を抽出した後。 **is**( **ctype**\< **CharType**>:: **space**, *ch*) が true の場合、文字が戻されます。

呼び出す関数が要素を抽出しなかった場合[setstate](../standard-library/basic-ios-class.md#setstate)(`ios_base::failbit`)。 いずれの場合も、 **istr**します。 **幅**(0) を返します\***この**します。

### <a name="example"></a>例

```cpp
// string_op_read_.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string c0;
   cout << "Input a string c0 ( try: Fibonacci numbers ): ";
   cin >> c0;
   cout << "The string entered is c0 = " << c0 << endl;
}
```

## <a name="see-also"></a>関連項目

[\<string>](../standard-library/string.md)<br/>
