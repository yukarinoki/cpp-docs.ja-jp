---
description: '詳細情報: &lt; sstream&gt;'
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: 5f0c5307073c2296f20df0adb663bce9b4b97d59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169100"
---
# <a name="ltsstreamgt"></a>&lt;sstream&gt;

割り当てられた配列オブジェクトに格納されているシーケンスの iostreams 操作をサポートする複数のクラステンプレートを定義します。 このようなシーケンスは、クラステンプレート [basic_string](../standard-library/basic-string-class.md)のオブジェクトとの間で簡単に変換できます。

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

*左側*\
`sstream` オブジェクトへの参照。

*そうです*\
`sstream` オブジェクトへの参照。

## <a name="remarks"></a>解説

型のオブジェクト `char *` は、ストリーミングに対しての機能を使用でき [\<strstream>](../standard-library/strstream.md) ます。 ただし、\<strstream> は非推奨とされ、\<sstream> の使用をお勧めします。

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|テンプレートパラメーターに特殊化された型を作成し `basic_istringstream` **`char`** ます。|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|テンプレートパラメーターに特殊化された型を作成し `basic_ostringstream` **`char`** ます。|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|テンプレートパラメーターに特殊化された型を作成し `basic_stringbuf` **`char`** ます。|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|テンプレートパラメーターに特殊化された型を作成し `basic_stringstream` **`char`** ます。|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|テンプレートパラメーターに特殊化された型を作成し `basic_istringstream` **`wchar_t`** ます。|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|テンプレートパラメーターに特殊化された型を作成し `basic_ostringstream` **`wchar_t`** ます。|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|テンプレートパラメーターに特殊化された型を作成し `basic_stringbuf` **`wchar_t`** ます。|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|テンプレートパラメーターに特殊化された型を作成し `basic_stringstream` **`wchar_t`** ます。|

### <a name="manipulators"></a>マニピュレーター

|名前|説明|
|-|-|
|[スワップ](../standard-library/sstream-functions.md#sstream_swap)|2 つの `sstream` オブジェクト間で値を交換します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|文字の特徴がクラス `Tr` によって決まる型 `Elem` の要素の、配列オブジェクトに格納されている要素のシーケンスとの間での転送を制御するストリーム バッファーについて説明します。|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|要素とエンコードされたオブジェクトの、クラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **Elem**、 **Tr**、> のストリームバッファーから、 `Alloc` 型の要素を使用して、文字の `Elem` 特徴がクラスによって決定され、その `Tr` 要素がクラスのアロケーターによって割り当てられているオブジェクトの抽出を制御するオブジェクトを記述し `Alloc` ます。|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|要素とエンコードされたオブジェクトをクラスのストリームバッファーに挿入する操作を[](../standard-library/basic-stringbuf-class.md)制御するオブジェクトについて説明し <   `Alloc` ます。型の要素には、 `Elem` 文字の特徴がクラスによって決定され、その `Tr` 要素はクラスのアロケーターによって割り当てられています (> `Alloc` basic_stringbuf)。|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを記述します。これは、クラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **Elem**、 **Tr**、> のストリームバッファーを `Alloc` 型の要素と共に使用し `Elem` 、その文字特性はクラスによって決定さ `Tr` れ、要素はクラスのアロケーターによって割り当てられ `Alloc` ます。|

## <a name="requirements"></a>要件

- **ヘッダー:**\<sstream>

- **名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
