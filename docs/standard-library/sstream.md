---
title: '&lt;sstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <sstream>
helpviewer_keywords:
- sstream header
ms.assetid: 56f55bc5-549d-4e7f-aaad-99e0ffa49c9e
ms.openlocfilehash: 8284e56e8afb1e5518cbcbb772079b4f19d57b18
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451728"
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
|*left*|`sstream` オブジェクトへの参照。|
|*right*|`sstream` オブジェクトへの参照。|

## <a name="remarks"></a>Remarks

`char *` 型のオブジェクトでは、ストリーミングに [\<strstream >](../standard-library/strstream.md) の機能を使用することができます。 ただし、 \<strstream > は非推奨とされ\<ており、sstream > を使用することをお勧めします。

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|Char テンプレートパラメーター `basic_istringstream`に特殊化された型を作成します。|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|Char テンプレートパラメーター `basic_ostringstream`に特殊化された型を作成します。|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|Char テンプレートパラメーター `basic_stringbuf`に特殊化された型を作成します。|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|Char テンプレートパラメーター `basic_stringstream`に特殊化された型を作成します。|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|Wchar_t テンプレートパラメーター `basic_istringstream`に特殊化された型を作成します。|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|Wchar_t テンプレートパラメーター `basic_ostringstream`に特殊化された型を作成します。|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|Wchar_t テンプレートパラメーター `basic_stringbuf`に特殊化された型を作成します。|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|Wchar_t テンプレートパラメーター `basic_stringstream`に特殊化された型を作成します。|

### <a name="manipulators"></a>マニピュレーター

|||
|-|-|
|[swap](../standard-library/sstream-functions.md#sstream_swap)|2 つの `sstream` オブジェクト間で値を交換します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|文字の特徴がクラス `Tr` によって決まる型 `Elem` の要素の、配列オブジェクトに格納されている要素のシーケンスとの間での転送を制御するストリーム バッファーについて説明します。|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを記述します[](../standard-library/basic-stringbuf-class.md)<。これは、basic_stringbuf `Alloc`**Elem**, Tr, > クラス`Elem`のストリームバッファーから、文字を持つ型の要素を使用して、特徴はクラス`Tr`によって決定され、その要素はクラス`Alloc`のアロケーターによって割り当てられます。|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを記述します。これは、文字`Alloc`の特徴を持つ型`Elem`の要素を使用して、 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, > クラスのストリームバッファーへの挿入を制御します。はクラス`Tr`によって決定され、その要素はクラス`Alloc`のアロケーターによって割り当てられます。|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを記述します。これは、 `Elem`型`Alloc`の要素を使用して、 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**, **Tr**, > クラスのストリームバッファーを使用します。文字の特徴はクラス`Tr`によって決定され、その要素はクラス`Alloc`のアロケーターによって割り当てられます。|

## <a name="requirements"></a>必要条件

- **ヘッダー:** \<sstream>

- **名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
