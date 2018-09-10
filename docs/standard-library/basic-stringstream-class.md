---
title: basic_stringstream クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
dev_langs:
- C++
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60a12c18ec4e174087900f7386d948ea3ab16a89
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102487"
---
# <a name="basicstringstream-class"></a>basic_stringstream クラス

クラス [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> のストリーム バッファーを使用して、要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Alloc*<br/>
アロケーター クラス。

*Elem*<br/>
文字列の基本要素の型。

*Tr*<br/>
文字列の基本要素に特化した文字の特徴。

## <a name="remarks"></a>Remarks

テンプレート クラスは、要素の挿入と抽出を制御するオブジェクトとクラスのストリーム バッファーを使用してエンコードされたオブジェクトについて説明します[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**、 **。Tr**、 `Alloc`>、型の要素を含む`Elem`、その文字特性はクラスによって決まります`Tr`、要素は、クラスのアロケーターによって割り当てられていると`Alloc`します。 このオブジェクトは、クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトを格納します。

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
|[rdbuf](#rdbuf)|型 `pointer` の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> に返します。|
|[str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|

## <a name="requirements"></a>要件

**ヘッダー:** \<sstream>

**名前空間:** std

## <a name="allocator_type"></a>  basic_stringstream::allocator_type

この型は、テンプレート パラメーター `Alloc` のシノニムです。

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstream"></a>  basic_stringstream::basic_stringstream

`basic_stringstream` 型のオブジェクトを構築します。

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*モード (_m)*<br/>
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*str*<br/>
`basic_string` 型のオブジェクト。

### <a name="remarks"></a>Remarks

最初のコンス トラクターを呼び出して基底クラスを初期化する[basic_iostream](../standard-library/basic-iostream-class.md)( **sb**) ここで、`sb`クラスの格納されているオブジェクトは、 [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **Elem**、 **Tr**、 `Alloc`>。 初期化も`sb`basic_stringbuf 呼び出し元によって < **Elem**、 **Tr**、 `Alloc`> ( `_Mode`)。

2 番目のコンストラクターが basic_iostream( **sb**) を呼び出して基底クラスを初期化します。 またを初期化します`sb`basic_stringbuf 呼び出し元によって < **Elem**、 **Tr**、 `Alloc`> (_ *Str*、 `_Mode`)。

## <a name="rdbuf"></a>  basic_stringstream::rdbuf

**pointer** 型の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> に返します。

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>戻り値

型の格納されたストリーム バッファーのアドレス`pointer`basic_stringbuf < **Elem**、 **Tr**、 `Alloc`>。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="str"></a>  basic_stringstream::str

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
