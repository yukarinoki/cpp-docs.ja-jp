---
description: '詳細情報: basic_stringstream クラス'
title: basic_stringstream クラス
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
ms.openlocfilehash: a236f8b382a2c0f8d77f971493fc16b9ac9da81f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325587"
---
# <a name="basic_stringstream-class"></a>basic_stringstream クラス

要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを記述します。クラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**、 **Tr**、> のストリームバッファーを使用し `Alloc` ます。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*割り当て*\
アロケーター クラス。

*Elem*\
文字列の基本要素の型。

*Tr*\
文字列の基本要素に特化した文字の特徴。

## <a name="remarks"></a>解説

クラステンプレートは、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを記述し[](../standard-library/basic-stringbuf-class.md)ます。これは、文字の <    `Alloc` `Elem` 特徴がクラスによって決定され、その `Tr` 要素がクラスのアロケーターによって割り当てられる、型の要素を> basic_stringbuf 使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御し `Alloc` ます。 このオブジェクトは、クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトを格納します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_stringstream](#basic_stringstream)|`basic_stringstream` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[allocator_type](#allocator_type)|この型は、テンプレート パラメーター `Alloc` のシノニムです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|型の格納されているストリームバッファーのアドレスを `pointer` [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` 、 `Tr` 、> に返し `Alloc` ます。|
|[str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|

## <a name="requirements"></a>要件

**ヘッダー:**\<sstream>

**名前空間:** std

## <a name="basic_stringstreamallocator_type"></a><a name="allocator_type"></a> basic_stringstream:: allocator_type

この型は、テンプレート パラメーター `Alloc` のシノニムです。

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstreambasic_stringstream"></a><a name="basic_stringstream"></a> basic_stringstream:: basic_stringstream

`basic_stringstream` 型のオブジェクトを構築します。

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*引数*\
`basic_string` 型のオブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは [basic_iostream](../standard-library/basic-iostream-class.md)( **sb**) を呼び出すことによって基底クラスを初期化します。ここで、 `sb` は、 [](../standard-library/basic-stringbuf-class.md) <  **Elem**、 **Tr**、> basic_stringbuf クラスの格納されているオブジェクトです `Alloc` 。 また、 `sb` basic_stringbuf< **Elem**、 **Tr**、> () を呼び出すことによって初期化し `Alloc` `_Mode` ます。

2 番目のコンストラクターが basic_iostream( **sb**) を呼び出して基底クラスを初期化します。 また、 `sb` basic_stringbuf< **Elem**, **Tr**, `Alloc`> (_ *Str*,) を呼び出すことによって初期化 `_Mode` します。

## <a name="basic_stringstreamrdbuf"></a><a name="rdbuf"></a> basic_stringstream:: rdbuf

**pointer** 型の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> に返します。

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>戻り値

`pointer` **Elem**、 **Tr**、>< basic_stringbuf する型の格納されたストリームバッファーのアドレス `Alloc` 。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_stringstreamstr"></a><a name="str"></a> basic_stringstream:: str

文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>パラメーター

*_Newstr*\
新しい文字列。

### <a name="return-value"></a>戻り値

[](../standard-library/basic-string-class.md) <    `Alloc` 制御されたシーケンスが **\* this** によって制御されるシーケンスのコピーである Elem、Tr、> basic_string クラスのオブジェクトを返します。

### <a name="remarks"></a>解説

1つ目のメンバー関数は、 [rdbuf](#rdbuf)  ->  [str](../standard-library/basic-stringbuf-class.md#str)を返します。 2番目のメンバー関数は `rdbuf`  ->  **str**() を呼び出し `_Newstr` ます。

### <a name="example"></a>例

の使用例については、「 [basic_stringbuf:: str](../standard-library/basic-stringbuf-class.md#str) 」を参照してください `str` 。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
