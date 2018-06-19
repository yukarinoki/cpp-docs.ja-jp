---
title: '&lt;ostream&gt; 演算子 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ostream/std::operator&lt;&lt;
dev_langs:
- C++
ms.assetid: 9282a62e-a3d1-4371-a284-fbc9515bb9a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e818c267f5fed9bd98b5c5998f4b0eac0c09f3e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857793"
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

`_Ch` 文字です。

`_Elem` 要素の型。

`_Ostr` A`basic_ostream`オブジェクト。

`str` 文字列を返します。

`_Tr` 文字の特徴です。

`val` 型

### <a name="return-value"></a>戻り値

ストリーム。

### <a name="remarks"></a>コメント

`basic_ostream`クラスもいくつかの挿入演算子を定義します。 詳細については、[basic_ostream::operator&lt;&lt;](../standard-library/basic-ostream-class.md#basic_ostream_operator_lt_lt)をご覧ください。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _ostr,
    const Elem *str);
```

長さ N = `str` で始まるシーケンスの `traits_type::`[length](../standard-library/char-traits-struct.md#length)(`str`) とし、シーケンスを挿入しています。 N < `_Ostr.`[width](../standard-library/ios-base-class.md#width) の場合は、関数はまた `_Ostr.width` - N 充填文字の繰り返しを挿入します。 繰り返し場合、シーケンスの前に (`_Ostr`です。 [フラグ](../standard-library/ios-base-class.md#flags) &  `adjustfield` ! =[左](../standard-library/ios-functions.md#left)です。 それ以外の場合、繰り返しはシーケンスに後続します。 `_Ostr` が返されます。

下記のテンプレート関数は

```cpp
template <class _Elem, class _Tr>
basic_ostream<Elem, _Tr>& operator<<(
    basic_ostream<Elem, _Tr>& _Ostr,
    Elem _Ch);
```

要素 `_Ch`を挿入しています。 1 < `_Ostr.width` である場合、この関数はまた `_Ostr.width` - 1 充填文字の繰り返しを挿入します。 `_Ostr.flags & adjustfield != left` である場合、繰り返しはシーケンスに先行します。 それ以外の場合、繰り返しはシーケンスに後続します。 `_Ostr` を返します。

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

異なる点は、`str` で始まるシーケンスの各要素 `_Ch` が、`_Ostr.`[put](../standard-library/basic-ostream-class.md#put)(`_Ostr.`[widen](../standard-library/basic-ios-class.md#widen)(`_Ch`)) を呼び出すことにより、`Elem` 型のオブジェクトに変換されることです。

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

異なる点は、`_Ostr.put`(`_Ostr.widen`(`_Ch`)) を呼び出すことにより、`_Ch` が `Elem` 型のオブジェクトに変換されることです。

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

(`_Ch`を挿入する前に拡張する必要はありません。)

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const signed char *str);
```

`_Ostr` << ( `const char *`) `str` を返します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    signed char _Ch);
```

`_Ostr` << ( `char`) `_Ch`を返します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    const unsigned char *str);
```

`_Ostr` << ( `const char *`) `str`を返します。

下記のテンプレート関数は

```cpp
template <class _Tr>
basic_ostream<char, _Tr>& operator<<(
    basic_ostream<char, _Tr>& _Ostr,
    unsigned char _Ch);
```

`_Ostr` << ( `char`) `_Ch`を返します。

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
