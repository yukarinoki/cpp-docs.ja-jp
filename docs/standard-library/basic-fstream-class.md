---
description: '詳細情報: basic_fstream クラス'
title: basic_fstream クラス
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_fstream
- fstream/std::basic_fstream::close
- fstream/std::basic_fstream::is_open
- fstream/std::basic_fstream::open
- fstream/std::basic_fstream::rdbuf
- fstream/std::basic_fstream::swap
helpviewer_keywords:
- std::basic_fstream [C++]
- std::basic_fstream [C++], close
- std::basic_fstream [C++], is_open
- std::basic_fstream [C++], open
- std::basic_fstream [C++], rdbuf
- std::basic_fstream [C++], swap
ms.assetid: 8473817e-42a4-430b-82b8-b476c86bcf8a
ms.openlocfilehash: df8ad83696422737b5b368b39bf21c82506e8b65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321574"
---
# <a name="basic_fstream-class"></a>basic_fstream クラス

型の要素を使用して、要素とエンコードされたオブジェクトの挿入と抽出[](../standard-library/basic-filebuf-class.md)を制御するオブジェクトを記述し <  `Elem` `Tr` `Elem` ます。これは、文字の特徴がクラスによって決定される型の要素を使用して> basic_filebuf `Tr` ます。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_fstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Elem*\
ファイル バッファーの基本要素。

*Tr*\
ファイル バッファーの基本要素の特徴 (通常は `char_traits`< `Elem`>)。

## <a name="remarks"></a>解説

このオブジェクトは、クラス `basic_filebuf`< `Elem`, `Tr`> のオブジェクトを格納します。

> [!NOTE]
> fstream オブジェクトの get ポインターおよび put ポインターは、互いに独立したポインターでは **ありません**。 get ポインターが移動すると、put ポインターも移動します。

## <a name="example"></a>例

次の例で、読み取りと書き込みが可能な `basic_fstream` オブジェクトの作成方法を示します。

```cpp
// basic_fstream_class.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    fstream fs("fstream.txt", ios::in | ios::out | ios::trunc);
    if (!fs.bad())
    {
        // Write to the file.
        fs << "Writing to a basic_fstream object..." << endl;
        fs.close();

        // Dump the contents of the file to cout.
        fs.open("fstream.txt", ios::in);
        cout << fs.rdbuf();
        fs.close();
    }
}
```

