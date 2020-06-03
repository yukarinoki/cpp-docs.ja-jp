---
title: basic_regex クラス
ms.date: 03/27/2019
f1_keywords:
- regex/std::basic_regex
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
ms.openlocfilehash: 74a8684c619e2cfbd5417950aa6108ad93511bf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376754"
---
# <a name="basic_regex-class"></a>basic_regex クラス

正規表現をラップします。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class RXtraits>
class basic_regex
```

## <a name="parameters"></a>パラメーター

*Elem*\
一致させる要素の型。

*ラックストレイツ*\
要素の特徴 (traits) クラス。

## <a name="remarks"></a>解説

クラス テンプレートは、正規表現を保持するオブジェクトを記述します。 このクラス テンプレートのオブジェクトは、regex_match、regex_search、[regex_match](../standard-library/regex-functions.md#regex_match)および[regex_search](../standard-library/regex-functions.md#regex_search)[regex_replace](../standard-library/regex-functions.md#regex_replace)のテンプレート関数に、適切なテキスト文字列引数と共に渡され、正規表現に一致するテキストを検索できます。 このクラス テンプレートには **、char**型の要素の型定義[regex](../standard-library/regex-typedefs.md#regex)と、型**wchar_t**の要素の[wregex](../standard-library/regex-typedefs.md#wregex)の 2 つの特殊化があります。

テンプレート引数*RXtraits*は、クラス テンプレートがサポートする正規表現の構文のさまざまな重要なプロパティを記述します。 これらの正規表現の特徴を指定するクラスは[、class](../standard-library/regex-traits-class.md)型のオブジェクトと同じ外部インターフェイスregex_traits必要があります。

一部の関数は、正規表現を定義するオペランド シーケンスを受け取ります。 その場合、オペランド シーケンスは次のような方法で指定できます。

`ptr`-- 終了要素`value_type()`が値で、オペランドシーケンスの一部ではない場合に始まる **(null**ポインター`ptr`であってはならない) から始まる NULL で終わるシーケンス (C 文字列、char 型の*Elem*など)

`ptr`、`count` : `count` (null ポインター以外) で始まる `ptr` 個の要素のシーケンスとして。

`str` : `basic_string` オブジェクト `str` によって指定されたシーケンスとして。

`first`、`last` : `first` と `last` の 2 つの反復子で区切られた範囲 `[first, last)` 内の要素のシーケンスとして。

`right` : `basic_regex` オブジェクト `right` として。

これらのメンバー関数は`flags`*、RXtraits*型で記述されているオプションに加えて、正規表現の解釈に関するさまざまなオプションを指定する引数も受け取ります。

### <a name="members"></a>メンバー

|メンバー|Default value|
|-|-|
|パブリック静的な定数flag_type icase|regex_constants::icase|
|パブリック静的定数flag_type nosubs|regex_constants::ノサブス|
|パブリック静的な定数flag_type最適化|regex_constants::最適化|
|パブリック静的コンストflag_type照合|regex_constants::照合|
|パブリック静的コンストflag_type ECMAScript|regex_constants::ECMAスクリプト|
|パブリック静的な定数flag_type基本|regex_constants::基本|
|パブリック静的な定数flag_type拡張|regex_constants::拡張|
|パブリック静的コンストflag_type awk|regex_constants::awk|
|パブリック静的 const flag_type grep|regex_constants::グレップ|
|パブリック静的定数flag_type egrep|regex_constants::egrep|
|プライベート RXtraits の特徴||

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[basic_regex](#basic_regex)|正規表現オブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[flag_type](#flag_type)|構文オプション フラグの型です。|
|[locale_type](#locale_type)|格納されているロケール オブジェクトの型。|
|[Value_type](#value_type)|要素型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[割り当てる](#assign)|値を正規表現オブジェクトに代入します。|
|[フラグ](#flags)|構文のオプション フラグを返します。|
|[getloc](#getloc)|格納されているロケール オブジェクトを返します。|
|[imbue](#imbue)|格納されているロケール オブジェクトを変更します。|
|[mark_count](#mark_count)|一致した部分式の数を返します。|
|[スワップ](#swap)|2 つの正規表現オブジェクトを交換します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子=](#op_eq)|値を正規表現オブジェクトに代入します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<regex>

**名前空間:** std

## <a name="example"></a>例

```cpp
// std__regex__basic_regex.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    regex::value_type elem = 'x';
    regex::flag_type flag = regex::grep;

    elem = elem;  // to quiet "unused" warnings
    flag = flag;

    // constructors
    regex rx0;
    cout << "match(\"abc\", \"\") == " << boolalpha
        << regex_match("abc", rx0) << endl;

    regex rx1("abcd", regex::ECMAScript);
    cout << "match(\"abc\", \"abcd\") == " << boolalpha
        << regex_match("abc", rx1) << endl;

    regex rx2("abcd", 3);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx2) << endl;

    regex rx3(rx2);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx3) << endl;

    string str("abcd");
    regex rx4(str);
    cout << "match(string(\"abcd\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx4) << endl;

    regex rx5(str.begin(), str.end() - 1);
    cout << "match(string(\"abc\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx5) << endl;
    cout << endl;

    // assignments
    rx0 = "abc";
    rx0 = rx1;
    rx0 = str;

    rx0.assign("abcd", regex::ECMAScript);
    rx0.assign("abcd", 3);
    rx0.assign(rx1);
    rx0.assign(str);
    rx0.assign(str.begin(), str.end() - 1);

    rx0.swap(rx1);

    // mark_count
    cout << "\"abc\" mark_count == "
        << regex("abc").mark_count() << endl;
    cout << "\"(abc)\" mark_count == "
        << regex("(abc)").mark_count() << endl;

    // locales
    regex::locale_type loc = rx0.imbue(locale());
    cout << "getloc == imbued == " << boolalpha
        << (loc == rx0.getloc()) << endl;

    // initializer_list
    regex rx6({ 'a', 'b', 'c' }, regex::ECMAScript);
    cout << "match(\"abc\") == " << boolalpha
        << regex_match("abc", rx6);
    cout << endl;
}
```

```Output
match("abc", "") == false
match("abc", "abcd") == false
match("abc", "abc") == true
match("abc", "abc") == true
match(string("abcd"), "abc") == false
match(string("abc"), "abc") == true

