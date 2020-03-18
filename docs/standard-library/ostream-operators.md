---
title: '&lt;ostream&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: c80abcb08423b4bb269e7d60ac43ef97d197a0e9
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425281"
---
# <a name="ltostreamgt-operators"></a>&lt;ostream&gt; 演算子

||
|-|
|[operator&lt;&lt;](#op_lt_lt)|

## <a name="op_lt_lt"></a>  演算子&lt;&lt;

さまざまな型をストリームに書き込みます。

```cpp
template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const Elem* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    Elem _Ch);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    const char* str);

template <class _Elem, class _Tr>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>& _Ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _ostr,
    char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char* str);

template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);

template <class _Elem, class _Tr, class T>
basic_ostream <_Elem, _Tr>& operator<<(
    basic_ostream<_Elem, _Tr>&& _Ostr,
    Ty val);
```

### <a name="parameters"></a>パラメーター

*_Ch*\
単一の文字。

*_Elem*\
要素型。

*_Ostr*\
`basic_ostream` オブジェクト。

*str*\
文字列。

*_Tr*\
文字の特徴 (traits)。

*val*\
型

### <a name="return-value"></a>戻り値

ストリームです。

### <a name="remarks"></a>解説

`basic_ostream`クラスもいくつかの挿入演算子を定義します。 詳細については、[basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt)をご覧ください。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

*str*から始まるシーケンスの長さ N = `traits_type::`[長さ](../standard-library/char-traits-struct.md#length)(`str`) を決定し、シーケンスを挿入します。 N < `_Ostr.`[width](../standard-library/ios-base-class.md#width) の場合は、関数はまた `_Ostr.width` - N 充填文字の繰り返しを挿入します。 (`_Ostr`の場合、繰り返しはシーケンスの前に置かれます。 [フラグ](../standard-library/ios-base-class.md#flags) & `adjustfield`! = [left](../standard-library/ios-functions.md#left)です。 それ以外の場合、繰り返しはシーケンスに後続します。 関数は *_Ostr*を返します。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

要素 `_Ch`を挿入しています。 1 < `_Ostr.width` である場合、この関数はまた `_Ostr.width` - 1 充填文字の繰り返しを挿入します。 `_Ostr.flags & adjustfield != left` である場合、繰り返しはシーケンスに先行します。 それ以外の場合、繰り返しはシーケンスに後続します。 *_Ostr*が返されます。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const char *str);
```

次の関数と同様に動作します。

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

ただし、 *str*で始まるシーケンスの各要素 *_Ch*は、`_Ostr.`[put](../standard-library/basic-ostream-class.md#put)(`_Ostr.`[拡大](../standard-library/basic-ios-class.md#widen)(`_Ch`)) を呼び出すことによって `Elem` 型のオブジェクトに変換されます。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    char _Ch);
```

次の関数と同様に動作します。

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

ただし、 *_Ch*は `_Ostr.put`(`_Ostr.widen`(`_Ch`)) を呼び出すことによって `Elem` 型のオブジェクトに変換されます。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const char *str);
```

次の関数と同様に動作します。

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    const Elem *str);
```

(要素を挿入する前に拡張する必要はありません。)

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    char _Ch);
```

次の関数と同様に動作します。

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

(挿入前に *_Ch*を拡大する必要はありません)。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

`_Ostr` < < (`const char *`) `str`を返します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

`_Ostr` < < (`char`) `_Ch`を返します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

`_Ostr` < < (`const char *`) `str`を返します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

`_Ostr` < < (`char`) `_Ch`を返します。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

`val` `<<` `_Ostr` を返します。また、`_Ostr` への[右辺値参照](../cpp/rvalue-reference-declarator-amp-amp.md)をプロセス内の左辺値に変換します。

### <a name="example"></a>例

[ の使用例は、](../standard-library/ostream-functions.md#flush)flush`operator<<` をご覧ください。

## <a name="see-also"></a>参照

[\<ostream>](../standard-library/ostream.md)
