---
title: '&lt;ostream&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::operator&lt;&lt;
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
ms.openlocfilehash: ee1a9a6829dbef13b034300d696c43ddba48d9d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449424"
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

*_Ch*<br/>
単一の文字。

*_Elem*<br/>
要素型。

*_Ostr*<br/>
`basic_ostream` オブジェクト。

*str*<br/>
文字列。

*_Tr*<br/>
文字の特徴 (traits)。

*val*<br/>
型

### <a name="return-value"></a>戻り値

ストリーム。

### <a name="remarks"></a>Remarks

`basic_ostream`クラスもいくつかの挿入演算子を定義します。 詳細については、[basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt)をご覧ください。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

長さ N を決定します = `traits_type::`[長さ](../standard-library/char-traits-struct.md#length)(`str`) で始まるシーケンスの*str*、およびシーケンスを挿入します。 N < `_Ostr.`[width](../standard-library/ios-base-class.md#width) の場合は、関数はまた `_Ostr.width` - N 充填文字の繰り返しを挿入します。 場合、繰り返しはシーケンスに先行 (`_Ostr`します。 [フラグ](../standard-library/ios-base-class.md#flags) &  `adjustfield` ! =[左](../standard-library/ios-functions.md#left)します。 それ以外の場合、繰り返しはシーケンスに後続します。 関数を返します *_Ostr*します。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

要素 `_Ch`を挿入しています。 1 < `_Ostr.width` である場合、この関数はまた `_Ostr.width` - 1 充填文字の繰り返しを挿入します。 `_Ostr.flags & adjustfield != left` である場合、繰り返しはシーケンスに先行します。 それ以外の場合、繰り返しはシーケンスに後続します。 返します *_Ostr*します。

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

各要素 *_Ch*で始まるシーケンスの*str*型のオブジェクトに変換されます`Elem`を呼び出して`_Ostr.`[配置](../standard-library/basic-ostream-class.md#put)(`_Ostr.` [widen](../standard-library/basic-ios-class.md#widen)(`_Ch`))。

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

点を除いて *_Ch*型のオブジェクトに変換されます`Elem`呼び出して`_Ostr.put`( `_Ostr.widen`( `_Ch`))。

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

(拡大変換することはありません *_Ch*挿入する前にします)。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

返します`_Ostr`<< (`const char *`)`str`します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

返します`_Ostr`<< (`char`)`_Ch`します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

返します`_Ostr`<< (`const char *`)`str`します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

返します`_Ostr`<< (`char`)`_Ch`します。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr, class T>
basic_ostream<_Elem, _Tr>& operator<<(
    basic_ostream<char, _Tr>&& _Ostr,
    T val);
```

`_Ostr` `<<` `val` を返します (さらに `_Ostr` への [RValue Reference](../cpp/rvalue-reference-declarator-amp-amp.md) をそのプロセス内の lvalue に変換します)。

### <a name="example"></a>例

`operator<<` の使用例は、[flush](../standard-library/ostream-functions.md#flush) をご覧ください。

## <a name="see-also"></a>関連項目

[\<ostream>](../standard-library/ostream.md)<br/>
