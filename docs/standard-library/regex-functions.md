---
title: '&lt;regex&gt; 関数'
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_match
- regex/std::regex_replace
- regex/std::regex_search
- regex/std::swap
ms.assetid: 91a8314b-6f7c-4e33-b7d6-d8583dd75585
helpviewer_keywords:
- std::regex_match [C++]
- std::regex_replace [C++]
- std::regex_search [C++]
- std::swap [C++]
- std::swap [C++]
ms.openlocfilehash: ff6ea37208aef19431bf7aefe612dccd589c638b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374544"
---
# <a name="ltregexgt-functions"></a>&lt;regex&gt; 関数

|||
|-|-|
|[regex_match](#regex_match)|正規表現がターゲット文字列全体と一致するかどうかをテストします。|
|[regex_replace](#regex_replace)|一致した正規表現を置換します。|
|[regex_search](#regex_search)|正規表現との一致を検索します。|
|[スワップ](#swap)|2 つまたは`basic_regex``match_results`複数のオブジェクトを入れ替えます。|

## <a name="regex_match"></a><a name="regex_match"></a>regex_match

正規表現がターゲット文字列全体と一致するかどうかをテストします。

```cpp
// (1)
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (2)
template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (3)
template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (4)
template <class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (5)
template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (6)
template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>パラメーター

*ビッドイット*\
サブマッチ用の反復子の型。 一般的なケース`string::const_iterator`では、 `wstring::const_iterator`、 `const char*` `const wchar_t*`、または のこの 1 つ。

*Alloc*\
一致結果のアロケーター クラス。

*Elem*\
一致させる要素の型。 一般的なケースでは`string`、 `wstring` `char*` 、 `wchar_t*`、または です。

*ラックストレイツ*\
要素の特徴 (traits) クラス。

*オロック2*\
正規表現のアロケーター クラス。

*イオトシツ*\
文字列の特徴 (traits) クラス。

*イオアロック*\
文字列のアロケーター クラス。

*フラグ*\
一致のフラグ。

*まずは*\
一致させるシーケンスの先頭。

*前の*\
一致させるシーケンスの末尾。

*一致*\
一致結果。 Elem の種類に対応します:`string`の[smatch](../standard-library/regex-typedefs.md#smatch) 、 の`char*` [wsmatch](../standard-library/regex-typedefs.md#wsmatch) `wstring`、の検索、または`wchar_t*`[wcmatch](../standard-library/regex-typedefs.md#cmatch)のを使用します。 [wcmatch](../standard-library/regex-typedefs.md#wcmatch)

*Ptr*\
一致させるシーケンスの先頭を指すポインター。 *ptr*が`char*`の場合`cmatch`は`regex`、 と を使用します。 *ptr*が`wchar_t*`使用されている`wcmatch`場合`wregex`、 と を使用します。

*再*\
照合する正規表現。 および`regex``string`と`char*`、または`wregex``wstring`と`wchar_t*`に と を入力します。

*Str*\
一致させる文字列。 *エレム*の型に対応します。

### <a name="remarks"></a>解説

各テンプレート関数は、*オペランドシーケンス*str 全体が正規表現引数*re*と完全に一致する場合にのみ true を返します。 [regex_search](../standard-library/regex-functions.md#regex_search)を使用して、ターゲット シーケンス内の部分文字列`regex_iterator`を照合し、複数の一致を検索します。 `match_results` オブジェクトを受け取る関数は、一致が成功したかどうかを反映し、さらに成功した場合は正規表現内のさまざまなキャプチャ グループがキャプチャした内容を反映するようにそのメンバーを設定します。

`match_results` オブジェクトを受け取る関数は、一致が成功したかどうかを反映し、さらに成功した場合は正規表現内のさまざまなキャプチャ グループがキャプチャした内容を反映するようにそのメンバーを設定します。

### <a name="example"></a>例

```cpp
// std__regex__regex_match.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    // (1) with char*
    // Note how const char* requires cmatch and regex
    const char *first = "abc";
    const char *last = first + strlen(first);
    cmatch narrowMatch;
    regex rx("a(b)c");

    bool found = regex_match(first, last, narrowMatch, rx);
    if (found)
        wcout << L"Regex found in abc" << endl;

    // (2) with std::wstring
    // Note how wstring requires wsmatch and wregex.
    // Note use of const iterators cbegin() and cend().
    wstring target(L"Hello");
    wsmatch wideMatch;
    wregex wrx(L"He(l+)o");

    if (regex_match(target.cbegin(), target.cend(), wideMatch, wrx))
        wcout << L"The matching text is:" << wideMatch.str() << endl;

    // (3) with std::string
    string target2("Drizzle");
    regex rx2(R"(D\w+e)"); // no double backslashes with raw string literal

    found = regex_match(target2.cbegin(), target2.cend(), rx2);
    if (found)
        wcout << L"Regex found in Drizzle" << endl;

    // (4) with wchar_t*
    const wchar_t* target3 = L"2014-04-02";
    wcmatch wideMatch2;

    // LR"(...)" is a  raw wide-string literal. Open and close parens
    // are delimiters, not string elements.
    wregex wrx2(LR"(\d{4}(-|/)\d{2}(-|/)\d{2})");
    if (regex_match(target3, wideMatch2, wrx2))
    {
        wcout << L"Matching text: " << wideMatch2.str() << endl;
    }

     return 0;
}
```

```Output
Regex found in abc
The matching text is: Hello
Regex found in Drizzle
The matching text is: 2014-04-02
```

## <a name="regex_replace"></a><a name="regex_replace"></a>regex_replace

一致した正規表現を置換します。

```cpp
template <class OutIt, class BidIt, class RXtraits, class Alloc, class Elem>
OutIt regex_replace(
    OutIt out,
    BidIt first,
    BidIt last,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);

template <class RXtraits, class Alloc, class Elem>
basic_string<Elem> regex_replace(
    const basic_string<Elem>& str,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>パラメーター

*アウトイット*\
置換用の反復子の型。

*ビッドイット*\
サブマッチ用の反復子の型。

*ラックストレイツ*\
要素の特徴 (traits) クラス。

*Alloc*\
正規表現のアロケーター クラス。

*Elem*\
一致させる要素の型。

*フラグ*\
一致のフラグ。

*まずは*\
一致させるシーケンスの先頭。

*Fmt*\
置換の形式。

*前の*\
一致させるシーケンスの末尾。

*乙*\
出力反復子。

*再*\
照合する正規表現。

*Str*\
一致させる文字列。

### <a name="remarks"></a>解説

最初の関数は[、regex_iterator Class](../standard-library/regex-iterator-class.md) `iter(first, last, re, flags)`オブジェクトを構築し、そのオブジェクトを`[first, last)`使用して、入力範囲を`T0 M0 T1 M1...TN-1 MN-1 TN`一連`Mn`のサブシーケンスに分割します。 一致が見つからない場合は、`T0` は入力範囲全体であり `N` はゼロです。 `(flags & format_first_only) != 0` である場合、最初の一致のみが使用され、`T1` がその一致に続く入力テキストのすべてであり、`N` は 1 です。 範囲`i``[0, N)`内の各テキストを反復`(flags & format_no_copy) == 0`子 out`Ti`にコピーする場合は、 の各フィールド*に対して*をコピーします。次に、`m.format(out, fmt, flags)`を`m`呼び`match_results`出しますが、ここで、サブシーケンス`iter``Mi`の反復オブジェクトによって返されるオブジェクトです。 最後に、`(flags & format_no_copy) == 0`範囲`TN`内のテキストを反復子 out にコピー*する*場合。関数は、 を返*します*。

2 番目の関数は、`basic_string<charT>` 型のローカル変数 `result` を構築し、`regex_replace(back_inserter(result), str.begin(), str.end(), re, fmt, flags)`を呼び出します。 `result` を返します。

### <a name="example"></a>例

```cpp
// std__regex__regex_replace.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    char buf[20];
    const char *first = "axayaz";
    const char *last = first + strlen(first);
    std::regex rx("a");
    std::string fmt("A");
    std::regex_constants::match_flag_type fonly =
        std::regex_constants::format_first_only;

    *std::regex_replace(&buf[0], first, last, rx, fmt) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    *std::regex_replace(&buf[0], first, last, rx, fmt, fonly) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    std::string str("adaeaf");
    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt) << std::endl;

    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt, fonly) << std::endl;

    return (0);
}
```

```Output
replacement == AxAyAz
replacement == Axayaz
replacement == AdAeAf
replacement == Adaeaf
```

## <a name="regex_search"></a><a name="regex_search"></a>regex_search

正規表現との一致を検索します。

```cpp
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>パラメーター

*ビッドイット*\
サブマッチ用の反復子の型。

*Alloc*\
一致結果のアロケーター クラス。

*Elem*\
一致させる要素の型。

*ラックストレイツ*\
要素の特徴 (traits) クラス。

*オロック2*\
正規表現のアロケーター クラス。

*イオトシツ*\
文字列の特徴 (traits) クラス。

*イオアロック*\
文字列のアロケーター クラス。

*フラグ*\
一致のフラグ。

*まずは*\
一致させるシーケンスの先頭。

*前の*\
一致させるシーケンスの末尾。

*一致*\
一致結果。

*Ptr*\
一致させるシーケンスの先頭を指すポインター。

*再*\
照合する正規表現。

*Str*\
一致させる文字列。

### <a name="remarks"></a>解説

各テンプレート関数は、オペランドシーケンス内で正規表現引数*の再*検索が成功した場合にのみ true を返します。 `match_results` オブジェクトを受け取る関数は、検索が成功したかどうかを反映し、さらに成功した場合は正規表現内のさまざまなキャプチャ グループがキャプチャした内容を反映するように、そのメンバーを設定します。

### <a name="example"></a>例

```cpp
// std__regex__regex_search.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    const char *first = "abcd";
    const char *last = first + strlen(first);
    std::cmatch mr;
    std::regex rx("abc");
    std::regex_constants::match_flag_type fl =
        std::regex_constants::match_default;

    std::cout << "search(f, f+1, \"abc\") == " << std::boolalpha
        << regex_search(first, first + 1, rx, fl) << std::endl;

    std::cout << "search(f, l, \"abc\") == " << std::boolalpha
        << regex_search(first, last, mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(\"a\", \"abc\") == " << std::boolalpha
        << regex_search("a", rx) << std::endl;

    std::cout << "search(\"xabcd\", \"abc\") == " << std::boolalpha
        << regex_search("xabcd", mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(std::string("a"), rx) << std::endl;

    std::string str("abcabc");
    std::match_results<std::string::const_iterator> mr2;
    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(str, mr2, rx) << std::endl;
    std::cout << "  matched: \"" << mr2.str() << "\"" << std::endl;

    return (0);
}
```

```Output
search(f, f+1, "abc") == false
search(f, l, "abc") == true
  matched: "abc"
search("a", "abc") == false
search("xabcd", "abc") == true
  matched: "abc"
search(string, "abc") == false
search(string, "abc") == true
  matched: "abc"
```

## <a name="swap"></a><a name="swap"></a>スワップ

2 つまたは`basic_regex``match_results`複数のオブジェクトを入れ替えます。

```cpp
template <class Elem, class RXtraits>
void swap(
    basic_regex<Elem, RXtraits, Alloc>& left,
    basic_regex<Elem, RXtraits>& right) noexcept;

template <class Elem, class IOtraits, class BidIt, class Alloc>
void swap(
    match_results<BidIt, Alloc>& left,
    match_results<BidIt, Alloc>& right) noexcept;
```

### <a name="parameters"></a>パラメーター

*Elem*\
一致させる要素の型。

*ラックストレイツ*\
要素の特徴 (traits) クラス。

### <a name="remarks"></a>解説

このテンプレート関数は、一定時間でそれぞれの引数の内容を交換し、例外をスローしません。

### <a name="example"></a>例

```cpp
// std__regex__swap.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    std::regex rx0("c(a*)|(b)");
    std::regex rx1;
    std::cmatch mr0;
    std::cmatch mr1;

    swap(rx0, rx1);
    std::regex_search("xcaaay", mr1, rx1);
    swap(mr0, mr1);

    std::csub_match sub = mr0[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;
    std::cout << "string == " << sub << std::endl;

    return (0);
}
```

```Output
matched == true
length == 3
string == aaa
```

## <a name="see-also"></a>関連項目

[\<正規表現>](../standard-library/regex.md)\
[regex_constantsクラス](../standard-library/regex-constants-class.md)\
[regex_errorクラス](../standard-library/regex-error-class.md)\
[regex_iteratorクラス](../standard-library/regex-iterator-class.md)\
[\<正規表現>演算子](../standard-library/regex-operators.md)\
[regex_token_iteratorクラス](../standard-library/regex-token-iterator-class.md)\
[regex_traitsクラス](../standard-library/regex-traits-class.md)\
[\<正規表現>のタイプ定義](../standard-library/regex-typedefs.md)