"abc" mark_count == 0
"(abc)" mark_count == 1
getloc == imbued == true
match("abc") == true
```

## <a name="basic_regexassign"></a><a name="assign"></a>basic_regex::割り当て

値を正規表現オブジェクトに代入します。

```cpp
basic_regex& assign(
    const basic_regex& right);

basic_regex& assign(
    const Elem* ptr,
    flag_type flags = ECMAScript);

basic_regex& assign(
    const Elem* ptr,
    size_type len,
    flag_type flags = ECMAScript);

basic_regex& assign(
    initializer_list<_Elem> IList,
    flag_type flags = regex_constants::ECMAScript);

template <class STtraits, class STalloc>
basic_regex& assign(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags = ECMAScript);

template <class InIt>
basic_regex& assign(
    InIt first, InIt last,
    flag_type flags = ECMAScript);
```

### <a name="parameters"></a>パラメーター

*海峡*\
文字列ソースの特徴 (traits) クラス。

*スタロック*\
文字列ソースのアロケーター クラス。

*Init*\
範囲ソースの入力反復子の型。

*そうです*\
コピーする Regex ソース。

*Ptr*\
コピーするシーケンスの先頭を指すポインター。

*フラグ*\
コピー中に追加する構文オプション フラグ。

*レン/TD>*\
コピーするシーケンスの長さ。

*Str*\
コピーする文字列。

*まずは*\
コピーするシーケンスの最初。

*前の*\
コピーするシーケンスの最後。

*Ilist*\
コピーする initializer_list。

### <a name="remarks"></a>解説

いずれのメンバー関数も、`*this` が保持している正規表現を、オペランド シーケンスが保持している正規表現に置き換えて、`*this` を返します。

## <a name="basic_regexbasic_regex"></a><a name="basic_regex"></a>basic_regex::basic_regex

正規表現オブジェクトを構築します。

```cpp
basic_regex();

explicit basic_regex(
    const Elem* ptr,
    flag_type flags);

explicit basic_regex(
    const Elem* ptr,
    size_type len,
    flag_type flags);

basic_regex(
    const basic_regex& right);

basic_regex(
    initializer_list<Type> IList,
    flag_type flags);

template <class STtraits, class STalloc>
explicit basic_regex(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags);

template <class InIt>
explicit basic_regex(
    InIt first,
    InIt last,
    flag_type flags);
