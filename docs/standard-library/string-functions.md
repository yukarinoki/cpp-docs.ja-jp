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
ms.openlocfilehash: 6534d93b4f04826188fa13c942efd080e152aebe
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954904"
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

** 文字列の抽出元の入力ストリーム。

*str*先は、文字のストリームから読み取った入力文字列。

*delim*行の区切り記号。

### <a name="return-value"></a>戻り値

入力ストリーム*は*します。

### <a name="remarks"></a>Remarks

マークされた関数シグネチャのペア`(1)`文字の抽出元*は*まで*delim*格納することで、見つかった*str*します。

マークされた関数シグネチャのペア`(2)`既定行の区切り記号として改行文字を使用して、として動作**getline**(`is`、 `str`、`is`します。 `widen`(' `\n`')) として動作します。

各ペアの 2 つ目の関数では、1 つ目の関数と同様に、[右辺値参照](../cpp/lvalues-and-rvalues-visual-cpp.md)がサポートされます。

抽出は、次のいずれかが発生したときに停止します。

- ファイルの末尾、その場合、内部状態フラグ*は*に設定されている`ios_base::eofbit`します。

- 関数が `delim` と等しい要素を抽出した場合。このとき、抽出された要素が制御対象シーケンスに戻されたり、追加されたりすることはありません。

