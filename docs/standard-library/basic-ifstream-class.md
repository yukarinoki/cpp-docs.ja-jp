---
title: basic_ifstream クラス
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_ifstream
- fstream/std::basic_ifstream::close
- fstream/std::basic_ifstream::is_open
- fstream/std::basic_ifstream::open
- fstream/std::basic_ifstream::rdbuf
- fstream/std::basic_ifstream::swap
helpviewer_keywords:
- std::basic_ifstream [C++]
- std::basic_ifstream [C++], close
- std::basic_ifstream [C++], is_open
- std::basic_ifstream [C++], open
- std::basic_ifstream [C++], rdbuf
- std::basic_ifstream [C++], swap
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
ms.openlocfilehash: 85a315ee393a002da4d0999569d4af6c34a37ee3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376843"
---
# <a name="basic_ifstream-class"></a>basic_ifstream クラス

[basic_filebuf](../standard-library/basic-filebuf-class.md)< basic_filebuf`Elem` `Tr`> クラスのストリーム バッファーから、文字の特徴がクラスによって決定される要素を含む、> の`Elem`ストリーム バッファーから要素およびエンコードされたオブジェクトの抽出を制御するオブジェクトについて説明`Tr`します。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ifstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Elem*\
ファイル バッファーの基本要素。

*Tr*\
ファイル バッファーの基本要素の特徴 (通常は `char_traits`< `Elem`>)。

## <a name="remarks"></a>解説

このオブジェクトは、クラス `basic_filebuf`< `Elem`, `Tr`> のオブジェクトを格納します。

## <a name="example"></a>例

次の例は、ファイルからテキストを読み取る方法を示しています。

```cpp
// basic_ifstream_class.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    ifstream ifs("basic_ifstream_class.txt");
    if (!ifs.bad())
    {
        // Dump the contents of the file to cout.
        cout << ifs.rdbuf();
        ifs.close();
    }
}
```

## <a name="input-basic_ifstream_classtxt"></a>入力: basic_ifstream_class.txt

```cpp
This is the contents of basic_ifstream_class.txt.
```

## <a name="output"></a>出力

```cpp
This is the contents of basic_ifstream_class.txt.
```

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[basic_ifstream](#basic_ifstream)|`basic_ifstream` オブジェクトの新しいインスタンスを初期化します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[閉じる](#close)|ファイルを閉じます。|
|[is_open](#is_open)|ファイルが開いているかどうかを判断します。|
|[open](#open)|ファイルを開きます。|
|[rdbuf](#rdbuf)|格納されたストリーム バッファーのアドレスを返します。|
|[スワップ](#swap)|この `basic_ifstream` の内容を、指定された `basic_ifstream` の内容と交換します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[演算子=](#op_eq)|このストリーム オブジェクトの内容を割り当てます。 これは、`rvalue` が関係する移動代入で、コピーを残しません。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<fstream>

**名前空間:** std

## <a name="basic_ifstreambasic_ifstream"></a><a name="basic_ifstream"></a>basic_ifstream::basic_ifstream

`basic_ifstream` 型のオブジェクトを構築します。

```cpp
basic_ifstream();

explicit basic_ifstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ifstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

basic_ifstream(basic_ifstream&& right);
```

### <a name="parameters"></a>パラメーター

*_Filename*\
開くファイルの名前。

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*_Prot*\
[_fsopen、_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md) の `shflag` パラメーターと同等の既定のファイル保護。

### <a name="remarks"></a>解説

最初のコンストラクターは[、basic_istream](../standard-library/basic-istream-class.md)( ) を`sb``sb`呼び出すことによって基本クラス[を](../standard-library/basic-filebuf-class.md)< `Elem`初期化します`Tr`basic_filebuf>。 また、`basic_filebuf`< `Elem`, `Tr`> を呼び出すことで `sb` の初期化もします。

2 番目と 3 番目のコンストラクターは、`basic_istream`( `sb`) を呼び出すことで基底クラスを初期化します。 また[、basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf)< `Elem``Tr`を`sb`呼び出すことによっても初期化>、 を呼び出します`sb`。 [開く](../standard-library/basic-filebuf-class.md#open) `_Mode` ( `ios_base::in` `_Filename`, &#124; ) 後者の関数が null ポインターを返す場合、コンストラクター`failbit`は**setstate**( ) を呼び出します。

4 番目のコンストラクターは、右辺値参照として扱われる `right` のコンテンツでオブジェクトを初期化します。

### <a name="example"></a>例

次の例は、ファイルからテキストを読み取る方法を示しています。 ファイルを作成するには、[basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) の例を参照してください。

```cpp
// basic_ifstream_ctor.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    ifstream ifs("basic_ifstream_ctor.txt");
    if (!ifs.bad())
    {
        // Dump the contents of the file to cout.
        cout << ifs.rdbuf();
        ifs.close();
    }
}
```

## <a name="basic_ifstreamclose"></a><a name="close"></a>basic_ifstream::閉じる

ファイルを閉じます。

```cpp
void close();
```

### <a name="remarks"></a>解説

メンバー関数は[rdbuf](#rdbuf) **->** [close](../standard-library/basic-filebuf-class.md#close)を呼び出します。

### <a name="example"></a>例

`close` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_ifstreamis_open"></a><a name="is_open"></a>basic_ifstream::is_open

ファイルが開いているかどうかを判断します。

```cpp
bool is_open() const;
```

### <a name="return-value"></a>戻り値

ファイルが開いている場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>解説

このメンバー関数は[rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open)を返します。

### <a name="example"></a>例

`is_open` の使用例については、「[basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open)」を参照してください。

## <a name="basic_ifstreamopen"></a><a name="open"></a>basic_ifstream::オープン

ファイルを開きます。

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in,
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

メンバ関数は[、rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ `_Mode` *ファイル名*、 &#124; **ios_base::in**) を呼び出します。 オープンが失敗した場合、関数は[setstate](../standard-library/basic-ios-class.md#setstate)()`failbit`を呼び出し、ios_base::failure 例外をスローする可能性があります。

### <a name="example"></a>例

を使用する例については[、basic_filebuf::open](../standard-library/basic-filebuf-class.md#open)を参照`open`してください。

## <a name="basic_ifstreamoperator"></a><a name="op_eq"></a>basic_ifstream::演算子=

このストリーム オブジェクトの内容を割り当てます。 これは、右辺値が関係する移動代入で、コピーを残しません。

```cpp
basic_ifstream& operator=(basic_ifstream&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`basic_ifstream` オブジェクトへの右辺値参照。

### <a name="return-value"></a>戻り値

`*this` が返されます。

### <a name="remarks"></a>解説

member 演算子は、右辺値参照として扱われる*right*の内容を使用して、オブジェクトの内容を置き換えます。 詳細については、「[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)」を参照してください。

## <a name="basic_ifstreamrdbuf"></a><a name="rdbuf"></a>basic_ifstream::rdbuf

格納されたストリーム バッファーのアドレスを返します。

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>戻り値

格納されているストリーム バッファーを表す [basic_filebuf](../standard-library/basic-filebuf-class.md) オブジェクトへのポインター。

### <a name="example"></a>例

`rdbuf` の使用例については、「[basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)」を参照してください。

## <a name="basic_ifstreamswap"></a><a name="swap"></a>basic_ifstream::スワップ

2 つの `basic_ifstream` オブジェクトの内容を交換します。

```cpp
void swap(basic_ifstream& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
別のストリーム バッファーへの参照。

### <a name="remarks"></a>解説

メンバー関数は、このオブジェクトの内容を*right*の内容と交換します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
