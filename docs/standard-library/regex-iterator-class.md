---
title: regex_iterator クラス
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_iterator
- regex/std::regex_iterator::operator==
- regex/std::regex_iterator::operator!=
- regex/std::regex_iterator::operator*
- regex/std::regex_iterator::operator->
- regex/std::regex_iterator::operator++
helpviewer_keywords:
- std::regex_iterator
- std::regex_iterator::operator==
- std::regex_iterator::operator!=
- std::regex_iterator::operator*
- std::regex_iterator::operator->
- std::regex_iterator::operator++
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
ms.openlocfilehash: d9d2baf99b1e2334132f54aeace3d8197b1e73da
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217585"
---
# <a name="regex_iterator-class"></a>regex_iterator クラス

一致の反復子クラス。

## <a name="syntax"></a>構文

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>パラメーター

*BidIt*\
サブマッチ用の反復子の型。

*Elem*\
一致させる要素の型。

*RXtraits*\
要素の特徴 (traits) クラス。

## <a name="remarks"></a>解説

クラステンプレートは、定数前方反復子オブジェクトを表します。 反復子範囲 `match_results<BidIt>` で定義された文字シーケンスに正規表現オブジェクト `*pregex` を繰り返し適用することによって、 `[begin, end)`型のオブジェクトを抽出します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[regex_iterator](#regex_iterator)|反復子を構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[difference_type](#difference_type)|反復子の差の型です。|
|[iterator_category](#iterator_category)|反復子カテゴリの型。|
|[pointer](#pointer)|一致へのポインターの型です。|
|[reference](#reference)|一致を指す参照の型です。|
|[regex_type](#regex_type)|一致させる正規表現の型。|
|[value_type](#value_type)|一致の型|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[operator! =](#op_neq)|反復子の非等値を比較します。|
|[operator](#op_star)|指定した一致にアクセスします。|
|[+ + 演算子](#op_add_add)|反復子をインクリメントします。|
|[operator =](#op_eq)|反復子が等しいかどうかを比較します。|
|[演算子->](#op_arrow)|指定した一致にアクセスします。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<regex>

**名前空間:** std

## <a name="examples"></a>例

正規表現の例については、以下の例をご覧ください。

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [スワップ](../standard-library/regex-functions.md#swap)

```cpp
// std__regex__regex_iterator.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="regex_iteratordifference_type"></a><a name="difference_type"></a>regex_iterator::d ifference_type

反復子の差の型です。

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>解説

この型は `std::ptrdiff_t` の同意語です。

## <a name="regex_iteratoriterator_category"></a><a name="iterator_category"></a>regex_iterator:: iterator_category

反復子カテゴリの型。

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>解説

この型は `std::forward_iterator_tag` の同意語です。

## <a name="regex_iteratoroperator"></a><a name="op_neq"></a>regex_iterator:: operator! =

反復子の非等値を比較します。

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
比較する反復子。

### <a name="remarks"></a>解説

このメンバー関数は、`!(*this == right)` を返します。

## <a name="regex_iteratoroperator"></a><a name="op_star"></a>regex_iterator:: operator *

指定した一致にアクセスします。

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>解説

このメンバー関数は、格納されている値 `match` を返します。

## <a name="regex_iteratoroperator"></a><a name="op_add_add"></a>regex_iterator:: operator + +

反復子をインクリメントします。

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>解説

現在の一致に文字が含まれていない場合は、最初の演算子が `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`を呼び出します。それ以外の場合は、現在の一致の後の最初の文字を指すように格納されている値 `begin` を増やしてから、 `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`を呼び出します。 どちらの場合も、検索に失敗したら、演算子がオブジェクトをシーケンス末尾の反復子に設定します。 演算子はそのオブジェクトを返します。

2 つ目の演算子は、オブジェクトのコピーを作成して、オブジェクトをインクリメントしてから、そのコピーを返します。

## <a name="regex_iteratoroperator"></a><a name="op_eq"></a>regex_iterator:: operator =

反復子が等しいかどうかを比較します。

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
比較する反復子。

### <a name="remarks"></a>解説

メンバー関数は、 **`*this`** と*right*が両方ともシーケンス末尾の反復子である場合、またはどちらもシーケンス末尾の反復子 (、、、) ではない場合に true を返し `begin == right.begin` `end == right.end` `pregex == right.pregex` `flags == right.flags` ます。 それ以外の場合は、false を返します。

## <a name="regex_iteratoroperator-gt"></a><a name="op_arrow"></a>regex_iterator:: operator-&gt;

指定した一致にアクセスします。

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>解説

メンバー関数は、格納されている値 `match`のアドレスを返します。

## <a name="regex_iteratorpointer"></a><a name="pointer"></a>regex_iterator::p ointer

一致へのポインターの型です。

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>解説

この型は `match_results<BidIt>*`のシノニムです。ここで `BidIt` はテンプレート パラメーターです。

## <a name="regex_iteratorreference"></a><a name="reference"></a>regex_iterator:: reference

一致を指す参照の型です。

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>解説

この型は `match_results<BidIt>&`のシノニムです。ここで `BidIt` はテンプレート パラメーターです。

## <a name="regex_iteratorregex_iterator"></a><a name="regex_iterator"></a>regex_iterator:: regex_iterator

反復子を構築します。

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>パラメーター

*まずは*\
一致させるシーケンスの先頭。

*前の*\
一致させるシーケンスの末尾。

*書き直し*\
照合する正規表現。

*f*\
一致のフラグ。

### <a name="remarks"></a>解説

1 つ目のコンストラクターは、シーケンス末尾の反復子を構築します。 2番目のコンストラクターは、格納された値を最初に、格納された値を最後に、格納され `begin` *first* `end` た値をで、 *last*格納されている値を f で初期化し `pregex` `&re` `flags` ます。 *f* 次に、 `regex_search(begin, end, match, *pregex, flags)`を呼び出します。 検索に失敗すると、コンストラクターがオブジェクトをシーケンス末尾の反復子に設定します。

## <a name="regex_iteratorregex_type"></a><a name="regex_type"></a>regex_iterator:: regex_type

一致させる正規表現の型。

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>解説

typedef は、`basic_regex<Elem, RXtraits>` の同意語です。

## <a name="regex_iteratorvalue_type"></a><a name="value_type"></a>regex_iterator:: value_type

一致の型

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>解説

この型は `match_results<BidIt>`のシノニムです。ここで `BidIt` はテンプレート パラメーターです。

## <a name="see-also"></a>関連項目

[\<regex>](../standard-library/regex.md)\
[regex_constants クラス](../standard-library/regex-constants-class.md)\
[regex_error クラス](../standard-library/regex-error-class.md)\
[\<regex>関数](../standard-library/regex-functions.md)\
[regex_iterator クラス](../standard-library/regex-iterator-class.md)\
[\<regex>通信](../standard-library/regex-operators.md)\
[regex_token_iterator クラス](../standard-library/regex-token-iterator-class.md)\
[regex_traits クラス](../standard-library/regex-traits-class.md)\
[\<regex>typedef](../standard-library/regex-typedefs.md)
