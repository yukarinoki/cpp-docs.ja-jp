---
title: '&lt;regex&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- regex/std::regex_match
- regex/std::regex_replace
- regex/std::regex_search
- regex/std::swap
dev_langs:
- C++
ms.assetid: 91a8314b-6f7c-4e33-b7d6-d8583dd75585
helpviewer_keywords:
- std::regex_match [C++]
- std::regex_replace [C++]
- std::regex_search [C++]
- std::swap [C++]
- std::swap [C++]
ms.openlocfilehash: 7c89f5509ec37e1ef91e92acb6732d1b4819f930
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863162"
---
# <a name="ltregexgt-functions"></a>&lt;regex&gt; 関数

||||
|-|-|-|
|[regex_match](#regex_match)|[regex_replace](#regex_replace)|[regex_search](#regex_search)|
|[swap](#swap)|

## <a name="regex_match"></a>  regex_match

正規表現がターゲット文字列全体と一致するかどうかをテストします。

```

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

`BidIt` サブマッチの反復子の型。 一般的には、string::const_iterator、wstring::const_iterator、const char* まはた const wchar_t\*です。

`Alloc` 一致結果のアロケーター クラス。

`Elem` 一致する要素の型。 一般的には、string、wstring、char*、または wchar_t* です\*。

`RXtraits` 要素の特徴 (traits) クラス。

`Alloc2` 正規表現のアロケーター クラス。

`IOtraits` 文字列の特徴 (traits) クラス。

`IOalloc` 文字列のアロケーター クラス。

`flags` 一致のフラグ。

`first` 一致させるシーケンスの先頭。

`last` 一致させるシーケンスの最後。

`match` 一致した結果。 Elem 型に対応します。string には [smatch](../standard-library/regex-typedefs.md#smatch)、wstring には [wsmatch](../standard-library/regex-typedefs.md#wsmatch)、char* には [cmatch](../standard-library/regex-typedefs.md#cmatch)、wchar_t には [wcmatch](../standard-library/regex-typedefs.md#wcmatch) が対応します\*。

`ptr` 一致させるシーケンスの先頭を指すポインターです。 ptr が char* の場合は、cmatch と regex を使用します。 ptr が wchar_t\* の場合は、wcmatch と wregex を使用します。

`re` 一致させる正規表現。 string および char* の場合は `regex` 型で、wstring および wchar_t* の場合は `wregex` です\*。

`str` 一致させる文字列。 Elem の型に対応します。

### <a name="remarks"></a>コメント

各テンプレート関数は、オペランド シーケンス `str` 全体が正規表現の引数 `re` に完全に一致している場合にのみ true を返します。 [regex_search](../standard-library/regex-functions.md#regex_search) を使用して、ターゲット シーケンス内の部分文字列と一致させ、regex_iterator を使用して複数の一致を検出します。 `match_results` オブジェクトを受け取る関数は、一致が成功したかどうかを反映し、さらに成功した場合は正規表現内のさまざまなキャプチャ グループがキャプチャした内容を反映するようにそのメンバーを設定します。

`match_results` オブジェクトを受け取る関数は、一致が成功したかどうかを反映し、さらに成功した場合は正規表現内のさまざまなキャプチャ グループがキャプチャした内容を反映するようにそのメンバーを設定します。

**(1):**

### <a name="example"></a>例

```cpp
#include "stdafx.h"
#include <regex>
#include <iostream>

using namespace std;

int _tmain(int argc, _TCHAR* argv[])
{

    // (1) with char*
    // Note how const char* requires cmatch and regex
    const char *first = "abc";
    const char *last = first + strlen(first);
    cmatch narrowMatch;
    regex rx("a(b)c");

    bool found = regex_match(first, last, narrowMatch, rx);

    // (1) with std::wstring
    // Note how wstring requires wsmatch and wregex.
    // Note use of const iterators cbegin() and cend().
    wstring target(L"Hello");
    wsmatch wideMatch;
    wregex wrx(L"He(l+)o");

    if (regex_match(target.cbegin(), target.cend(), wideMatch, wrx))
        wcout << L"The matching text is:" << wideMatch.str() << endl;

    // (2) with std::string
    string target2("Drizzle");
    regex rx2(R"(D\w+e)"); // no double backslashes with raw string literal
    found = regex_match(target2.cbegin(), target2.cend(), rx2);

    // (3) with wchar_t*
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

## <a name="regex_replace"></a>  regex_replace

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

`OutIt` 置換の反復子の型。

`BidIt` サブマッチの反復子の型。

`RXtraits` 要素の特徴 (traits) クラス。

`Alloc` 正規表現のアロケーター クラス。

`Elem` 一致する要素の型。

`flags` 一致のフラグ。

`first` 一致させるシーケンスの先頭。

`fmt` 置換の形式。

`last` 一致させるシーケンスの最後。

`out` 出力反復子。

`re` 一致させる正規表現。

`str` 一致させる文字列。

### <a name="remarks"></a>コメント

最初の関数は [regex_iterator クラス](../standard-library/regex-iterator-class.md) オブジェクト `iter(first, last, re, flags)` を構築し、それを使用してその入力範囲 `[first, last)` を一連のサブシーケンス `T0M0T1M1...TN-1MN-1TN` に分割します。ここで、`Mn` は反復子によって検出される `nth` の一致です。 一致が見つからない場合は、`T0` は入力範囲全体であり `N` はゼロです。 `(flags & format_first_only) != 0` である場合、最初の一致のみが使用され、`T1` がその一致に続く入力テキストのすべてであり、`N` は 1 です。 範囲 `[0, N)` 内の `i` ごとに、`(flags & format_no_copy) == 0` である場合は範囲 `Ti` 内のテキストを反復子 `out` にコピーします。 そして `m.format(out, fmt, flags)` を呼び出します。ここで `m` はサブシーケンス `Mi` の反復子オブジェクト `iter` によって返される `match_results` オブジェクトです。 最後に、`(flags & format_no_copy) == 0` である場合、範囲 `TN` 内のテキストを反復子 `out` にコピーします。 `out` が返されます。

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

## <a name="regex_search"></a>  regex_search

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

`BidIt` サブマッチの反復子の型。

`Alloc` 一致結果のアロケーター クラス。

`Elem` 一致する要素の型。

`RXtraits` 要素の特徴 (traits) クラス。

`Alloc2` 正規表現のアロケーター クラス。

`IOtraits` 文字列の特徴 (traits) クラス。

`IOalloc` 文字列のアロケーター クラス。

`flags` 一致のフラグ。

`first` 一致させるシーケンスの先頭。

`last` 一致させるシーケンスの最後。

`match` 一致した結果。

`ptr` 一致させるシーケンスの先頭を指すポインターです。

`re` 一致させる正規表現。

`str` 一致させる文字列。

### <a name="remarks"></a>コメント

各テンプレート関数は、その正規表現の引数 `re` のオペランド シーケンスにおける検索が成功した場合にのみ true を返します。 `match_results` オブジェクトを受け取る関数は、検索が成功したかどうかを反映し、さらに成功した場合は正規表現内のさまざまなキャプチャ グループがキャプチャした内容を反映するように、そのメンバーを設定します。

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

## <a name="swap"></a>  swap

basic_regex または match_results の 2 つのオブジェクトを交換します。

```cpp
template <class Elem, class RXtraits>
void swap(
    basic_regex<Elem, RXtraits, Alloc>& left,
    basic_regex<Elem, RXtraits>& right) throw();

template <class Elem, class IOtraits, class BidIt, class Alloc>
void swap(
    match_results<BidIt, Alloc>& left,
    match_results<BidIt, Alloc>& right) throw();
```

### <a name="parameters"></a>パラメーター

`Elem` 一致する要素の型。

`RXtraits` 要素の特徴 (traits) クラス。

### <a name="remarks"></a>コメント

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

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants クラス](../standard-library/regex-constants-class.md)<br/>
[regex_error クラス](../standard-library/regex-error-class.md)<br/>
[regex_iterator クラス](../standard-library/regex-iterator-class.md)<br/>
[\<regex> 系演算子](../standard-library/regex-operators.md)<br/>
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits クラス](../standard-library/regex-traits-class.md)<br/>
[\<regex> typedefs](../standard-library/regex-typedefs.md)<br/>
