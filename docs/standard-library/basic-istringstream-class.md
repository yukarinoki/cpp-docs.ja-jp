---
title: basic_istringstream クラス
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
ms.openlocfilehash: 6a8ead5f1014e7f750e01988241ab020431312da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376802"
---
# <a name="basic_istringstream-class"></a>basic_istringstream クラス

[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **クラス basic_stringbuf Tr** **、>** のストリーム バッファーからの要素およびエンコードされたオブジェクトの抽出を制御するオブジェクトについて`Alloc`説明します。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Alloc*\
アロケーター クラス。

*Elem*\
文字列の基本要素の型。

*Tr*\
文字列の基本要素に特化した文字の特徴。

## <a name="remarks"></a>解説

クラス テンプレートは **、Elem** `Alloc` **、Tr、>** [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< クラスのストリーム バッファーから要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表し、*その*文字の特徴はクラス*Tr*によって決定され、その要素はクラス*Alloc*のアロケーターによって割り当てられます。 このオブジェクトは、クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトを格納します。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[basic_istringstream](#basic_istringstream)|`basic_istringstream` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[allocator_type](#allocator_type)|この型は、テンプレート パラメーター `Alloc` のシノニムです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|>`pointer`に[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`する型の格納されたストリーム バッファーの`Tr`アドレス`Alloc`を返します。|
|[Str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|
|[スワップ](#swap)|この `basic_istringstream` オブジェクト内の値を、提供されるオブジェクトの値と交換します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子=](#op_eq)|オブジェクト パラメーターの値をこの `basic_istringstream` オブジェクトに代入します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<sstream>

**名前空間:** std

## <a name="basic_istringstreamallocator_type"></a><a name="allocator_type"></a>basic_istringstream::allocator_type

この型は、テンプレート パラメーター `Alloc` のシノニムです。

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstreambasic_istringstream"></a><a name="basic_istringstream"></a>basic_istringstream::basic_istringstream

`basic_istringstream` 型のオブジェクトを構築します。

```cpp
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```

### <a name="parameters"></a>パラメーター

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*Str*\
`basic_string` 型オブジェクト。

*そうです*\
`basic_istringstream` オブジェクトの右辺値参照。

### <a name="remarks"></a>解説

最初のコンストラクターは、クラス[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`の格納された`sb`オブジェクトである`sb`[basic_istream](../standard-library/basic-istream-class.md)( ) を`Tr`呼`Alloc`び出して、基本クラスを初期化>。 また、`basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`) を呼び出すことで `sb` の初期化もします。

2 番目のコンストラクターが `basic_istream(sb)` を呼び出して基底クラスを初期化します。 また、`basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`) を呼び出すことで `sb` の初期化もします。

3 番目のコンストラクターは、右辺値参照として扱われる*right*の内容でオブジェクトを初期化します。

## <a name="basic_istringstreamoperator"></a><a name="op_eq"></a>basic_istringstream::演算子=

オブジェクト パラメーターの値をこの `basic_istringstream` オブジェクトに代入します。

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`basic_istringstream` オブジェクトへの右辺値参照。

### <a name="remarks"></a>解説

メンバ演算子は、オブジェクトの内容を*right*の内容に置き換えます。

## <a name="basic_istringstreamrdbuf"></a><a name="rdbuf"></a>basic_istringstream::rdbuf

> の**Elem** **、Tr**`pointer`に格納されているストリーム バッファーの`Alloc`アドレスを[返](../standard-library/basic-stringbuf-class.md)< basic_stringbuf。

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>戻り値

`pointer` **elem** **、Tr、><basic_stringbuf**するタイプの格納されたストリームバッファの`Alloc`アドレス。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_istringstreamstr"></a><a name="str"></a>basic_istringstream::str

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

制御シーケンスが**\*、この**メソッド[によって](../standard-library/basic-string-class.md)< 制御されるシーケンスの`Alloc`コピーである、クラス basic_string**Elem** **、Tr**、>のオブジェクトを返します。

### <a name="remarks"></a>解説

最初のメンバー関数は[rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str)を返します。 2 番目のメンバー`rdbuf` -> 関数は`_Newstr` **str**( ) を呼び出します。

### <a name="example"></a>例

を使用する例については[、 basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str)を参照`str`してください。

## <a name="basic_istringstreamswap"></a><a name="swap"></a>basic_istringstream::スワップ

2 つの `basic_istringstream` オブジェクトの値を交換します。

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*そうです*|`basic_istringstream` オブジェクトへの `lvalue` 参照。|

### <a name="remarks"></a>解説

メンバー関数は、このオブジェクトの値と*right*の値を交換します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
