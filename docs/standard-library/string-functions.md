---
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
ms.openlocfilehash: 3f1dca71a6bb9d5461150378191b9373f907ecd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376660"
---
# <a name="ltstringgt-functions"></a>&lt;string&gt; 関数

||||
|-|-|-|
|[Getline](#getline)|[ストッド](#stod)|[ストフ](#stof)|
|[ストイ](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[ストル](#stoul)|[ストゥール](#stoull)|
|[スワップ](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a><a name="getline"></a>Getline

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

*in_stream*\
文字列の抽出元となる入力ストリーム。

*Str*\
入力ストリームから抽出した文字の読み込み先となる文字列。

*区切り 記号*\
行の区切り記号。

### <a name="return-value"></a>戻り値

入力ストリーム*in_stream。*

### <a name="remarks"></a>解説

区切*り文字*が見つかるまで`(1)`*、in_stream*から文字を抽出し *、str*に格納する関数シグネチャのペア。

マークされた`(2)`関数シグネチャのペアでは、改行文字がデフォルトの行区切り文字として使用`getline(in_stream, str, in_stream. widen('\n'))`され、 として動作します。

各ペアの 2 つ目の関数では、1 つ目の関数と同様に、[右辺値参照](../cpp/lvalues-and-rvalues-visual-cpp.md)がサポートされます。

抽出は、次のいずれかが発生したときに停止します。

- ファイルの末尾で、in_streamの内部状態フラグが に*in_stream*`ios_base::eofbit`設定されます。

- 関数が *、区切り記号*と等しい要素を抽出した後。 要素は、制御されたシーケンスに戻ったり、追加されたりしません。

- 関数の後に`str.`[max_size](../standard-library/basic-string-class.md#max_size)要素を抽出します。 in_stream*の内部*状態フラグは に設定`ios_base::failbit`されます。

- 上記以外のエラー。*in_stream*の内部状態フラグが に`ios_base::badbit`設定されます。

内部状態フラグについては、「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照してください。

関数が要素を抽出しない場合 *、in_stream*の内部状態フラグは に`ios_base::failbit`設定されます。 いずれの場合も、 `getline` *in_stream*を返します。

例外がスローされた場合 *、in_stream*と*str*は有効な状態のままになります。

### <a name="example"></a>例

次のコードは、2 つのモードの `getline()` を示しています。1 つ目は既定の区切り文字 (改行文字)、2 つ目は区切り文字として空白文字を使用しています。 また、while ループの終了を制御するために、ファイル終端文字 (Ctrl + Z キー) を使用しています。 この値は、2 番目の`cin` `eofbit`while ループが正常に動作する前に[basic_ios::clear()](../standard-library/basic-ios-class.md#clear)でクリアする必要がある 内部状態フラグを に設定します。

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

## <a name="stod"></a><a name="stod"></a>ストッド

文字シーケンスを**`double`**.

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

*Str*\
変換する文字シーケンス。

*Idx*\
最初の未変換文字のインデックス値。

### <a name="return-value"></a>戻り値

値**`double`**。

### <a name="remarks"></a>解説

この関数は *、str*内の要素のシーケンスを、関数**`double`**`strtod( str.c_str(), _Eptr)`の内部のオブジェクト`_Eptr`である場合と同じ型の値に変換します。 の`str.c_str() == *_Eptr`場合は、 型のオブジェクトを`invalid_argument`スローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合 *、idx*が null ポインターでない場合`*_Eptr -  str.c_str()`、`*idx`関数は、値を格納して返します。

## <a name="stof"></a><a name="stof"></a>ストフ

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

*Str*\
変換する文字シーケンス。

*Idx*\
最初の未変換文字のインデックス値。

### <a name="return-value"></a>戻り値

値**`float`**。

### <a name="remarks"></a>解説

この関数は *、str*内の要素のシーケンスを、関数**`float`**`strtof( str.c_str(), _Eptr)`の内部のオブジェクト`_Eptr`である場合と同じ型の値に変換します。 の`str.c_str() == *_Eptr`場合は、 型のオブジェクトを`invalid_argument`スローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合 *、idx*が null ポインターでない場合`*_Eptr -  str.c_str()`、`*idx`関数は、値を格納して返します。

## <a name="stoi"></a><a name="stoi"></a>ストイ

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

*Str*\
変換する文字シーケンス。

*Idx*\
最初の未変換文字のインデックス値。

*ベース*\
使用する基数。

### <a name="remarks"></a>解説

str`stoi`*内の*文字のシーケンスを型**`int`** の値に変換し、値を返します。 たとえば、文字シーケンス "10" を渡した場合、`stoi` によって返される値は整数 10 です。

`stoi`1 バイト文字が`strtol`呼び出された場合、関数の場合`strtol( str.c_str(), _Eptr, idx)``_Eptr`と同様に動作します。または`wcstol`ワイド文字の場合は、同様の方法で呼び出`wcstol(Str.c_str(), _Eptr, idx)`されると、 . 詳細については、「[strtol、wcstol、_strtol_l、_wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)」を参照してください。

の`str.c_str() == *_Eptr`場合`stoi`は、 型のオブジェクト`invalid_argument`をスローします。 このような呼び出しが`errno`設定される場合、または戻り値を型のオブジェクトとして表す可能性**`int`** がある場合は、型のオブジェクトを`out_of_range`スローします。 それ以外の場合 *、idx*が null ポインターでない場合`*_Eptr - str.c_str()`、`*idx`関数は に格納されます。

## <a name="stol"></a><a name="stol"></a>Stol

文字シーケンスを**`long`**.

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

*Str*\
変換する文字シーケンス。

*Idx*\
最初の未変換文字のインデックス値。

*ベース*\
使用する基数。

### <a name="return-value"></a>戻り値

長整数値。

### <a name="remarks"></a>解説

この関数は *、str*内の要素のシーケンスを、関数**`long`**`strtol( str.c_str(), _Eptr, idx)`の内部のオブジェクト`_Eptr`である場合と同じ型の値に変換します。 の`str.c_str() == *_Eptr`場合は、 型のオブジェクトを`invalid_argument`スローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合 *、idx*が null ポインターでない場合`*_Eptr -  str.c_str()`、`*idx`関数は、値を格納して返します。

## <a name="stold"></a><a name="stold"></a>ストルド

文字シーケンスを**`long double`**.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>パラメーター

*Str*\
変換する文字シーケンス。

*Idx*\
最初の未変換文字のインデックス値。

### <a name="return-value"></a>戻り値

値**`long double`**。

### <a name="remarks"></a>解説

この関数は *、str*内の要素のシーケンスを、関数**`long double`**`strtold( str.c_str(), _Eptr)`の内部のオブジェクト`_Eptr`である場合と同じ型の値に変換します。 の`str.c_str() == *_Eptr`場合は、 型のオブジェクトを`invalid_argument`スローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合 *、idx*が null ポインターでない場合`*_Eptr -  str.c_str()`、`*idx`関数は、値を格納して返します。

## <a name="stoll"></a><a name="stoll"></a>ストール

文字シーケンスを**`long long`**.

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

*Str*\
変換する文字シーケンス。

*Idx*\
最初の未変換文字のインデックス値。

*ベース*\
使用する基数。

### <a name="return-value"></a>戻り値

値**`long long`**。

### <a name="remarks"></a>解説

この関数は *、str*内の要素のシーケンスを、関数**`long long`**`strtoll( str.c_str(), _Eptr, idx)`の内部のオブジェクト`_Eptr`である場合と同じ型の値に変換します。 の`str.c_str() == *_Eptr`場合は、 型のオブジェクトを`invalid_argument`スローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合 *、idx*が null ポインターでない場合`*_Eptr -  str.c_str()`、`*idx`関数は、値を格納して返します。

## <a name="stoul"></a><a name="stoul"></a>ストル

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

*Str*\
変換する文字シーケンス。

*Idx*\
最初の未変換文字のインデックス値。

*ベース*\
使用する基数。

### <a name="return-value"></a>戻り値

unsigned long 整数値。

### <a name="remarks"></a>解説

この関数は *、str*内の要素のシーケンスを、関数**`unsigned long`**`strtoul( str.c_str(), _Eptr, idx)`の内部のオブジェクト`_Eptr`である場合と同じ型の値に変換します。 の`str.c_str() == *_Eptr`場合は、 型のオブジェクトを`invalid_argument`スローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合 *、idx*が null ポインターでない場合`*_Eptr -  str.c_str()`、`*idx`関数は、値を格納して返します。

## <a name="stoull"></a><a name="stoull"></a>ストゥール

文字シーケンスを に変換します**`unsigned long long`**。

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

*Str*\
変換する文字シーケンス。

*Idx*\
最初の未変換文字のインデックス値。

*ベース*\
使用する基数。

### <a name="return-value"></a>戻り値

値**`unsigned long long`**。

### <a name="remarks"></a>解説

この関数は *、str*内の要素のシーケンスを、関数**`unsigned long long`**`strtoull( str.c_str(), _Eptr, idx)`の内部のオブジェクト`_Eptr`である場合と同じ型の値に変換します。 の`str.c_str() == *_Eptr`場合は、 型のオブジェクトを`invalid_argument`スローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外の場合 *、idx*が null ポインターでない場合`*_Eptr -  str.c_str()`、`*idx`関数は、値を格納して返します。

## <a name="swap"></a><a name="swap"></a>スワップ

2 つの文字列の、文字の配列を交換します。

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左*\
要素が別の文字列の要素と入れ替わる文字列。

*そうです*\
最初の文字列と要素を交換するもう一方の文字列。

### <a name="remarks"></a>解説

テンプレート関数は、特殊なメンバ関数*を左*に実行します。[一](../standard-library/basic-string-class.md#swap)定の複雑さを保証する文字列のスワップ(*右*) 。

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

## <a name="to_string"></a><a name="to_string"></a>to_string

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

*値*\
変換する値。

### <a name="return-value"></a>戻り値

値を表す `string` 値。

### <a name="remarks"></a>解説

関数は、*値*を、関数内部の配列オブジェクト`Buf`に格納されている要素のシーケンスに変換`sprintf(Buf, Fmt, value)`します。 `Fmt`

- `"%d"`*値*がタイプの場合**`int`**

- `"%u"`*値*がタイプの場合**`unsigned int`**

- `"%ld"`*値*がタイプの場合**`long`**

- `"%lu"`*値*がタイプの場合**`unsigned long`**

- `"%lld"`*値*がタイプの場合**`long long`**

- `"%llu"`*値*がタイプの場合**`unsigned long long`**

- `"%f"`*値*がタイプまたはタイプ**`float`** の場合**`double`**

- `"%Lf"`*値*がタイプの場合**`long double`**

`string(Buf)` が返されます。

## <a name="to_wstring"></a><a name="to_wstring"></a>to_wstring

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

*値*\
変換する値。

### <a name="return-value"></a>戻り値

値を表すワイド文字列。

### <a name="remarks"></a>解説

関数は、*値*を、関数内部の配列オブジェクト`Buf`に格納されている要素のシーケンスに変換`swprintf(Buf, Len, Fmt, value)`します。 `Fmt`

- `L"%d"`*値*がタイプの場合**`int`**

- `L"%u"`*値*がタイプの場合**`unsigned int`**

- `L"%ld"`*値*がタイプの場合**`long`**

- `L"%lu"`*値*がタイプの場合**`unsigned long`**

- `L"%lld"`*値*がタイプの場合**`long long`**

- `L"%llu"`*値*がタイプの場合**`unsigned long long`**

- `L"%f"`*値*がタイプまたはタイプ**`float`** の場合**`double`**

- `L"%Lf"`*値*がタイプの場合**`long double`**

`wstring(Buf)` が返されます。

## <a name="see-also"></a>関連項目

[\<文字列>](../standard-library/string.md)
