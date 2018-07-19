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
ms.openlocfilehash: 8801c41b23ab2c33e4c4e2df9cde8155c1eefafb
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957769"
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

`char *` 型のオブジェクトでは、ストリーミングに [\<strstream >](../standard-library/strstream.md) の機能を使用することができます。 ただし、 \<strstream > は非推奨の使用と\<sstream > ことお勧めします。

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[istringstream](../standard-library/sstream-typedefs.md#istringstream)|型を作成します`basic_istringstream`に特殊化された、 **char**テンプレート パラメーター。|
|[ostringstream](../standard-library/sstream-typedefs.md#ostringstream)|型を作成します`basic_ostringstream`に特殊化された、 **char**テンプレート パラメーター。|
|[stringbuf](../standard-library/sstream-typedefs.md#stringbuf)|型を作成します`basic_stringbuf`に特殊化された、 **char**テンプレート パラメーター。|
|[stringstream](../standard-library/sstream-typedefs.md#stringstream)|型を作成します`basic_stringstream`に特殊化された、 **char**テンプレート パラメーター。|
|[wistringstream](../standard-library/sstream-typedefs.md#wistringstream)|型を作成します`basic_istringstream`に特殊化された、 **wchar_t**テンプレート パラメーター。|
|[wostringstream](../standard-library/sstream-typedefs.md#wostringstream)|型を作成します`basic_ostringstream`に特殊化された、 **wchar_t**テンプレート パラメーター。|
|[wstringbuf](../standard-library/sstream-typedefs.md#wstringbuf)|型を作成します`basic_stringbuf`に特殊化された、 **wchar_t**テンプレート パラメーター。|
|[wstringstream](../standard-library/sstream-typedefs.md#wstringstream)|型を作成します`basic_stringstream`に特殊化された、 **wchar_t**テンプレート パラメーター。|

### <a name="manipulators"></a>マニピュレーター

|||
|-|-|
|[swap](../standard-library/sstream-functions.md#sstream_swap)|2 つの `sstream` オブジェクト間で値を交換します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_stringbuf](../standard-library/basic-stringbuf-class.md)|文字の特徴がクラス `Tr` によって決まる型 `Elem` の要素の、配列オブジェクトに格納されている要素のシーケンスとの間での転送を制御するストリーム バッファーについて説明します。|
|[basic_istringstream](../standard-library/basic-istringstream-class.md)|クラスのストリーム バッファーからエンコードされたオブジェクトと要素の抽出を制御するオブジェクトについて説明します[basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**、 **Tr**、 `Alloc`>、型の要素を含む`Elem`、その文字特性はクラスによって決まります`Tr`、要素は、クラスのアロケーターによって割り当てられていると`Alloc`します。|
|[basic_ostringstream](../standard-library/basic-ostringstream-class.md)|クラスのストリーム バッファーにエンコードされたオブジェクトと要素の挿入を制御するオブジェクトを記述します[basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**、 **Tr**、 `Alloc`>、型の要素を含む`Elem`、その文字特性はクラスによって決まります`Tr`、要素は、クラスのアロケーターによって割り当てられていると`Alloc`します。|
|[basic_stringstream](../standard-library/basic-stringstream-class.md)|要素の挿入と抽出を制御するオブジェクトとクラスのストリーム バッファーを使用してエンコードされたオブジェクトについて説明します[basic_stringbuf](../standard-library/basic-stringbuf-class.md)<**Elem**、 **Tr**、 `Alloc`>、型の要素を含む`Elem`、その文字特性はクラスによって決まります`Tr`、要素は、クラスのアロケーターによって割り当てられていると`Alloc`します。|

## <a name="requirements"></a>必要条件

- **ヘッダー:** \<sstream>

- **名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
