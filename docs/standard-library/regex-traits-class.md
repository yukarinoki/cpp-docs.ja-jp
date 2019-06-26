---
title: regex_traits クラス
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_traits
- regex/std::regex_traits::char_type
- regex/std::regex_traits::size_type
- regex/std::regex_traits::string_type
- regex/std::regex_traits::locale_type
- regex/std::regex_traits::char_class_type
- regex/std::regex_traits::length
- regex/std::regex_traits::translate
- regex/std::regex_traits::translate_nocase
- regex/std::regex_traits::transform
- regex/std::regex_traits::transform_primary
- regex/std::regex_traits::lookup_classname
- regex/std::regex_traits::lookup_collatename
- regex/std::regex_traits::isctype
- regex/std::regex_traits::value
- regex/std::regex_traits::imbue
- regex/std::regex_traits::getloc
helpviewer_keywords:
- std::regex_traits [C++]
- std::regex_traits [C++], char_type
- std::regex_traits [C++], size_type
- std::regex_traits [C++], string_type
- std::regex_traits [C++], locale_type
- std::regex_traits [C++], char_class_type
- std::regex_traits [C++], length
- std::regex_traits [C++], translate
- std::regex_traits [C++], translate_nocase
- std::regex_traits [C++], transform
- std::regex_traits [C++], transform_primary
- std::regex_traits [C++], lookup_classname
- std::regex_traits [C++], lookup_collatename
- std::regex_traits [C++], isctype
- std::regex_traits [C++], value
- std::regex_traits [C++], imbue
- std::regex_traits [C++], getloc
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
ms.openlocfilehash: 47e0a1e51809efad2924a2051d1627fe2e9ff95f
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400670"
---
# <a name="regextraits-class"></a>regex_traits クラス

照合する要素の特性を記述します。

## <a name="syntax"></a>構文

```cpp
template<class Elem>
class regex_traits
```

## <a name="parameters"></a>パラメーター

*Elem*<br/>
記述する文字要素の型。

## <a name="remarks"></a>Remarks

このテンプレート クラスは、型のさまざまな正規表現の特性を表します*Elem*します。 テンプレート クラスは、 [basic_regex クラス](../standard-library/basic-regex-class.md)この情報を使用して型の要素を操作する*Elem*します。

