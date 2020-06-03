---
title: match_results クラス
ms.date: 09/10/2018
f1_keywords:
- regex/std::match_results
helpviewer_keywords:
- match_results class
ms.assetid: b504fdca-e5dd-429d-9960-6e27c9167fa6
ms.openlocfilehash: 31154a38f8bbcb879fd871f1eb1bf5a4b15af79b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371023"
---
# <a name="match_results-class"></a>match_results クラス

サブマッチのシーケンスを保持します。

## <a name="syntax"></a>構文

```cpp
template <class BidIt, class Alloc>
class match_results
```

## <a name="parameters"></a>パラメーター

*ビッドイット*\
サブマッチ用の反復子の型。

*Alloc*\
ストレージを管理するためのアロケーターの型です。

## <a name="remarks"></a>解説

クラス テンプレートは、正規表現検索によって生成される型`sub_match<BidIt>`の要素の変更不可能なシーケンスを制御するオブジェクトを表します。 各要素は、それに対応するキャプチャ グループと一致したサブシーケンスを指します。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[match_results](#match_results)|オブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[allocator_type](#allocator_type)|ストレージを管理するためのアロケーターの型です。|
|[char_type](#char_type)|要素の型。|
|[const_iterator](#const_iterator)|サブマッチ用の const 反復子の型。|
|[const_reference](#const_reference)|要素の定数参照の型。|
|[difference_type](#difference_type)|反復子の差の型です。|
|[反復 子](#iterator)|サブマッチ用の反復子の型。|
|[参照](#reference)|要素の参照の型。|
|[Size_type](#size_type)|サブマッチ数の型。|
|[string_type](#string_type)|文字列の型。|
|[Value_type](#value_type)|サブマッチの型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[開始](#begin)|サブマッチのシーケンスの最初を指定します。|
|[empty](#empty)|サブマッチが存在しないかどうかをテストします。|
|[end](#end)|サブマッチのシーケンスの最後を指定します。|
|[形式](#format)|サブマッチの形式を設定します。|
|[get_allocator](#get_allocator)|格納されているアロケーターを返します。|
|[length](#length)|サブマッチの長さを返します。|
|[max_size](#max_size)|サブマッチの最大数を取得します。|
|[位置](#position)|サブグループの開始オフセットを取得します。|
|[プレフィックス](#prefix)|最初のサブマッチの前のシーケンスを取得します。|
|[サイズ](#size)|サブマッチの数をカウントします。|
|[Str](#str)|サブマッチが返されます。|
|[サフィックス](#suffix)|最後のサブマッチ後に、シーケンスを取得します。|
|[スワップ](#swap)|2 つの match_results オブジェクトを交換します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子=](#op_eq)|match_results オブジェクトをコピーします。|
|[演算子\[\]](#op_at)|サブオブジェクトにアクセスします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<regex>

**名前空間:** std

## <a name="example"></a>例

```cpp
// std__regex__match_results.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    std::regex rx("c(a*)|(b)");
    std::cmatch mr;

    std::regex_search("xcaaay", mr, rx);

    std::cout << "prefix: matched == " << std::boolalpha
        << mr.prefix().matched
        << ", value == " << mr.prefix() << std::endl;
    std::cout << "whole match: " << mr.length() << " chars, value == "
        << mr.str() << std::endl;
    std::cout << "suffix: matched == " << std::boolalpha
        << mr.suffix().matched
        << ", value == " << mr.suffix() << std::endl;
    std::cout << std::endl;

    std::string fmt("\"c(a*)|(b)\" matched \"$&\"\n"
        "\"(a*)\" matched \"$1\"\n"
        "\"(b)\" matched \"$2\"\n");
    std::cout << mr.format(fmt) << std::endl;
    std::cout << std::endl;

    // index through submatches
    for (size_t n = 0; n < mr.size(); ++n)
    {
        std::cout << "submatch[" << n << "]: matched == " << std::boolalpha
            << mr[n].matched <<
            " at position " << mr.position(n) << std::endl;
        std::cout << "  " << mr.length(n)
            << " chars, value == " << mr[n] << std::endl;
    }
    std::cout << std::endl;

    // iterate through submatches
    for (std::cmatch::iterator it = mr.begin(); it != mr.end(); ++it)
    {
        std::cout << "next submatch: matched == " << std::boolalpha
            << it->matched << std::endl;
        std::cout << "  " << it->length()
            << " chars, value == " << *it << std::endl;
    }
    std::cout << std::endl;

    // other members
    std::cout << "empty == " << std::boolalpha << mr.empty() << std::endl;

    std::cmatch::allocator_type al = mr.get_allocator();
    std::cmatch::string_type str = std::string("x");
    std::cmatch::size_type maxsiz = mr.max_size();
    std::cmatch::char_type ch = 'x';
    std::cmatch::difference_type dif = mr.begin() - mr.end();
    std::cmatch::const_iterator cit = mr.begin();
    std::cmatch::value_type val = *cit;
    std::cmatch::const_reference cref = val;
    std::cmatch::reference ref = val;

    maxsiz = maxsiz;  // to quiet "unused" warnings
    if (ref == cref)
        ch = ch;
    dif = dif;

    return (0);
}
```

```Output
prefix: matched == true, value == x
whole match: 4 chars, value == caaa
suffix: matched == true, value == y

"c(a*)|(b)" matched "caaa"
"(a*)" matched "aaa"
"(b)" matched ""

submatch[0]: matched == true at position 1
  4 chars, value == caaa
submatch[1]: matched == true at position 2
  3 chars, value == aaa
submatch[2]: matched == false at position 6
  0 chars, value ==

next submatch: matched == true
  4 chars, value == caaa
next submatch: matched == true
  3 chars, value == aaa
next submatch: matched == false
  0 chars, value ==

empty == false
```

## <a name="match_resultsallocator_type"></a><a name="allocator_type"></a>match_results::allocator_type

ストレージを管理するためのアロケーターの型です。

```cpp
typedef Alloc allocator_type;
```

### <a name="remarks"></a>解説

typedef はテンプレート引数*Alloc*の同義語です。

## <a name="match_resultsbegin"></a><a name="begin"></a>match_results::開始

サブマッチのシーケンスの最初を指定します。

```cpp
const_iterator begin() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、シーケンスの最初の要素 (または空のシーケンスの末尾の次の位置) を示すランダム アクセス反復子を返します。

## <a name="match_resultschar_type"></a><a name="char_type"></a>match_results::char_type

要素の型。

```cpp
typedef typename iterator_traits<BidIt>::value_type char_type;
```

### <a name="remarks"></a>解説

この typedef は、検索された文字シーケンスの要素の型である `iterator_traits<BidIt>::value_type`型のシノニムです。

## <a name="match_resultsconst_iterator"></a><a name="const_iterator"></a>match_results::const_iterator

サブマッチ用の const 反復子の型。

```cpp
typedef T0 const_iterator;
```

### <a name="remarks"></a>解説

typedef は、被制御シーケンスの定数ランダム アクセス反復子として使用できるオブジェクトを表します。

## <a name="match_resultsconst_reference"></a><a name="const_reference"></a>match_results::const_reference

要素の定数参照の型。

```cpp
typedef const typename Alloc::const_reference const_reference;
```

### <a name="remarks"></a>解説

この typedef は、被制御シーケンスの要素への定数参照として使用できるオブジェクトを表します。

## <a name="match_resultsdifference_type"></a><a name="difference_type"></a>match_results::difference_type

反復子の差の型です。

```cpp
typedef typename iterator_traits<BidIt>::difference_type difference_type;
```

### <a name="remarks"></a>解説

typedef は `iterator_traits<BidIt>::difference_type`型の同意語です。被制御シーケンスの要素を指す任意の 2 つの反復子の差を表現することが可能なオブジェクトを表します。

## <a name="match_resultsempty"></a><a name="empty"></a>match_results::空

サブマッチが存在しないかどうかをテストします。

```cpp
bool empty() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、正規表現検索に失敗した場合にのみ true を返します。

## <a name="match_resultsend"></a><a name="end"></a>match_results::終了

サブマッチのシーケンスの最後を指定します。

```cpp
const_iterator end() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、シーケンスの最後を越えたところを示す反復子を返します。

## <a name="match_resultsformat"></a><a name="format"></a>match_results:形式

サブマッチの形式を設定します。

```cpp
template <class OutIt>
OutIt format(OutIt out,
    const string_type& fmt, match_flag_type flags = format_default) const;

string_type format(const string_type& fmt, match_flag_type flags = format_default) const;
```

### <a name="parameters"></a>パラメーター

*アウトイット*\
出力反復子の型。

*乙*\
書き込み先の出力ストリーム。

*Fmt*\
書式指定文字列。

*フラグ*\
書式指定フラグ。

### <a name="remarks"></a>解説

各メンバー関数は、 *fmt*形式の制御下で書式付きテキストを生成します。 最初のメンバー関数は、書式付きテキストを引数*out*で定義されたシーケンスに書き込み、out を返*します*。2 番目のメンバー関数は、書式設定されたテキストのコピーを保持する文字列オブジェクトを返します。

書式指定されたテキストを生成する際、 書式指定文字列内のリテラル テキストは、ターゲット シーケンスにコピーされるのが一般的です。 書式指定文字列内の各エスケープ シーケンスは、それが表すテキストに置き換えられます。 コピーと置換の詳細な動作は、関数に渡された書式指定フラグによって制御されます。

## <a name="match_resultsget_allocator"></a><a name="get_allocator"></a>match_results::get_allocator

格納されているアロケーターを返します。

```cpp
allocator_type get_allocator() const;
```

### <a name="remarks"></a>解説

このメンバー関数は `sub_match` オブジェクトを割り当てる `*this` で使用されるアロケーター オブジェクトのコピーを返します。

## <a name="match_resultsiterator"></a><a name="iterator"></a>match_results::反復器

サブマッチ用の反復子の型。

```cpp
typedef const_iterator iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスのランダム アクセス反復子として使用できるオブジェクトを表します。

## <a name="match_resultslength"></a><a name="length"></a>match_results::長さ

サブマッチの長さを返します。

```cpp
difference_type length(size_type sub = 0) const;
```

### <a name="parameters"></a>パラメーター

*サブ*\
サブマッチのインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、`(*this)[sub].length()` を返します。

## <a name="match_resultsmatch_results"></a><a name="match_results"></a>match_results::match_results

オブジェクトを構築します。

```cpp
explicit match_results(const Alloc& alloc = Alloc());

match_results(const match_results& right);
```

### <a name="parameters"></a>パラメーター

*Alloc*\
格納するアロケーター オブジェクト。

*そうです*\
コピーする match_results オブジェクトです。

### <a name="remarks"></a>解説

1 つ目のコンストラクターは、サブマッチを保持しない `match_results` オブジェクトを構築します。 2 番目のコンストラクターは`match_results`、 *right*のコピーであるオブジェクトを構築します。

## <a name="match_resultsmax_size"></a><a name="max_size"></a>match_results::max_size

サブマッチの最大数を取得します。

```cpp
size_type max_size() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、オブジェクトが制御できる最も長いシーケンスの長さを返します。

## <a name="match_resultsoperator"></a><a name="op_eq"></a>match_results::演算子=

match_results オブジェクトをコピーします。

```cpp
match_results& operator=(const match_results& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
コピーする match_results オブジェクトです。

### <a name="remarks"></a>解説

メンバー演算子は、 によって`*this`制御されるシーケンスを*right*で制御されるシーケンスのコピーに置き換えます。

## <a name="match_resultsoperator"></a><a name="op_at"></a>match_results::演算子[]

サブオブジェクトにアクセスします。

```cpp
const_reference operator[](size_type n) const;
```

### <a name="parameters"></a>パラメーター

*N*\
サブマッチのインデックス。

### <a name="remarks"></a>解説

メンバー関数は、被制御シーケンスの要素*n*への参照、またはキャプチャ グループ`sub_match`n`size() <= n`が一致の*n*一部でない場合は空のオブジェクトへの参照を返します。

## <a name="match_resultsposition"></a><a name="position"></a>match_results::pの

サブグループの開始オフセットを取得します。

```cpp
difference_type position(size_type sub = 0) const;
```

### <a name="parameters"></a>パラメーター

*サブ*\
サブマッチのインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、 `std::distance(prefix().first, (*this)[sub].first)`、つまり、ターゲット シーケンス内の最初の文字から被制御シーケンスの要素 `n` によって示されるサブマッチ内の最初の文字までの距離を返します。

## <a name="match_resultsprefix"></a><a name="prefix"></a>match_results::p修正

最初のサブマッチの前のシーケンスを取得します。

```cpp
const_reference prefix() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、ターゲット シーケンスの先頭から始まって `sub_match<BidIt>` で終わる文字シーケンスを指す、`(*this)[0].first` 型のオブジェクトへの参照を返します。つまり、この参照は一致したサブシーケンスの直前のテキストを指すことになります。

## <a name="match_resultsreference"></a><a name="reference"></a>match_results::参照

要素の参照の型。

```cpp
typedef const_reference reference;
```

### <a name="remarks"></a>解説

この型は、 `const_reference`型のシノニムです。

## <a name="match_resultssize"></a><a name="size"></a>match_results::サイズ

サブマッチの数をカウントします。

```cpp
size_type size() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、検索に使用された正規表現内のキャプチャ グループの数 + 1 を返します。検索が実行されなかった場合は 0 を返します。

## <a name="match_resultssize_type"></a><a name="size_type"></a>match_results::size_type

サブマッチ数の型。

```cpp
typedef typename Alloc::size_type size_type;
```

### <a name="remarks"></a>解説

この型は、 `Alloc::size_type`型のシノニムです。

## <a name="match_resultsstr"></a><a name="str"></a>match_results::str

サブマッチが返されます。

```cpp
string_type str(size_type sub = 0) const;
```

### <a name="parameters"></a>パラメーター

*サブ*\
サブマッチのインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、`string_type((*this)[sub])` を返します。

## <a name="match_resultsstring_type"></a><a name="string_type"></a>match_results::string_type

文字列の型。

```cpp
typedef basic_string<char_type> string_type;
```

### <a name="remarks"></a>解説

この型は、 `basic_string<char_type>`型のシノニムです。

## <a name="match_resultssuffix"></a><a name="suffix"></a>match_results::接尾辞

最後のサブマッチ後に、シーケンスを取得します。

```cpp
const_reference suffix() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、 `sub_match<BidIt>` から始まってターゲット シーケンスの末尾で終わる文字シーケンスを指す (つまり、一致したサブシーケンスに続くテキストを指す) `(*this)[size() - 1].second` 型のオブジェクトへの参照を返します。

## <a name="match_resultsswap"></a><a name="swap"></a>match_results::スワップ

2 つの match_results オブジェクトを交換します。

```cpp
void swap(const match_results& right) throw();
```

### <a name="parameters"></a>パラメーター

*そうです*\
交換する match_results オブジェクト。

### <a name="remarks"></a>解説

メンバー関数は、一定の時間`*this`で*内容*を入れ替え、例外をスローしません。

## <a name="match_resultsvalue_type"></a><a name="value_type"></a>match_results::value_type

サブマッチの型。

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>解説

typedef は、型 `sub_match<BidIt>` の同意語です。

## <a name="see-also"></a>関連項目

[\<正規表現>](../standard-library/regex.md)