```Output
Writing to a basic_fstream object...
```

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_fstream](#basic_fstream)|`basic_fstream` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[close](#close)|ファイルを閉じます。|
|[is_open](#is_open)|ファイルが開いているかどうかを判断します。|
|[open](#open)|ファイルを開きます。|
|[rdbuf](#rdbuf)|[Basic_filebuf](../standard-library/basic-filebuf-class.md)、> へのポインター型の、格納されているストリームバッファーのアドレスを返し <  `Elem` `Tr` ます。|
|[スワップ](#swap)|このオブジェクトの内容を別の `basic_fstream` オブジェクトの内容と交換します。|

## <a name="requirements"></a>要件

**ヘッダー:**\<fstream>

**名前空間:** std

## <a name="basic_fstreambasic_fstream"></a><a name="basic_fstream"></a> basic_fstream:: basic_fstream

`basic_fstream` 型のオブジェクトを構築します。

```cpp
basic_fstream();

explicit basic_fstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_fstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

basic_fstream(basic_fstream&& right);
```

### <a name="parameters"></a>パラメーター

*_Filename*\
開くファイルの名前。

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*_Prot*\
既定のファイルを開く保護。 _fsopen の *shflag* パラメーターに相当します。 [_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)。

### <a name="remarks"></a>解説

最初のコンストラクターは[basic_iostream](../standard-library/basic-iostream-class.md)() を呼び出すことによって基底クラスを初期化し `sb` `sb` ます。は、 [basic_filebuf](../standard-library/basic-filebuf-class.md)クラスの格納されているオブジェクトです \< **Elem**, **Tr**> 。 また、 `sb` を呼び出すことによって初期化 `basic_filebuf` \< **Elem**, **Tr**> します。

2 番目と 3 番目のコンストラクターは、`basic_iostream`( **sb**) を呼び出すことで基底クラスを初期化します。 また `sb` 、を呼び出して `basic_filebuf` \< **Elem**, **Tr**> を初期化し、次に sb を [開き](../standard-library/basic-filebuf-class.md#open)**ます**(_ *Filename*, `_Mode` )。 後者の関数が null ポインターを返す場合、コンストラクターは [setstate](../standard-library/basic-ios-class.md#setstate)( `failbit` ) を呼び出します。

4 番目のコンストラクターは、右辺値参照として扱われる `right` のコンテンツでオブジェクトを初期化します。

### <a name="example"></a>例

`basic_fstream` の使用例については、「[streampos](../standard-library/ios-typedefs.md#streampos)」を参照してください。

## <a name="basic_fstreamclose"></a><a name="close"></a> basic_fstream:: close

ファイルを閉じます。

```cpp
void close();
```

### <a name="remarks"></a>解説

このメンバー関数は、 [rdbuf](#rdbuf) **->** [close](../standard-library/basic-filebuf-class.md#close)を呼び出します。

### <a name="example"></a>例

`close` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_fstreamis_open"></a><a name="is_open"></a> basic_fstream:: is_open

ファイルが開いているかどうかを判断します。

```cpp
bool is_open() const;
```

### <a name="return-value"></a>戻り値

**`true`** ファイルが開いている場合は **`false`** 。それ以外の場合は。

### <a name="remarks"></a>解説

このメンバー関数は、 [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)を返します。

### <a name="example"></a>例

`is_open` の使用例については、「[basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open)」を参照してください。

## <a name="basic_fstreamopen"></a><a name="open"></a> basic_fstream:: open

ファイルを開きます。

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in | ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>パラメーター

*_Filename*\
開くファイルの名前。

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*_Prot*\
既定のファイルを開く保護。 _fsopen の *shflag* パラメーターに相当します。 [_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)。

### <a name="remarks"></a>解説

このメンバー関数は、 [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*,) を呼び出し `_Mode` ます。 この関数が null ポインターを返す場合、関数は [setstate](../standard-library/basic-ios-class.md#setstate)( `failbit` ) を呼び出します。

### <a name="example"></a>例

の使用例については、「 [basic_filebuf:: open](../standard-library/basic-filebuf-class.md#open) 」を参照してください `open` 。

## <a name="basic_fstreamoperator"></a><a name="op_eq"></a> basic_fstream:: operator =

指定したストリーム オブジェクトからコンテンツをこのオブジェクトに割り当てます。 これは、コピーを残さない右辺値を伴う移動代入です。

```cpp
basic_fstream& operator=(basic_fstream&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`basic_fstream` オブジェクトへの左辺値参照。

### <a name="return-value"></a>戻り値

を返し **`*this`** ます。

### <a name="remarks"></a>解説

メンバー演算子は、右辺値参照として扱われる *right* の内容を使用して、オブジェクトの内容を置き換えます。

## <a name="basic_fstreamrdbuf"></a><a name="rdbuf"></a> basic_fstream:: rdbuf

[Basic_filebuf](../standard-library/basic-filebuf-class.md)へのポインター型の、格納されているストリームバッファーのアドレスを返し \< **Elem**, **Tr**> ます。

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>戻り値

格納されたストリーム バッファーのアドレス。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_fstreamswap"></a><a name="swap"></a> basic_fstream:: swap

2 つの `basic_fstream` オブジェクトの内容を交換します。

```cpp
void swap(basic_fstream& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`basic_fstream` オブジェクトへの `lvalue` 参照。

### <a name="remarks"></a>解説

このメンバー関数は、このオブジェクトの内容と、 *right* の内容を交換します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
