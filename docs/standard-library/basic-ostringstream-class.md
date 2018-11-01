---
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
ms.openlocfilehash: 45a7eb1384c70b488e057fb9df8ad4c496272316
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582772"
---
# <a name="basicostringstream-class"></a>basic_ostringstream クラス

要素とエンコードされたオブジェクトを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> クラスのストリーム バッファーに挿入する操作を制御するオブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Alloc*<br/>
アロケーター クラス。

*Elem*<br/>
文字列の基本要素の型。

*Tr*<br/>
文字列の基本要素に特化した文字の特徴。

## <a name="remarks"></a>Remarks

クラスは、型の要素のストリーム バッファーにエンコードされたオブジェクトと要素の挿入を制御するオブジェクトを表します`Elem`、その文字特性はクラスによって決まります`Tr`のアロケーターによって割り当てられている要素とクラス`Alloc`します。 このオブジェクトは、クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトを格納します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|`basic_ostringstream` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[allocator_type](#allocator_type)|型はテンプレート パラメーターのシノニム*アロケーション*します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|型 `pointer` の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> に返します。|
|[str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<sstream>

**名前空間:** std

## <a name="allocator_type"></a>  basic_ostringstream::allocator_type

型はテンプレート パラメーターのシノニム*アロケーション*します。

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstream"></a>  basic_ostringstream::basic_ostringstream

basic_ostringstream 型のオブジェクトを構築します。

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>パラメーター

*モード (_m)*<br/>
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*str*<br/>
`basic_string` 型のオブジェクト。

### <a name="remarks"></a>Remarks

最初のコンス トラクターを呼び出して基底クラスを初期化する[basic_ostream](../standard-library/basic-ostream-class.md)( **sb**) ここで、`sb`クラスの格納されているオブジェクトは、 [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **Elem**、 **Tr**、 `Alloc`>。 また、basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode` &#124; `ios_base::out`) を呼び出すことで **sb** の初期化もします。

2 番目のコンストラクターが basic_ostream( **sb**) を呼び出して基底クラスを初期化します。 初期化も`sb`basic_stringbuf 呼び出し元によって < **Elem**、 **Tr**、 `Alloc`> (_ *Str*、 `_Mode` &#124; `ios_base::out`).

## <a name="rdbuf"></a>  basic_ostringstream::rdbuf

型の格納されたストリーム バッファーのアドレスを返して`pointer`に[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**、 **Tr**、 `Alloc`>。

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>戻り値

型の格納されたストリーム バッファーのアドレス`pointer`basic_stringbuf < **Elem**、 **Tr**、 `Alloc`>。

### <a name="remarks"></a>Remarks

メンバー関数は、型の格納されたストリーム バッファーのアドレスを返します`pointer`basic_stringbuf < **Elem**、 **Tr**、 `Alloc`>。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="str"></a>  basic_ostringstream::str

文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>パラメーター

*_Newstr*<br/>
新しい文字列。

### <a name="return-value"></a>戻り値

制御されたシーケンスが **\*this** によって制御されるシーケンスのコピーである、クラス [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> のオブジェクトを返します。

### <a name="remarks"></a>Remarks

最初のメンバー関数は [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str) を返します。 2 番目のメンバー関数は `rdbuf` -> **str**( `_Newstr`) を呼び出します。

### <a name="example"></a>例

参照してください[basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str)を使用する例については`str`します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
