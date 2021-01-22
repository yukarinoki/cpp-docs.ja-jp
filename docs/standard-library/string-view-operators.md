---
title: '&lt;string_view &gt; 演算子'
description: '`string_view`2 つの `string_view` オブジェクト、または `string_view` とその他の文字列オブジェクトを比較するために使用される演算子の API リファレンス'
ms.date: 01/15/2021
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
- xstring/std::literals::string_view_literals::operator "sv
- std::literals::string_view_literals::operator sv
- std::literals::string_view_literals
- string_view_literals
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: a14d82dc0b29f88cb25f5b24f0836f033d2b828e
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666902"
---
# <a name="string_view-operators"></a>`<string_view>` 演算子

これらの演算子を使用して、2つの `string_view` オブジェクト、または `string_view` と、暗黙的な [`std::string`](basic-string-class.md) `char*` 変換が提供される他の文字列オブジェクト (やなど) を比較します。

[`operator!=`](#op_neq)\
[`operator>`](#op_gt)\
[`operator>=`](#op_gt_eq)\
[`operator<`](#op_lt)\
[`operator<<`](#op_lt_lt)\
[`operator<=`](#op_lt_eq)\
[`operator==`](#op_eq_eq)\
[`operator""sv`](#op_sv)

## <a name="operator"></a><a name="op_neq"></a> `operator!=`

演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。

```cpp
template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator!=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

*そうです*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左側のオブジェクトが右側のオブジェクトと等しくない場合は、辞書式になります。それ以外の場合は **`false`** 。

### <a name="remarks"></a>注釈

*Convertible_string_type* からもう一方の側のへの暗黙的な変換が存在する必要があり `string_view` ます。

比較は、文字シーケンスのペアの辞書式の比較に基づいています。 同じ数の要素を持ち、要素がすべて等しい場合、2つのオブジェクトは等しくなります。 それ以外の場合は等しくありません。

## <a name="operator"></a><a name="op_eq_eq"></a> `operator==`

演算子の左側のオブジェクトが右側のオブジェクトと等しいかどうかを調べます。

```cpp
template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator==(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

*そうです*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左側のオブジェクトが右側のオブジェクトと等しい場合は、辞書式を返します。それ以外の場合は **`false`** 。

### <a name="remarks"></a>注釈

*Convertible_string_type* からもう一方の側のへの暗黙的な変換が存在する必要があり `string_view` ます。

比較は、文字シーケンスのペアの辞書式の比較に基づいています。 同じ数の要素を持ち、要素がすべて等しい場合、2つのオブジェクトは等しくなります。

## <a name="operator"></a><a name="op_lt"></a> `operator<`

演算子の左側のオブジェクトが右側のオブジェクトより小さいかどうかを調べます。

```cpp
template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

*そうです*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左側のオブジェクトが右側のオブジェクトよりも辞書式小さい場合は、それ以外の場合は **`false`** 。

### <a name="remarks"></a>注釈

*Convertible_string_type* からもう一方の側の string_view への暗黙的な変換が存在する必要があります。

比較は、文字シーケンスのペアの辞書式の比較に基づいています。 最初の等しくない文字ペアが見つかった場合は、その比較の結果が返されます。 等しくない文字が見つからなくても、1つのシーケンスが短い場合は、短いシーケンスが長い方よりも小さくなります。 言い換えると、"cat" は "猫" よりも小さくなります。

### <a name="example"></a>例

```cpp
#include <string>
#include <string_view>

using namespace std;

int main()
{
    string_view sv1 { "ABA" };
    string_view sv2{ "ABAC" };
    string_view sv3{ "ABAD" };
    string_view sv4{ "ABACE" };

    bool result = sv2 > sv1; // true
    result = sv3 > sv2; // true
    result = sv3 != sv1; // true
    result = sv4 < sv3; // true because `C` < `D`
}
```

## <a name="operator"></a><a name="op_lt_eq"></a> `operator<=`

演算子の左側のオブジェクトが右側のオブジェクト以下かどうかを調べます。

```cpp
template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

*そうです*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左側のオブジェクトが右側のオブジェクト以下である場合は、辞書式を返します。それ以外の場合は **`false`** 。

### <a name="remarks"></a>注釈

[`operator<`](#op_lt)に関するページを参照してください。

## <a name="operator"></a><a name="op_lt_lt"></a> `operator<<`

を `string_view` 出力ストリームに書き込みます。

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>パラメーター

*`Ostr`*\
書き込み先の出力ストリーム。

*`Str`*\
出力ストリームに入力する string_view。

### <a name="return-value"></a>戻り値

書き込み先の出力ストリーム。

### <a name="remarks"></a>注釈

この演算子を使用して、の内容を `string_view` 出力ストリームに挿入します。たとえば、を使用し [`std::cout`](iostream.md#cout) ます。

## <a name="operator"></a><a name="op_gt"></a> `operator>`

演算子の左側のオブジェクトが右側のオブジェクトより大きいかどうかを調べます。

```cpp
template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

*そうです*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左側のオブジェクトが右側のオブジェクトより辞書式大きい場合は `string_view` 。それ以外の場合は **`false`** 。

### <a name="remarks"></a>注釈

[`operator<`](#op_lt)に関するページを参照してください。

## <a name="operator"></a><a name="op_gt_eq"></a> `operator>=`

演算子の左側のオブジェクトが右側のオブジェクト以上であるかどうかを調べます。

```cpp
template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*`left`*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

*`right`*\
変換可能な文字列型または比較対象の型のオブジェクト `basic_string_view` 。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左側のオブジェクトが右側のオブジェクト以上である場合は、辞書式の場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>注釈

[`operator<`](#op_lt)に関するページを参照してください。

## <a name="operator-sv-string_view-literal"></a><a name="op_sv"></a>`operator"" sv`( `string_view` リテラル)

`string_view`文字列リテラルからを構築します。 名前空間が必要 `std::literals::string_view_literals` です。

### <a name="example"></a>例

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="requirements"></a>必要条件

[`/std:c++17`](../build/reference/std-specify-language-standard-version.md)

## <a name="see-also"></a>関連項目

[`<string_view>`](../standard-library/string-view.md)
