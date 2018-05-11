---
title: '&lt;string&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 0089a7259601b766bff3b470c5ba23c1b9952fb6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltstringgt-functions"></a>&lt;string&gt; 関数

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[swap](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a>  getline

入力ストリームから文字列を行単位で抽出します。

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delim);


template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delim);


// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str);


template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>パラメーター

`is` 文字列を抽出する元となる入力ストリーム。

`str` 読み込み先となる文字の入力ストリームから文字列です。

`delim` 行の区切り記号。

### <a name="return-value"></a>戻り値

入力ストリーム `is`。

### <a name="remarks"></a>コメント

`(1)` としてマークされた関数シグネチャのペアが、`is` が検出されるまで `delim` から文字を抽出し、それらを `str` に格納します。

`(2)` としてマークされた関数シグネチャのペアが、既定行の区切り文字として改行文字を使用し、**getline**( `is`, `str`, `is`. `widen`(' `\n`')) として動作します。

各ペアの 2 つ目の関数では、1 つ目の関数と同様に、[右辺値参照](../cpp/lvalues-and-rvalues-visual-cpp.md)がサポートされます。

抽出は、次のいずれかが発生したときに停止します。

- ファイルの末尾に達した場合。このとき、内部状態フラグ `is` は `ios_base::eofbit` に設定されます。

- 関数が **delim** と等しい要素を抽出した場合。このとき、抽出された要素が制御対象シーケンスに戻されたり、追加されたりすることはありません。