```

### <a name="parameters"></a>パラメーター

*海峡*\
文字列ソースの特徴 (traits) クラス。

*スタロック*\
文字列ソースのアロケーター クラス。

*Init*\
範囲ソースの入力反復子の型。

*そうです*\
コピーする Regex ソース。

*Ptr*\
コピーするシーケンスの先頭を指すポインター。

*フラグ*\
コピー中に追加する構文オプション フラグ。

*レン/TD>*\
コピーするシーケンスの長さ。

*Str*\
コピーする文字列。

*まずは*\
コピーするシーケンスの最初。

*前の*\
コピーするシーケンスの最後。

*Ilist*\
コピーする initializer_list。

### <a name="remarks"></a>解説

すべてのコンストラクターは、既定で構築される、`RXtraits` 型のオブジェクトを格納します。

1 つ目のコンストラクターは、空の `basic_regex` オブジェクトを構築します。 それ以外のコンストラクターは、オペランド シーケンスで記述された正規表現を保持する `basic_regex` オブジェクトを構築します。

空`basic_regex`のオブジェクト[は、](../standard-library/regex-functions.md#regex_search)、 regex_search 、 または[regex_replace](../standard-library/regex-functions.md#regex_replace) [regex_match](../standard-library/regex-functions.md#regex_match)に渡された場合、どの文字シーケンスにも一致しません。

## <a name="basic_regexflag_type"></a><a name="flag_type"></a>basic_regex::flag_type

構文オプション フラグの型です。

```cpp
typedef regex_constants::syntax_option_type flag_type;
```

### <a name="remarks"></a>解説

この型は [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type)のシノニムです。

## <a name="basic_regexflags"></a><a name="flags"></a>basic_regex::フラグ

構文のオプション フラグを返します。

```cpp
flag_type flags() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、[basic_regex::assign](#assign) メンバー関数のうち直前に呼び出された関数に渡された `flag_type` 引数の値を返します。これに当たる呼び出しが行われていなかった場合は、コンストラクターに渡した値が返されます。

## <a name="basic_regexgetloc"></a><a name="getloc"></a>basic_regex::ゲットロック

格納されているロケール オブジェクトを返します。

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>解説

メンバー関数は`traits.`[regex_traits::getloc](../standard-library/regex-traits-class.md#getloc)`()`を返します。

## <a name="basic_regeximbue"></a><a name="imbue"></a>basic_regex::インビュー

格納されているロケール オブジェクトを変更します。

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>パラメーター

*Loc*\
格納するロケール オブジェクト。

### <a name="remarks"></a>解説

メンバー関数は空に`*this`し`traits.`[、regex_traits::インブーを](../standard-library/regex-traits-class.md#imbue)`(loc)`返します。

## <a name="basic_regexlocale_type"></a><a name="locale_type"></a>basic_regex::locale_type

格納されているロケール オブジェクトの型。

```cpp
typedef typename RXtraits::locale_type locale_type;
```

### <a name="remarks"></a>解説

この型は [regex_traits::locale_type](../standard-library/regex-traits-class.md#locale_type)のシノニムです。

## <a name="basic_regexmark_count"></a><a name="mark_count"></a>basic_regex::mark_count

一致した部分式の数を返します。

```cpp
unsigned mark_count() const;
```

### <a name="remarks"></a>解説

メンバー関数は、正規表現のキャプチャ グループの数を返します。

## <a name="basic_regexoperator"></a><a name="op_eq"></a>basic_regex::演算子=

値を正規表現オブジェクトに代入します。

```cpp
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```

### <a name="parameters"></a>パラメーター

*海峡*\
文字列ソースの特徴 (traits) クラス。

*スタロック*\
文字列ソースのアロケーター クラス。

*そうです*\
コピーする Regex ソース。

*Str*\
コピーする文字列。

### <a name="remarks"></a>解説

それぞれの演算子が、 `*this` に保持されている正規表現を、オペランド シーケンスで記述された正規表現に置き換えてから、 `*this`を返します。

## <a name="basic_regexswap"></a><a name="swap"></a>basic_regex::スワップ

2 つの正規表現オブジェクトを交換します。

```cpp
void swap(basic_regex& right) throw();
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する正規表現オブジェクト。

### <a name="remarks"></a>解説

メンバー関数は、 と*の*間`*this`で正規表現を入れ替えます。 一定時間に実行し、例外をスローしません。

## <a name="basic_regexvalue_type"></a><a name="value_type"></a>basic_regex::value_type

要素型。

```cpp
typedef Elem value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメータ*Elem*のシノニムです。

## <a name="see-also"></a>関連項目

[\<正規表現>](../standard-library/regex.md)\
[regex_match](../standard-library/regex-functions.md#regex_match)\
[regex_search](../standard-library/regex-functions.md#regex_search)\
[regex_replace](../standard-library/regex-functions.md#regex_replace)\
[Regex](../standard-library/regex-typedefs.md#regex)\
[ドレネックス](../standard-library/regex-typedefs.md#wregex)\
[regex_traits クラス](../standard-library/regex-traits-class.md)
