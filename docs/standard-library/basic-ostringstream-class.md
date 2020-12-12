---
description: '詳細情報: basic_ostringstream クラス'
title: basic_ostringstream クラス
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
ms.openlocfilehash: b745f6b733d093b620e15d0aa22593713988caf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325642"
---
# <a name="basic_ostringstream-class"></a>basic_ostringstream クラス

要素とエンコードされたオブジェクトを [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**、 **Tr**、> クラスのストリームバッファーに挿入する操作を制御するオブジェクトを記述し `Alloc` ます。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*割り当て*\
アロケーター クラス。

*Elem*\
文字列の基本要素の型。

*Tr*\
文字列の基本要素に特化した文字の特徴。

## <a name="remarks"></a>解説

クラスは、要素とエンコードされたオブジェクトのストリームバッファーへの挿入を制御するオブジェクトを表し `Elem` ます。これは、文字の特徴がクラスによって決定され、その `Tr` 要素がクラスのアロケーターによって割り当てられる、型の要素を使用し `Alloc` ます。 このオブジェクトは、クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトを格納します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|`basic_ostringstream` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[allocator_type](#allocator_type)|この型は、テンプレートパラメーター *Alloc* のシノニムです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|型の格納されているストリームバッファーのアドレスを `pointer` [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` 、 `Tr` 、> に返し `Alloc` ます。|
|[str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|

## <a name="requirements"></a>要件

**ヘッダー:**\<sstream>

**名前空間:** std

## <a name="basic_ostringstreamallocator_type"></a><a name="allocator_type"></a> basic_ostringstream:: allocator_type

この型は、テンプレートパラメーター *Alloc* のシノニムです。

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstreambasic_ostringstream"></a><a name="basic_ostringstream"></a> basic_ostringstream:: basic_ostringstream

basic_ostringstream 型のオブジェクトを構築します。

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>パラメーター

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*引数*\
`basic_string` 型のオブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは [basic_ostream](../standard-library/basic-ostream-class.md)( **sb**) を呼び出すことによって基底クラスを初期化します。ここで、 `sb` は、 [](../standard-library/basic-stringbuf-class.md) <  **Elem**、 **Tr**、> basic_stringbuf クラスの格納されているオブジェクトです `Alloc` 。 また、basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode` &#124; `ios_base::out`) を呼び出すことで **sb** の初期化もします。

2 番目のコンストラクターが basic_ostream( **sb**) を呼び出して基底クラスを初期化します。 また、 `sb` basic_stringbuf< **Elem**、 **Tr**、 `Alloc`> (_ *Str*、&#124;) を呼び出すことによって初期化 `_Mode` `ios_base::out` します。

## <a name="basic_ostringstreamrdbuf"></a><a name="rdbuf"></a> basic_ostringstream:: rdbuf

型の格納されたストリームバッファーのアドレス `pointer` を [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**、 **Tr**、 `Alloc`> に返します。

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>戻り値

`pointer`< **Elem**、 **Tr**、> を basic_stringbuf する型の格納されたストリームバッファーのアドレス `Alloc` 。

### <a name="remarks"></a>解説

このメンバー関数は、型の格納されているストリームバッファーのアドレスを `pointer` basic_stringbuf< **Elem**、 **Tr**、> にし `Alloc` ます。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_ostringstreamstr"></a><a name="str"></a> basic_ostringstream:: str

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
