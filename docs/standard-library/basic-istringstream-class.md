---
title: basic_istringstream クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0754ba9dc63f77793ced17e7950c7fc3ea3290d7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847443"
---
# <a name="basicistringstream-class"></a>basic_istringstream クラス

クラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

`Alloc` アロケーター クラス。

`Elem` 文字列の基本要素の型。

*Tr*文字列の基本要素に特化した文字の特徴です。

## <a name="remarks"></a>コメント

このテンプレート クラスは、**Elem** 型の要素を含む [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> クラスのストリーム バッファーから要素とエンコードされたオブジェクトを抽出する際の、抽出を制御するオブジェクトを記述します。Elem 型の文字特性は **Tr** クラスによって決められ、その要素は `Alloc` クラスのアロケーターによって割り当てられます。 このオブジェクトは、クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトを格納します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_istringstream](#basic_istringstream)|`basic_istringstream` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[allocator_type](#allocator_type)|この型は、テンプレート パラメーター `Alloc` のシノニムです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|型 `pointer` の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> に返します。|
|[str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|
|[swap](#swap)|この `basic_istringstream` オブジェクト内の値を、提供されるオブジェクトの値と交換します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator=](#op_eq)|オブジェクト パラメーターの値をこの `basic_istringstream` オブジェクトに代入します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<sstream>

**名前空間:** std

## <a name="allocator_type"></a>  basic_istringstream::allocator_type

この型は、テンプレート パラメーター `Alloc` のシノニムです。

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstream"></a>  basic_istringstream::basic_istringstream

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

`_Mode` 列挙のいずれかの[ios_base::openmode](../standard-library/ios-base-class.md#openmode)です。

`str` 型のオブジェクト`basic_string`です。

`right` 右辺値参照、`basic_istringstream`オブジェクト。

### <a name="remarks"></a>コメント

最初のコンストラクターは、[basic_istream](../standard-library/basic-istream-class.md)( `sb`) を呼び出すことで基底クラスを初期化します。ここで、`sb` はクラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> の格納されているオブジェクトです。 また、`basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`) を呼び出すことで `sb` の初期化もします。

2 番目のコンストラクターが `basic_istream(sb)` を呼び出して基底クラスを初期化します。 また、`basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`) を呼び出すことで `sb` の初期化もします。

3 番目のコンストラクターは、右辺値参照として扱われる `right` のコンテンツでオブジェクトを初期化します。

## <a name="op_eq"></a>  basic_istringstream::operator=

オブジェクト パラメーターの値をこの `basic_istringstream` オブジェクトに代入します。

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>パラメーター

`right` 右辺値参照、`basic_istringstream`オブジェクト。

### <a name="remarks"></a>コメント

メンバー演算子は右辺値参照の移動代入として処理され、このオブジェクトの内容が `right` の内容で置き換えられます。

## <a name="rdbuf"></a>  basic_istringstream::rdbuf

**pointer** 型の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> に返します。

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>戻り値

basic_stringbuf< **Elem**, **Tr**, `Alloc`> に返す **pointer** 型の格納されたストリーム バッファーのアドレス。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="str"></a>  basic_istringstream::str

文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。

```cpp
basic_string<Elem, Tr, Alloc> str() const;


void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>パラメーター

`_Newstr` 新しい文字列。

### <a name="return-value"></a>戻り値

制御されたシーケンスが **\*this** によって制御されるシーケンスのコピーである、クラス [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> のオブジェクトを返します。

### <a name="remarks"></a>コメント

最初のメンバー関数は [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str) を返します。 2 番目のメンバー関数は `rdbuf` -> **str**( `_Newstr`) を呼び出します。

### <a name="example"></a>例

**str** の使用例については、「[basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str)」を参照してください。

## <a name="swap"></a>  basic_istringstream::swap

2 つの `basic_istringstream` オブジェクトの値を交換します。

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`right`|`basic_istringstream` オブジェクトへの `lvalue` 参照。|

### <a name="remarks"></a>コメント

メンバー関数は、このオブジェクトの値と `right` の値を交換します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
