---
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
ms.openlocfilehash: f08689b1080837f042abfb3c4c52bb0ad558a448
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364869"
---
# <a name="basic_stringstream-class"></a>basic_stringstream クラス

**>** のクラス[basic_stringbuf](../standard-library/basic-stringbuf-class.md)<  **Tr**のストリーム バッファーを使用して、要素およびエンコードされたオブジェクトの挿入と抽出を`Alloc`制御するオブジェクトについて説明します。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Alloc*\
アロケーター クラス。

*Elem*\
文字列の基本要素の型。

*Tr*\
文字列の基本要素に特化した文字の特徴。

## <a name="remarks"></a>解説

クラス テンプレートは、クラス[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**、 **Tr** `Alloc` 、>`Elem`のストリーム バッファーを使用して、要素の挿入と抽出`Tr`を制御するオブジェクト、およびエンコードされたオブジェクトを表します。 `Alloc` このオブジェクトは、クラス basic_stringbuf< **Elem**, **Tr**, `Alloc`> のオブジェクトを格納します。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[basic_stringstream](#basic_stringstream)|`basic_stringstream` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[allocator_type](#allocator_type)|この型は、テンプレート パラメーター `Alloc` のシノニムです。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[rdbuf](#rdbuf)|>`pointer`に[basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`する型の格納されたストリーム バッファーの`Tr`アドレス`Alloc`を返します。|
|[Str](#str)|文字列バッファー内のテキストを設定または取得します。書き込み位置は変更しません。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<sstream>

**名前空間:** std

## <a name="basic_stringstreamallocator_type"></a><a name="allocator_type"></a>basic_stringstream::allocator_type

この型は、テンプレート パラメーター `Alloc` のシノニムです。

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstreambasic_stringstream"></a><a name="basic_stringstream"></a>basic_stringstream::basic_stringstream

`basic_stringstream` 型のオブジェクトを構築します。

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*Str*\
`basic_string` 型オブジェクト。

### <a name="remarks"></a>解説

最初の**Tr**コンストラクターは`Alloc`、>**basic_iostream** [(](../standard-library/basic-iostream-class.md) **sb**)`sb`を呼び出して基本クラス[basic_stringbufを](../standard-library/basic-stringbuf-class.md)< 初期化します。 また、basic_stringbuf `sb`<**エレム**、 **Tr** `Alloc` 、 `_Mode`>() を呼び出して初期化します。

2 番目のコンストラクターが basic_iostream( **sb**) を呼び出して基底クラスを初期化します。 また`sb`**、<エレム** **、Tr**、>(_ `Alloc` *Str*)`_Mode`を basic_stringbuf呼び出すことによっても初期化されます。

## <a name="basic_stringstreamrdbuf"></a><a name="rdbuf"></a>basic_stringstream::rdbuf

**pointer** 型の格納されたストリーム バッファーのアドレスを [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> に返します。

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>戻り値

`pointer` **elem** **、Tr、><basic_stringbuf**するタイプの格納されたストリームバッファの`Alloc`アドレス。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_stringstreamstr"></a><a name="str"></a>basic_stringstream::str

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

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
