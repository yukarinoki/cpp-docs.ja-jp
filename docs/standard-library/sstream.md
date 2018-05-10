---
title: '&lt;sstream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <sstream>
dev_langs:
- C++
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ee9beb54dd241c6987b79db238f033f3d169497
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

割り当てられた配列オブジェクトに格納されているシーケンスの iostreams 操作をサポートする、いくつかのテンプレート クラスを定義します。 テンプレート クラス [basic_string](../standard-library/basic-string-class.md) のオブジェクトとの間で、このようなシーケンスが簡単に変換されます。

## <a name="syntax"></a>構文

```cpp
namespace std {
template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringbuf;
typedef basic_stringbuf<char>
stringbuf;
typedef basic_stringbuf<wchar_t> wstringbuf;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_istringstream;
typedef basic_istringstream<char>
istringstream;
typedef basic_istringstream<wchar_t> wistringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_ostringstream;
typedef basic_ostringstream<char>
ostringstream;
typedef basic_ostringstream<wchar_t> wostringstream;

template <class CharType, class Traits = char_traits<CharType>, class Allocator = allocator<CharType>>
class basic_stringstream;
typedef basic_stringstream<char>
stringstream;
typedef basic_stringstream<wchar_t> wstringstream;
// TEMPLATE FUNCTIONS
template <class CharType, class Traits, class Allocator>
void swap(
    basic_stringbuf<CharType, Traits, Allocator>& left,
    basic_stringbuf<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_istringstream<CharType, Traits, Allocator>& left,
    basic_istringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap(
    basic_ostringstream<CharType, Traits, Allocator>& left,
    basic_ostringstream<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
void swap (
    basic_stringstream<CharType, Traits, Allocator>& left,
    basic_stringstream<CharType, Traits, Allocator>& right);

}  // namespace std
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`left`|`sstream` オブジェクトへの参照。|
|`right`|`sstream` オブジェクトへの参照。|

## <a name="remarks"></a>コメント

`char *` 型のオブジェクトでは、ストリーミングに [\<strstream >](../standard-library/strstream.md) の機能を使用することができます。 ただし、 \<strstream > は使用されなくなりましたし、使用\<sstream > をお勧めします。

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|`char` テンプレート パラメーターに特殊化された `basic_istringstream` 型を作成します。|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|`char` テンプレート パラメーターに特殊化された `basic_ostringstream` 型を作成します。|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|`char` テンプレート パラメーターに特殊化された `basic_stringbuf` 型を作成します。|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|`char` テンプレート パラメーターに特殊化された `basic_stringstream` 型を作成します。|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|`wchar_t` テンプレート パラメーターに特殊化された `basic_istringstream` 型を作成します。|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|`wchar_t` テンプレート パラメーターに特殊化された `basic_ostringstream` 型を作成します。|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|`wchar_t` テンプレート パラメーターに特殊化された `basic_stringbuf` 型を作成します。|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|`wchar_t` テンプレート パラメーターに特殊化された `basic_stringstream` 型を作成します。|

### <a name="manipulators"></a>マニピュレーター

|||
|-|-|
|[swap](../standard-library/sstream-functions.md#sstream_swap)|2 つの `sstream` オブジェクト間で値を交換します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|文字の特徴がクラス **Tr** によって決まる **Elem** 型の要素の、配列オブジェクトに格納されている要素のシーケンスとの間での転送を制御するストリーム バッファーについて説明します。|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|**Elem** 型の要素を含む [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`> クラスのストリーム バッファーから要素とエンコードされたオブジェクトを抽出する際の、抽出を制御するオブジェクトを記述します。Elem 型の文字特性は **Tr** クラスによって決められ、その要素は `Alloc` クラスのアロケーターによって割り当てられます。|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|**Elem** 型の要素を含む [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`> クラスのストリーム バッファーへ要素とエンコードされたオブジェクトを挿入する際の、挿入を制御するオブジェクトを記述します。Elem 型の文字特性は **Tr** クラスによって決められ、その要素は `Alloc` クラスのアロケーターによって割り当てられます。|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|**Elem** 型の要素を含む [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, `Alloc`> クラスのストリーム バッファーを使用して要素とエンコードされたオブジェクトを挿入および抽出する際の、挿入と抽出を制御するオブジェクトを記述します。Elem 型の文字特性は **Tr** クラスによって決められ、その要素は `Alloc` クラスのアロケーターによって割り当てられます。|

## <a name="requirements"></a>要件

- **ヘッダー:** \<sstream>

- **名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
