---
title: '&lt;string_view&gt;演算子'
ms.date: 04/19/2019
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: 1fbb7faf7d6fc92a053c0f4d47575c5c53c7968e
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346920"
---
# <a name="ltstringviewgt-operators"></a>&lt;string_view&gt;演算子

これらの演算子を使用して、2 つの string_view オブジェクト、または、string_view と他の文字列オブジェクトを比較する (たとえば[std::string](basic-string-class.md)、または**char\***) の暗黙的な変換が提供されています。 

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|[operator""sv](#op_sv)|

## <a name="op_neq"></a> operator!=

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

*left*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

*right*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

### <a name="return-value"></a>戻り値

**true**演算子の左側にあるオブジェクトが辞書式の右側にあるオブジェクトと等しいそれ以外の場合**false**します。

### <a name="remarks"></a>Remarks

暗黙的な変換が存在する必要があります*convertible_string_type*もう一方の側で string_view にします。 

比較は、ペアワイズに基づいている文字のシーケンスを比較します。 同じ数の要素がある要素がすべて等しい場合は、2 つのオブジェクトが等しいです。 それ以外の場合は等しくありません。

## <a name="op_eq_eq"></a> 演算子 = =

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

*left*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

*right*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

### <a name="return-value"></a>戻り値

**true**演算子の左側にあるオブジェクトが辞書式の右側にあるオブジェクトと等しいそれ以外の場合は**false**します。

### <a name="remarks"></a>Remarks

暗黙的な変換が存在する必要があります*convertible_string_type*もう一方の側で string_view にします。 

比較は、ペアワイズに基づいている文字のシーケンスを比較します。 同じ数の要素がある要素がすべて等しい場合は、2 つのオブジェクトが等しいです。


## <a name="op_lt"></a> 演算子&lt;

演算子の左側にあるオブジェクトが、適切な sidestring_view オブジェクトより小さいかどうか
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

*left*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

*right*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

### <a name="return-value"></a>戻り値

**true**演算子の左側にあるオブジェクトが右側にある; 上のオブジェクトよりも辞書順で小さい場合はそれ以外の場合**false**します。

### <a name="remarks"></a>Remarks

暗黙的な変換が存在する必要があります*convertible_string_type*もう一方の側で string_view にします。 

比較は、ペアワイズに基づいている文字のシーケンスを比較します。 文字の最初の等しくないペアが発生すると、その比較の結果が返されます。 等しくない文字が見つからない場合、1 つのシーケンスが短いシーケンスが短いシーケンスが小さいよりも長くなります。 つまり、"cat"は、「猫」より小さいです。

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

## <a name="op_lt_eq"></a> 演算子&lt;=

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

*left*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

*right*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

### <a name="return-value"></a>戻り値

**true**演算子の左側にあるオブジェクトが辞書順で小さいよりもまたは右側にあるオブジェクトと等しいそれ以外の場合は**false**します。

### <a name="remarks"></a>Remarks

参照してください[演算子&lt;](#op_lt)します。

## <a name="op_lt_lt"></a> 演算子&lt;&lt;

String_view を出力ストリームに書き込みます。

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>パラメーター

*Ostr*<br/>
出力ストリームに書き込まれています。

*str*<br/>
出力ストリームに入力される string_view します。

### <a name="return-value"></a>戻り値

出力ストリームに書き込まれています。

### <a name="remarks"></a>Remarks

この演算子を使用して、たとえばを使用して、出力ストリームに、string_view の内容を挿入する[:cout](iostream.md#cout)します。

## <a name="op_gt"></a> 演算子&gt;

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

*left*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

*right*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

### <a name="return-value"></a>戻り値

**true**演算子の左側にあるオブジェクトが辞書式の右側にある string_view オブジェクトよりも大きいそれ以外の場合は**false**します。

### <a name="remarks"></a>Remarks

参照してください[演算子&lt;](#op_lt)します。

## <a name="op_gt_eq"></a> 演算子&gt;=

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

*left*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

*right*<br/>
任意の文字列を変換できる型または型のオブジェクト`basic_string_view`と比較します。

### <a name="return-value"></a>戻り値

**true**演算子の左側にあるオブジェクトが辞書式より大きいか、右側にあるオブジェクトと等しいそれ以外の場合は**false**します。

### <a name="remarks"></a>Remarks

参照してください[演算子&lt;](#op_lt)します。

## <a name="op_sv"></a> operator""sv (string_view リテラル)

文字列リテラルからの string_view を構築します。 名前空間が必要です`std::literals::string_view_literals`します。 

### <a name="example"></a>例

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="see-also"></a>関連項目

[\<string_view>](../standard-library/string-view.md)<br/>
