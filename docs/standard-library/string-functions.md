---
description: '詳細情報: &lt; 文字列 &gt; 関数'
title: '&lt;string&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.openlocfilehash: 80c3fc82ebd099f465f9929c5b5fab63d3f4ec84
ms.sourcegitcommit: a89eac9acdbd54a181e3bd5d5bc71a3ef3c1abca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "106506040"
---
# <a name="string-functions"></a>`<string>` 関数

[`getline`](#getline)\
[`stod`](#stod)\
[`stof`](#stof)\
[`stoi`](#stoi)\
[`stol`](#stol)\
[`stold`](#stold)\
[`stoll`](#stoll)\
[`stoul`](#stoul)\
[`stoull`](#stoull)\
[`swap`](#swap)\
[`to_string`](#to_string)\
[`to_wstring`](#to_wstring)

## <a name="getline"></a><a name="getline"></a> `getline`

入力ストリームから文字列を行単位で抽出します。

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delimiter);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delimiter);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& in_stream,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>パラメーター

*`in_stream`*\
文字列の抽出元となる入力ストリーム。

*`str`*\
入力ストリームから抽出した文字の読み込み先となる文字列。

*`delimiter`*\
行の区切り記号。

### <a name="return-value"></a>戻り値

入力ストリーム *`in_stream`* 。

### <a name="remarks"></a>Remarks

が見つかるまで、から文字を抽出する関数シグネチャのペアは、 `(1)` *`in_stream`* *`delimiter`* に格納され *`str`* ます。

としてマークされた関数シグネチャのペアは、 `(2)` 既定の行区切り記号として改行を使用し、として動作し `getline(in_stream, str, in_stream. widen('\n'))` ます。

各ペアの2番目の関数は、 [ `rvalue` 参照](../cpp/lvalues-and-rvalues-visual-cpp.md)をサポートするための1番目の関数です。

抽出は、次のいずれかが発生したときに停止します。

- ファイルの末尾で、の内部状態フラグ *`in_stream`* がに設定されて `ios_base::eofbit` います。

- 関数がと等しい要素を抽出した後 *`delimiter`* 。 要素は、被制御シーケンスに戻されたり、追加されたりすることはありません。

- 関数が要素を抽出した後 [`str.max_size`](../standard-library/basic-string-class.md#max_size) 。 の内部状態フラグ *`in_stream`* がに設定されて `ios_base::failbit` います。

- 以前に一覧表示されていないエラーがあります。の内部状態フラグ *`in_stream`* がに設定されて `ios_base::badbit` います。

内部状態フラグの詳細については、「」を参照してください [`ios_base::iostate`](../standard-library/ios-base-class.md#iostate) 。

関数が要素を抽出しなかった場合、の内部状態フラグ *`in_stream`* はに設定され `ios_base::failbit` ます。 いずれの場合も、は `getline` を返し *`in_stream`* ます。

例外がスローされた場合、 *`in_stream`* と *`str`* は有効な状態のままになります。

### <a name="example"></a>例

次のコードは、2 つのモードの `getline()` を示しています。1 つ目は既定の区切り文字 (改行文字)、2 つ目は区切り文字として空白文字を使用しています。 また、while ループの終了を制御するために、ファイル終端文字 (Ctrl + Z キー) を使用しています。 この値は、の内部状態フラグ `cin` をに設定し `eofbit` ます。これは、2番目のループが正常に機能するためには、で消去する必要があり [`basic_ios::clear()`](../standard-library/basic-ios-class.md#clear) ます。

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}
```

## <a name="stod"></a><a name="stod"></a> `stod`

文字シーケンスをに変換 **`double`** します。

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>パラメーター

*`str`*\
変換する文字シーケンス。

*`idx`*\
最初の未変換文字のインデックス値。

### <a name="return-value"></a>戻り値

**`double`** 値。

### <a name="remarks"></a>Remarks

関数は *`str`* 、を呼び出した場合と同じように、内の要素のシーケンスを型の値に変換し **`double`** `strtod( str.c_str(), _Eptr)` `_Eptr` ます。は関数の内部オブジェクトです。 `str.c_str() == *_Eptr`の場合、型のオブジェクトをスロー `invalid_argument` します。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合、が null ポインターでない場合、 *`idx`* 関数はを格納 `*_Eptr -  str.c_str()` し、値を `*idx` 返します。

## <a name="stof"></a><a name="stof"></a> `stof`

文字シーケンスを float に変換します。

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>パラメーター

*`str`*\
変換する文字シーケンス。

*`idx`*\
最初の未変換文字のインデックス値。

### <a name="return-value"></a>戻り値

**`float`** 値。

### <a name="remarks"></a>Remarks

関数は *`str`* 、を呼び出した場合と同じように、内の要素のシーケンスを型の値に変換し **`float`** `strtof( str.c_str(), _Eptr)` `_Eptr` ます。は関数の内部オブジェクトです。 `str.c_str() == *_Eptr`の場合、型のオブジェクトをスロー `invalid_argument` します。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合、が null ポインターでない場合、 *`idx`* 関数はを格納 `*_Eptr -  str.c_str()` し、値を `*idx` 返します。

## <a name="stoi"></a><a name="stoi"></a> `stoi`

文字シーケンスを integer に変換します。

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>戻り値

整数値。

### <a name="parameters"></a>パラメーター

*`str`*\
変換する文字シーケンス。

*`idx`*\
最初の未変換文字のインデックス値。

*`base`*\
使用する基数。

### <a name="remarks"></a>Remarks

関数は、 `stoi` *str* 内の文字のシーケンスを型の値に変換し、 **`int`** 値を返します。 たとえば、文字シーケンス "10" を渡した場合、`stoi` によって返される値は整数 10 です。

`stoi``strtol`は、1バイト文字の場合と同じように動作し `strtol( str.c_str(), _Eptr, idx)` ます。ここで、 `_Eptr` は関数の内部オブジェクトです。 `wcstol` ワイド文字の場合は、同様の方法で呼び出され `wcstol(Str.c_str(), _Eptr, idx)` ます。 詳細については、「」、「」、「」を参照してください[ `strtol` `wcstol` `_strtol_l` `_wcstol_l` ](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)。

`str.c_str() == *_Eptr`の場合、 `stoi` 型のオブジェクトをスロー `invalid_argument` します。 このような呼び出しによってが設定される場合 `errno` 、または戻り値を型のオブジェクトとして表すことができない場合は、 **`int`** 型のオブジェクトをスローし `out_of_range` ます。 それ以外の場合、 *idx* が null ポインターではない場合、関数は `*_Eptr - str.c_str()` をに格納し `*idx` ます。

## <a name="stol"></a><a name="stol"></a> `stol`

文字シーケンスをに変換 **`long`** します。

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>パラメーター

*`str`*\
変換する文字シーケンス。

*`idx`*\
最初の未変換文字のインデックス値。

*`base`*\
使用する基数。

### <a name="return-value"></a>戻り値

長整数値。

### <a name="remarks"></a>Remarks

関数は、を呼び出した場合と同じように、 *str* 内の要素のシーケンスを型の値に変換し **`long`** `strtol( str.c_str(), _Eptr, idx)` `_Eptr` ます。は関数の内部オブジェクトです。 `str.c_str() == *_Eptr`の場合、型のオブジェクトをスロー `invalid_argument` します。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合、が null ポインターでない場合、 *`idx`* 関数はを格納 `*_Eptr -  str.c_str()` し、値を `*idx` 返します。

## <a name="stold"></a><a name="stold"></a> `stold`

文字シーケンスをに変換 **`long double`** します。

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>パラメーター

*`str`*\
変換する文字シーケンス。

*`idx`*\
最初の未変換文字のインデックス値。

### <a name="return-value"></a>戻り値

**`long double`** 値。

### <a name="remarks"></a>Remarks

関数は、を呼び出した場合と同じように、 *str* 内の要素のシーケンスを型の値に変換し **`long double`** `strtold( str.c_str(), _Eptr)` `_Eptr` ます。は関数の内部オブジェクトです。 `str.c_str() == *_Eptr`の場合、型のオブジェクトをスロー `invalid_argument` します。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合、が null ポインターでない場合、 *`idx`* 関数はを格納 `*_Eptr -  str.c_str()` し、値を `*idx` 返します。

## <a name="stoll"></a><a name="stoll"></a> `stoll`

文字シーケンスをに変換 **`long long`** します。

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>パラメーター

*`str`*\
変換する文字シーケンス。

*`idx`*\
最初の未変換文字のインデックス値。

*`base`*\
使用する基数。

### <a name="return-value"></a>戻り値

**`long long`** 値。

### <a name="remarks"></a>Remarks

関数は、を呼び出した場合と同じように、 *str* 内の要素のシーケンスを型の値に変換し **`long long`** `strtoll( str.c_str(), _Eptr, idx)` `_Eptr` ます。は関数の内部オブジェクトです。 `str.c_str() == *_Eptr`の場合、型のオブジェクトをスロー `invalid_argument` します。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合、 *idx* が null ポインターではない場合、関数はを格納 `*_Eptr -  str.c_str()` し、値を `*idx` 返します。

## <a name="stoul"></a><a name="stoul"></a> `stoul`

文字シーケンスを unsigned long に変換します。

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>パラメーター

*`str`*\
変換する文字シーケンス。

*`idx`*\
最初の未変換文字のインデックス値。

*`base`*\
使用する基数。

### <a name="return-value"></a>戻り値

unsigned long 整数値。

### <a name="remarks"></a>Remarks

関数は、を呼び出した場合と同じように、 *str* 内の要素のシーケンスを型の値に変換し **`unsigned long`** `strtoul( str.c_str(), _Eptr, idx)` `_Eptr` ます。は関数の内部オブジェクトです。 `str.c_str() == *_Eptr`の場合、型のオブジェクトをスロー `invalid_argument` します。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合、 *idx* が null ポインターではない場合、関数はを格納 `*_Eptr -  str.c_str()` し、値を `*idx` 返します。

## <a name="stoull"></a><a name="stoull"></a> `stoull`

文字シーケンスをに変換 **`unsigned long long`** します。

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>パラメーター

*`str`*\
変換する文字シーケンス。

*`idx`*\
最初の未変換文字のインデックス値。

*`base`*\
使用する基数。

### <a name="return-value"></a>戻り値

**`unsigned long long`** 値。

### <a name="remarks"></a>Remarks

関数は、を呼び出した場合と同じように、 *str* 内の要素のシーケンスを型の値に変換し **`unsigned long long`** `strtoull( str.c_str(), _Eptr, idx)` `_Eptr` ます。は関数の内部オブジェクトです。 `str.c_str() == *_Eptr`の場合、型のオブジェクトをスロー `invalid_argument` します。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合、が null ポインターでない場合、 *`idx`* 関数はを格納 `*_Eptr -  str.c_str()` し、値を `*idx` 返します。

## <a name="swap"></a><a name="swap"></a> `swap`

2 つの文字列の、文字の配列を交換します。

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*`left`*\
要素が別の文字列の要素と交換される1つの文字列。

*`right`*\
最初の文字列と要素を交換するもう一方の文字列。

### <a name="remarks"></a>Remarks

このテンプレート関数は、 [`left.swap`](../standard-library/basic-string-class.md#swap) *`right`* 一定の複雑さを保証する文字列に対して特殊なメンバー関数 () を実行します。

### <a name="example"></a>例

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a><a name="to_string"></a> `to_string`

値を `string` に変換します。

```cpp
string to_string(int value);
string to_string(unsigned int value);
string to_string(long value);
string to_string(unsigned long value);
string to_string(long long value);
string to_string(unsigned long long value);
string to_string(float value);
string to_string(double value);
string to_string(long double value);
```

### <a name="parameters"></a>パラメーター

*`value`*\
変換する値。

### <a name="return-value"></a>戻り値

値を表す `string` 値。

### <a name="remarks"></a>Remarks

関数は `Buf` 、を呼び出した場合と同様に、関数内部の配列オブジェクトに格納されている要素のシーケンスに値を変換します。 `sprintf(Buf, Fmt, value)` ここで、 `Fmt` はです。

- `"%d"`*`value`* が型である場合 **`int`**

- `"%u"`*`value`* が型である場合 **`unsigned int`**

- `"%ld"`*`value`* が型である場合 **`long`**

- `"%lu"`*`value`* が型である場合 **`unsigned long`**

- `"%lld"`*`value`* が型である場合 **`long long`**

- `"%llu"`*`value`* が型である場合 **`unsigned long long`**

- `"%f"`*`value`* の型が **`float`** またはの場合 **`double`**

- `"%Lf"`*`value`* が型である場合 **`long double`**

`string(Buf)` が返されます。

## <a name="to_wstring"></a><a name="to_wstring"></a> `to_wstring`

値をワイド文字列に変換します。

```cpp
wstring to_wstring(int value);
wstring to_wstring(unsigned int value);
wstring to_wstring(long value);
wstring to_wstring(unsigned long value);
wstring to_wstring(long long value);
wstring to_wstring(unsigned long long value);
wstring to_wstring(float value);
wstring to_wstring(double value);
wstring to_wstring(long double value);
```

### <a name="parameters"></a>パラメーター

*`value`*\
変換する値。

### <a name="return-value"></a>戻り値

値を表すワイド文字列。

### <a name="remarks"></a>Remarks

関数は *`value`* 、を呼び出した場合と同様に、関数内部の配列オブジェクトに格納されている要素のシーケンスに変換します。 `Buf` `swprintf(Buf, Len, Fmt, value)` ここ `Fmt` で、はです。

- `L"%d"`*`value`* が型である場合 **`int`**

- `L"%u"`*`value`* が型である場合 **`unsigned int`**

- `L"%ld"`*`value`* が型である場合 **`long`**

- `L"%lu"`*`value`* が型である場合 **`unsigned long`**

- `L"%lld"`*`value`* が型である場合 **`long long`**

- `L"%llu"`*`value`* が型である場合 **`unsigned long long`**

- `L"%f"`*`value`* の型が **`float`** またはの場合 **`double`**

- `L"%Lf"`*`value`* が型である場合 **`long double`**

`wstring(Buf)` が返されます。

## <a name="see-also"></a>関連項目

[`<string>`](../standard-library/string.md)