- 関数抽出後`str.` [max_size](../standard-library/basic-string-class.md#max_size)を要素の内部状態フラグのケース*は*に設定されている`ios_base::failbit`します。

- その他のエラー以外上記に示した、その場合、内部状態フラグ*は*に設定されています。 `ios_base::badbit`

内部状態フラグについては、「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照してください。

関数が要素を抽出しなかった場合、内部状態フラグ*は*に設定されている`ios_base::failbit`します。 いずれの場合も、`getline`返します*は*します。

例外がスローされた場合*は*と*str*有効な状態で残されます。

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

文字シーケンスに変換する**二重**します。

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
|*str*|変換する文字シーケンス。|
|*idx*|最初の未変換文字のインデックス値。|

### <a name="return-value"></a>戻り値

**二重**値。

### <a name="remarks"></a>Remarks

関数内の要素のシーケンスを変換する*str*値に`val`型の**二重**を呼び出した場合と`strtod( str.c_str(), _Eptr)`ここで、`_Eptr`関数の内部オブジェクトは、します。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 の場合*idx*関数は、null ポインターではない`*_Eptr -  str.c_str()`で`*idx`返します`val`します。

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
|*str*|変換する文字シーケンス。|
|*idx*|最初の未変換文字のインデックス値。|

### <a name="return-value"></a>戻り値

浮動小数点数値。

### <a name="remarks"></a>Remarks

関数内の要素のシーケンスを変換する*str*値に`val`型の**float**を呼び出した場合と`strtof( str.c_str(), _Eptr)`ここで、`_Eptr`関数の内部オブジェクトは、します。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 の場合*idx*関数は、null ポインターではない`*_Eptr -  str.c_str()`で`*idx`返します`val`します。

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
|*str*|変換する文字シーケンス。|
|*idx*|値が返されるときに、最初の未変換文字のインデックスが格納されます。|
|*base*|使用する基数。|

### <a name="remarks"></a>Remarks

関数は、`stoi`内の文字シーケンスに変換します*str*型の値に**int**値を返します。 たとえば、文字シーケンス "10" を渡した場合、`stoi` によって返される値は整数 10 です。

1 バイト文字に対しては、`stoi` は `strtol` の形式で呼び出された場合の `strtol( str.c_str(), _Eptr, idx)` と同様に動作します。`_Eptr` は関数の内部オブジェクトです。ワイド文字に対しては、類似した `wcstol` の形式で呼び出された場合の `wcstol(Str.c_str(), _Eptr, idx)` と同様に動作します。 詳細については、「[strtol、wcstol、_strtol_l、_wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)」を参照してください。

場合`str.c_str() == *_Eptr`、`stoi`型のオブジェクトをスローします`invalid_argument`します。 このような呼び出しを設定する場合`errno`、型のオブジェクトとして返される値を表すことができない場合または**int**、型のオブジェクトをスローします`out_of_range`します。 の場合*idx*関数は、null ポインターではない`*_Eptr - str.c_str()`で`*idx`します。

## <a name="stol"></a>  stol

文字シーケンスに変換する**長い**。

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
|*str*|変換する文字シーケンス。|
|*idx*|最初の未変換文字のインデックス値。|
|*base*|使用する基数。|

### <a name="return-value"></a>戻り値

長整数値。

### <a name="remarks"></a>Remarks

関数内の要素のシーケンスを変換する*str*値に`val`型の**長い**を呼び出した場合と`strtol( str.c_str(), _Eptr, idx)`ここで、`_Eptr`関数の内部オブジェクトは、します。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 の場合*idx*関数は、null ポインターではない`*_Eptr -  str.c_str()`で`*idx`返します`val`します。

## <a name="stold"></a>  stold

文字シーケンスに変換する**long double**します。

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
|*str*|変換する文字シーケンス。|
|*idx*|最初の未変換文字のインデックス値。|

### <a name="return-value"></a>戻り値

**Long double**値。

### <a name="remarks"></a>Remarks

関数内の要素のシーケンスを変換する*str*値に`val`型の**long double**を呼び出した場合と`strtold( str.c_str(), _Eptr)`ここで、`_Eptr`関数の内部オブジェクトは、します。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 の場合*idx*関数は、null ポインターではない`*_Eptr -  str.c_str()`で`*idx`返します`val`します。

## <a name="stoll"></a>  stoll

文字シーケンスに変換する**long**。

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
|*str*|変換する文字シーケンス。|
|*idx*|最初の未変換文字のインデックス値。|
|*base*|使用する基数。|

### <a name="return-value"></a>戻り値

**Long**値。

### <a name="remarks"></a>Remarks

関数内の要素のシーケンスを変換する*str*値に`val`型の**long**を呼び出した場合と`strtoll( str.c_str(), _Eptr, idx)`ここで、`_Eptr`関数の内部オブジェクトは、します。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 の場合*idx*関数は、null ポインターではない`*_Eptr -  str.c_str()`で`*idx`返します`val`します。

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
|*str*|変換する文字シーケンス。|
|*idx*|最初の未変換文字のインデックス値。|
|*base*|使用する基数。|

### <a name="return-value"></a>戻り値

unsigned long 整数値。

### <a name="remarks"></a>Remarks

関数内の要素のシーケンスを変換する*str*値に`val`型の**unsigned long**を呼び出した場合と`strtoul( str.c_str(), _Eptr, idx)`ここで、`_Eptr`オブジェクトを関数の内部には. ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 の場合*idx*関数は、null ポインターではない`*_Eptr -  str.c_str()`で`*idx`返します`val`します。

## <a name="stoull"></a>  stoull

文字シーケンスに変換する**unsigned long long 型**します。

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
|*str*|変換する文字シーケンス。|
|*idx*|最初の未変換文字のインデックス値。|
|*base*|使用する基数。|

### <a name="return-value"></a>戻り値

**Unsigned long long 型**値。

### <a name="remarks"></a>Remarks

関数内の要素のシーケンスを変換する*str*値に`val`型の**unsigned long long 型**を呼び出した場合と`strtoull( str.c_str(), _Eptr, idx)`ここで、`_Eptr`オブジェクトの内部に、関数。 ` str.c_str() == *_Eptr` の場合、`invalid_argument` 型のオブジェクトをスローします。 このような呼び出しによって `errno` が設定される場合、`out_of_range` 型のオブジェクトをスローします。 の場合*idx*関数は、null ポインターではない`*_Eptr -  str.c_str()`で`*idx`返します`val`します。

## <a name="swap"></a>  swap

2 つの文字列の、文字の配列を交換します。

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

*左*別の文字列を交換する要素が 1 つの文字列。

*適切な*要素が最初の文字列を交換する他の文字列。

### <a name="remarks"></a>Remarks

テンプレート関数は、特殊なメンバー関数を実行します*左*。[ 。スワップ](../standard-library/basic-string-class.md#swap)(*右*) 一定の複雑さを保証する文字列の場合。

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
|*val*|変換する値。|

### <a name="return-value"></a>戻り値

値を表す `string` 値。

### <a name="remarks"></a>Remarks

関数は、 *Val*配列オブジェクトに格納されている要素のシーケンスに`Buf`を呼び出した場合、関数に内部`sprintf(Buf, Fmt, Val)`ここで、`Fmt`は

- `"%d"` 場合`Val`型を持つ**int**

- `"%u"` 場合`Val`型を持つ**符号なし int**

- `"%ld"` 場合`Val`型を持つ**長**

- `"%lu"` 場合`Val`型を持つ**unsigned long**

- `"%lld"` 場合`Val`型を持つ**long**

- `"%llu"` 場合`Val`型を持つ**unsigned long long 型**

- `"%f"` 場合`Val`型を持つ**float**または**double**

- `"%Lf"` 場合`Val`型を持つ**long double**

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

### <a name="remarks"></a>Remarks

関数は `Val` を呼び出すように、`Buf` を関数内部の配列オブジェクト `swprintf(Buf, Len, Fmt, Val)` に格納された要素シーケンスに変換します。ここで、`Fmt` は

- `L"%d"` 場合`Val`型を持つ**int**

- `L"%u"` 場合`Val`型を持つ**符号なし int**

- `L"%ld"` 場合`Val`型を持つ**長**

- `L"%lu"` 場合`Val`型を持つ**unsigned long**

- `L"%lld"` 場合`Val`型を持つ**long**

- `L"%llu"` 場合`Val`型を持つ**unsigned long long 型**

- `L"%f"` 場合`Val`型を持つ**float**または**double**

- `L"%Lf"` 場合`Val`型を持つ**long double**

`wstring(Buf)` が返されます。

## <a name="see-also"></a>関連項目

[\<string>](../standard-library/string.md)<br/>
