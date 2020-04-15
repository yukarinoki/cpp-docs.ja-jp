---
title: basic_ofstream クラス
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_ofstream
- fstream/std::basic_ofstream::close
- fstream/std::basic_ofstream::is_open
- fstream/std::basic_ofstream::open
- fstream/std::basic_ofstream::rdbuf
- fstream/std::basic_ofstream::swap
helpviewer_keywords:
- std::basic_ofstream [C++]
- std::basic_ofstream [C++], close
- std::basic_ofstream [C++], is_open
- std::basic_ofstream [C++], open
- std::basic_ofstream [C++], rdbuf
- std::basic_ofstream [C++], swap
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
ms.openlocfilehash: f2d0facd92e0ef1935f8218a6d323a62edb81e5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376794"
---
# <a name="basic_ofstream-class"></a>basic_ofstream クラス

クラス> のストリーム バッファーへの要素とエンコードされたオブジェクト[basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem``Tr`の挿入を制御するオブジェクトについて説明します`Elem``Tr`。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Elem*\
ファイル バッファーの基本要素。

*Tr*\
ファイル バッファーの基本要素の特徴 (通常は `char_traits`< `Elem`>)。

## <a name="remarks"></a>解説

ファイルへの**wchar_t**`basic_ofstream`書き込みのwchar_t特殊化時に、ファイルがテキストモードで開かれている場合、MBCS シーケンスが書き込まれます。 内部表現には `wchar_t` 文字のバッファーが使用されます。

このオブジェクトは、クラス `basic_filebuf`< `Elem`, `Tr`> のオブジェクトを格納します。

## <a name="example"></a>例

次の例では、`basic_ofstream` オブジェクトを作成して、これにテキストを書き込む方法を示します。

```cpp
// basic_ofstream_class.cpp
// compile with: /EHsc
#include <fstream>

using namespace std;

int main(int argc, char **argv)
{
    ofstream ofs("ofstream.txt");
    if (!ofs.bad())
    {
        ofs << "Writing to a basic_ofstream object..." << endl;
        ofs.close();
    }
}
```

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[basic_ofstream](#basic_ofstream)|`basic_ofstream` 型のオブジェクトを作成します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[閉じる](#close)|ファイルを閉じます。|
|[is_open](#is_open)|ファイルが開いているかどうかを判断します。|
|[open](#open)|ファイルを開きます。|
|[rdbuf](#rdbuf)|格納されたストリーム バッファーのアドレスを返します。|
|[スワップ](#swap)|この `basic_ofstream` の内容を、指定された `basic_ofstream` の内容と交換します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子=](#op_eq)|このストリーム オブジェクトの内容を割り当てます。 これは、`rvalue reference` が関係する移動代入で、コピーを残しません。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<fstream>

**名前空間:** std

## <a name="basic_ofstreambasic_ofstream"></a><a name="basic_ofstream"></a>basic_ofstream::basic_ofstream

`basic_ofstream` 型のオブジェクトを作成します。

```cpp
basic_ofstream();

explicit basic_ofstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ofstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

basic_ofstream(
    basic_ofstream&& right);
```

### <a name="parameters"></a>パラメーター

*_Filename*\
開くファイルの名前。

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*_Prot*\
[_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) の `shflag` パラメーターと同等の既定のファイル保護。

*そうです*\
この `basic_ofstream` オブジェクトを初期化するために使用されている `basic_ofstream` オブジェクトへの右辺値参照。

### <a name="remarks"></a>解説

最初のコンストラクターは、basic_ostream [(](../standard-library/basic-ostream-class.md)`sb`) を呼び`sb`出すことによって基本クラスを初期化します`Tr`( ) は、> クラス[basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`の格納されたオブジェクトです。 また、`basic_filebuf`< `Elem`, `Tr`> を呼び出すことで `sb` の初期化もします。

2 番目と 3 番目のコンストラクターは、`basic_ostream`( **sb**) を呼び出すことで基底クラスを初期化します。 また、 を`sb`呼び`basic_filebuf`< `Elem`出`Tr`して初期化>、 そして 、 を呼び出します`sb`。 [開く](../standard-library/basic-filebuf-class.md#open) `_Mode` ( `ios_base::out` `_Filename`, &#124; ) 後者の関数が null ポインターを返す場合、コンストラクター`failbit`は[setstate](../standard-library/basic-ios-class.md#setstate)( ) を呼び出します。

4 番目のコンストラクターは、copy 関数です。 右辺値参照として扱われる*right*の内容でオブジェクトを初期化します。

### <a name="example"></a>例

次の例では、`basic_ofstream` オブジェクトを作成して、これにテキストを書き込む方法を示します。

```cpp
// basic_ofstream_ctor.cpp
// compile with: /EHsc
#include <fstream>

using namespace std;

int main(int argc, char **argv)
{
    ofstream ofs("C:\\ofstream.txt");
    if (!ofs.bad())
    {
        ofs << "Writing to a basic_ofstream object..." << endl;
        ofs.close();
    }
}
```

## <a name="basic_ofstreamclose"></a><a name="close"></a>basic_ofstream::閉じる

ファイルを閉じます。

```cpp
void close();
```

### <a name="remarks"></a>解説

メンバー関数は[rdbuf](../standard-library/basic-ifstream-class.md#rdbuf)**->**[close](../standard-library/basic-filebuf-class.md#close)を呼び出します。

### <a name="example"></a>例

`close` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_ofstreamis_open"></a><a name="is_open"></a>basic_ofstream::is_open

ファイルが開いているかどうかを示します。

```cpp
bool is_open() const;
```

### <a name="return-value"></a>戻り値

ファイルが開いている場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>解説

このメンバー関数は[rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)を返します。

### <a name="example"></a>例

```cpp
// basic_ofstream_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   // Open and close with a basic_filebuf
   file.rdbuf( )->open( "basic_ofstream_is_open.txt", ios::in );
   file.close( );
   if (file.is_open())
      cout << "it's open" << endl;
   else
      cout << "it's closed" << endl;
}
```

## <a name="basic_ofstreamopen"></a><a name="open"></a>basic_ofstream::オープン

ファイルを開きます。

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
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
[_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) の `shflag` パラメーターと同等の既定のファイル保護。

### <a name="remarks"></a>解説

メンバ関数は[、rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ `_Mode` `ios_base::out`*ファイル名*、 &#124; ) を呼び出します。 その関数が null ポインタを返す場合、関数は`failbit` [setstate](../standard-library/basic-ios-class.md#setstate)( ) を呼び出します。

### <a name="example"></a>例

を使用する例については[、basic_filebuf::open](../standard-library/basic-filebuf-class.md#open)を参照`open`してください。

## <a name="basic_ofstreamoperator"></a><a name="op_eq"></a>basic_ofstream::演算子=

このストリーム オブジェクトの内容を割り当てます。 これは、`rvalue reference` が関係する移動代入で、コピーを残しません。

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`basic_ofstream` オブジェクトへの右辺値参照。

### <a name="return-value"></a>戻り値

`*this` が返されます。

### <a name="remarks"></a>解説

member 演算子は、右辺値参照として扱われる*right*の内容を使用して、オブジェクトの内容を置き換えます。

## <a name="basic_ofstreamrdbuf"></a><a name="rdbuf"></a>basic_ofstream::rdbuf

格納されたストリーム バッファーのアドレスを返します。

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>戻り値

格納されたストリーム バッファーのアドレスを返します。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_ofstreamswap"></a><a name="swap"></a>basic_ofstream::スワップ

2 つの `basic_ofstream` オブジェクトの内容を交換します。

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
別の `basic_ofstream` オブジェクトへの `lvalue` 参照です。

### <a name="remarks"></a>解説

メンバー関数は、このオブジェクトの内容を*right*の内容と交換します。

## <a name="see-also"></a>関連項目

[basic_ostreamクラス](../standard-library/basic-ostream-class.md)\
[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