- 関数が `str.`[max_size](../standard-library/basic-string-class.md#max_size) 要素を抽出した場合。このとき、内部状態フラグ `is` は `ios_base::failbit` に設定されます。

- 上記に含まれていないその他のエラーが発生した場合。このとき、内部状態フラグ `is` は `ios_base::badbit` に設定されます。

内部状態フラグについては、「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照してください。

関数が要素を抽出しなかった場合、内部状態フラグ `is` は `ios_base::failbit` に設定されます。 いずれの場合も、`getline` は `is` を返します。

例外がスローされた場合、`is` と `str` は引き続き有効な状態になります。

### <a name="example"></a>例

次のコードは、2 つのモードの `getline()` を示しています。1 つ目は既定の区切り文字 (改行文字)、2 つ目は区切り文字として空白文字を使用しています。 また、while ループの終了を制御するために、ファイル終端文字 (Ctrl + Z キー) を使用しています。 この文字により、内部状態フラグ `cin` が `eofbit` に設定されます。2 つ目の while ループを正常に動作させるには、このフラグを [basic_ios::clear()](../standard-library/basic-ios-class.md#clear) でクリアする必要があります。

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

## <a name="stod"></a>  stod

文字シーケンスを `double` に変換します。

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

|パラメーター|説明|
|---------------|-----------------|
|`str`|変換する文字シーケンス。|
|`idx`|最初の未変換文字のインデックス値。|

### <a name="return-value"></a>戻り値

`double` 値。

### <a name="remarks"></a>コメント

この関数は、`str` を呼び出したときと同じように、`val` 内の要素のシーケンスを `double` 型の値 `strtod( str.c_str(), _Eptr)` に変換します。`_Eptr` は関数の内部オブジェクトです。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外で、`idx` が null ポインターではない場合、この関数は `*_Eptr -  str.c_str()` を `*idx` に格納し、`val` を返します。

## <a name="stof"></a>  stof

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

|パラメーター|説明|
|---------------|-----------------|
|`str`|変換する文字シーケンス。|
|`idx`|最初の未変換文字のインデックス値。|

### <a name="return-value"></a>戻り値

浮動小数点数値。

### <a name="remarks"></a>コメント

この関数は、`str` を呼び出したときと同じように、`val` 内の要素のシーケンスを `float` 型の値 `strtof( str.c_str(), _Eptr)` に変換します。`_Eptr` は関数の内部オブジェクトです。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外で、`idx` が null ポインターではない場合、この関数は `*_Eptr -  str.c_str()` を `*idx` に格納し、`val` を返します。

## <a name="stoi"></a>  stoi

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

|パラメーター|説明|
|---------------|-----------------|
|`str`|変換する文字シーケンス。|
|`idx`|値が返されるときに、最初の未変換文字のインデックスが格納されます。|
|`base`|使用する基数。|

### <a name="remarks"></a>コメント

関数 `stoi` は、`str` 内の文字のシーケンスを `int` 型の値に変換し、その値を返します。 たとえば、文字シーケンス "10" を渡した場合、`stoi` によって返される値は整数 10 です。

1 バイト文字に対しては、`stoi` は `strtol` の形式で呼び出された場合の `strtol( str.c_str(), _Eptr, idx)` と同様に動作します。`_Eptr` は関数の内部オブジェクトです。ワイド文字に対しては、類似した `wcstol` の形式で呼び出された場合の `wcstol(Str.c_str(), _Eptr, idx)` と同様に動作します。 詳細については、「[strtol、wcstol、_strtol_l、_wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)」を参照してください。

場合`str.c_str() == *_Eptr`、`stoi`型のオブジェクトをスロー`invalid_argument`です。 このような呼び出しによって `errno` が設定されるか、戻り値を `int` 型のオブジェクトとして表すことができない場合、`out_of_range` 型のオブジェクトをスローします。 それ以外で、`idx` が null ポインターではない場合、この関数は `*_Eptr - str.c_str()` を `*idx` に格納します。

## <a name="stol"></a>  stol

文字シーケンスを `long` に変換します。

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

|パラメーター|説明|
|---------------|-----------------|
|`str`|変換する文字シーケンス。|
|`idx`|最初の未変換文字のインデックス値。|
|`base`|使用する基数。|

### <a name="return-value"></a>戻り値

長整数値。

### <a name="remarks"></a>コメント

この関数は、`str` を呼び出したときと同じように、`val` 内の要素のシーケンスを `long` 型の値 `strtol( str.c_str(), _Eptr, idx)` に変換します。`_Eptr` は関数の内部オブジェクトです。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外で、`idx` が null ポインターではない場合、この関数は `*_Eptr -  str.c_str()` を `*idx` に格納し、`val` を返します。

## <a name="stold"></a>  stold

文字シーケンスを `long double` に変換します。

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`str`|変換する文字シーケンス。|
|`idx`|最初の未変換文字のインデックス値。|

### <a name="return-value"></a>戻り値

`long double` 値。

### <a name="remarks"></a>コメント

この関数は、`str` を呼び出したときと同じように、`val` 内の要素のシーケンスを `long double` 型の値 `strtold( str.c_str(), _Eptr)` に変換します。`_Eptr` は関数の内部オブジェクトです。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外で、`idx` が null ポインターではない場合、この関数は `*_Eptr -  str.c_str()` を `*idx` に格納し、`val` を返します。

## <a name="stoll"></a>  stoll

文字シーケンスを `long long` に変換します。

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

|パラメーター|説明|
|---------------|-----------------|
|`str`|変換する文字シーケンス。|
|`idx`|最初の未変換文字のインデックス値。|
|`base`|使用する基数。|

### <a name="return-value"></a>戻り値

`long long` 値。

### <a name="remarks"></a>コメント

この関数は、`str` を呼び出したときと同じように、`val` 内の要素のシーケンスを `long long` 型の値 `strtoll( str.c_str(), _Eptr, idx)` に変換します。`_Eptr` は関数の内部オブジェクトです。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外で、`idx` が null ポインターではない場合、この関数は `*_Eptr -  str.c_str()` を `*idx` に格納し、`val` を返します。

## <a name="stoul"></a>  stoul

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

|パラメーター|説明|
|---------------|-----------------|
|`str`|変換する文字シーケンス。|
|`idx`|最初の未変換文字のインデックス値。|
|`base`|使用する基数。|

### <a name="return-value"></a>戻り値

unsigned long 整数値。

### <a name="remarks"></a>コメント

この関数は、`str` を呼び出したときと同じように、`val` 内の要素のシーケンスを `unsigned long` 型の値 `strtoul( str.c_str(), _Eptr, idx)` に変換します。`_Eptr` は関数の内部オブジェクトです。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外で、`idx` が null ポインターではない場合、この関数は `*_Eptr -  str.c_str()` を `*idx` に格納し、`val` を返します。

## <a name="stoull"></a>  stoull

文字シーケンスを `unsigned long long` に変換します。

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

|パラメーター|説明|
|---------------|-----------------|
|`str`|変換する文字シーケンス。|
|`idx`|最初の未変換文字のインデックス値。|
|`base`|使用する基数。|

### <a name="return-value"></a>戻り値

`unsigned long long` 値。

### <a name="remarks"></a>コメント

この関数は、`str` を呼び出したときと同じように、`val` 内の要素のシーケンスを `unsigned long long` 型の値 `strtoull( str.c_str(), _Eptr, idx)` に変換します。`_Eptr` は関数の内部オブジェクトです。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 それ以外で、`idx` が null ポインターではない場合、この関数は `*_Eptr -  str.c_str()` を `*idx` に格納し、`val` を返します。

## <a name="swap"></a>  swap

2 つの文字列の、文字の配列を交換します。

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

`left` 1 つ要素の文字列を別の文字列のものと交換します。

`right` その他の要素の文字列を交換する最初の文字列。

### <a name="remarks"></a>コメント

このテンプレート関数は、特殊なメンバー関数を実行します*左*.[スワップ](../standard-library/basic-string-class.md#swap)(*右*) 文字列は、一定の複雑さを保証します。

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

## <a name="to_string"></a>  to_string

値を `string` に変換します。

```cpp
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Val`|変換する値。|

### <a name="return-value"></a>戻り値

値を表す `string` 値。

### <a name="remarks"></a>コメント

関数は `Val` を呼び出すように、`Buf` を関数内部の配列オブジェクト `sprintf(Buf, Fmt, Val)` に格納された要素シーケンスに変換します。ここで、`Fmt` は

- `"%d"` に `Val` 型がある場合、`int` です。

- `"%u"` に `Val` 型がある場合、`unsigned int` です。

- `"%ld"` に `Val` 型がある場合、`long` です。

- `"%lu"` に `Val` 型がある場合、`unsigned long` です。

- `"%lld"` に `Val` 型がある場合、`long long` です。

- `"%llu"` に `Val` 型がある場合、`unsigned long long` です。

- `"%f"` に `Val` 型または `float` 型がある場合、`double` です。

- `"%Lf"` に `Val` 型がある場合、`long double` です。

`string(Buf)` が返されます。

## <a name="to_wstring"></a>  to_wstring

値をワイド文字列に変換します。

```cpp
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Val`|変換する値。|

### <a name="return-value"></a>戻り値

値を表すワイド文字列。

### <a name="remarks"></a>コメント

関数は `Val` を呼び出すように、`Buf` を関数内部の配列オブジェクト `swprintf(Buf, Len, Fmt, Val)` に格納された要素シーケンスに変換します。ここで、`Fmt` は

- `L"%d"` に `Val` 型がある場合、`int` です。

- `L"%u"` に `Val` 型がある場合、`unsigned int` です。

- `L"%ld"` に `Val` 型がある場合、`long` です。

- `L"%lu"` に `Val` 型がある場合、`unsigned long` です。

- `L"%lld"` に `Val` 型がある場合、`long long` です。

- `L"%llu"` に `Val` 型がある場合、`unsigned long long` です。

- `L"%f"` に `Val` 型または `float` 型がある場合、`double` です。

- `L"%Lf"` に `Val` 型がある場合、`long double` です。

`wstring(Buf)` が返されます。

## <a name="see-also"></a>関連項目

[\<string>](../standard-library/string.md)<br/>