各 `regex_traits` オブジェクトは、そのオブジェクトの一部のメンバー関数が使用する `regex_traits::locale` 型のオブジェクトを保持します。 既定のロケールは、 `regex_traits::locale()`のコピーです。 メンバー関数 `imbue` は、ロケール オブジェクトを置き換えます。また、メンバー関数 `getloc` は、ロケール オブジェクトのコピーを返します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[regex_traits](#regex_traits)|オブジェクトを構築します。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[char_class_type](#char_class_type)|文字クラス指定子の型。|
|[char_type](#char_type)|要素の型。|
|[locale_type](#locale_type)|格納されているロケール オブジェクトの型。|
|[size_type](#size_type)|シーケンスの長さの型。|
|[string_type](#string_type)|要素の文字列の型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[getloc](#getloc)|格納されているロケール オブジェクトを返します。|
|[imbue](#imbue)|格納されているロケール オブジェクトを変更します。|
|[isctype](#isctype)|クラスのメンバーシップをテストします。|
|[length](#length)|Null で終わるシーケンスの長さを返します。|
|[lookup_classname](#lookup_classname)|シーケンスを文字クラスにマップします。|
|[lookup_collatename](#lookup_collatename)|シーケンスを照合要素にマップします。|
|[transform](#transform)|同等の順序付けられたシーケンスに変換します。|
|[transform_primary](#transform_primary)|同等のケースレス順序付きシーケンスに変換します。|
|[translate](#translate)|一致する同等の要素に変換します。|
|[translate_nocase](#translate_nocase)|一致する同等のケースレス要素に変換します。|
|[value](#value)|要素を数値に変換します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<regex>

**名前空間:** std

## <a name="example"></a>例

```cpp
// std__regex__regex_traits.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_traits<char> Mytr;
int main()
    {
    Mytr tr;

    Mytr::char_type ch = tr.translate('a');
    std::cout << "translate('a') == 'a' == " << std::boolalpha
        << (ch == 'a') << std::endl;

    std::cout << "nocase 'a' == 'A' == " << std::boolalpha
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))
        << std::endl;

    const char *lbegin = "abc";
    const char *lend = lbegin + strlen(lbegin);
    Mytr::size_type size = tr.length(lbegin);
    std::cout << "length(\"abc\") == " << size <<std::endl;

    Mytr::string_type str = tr.transform(lbegin, lend);
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha
        << (str < "abc") << std::endl;

    const char *ubegin = "ABC";
    const char *uend = ubegin + strlen(ubegin);
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha
        << (tr.transform_primary(ubegin, uend) <
            tr.transform_primary(lbegin, lend))
        << std::endl;

    const char *dig = "digit";
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);
    std::cout << "class digit == d == " << std::boolalpha
        << (cl == tr.lookup_classname(dig, dig + 1))
        << std::endl;

    std::cout << "'3' is digit == " <<std::boolalpha
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))
        << std::endl;

    std::cout << "hex C == " << tr.value('C', 16) << std::endl;

// other members
    str = tr.lookup_collatename(dig, dig + 5);

    Mytr::locale_type loc = tr.getloc();
    tr.imbue(loc);

    return (0);
    }
```

```Output
translate('a') == 'a' == true
nocase 'a' == 'A' == true
length("abc") == 3
transform("abc") < "abc" == false
primary "ABC" < "abc" == false
class digit == d == true
'3' is digit == true
hex C == 12
```

## <a name="char_class_type"></a>  regex_traits::char_class_type

文字クラス指定子の型。

```cpp
typedef T8 char_class_type;
```

### <a name="remarks"></a>Remarks

この型は、文字クラスを指定する未指定の型のシノニムです。 この型の値は、 `|` 演算子で連結して、オペランドで指定されたクラスの共用体である文字クラスを指定することができます。

## <a name="char_type"></a>  regex_traits::char_type

要素の型。

```cpp
typedef Elem char_type;
```

### <a name="remarks"></a>Remarks

この typedef は、テンプレート引数 `Elem` のシノニムです。

## <a name="getloc"></a>  regex_traits::getloc

格納されているロケール オブジェクトを返します。

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Remarks

メンバー関数は、格納されている `locale` オブジェクトを返します。

## <a name="imbue"></a>  regex_traits::imbue

格納されているロケール オブジェクトを変更します。

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>パラメーター

*loc*<br/>
格納するロケール オブジェクト。

### <a name="remarks"></a>Remarks

メンバー関数のコピー *loc*に格納されている`locale`オブジェクトし、格納されているは、前の値のコピーを返します`locale`オブジェクト。

## <a name="isctype"></a>  regex_traits::isctype

クラスのメンバーシップをテストします。

```cpp
bool isctype(char_type ch, char_class_type cls) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
テストする要素。

*cls*<br/>
テストするクラス。

### <a name="remarks"></a>Remarks

場合にのみ、メンバー関数は true を返します文字*ch*によって指定された文字クラスでは、 *cls*します。

## <a name="length"></a>  regex_traits::length

Null で終わるシーケンスの長さを返します。

```cpp
static size_type length(const char_type *str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
Null 終端シーケンス。

### <a name="remarks"></a>Remarks

この静的メンバー関数は `std::char_traits<char_type>::length(str)`を返します。

## <a name="locale_type"></a>  regex_traits::locale_type

格納されているロケール オブジェクトの型。

```cpp
typedef T7 locale_type;
```

### <a name="remarks"></a>Remarks

typedef は、ロケールをカプセル化する型の同意語です。 特化された型である `regex_traits<char>` と `regex_traits<wchar_t>` では、`std::locale` の同意語です。

## <a name="lookup_classname"></a>  regex_traits::lookup_classname

シーケンスを文字クラスにマップします。

```cpp
template <class FwdIt>
char_class_type lookup_classname(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>パラメーター

*first*<br/>
検索するシーケンスの最初。

*last*<br/>
検索するシーケンスの最後。

### <a name="remarks"></a>Remarks

このメンバー関数は、引数が指し示す文字シーケンスによって指定された文字クラスを表す値を返します。 この値は、シーケンス内の文字のケース (大文字と小文字) には依存しません。

特殊化した`regex_traits<char>` は、大文字と小文字の区別に関係なく、各種の名前 (`"d"`、`"s"`、`"w"`、`"alnum"`、`"alpha"`、`"blank"`、`"cntrl"`、`"digit"`、`"graph"`、`"lower"`、`"print"`、`"punct"`、`"space"`、`"upper"`、`"xdigit"` など) を認識します。

特殊化した`regex_traits<wchar_t>` は、大文字と小文字の区別に関係なく、各種の名前 (`L"d"`、`L"s"`、`L"w"`、`L"alnum"`、`L"alpha"`、`L"blank"`、`L"cntrl"`、`L"digit"`、`L"graph"`、`L"lower"`、`L"print"`、`L"punct"`、`L"space"`、`L"upper"`、`L"xdigit"` など) を認識します。

## <a name="lookup_collatename"></a>  regex_traits::lookup_collatename

シーケンスを照合要素にマップします。

```cpp
template <class FwdIt>
string_type lookup_collatename(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>パラメーター

*first*<br/>
検索するシーケンスの最初。

*last*<br/>
検索するシーケンスの最後。

### <a name="remarks"></a>Remarks

このメンバー関数は、シーケンス `[first, last)` に対応する照合要素を含んだ文字列オブジェクトを返します。シーケンスが有効な照合要素でない場合は、空の文字列を返します。

## <a name="regex_traits"></a>  regex_traits::regex_traits

オブジェクトを構築します。

```cpp
regex_traits();
```

### <a name="remarks"></a>Remarks

コンストラクターは、格納された `locale` オブジェクトが既定ロケールに初期化されるオブジェクトを作成します。

## <a name="size_type"></a>  regex_traits::size_type

シーケンスの長さの型。

```cpp
typedef T6 size_type;
```

### <a name="remarks"></a>Remarks

Typedef は符号なし整数型の同意語です。 特化された型である `regex_traits<char>` と `regex_traits<wchar_t>` では、`std::size_t` の同意語です。

typedef は、`std::size_t` の同意語です。

## <a name="string_type"></a>  regex_traits::string_type

要素の文字列の型。

```cpp
typedef basic_string<Elem> string_type;
```

### <a name="remarks"></a>Remarks

typedef は、`basic_string<Elem>` の同意語です。

## <a name="transform"></a>  regex_traits::transform

同等の順序付けられたシーケンスに変換します。

```cpp
template <class FwdIt>
string_type transform(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>パラメーター

*first*<br/>
変換するシーケンスの最初。

*last*<br/>
変換するシーケンスの最後。

### <a name="remarks"></a>Remarks

このメンバー関数は、格納されている `locale` オブジェクトによって異なる変換規則を使用して生成された文字列を返します。 反復子の範囲の `[first1, last1)` と `[first2, last2)`で指定された 2 つの文字シーケンスでは、反復子の範囲 `transform(first1, last1) < transform(first2, last2)` で指定された文字シーケンスが、反復子の範囲 `[first1, last1)` で指定された文字シーケンスより前に来る場合は、 `[first2, last2)`です。

## <a name="transform_primary"></a>  regex_traits::transform_primary

同等のケースレス順序付きシーケンスに変換します。

```cpp
template <class FwdIt>
string_type transform_primary(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>パラメーター

*first*<br/>
変換するシーケンスの最初。

*last*<br/>
変換するシーケンスの最後。

### <a name="remarks"></a>Remarks

このメンバー関数は、格納されている `locale` オブジェクトによって異なる変換規則を使用して生成された文字列を返します。 反復子の範囲の `[first1, last1)` と `[first2, last2)`で指定された 2 つの文字シーケンスでは、反復子の範囲 `transform_primary(first1, last1) < transform_primary(first2, last2)` で指定された文字シーケンスが、ケースやアクセントに関係なく、反復子の範囲 `[first1, last1)` で指定された文字シーケンスより前に来る場合は、 `[first2, last2)` です。

## <a name="translate"></a>  regex_traits::translate

一致する同等の要素に変換します。

```cpp
char_type translate(char_type ch) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
変換する要素。

### <a name="remarks"></a>Remarks

このメンバー関数は、格納されている `locale` オブジェクトによって異なる変換規則を使用して生成された文字を返します。 2 つの `char_type` オブジェクト `ch1` と `ch2`があるとします。一方が正規表現の定義に出現し、もう一方がターゲット シーケンス内の対応する位置に出現した場合にロケールを区別して比較して `translate(ch1) == translate(ch2)` と `ch1` が一致するときのみ、 `ch2` になります。

## <a name="translate_nocase"></a>  regex_traits::translate_nocase

一致する同等のケースレス要素に変換します。

```cpp
char_type translate_nocase(char_type ch) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
変換する要素。

### <a name="remarks"></a>Remarks

このメンバー関数は、格納されている `locale` オブジェクトによって異なる変換規則を使用して生成された文字を返します。 2 つの `char_type` オブジェクト `ch1` と `ch2`では、 `translate_nocase(ch1) == translate_nocase(ch2)` と `ch1` のいずれか一方が正規表現の定義で出現し、もう一方がターゲット シーケンス内の対応する位置に出現し、大文字と小文字を区別せずに比較して両者が一致する場合に限り、 `ch2` になります。

## <a name="value"></a>  regex_traits::value

要素を数値に変換します。

```cpp
int value(Elem ch, int radix) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
変換する要素。

*radix*<br/>
使用する算術的な基数。

### <a name="remarks"></a>Remarks

このメンバー関数は文字で表される値を返します*ch*ベース*基数*、場合は-1 *ch*ベースで有効な数字でない*基数*. 関数でのみ呼び出される、*基数*8、10、または 16 の引数。

## <a name="see-also"></a>関連項目

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants クラス](../standard-library/regex-constants-class.md)<br/>
[regex_error クラス](../standard-library/regex-error-class.md)<br/>
[\<regex> 系関数](../standard-library/regex-functions.md)<br/>
[regex_iterator クラス](../standard-library/regex-iterator-class.md)<br/>
[\<regex> 系演算子](../standard-library/regex-operators.md)<br/>
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)<br/>
[\<regex> typedefs](../standard-library/regex-typedefs.md)<br/>
[regex_traits\<char > クラス](../standard-library/regex-traits-char-class.md)<br/>
[regex_traits\<wchar_t> クラス](../standard-library/regex-traits-wchar-t-class.md)<br/>
