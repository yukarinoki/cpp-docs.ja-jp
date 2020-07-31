---
title: basic_filebuf クラス
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_filebuf
- fstream/std::basic_filebuf::char_type
- fstream/std::basic_filebuf::int_type
- fstream/std::basic_filebuf::off_type
- fstream/std::basic_filebuf::pos_type
- fstream/std::basic_filebuf::traits_type
- fstream/std::basic_filebuf::close
- fstream/std::basic_filebuf::is_open
- fstream/std::basic_filebuf::open
- fstream/std::basic_filebuf::overflow
- fstream/std::basic_filebuf::pbackfail
- fstream/std::basic_filebuf::seekoff
- fstream/std::basic_filebuf::seekpos
- fstream/std::basic_filebuf::setbuf
- fstream/std::basic_filebuf::Swap
- fstream/std::basic_filebuf::sync
- fstream/std::basic_filebuf::uflow
- fstream/std::basic_filebuf::underflow
helpviewer_keywords:
- std::basic_filebuf [C++]
- std::basic_filebuf [C++], char_type
- std::basic_filebuf [C++], int_type
- std::basic_filebuf [C++], off_type
- std::basic_filebuf [C++], pos_type
- std::basic_filebuf [C++], traits_type
- std::basic_filebuf [C++], close
- std::basic_filebuf [C++], is_open
- std::basic_filebuf [C++], open
- std::basic_filebuf [C++], overflow
- std::basic_filebuf [C++], pbackfail
- std::basic_filebuf [C++], seekoff
- std::basic_filebuf [C++], seekpos
- std::basic_filebuf [C++], setbuf
- std::basic_filebuf [C++], Swap
- std::basic_filebuf [C++], sync
- std::basic_filebuf [C++], uflow
- std::basic_filebuf [C++], underflow
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
ms.openlocfilehash: 7dc244cde3d77ad99add1c35716779a55eac9263
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219314"
---
# <a name="basic_filebuf-class"></a>basic_filebuf クラス

型*Char_T*の要素の転送を制御するストリームバッファーを記述します。このストリームバッファーは、文字の特徴がクラス*Tr*によって決定され、外部ファイルに格納されている要素のシーケンスとの間で送受信されます。

## <a name="syntax"></a>構文

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_filebuf : public basic_streambuf<Char_T, Tr>
```

### <a name="parameters"></a>パラメーター

*Char_T*\
ファイル バッファーの基本要素。

*Tr*\
ファイルバッファーの基本要素の特徴 (通常は `char_traits<Char_T>` )。

## <a name="remarks"></a>解説

クラステンプレートは、 *Char_T*型の要素の転送を制御するストリームバッファーを記述します。このストリームバッファーは、文字の特徴がクラス*Tr*によって決定され、外部ファイルに格納されている要素のシーケンスとの間で送受信されます。

> [!NOTE]
> 型のオブジェクト `basic_filebuf` は、 __ \* __ `char_type` 型パラメーター *Char_T*によって指定されたに関係なく、char 型の内部バッファーを使用して作成されます。 つまり、Unicode 文字列 (文字を含む **`wchar_t`** ) は、 **`char`** 内部バッファーに書き込まれる前に、(文字を含む) ANSI 文字列に変換されます。 Unicode 文字列をバッファーに格納するには、型の新しいバッファーを作成 **`wchar_t`** し、メソッドを使用して設定し [`basic_streambuf::pubsetbuf`](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` ます。 この動作を示す例については、以降のセクションを参照してください。

クラスのオブジェクトは、 `basic_filebuf<Char_T, Tr>` ファイルポインターを格納します。これは、 `FILE` 開いているファイルに関連付けられているストリームを制御するオブジェクトを指定します。 さらに、プロテクト メンバー関数である [overflow](#overflow) と [underflow](#underflow) で使用される 2 つのファイル変換ファセットへのポインターも格納します。 詳細については、「[`basic_filebuf::open`](#open)」を参照してください。

## <a name="example"></a>例

次の例では、`pubsetbuf()` メソッドを呼び出して、`basic_filebuf<wchar_t>` 型のオブジェクトの内部バッファーに Unicode 文字を強制的に格納しています。

```cpp
// unicode_basic_filebuf.cpp
// compile with: /EHsc

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>
#include <memory.h>
#include <string.h>

#define IBUFSIZE 16

using namespace std;

void hexdump(const string& filename);

int main()
{
    wchar_t* wszHello = L"Hello World";
    wchar_t wBuffer[128];

    basic_filebuf<wchar_t> wOutFile;

    // Open a file, wcHello.txt, then write to it, then dump the
    // file's contents in hex
    wOutFile.open("wcHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wcHello.txt\n";
        return -1;
    }
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";
    hexdump(string("wcHello.txt"));

    // Open a file, wwHello.txt, then set the internal buffer of
    // the basic_filebuf object to be of type wchar_t, then write
    // to the file and dump the file's contents in hex
    wOutFile.open("wwHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wwHello.txt\n";
        return -1;
    }
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";
    hexdump(string("wwHello.txt"));

    return 0;
}

// dump contents of filename to stdout in hex
void hexdump(const string& filename)
{
    fstream ifile(filename.c_str(),
        ios_base::in | ios_base::binary);
    char *ibuff = new char[IBUFSIZE];
    char *obuff = new char[(IBUFSIZE*2)+1];
    int i;

    if(!ifile.is_open())
    {
        cout << "Cannot Open " << filename.c_str()
             << " for reading\n";
        return;
    }
    if(!ibuff || !obuff)
    {
        cout << "Cannot Allocate buffers\n";
        ifile.close();
        return;
    }

    while(!ifile.eof())
    {
        memset(obuff,0,(IBUFSIZE*2)+1);
        memset(ibuff,0,IBUFSIZE);
        ifile.read(ibuff,IBUFSIZE);

        // corner case where file is exactly a multiple of
        // 16 bytes in length
        if(ibuff[0] == 0 && ifile.eof())
            break;

        for(i = 0; i < IBUFSIZE; i++)
        {
            if(ibuff[i] >= ' ')
                obuff[i] = ibuff[i];
            else
                obuff[i] = '.';

            cout << setfill('0') << setw(2) << hex
                 << (int)ibuff[i] << ' ';
        }
        cout << "  " << obuff << endl;
    }
    ifile.close();
}
```

```Output
Hex Dump of wcHello.txt - note that output is ANSI chars:
48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....

Hex Dump of wwHello.txt - note that output is wchar_t chars:
48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o. .W.o.
72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........
```

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_filebuf](#basic_filebuf)|`basic_filebuf` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|型名を `Char_T` テンプレート パラメーターに関連付けます。|
|[int_type](#int_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[off_type](#off_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[pos_type](#pos_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[traits_type](#traits_type)|型名を `Tr` テンプレート パラメーターに関連付けます。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[ok](#close)|ファイルを閉じます。|
|[is_open](#is_open)|ファイルが開いているかどうかを示します。|
|[open](#open)|ファイルを開きます。|
|[超え](#overflow)|いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。|
|[pbackfail](#pbackfail)|プロテクト仮想メンバー関数が要素を入力ストリームに戻そうと試み、その要素を現在の要素に (次のポインターによって指されるように) します。|
|[seekoff](#seekoff)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|
|[seekpos](#seekpos)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|
|[setbuf](#setbuf)|プロテクト仮想メンバー関数が、各派生ストリーム バッファーに固有の操作を実行します。|
|[フォト](#swap)|この `basic_filebuf` の内容を、指定された `basic_filebuf` パラメーターの内容と交換します。|
|[頻度](#sync)|プロテクト仮想関数が、制御されているストリームと、関連付けられている外部ストリームとを同期しようと試みます。|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|
|[アンダー](#underflow)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<fstream>

**名前空間:** std

## <a name="basic_filebufbasic_filebuf"></a><a name="basic_filebuf"></a>basic_filebuf:: basic_filebuf

`basic_filebuf` 型のオブジェクトを構築します。

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>解説

最初のコンストラクターは、入力バッファーと出力バッファーを制御するすべてのポインターに Null ポインターを格納します。 また、ファイル ポインターにも Null ポインターを格納します。

2番目のコンストラクターは、右辺値参照として扱われる*right*の内容を使用してオブジェクトを初期化します。

## <a name="basic_filebufchar_type"></a><a name="char_type"></a>basic_filebuf:: char_type

型名を `Char_T` テンプレート パラメーターに関連付けます。

```cpp
typedef Char_T char_type;
```

## <a name="basic_filebufclose"></a><a name="close"></a>basic_filebuf:: close

ファイルを閉じます。

```cpp
basic_filebuf<Char_T, Tr> *close();
```

### <a name="return-value"></a>戻り値

メンバー関数は、ファイル ポインターが Null ポインターの場合に、Null ポインターを返します。

### <a name="remarks"></a>解説

`close` は `fclose(fp)` を呼び出します。 その関数がゼロ以外の値を返す場合、関数は Null ポインターを返します。 それ以外の場合は、を返して、 **`this`** ファイルが正常に閉じられたことを示します。

ワイドストリームの場合、ストリームが開かれた後、またはの最後の呼び出し以降に挿入が発生した場合、 `streampos` 関数はを呼び出し [`overflow`](#overflow) ます。 また、必要に応じて、ファイル変換ファセットを使用してを呼び出すことにより、初期の変換状態を復元するために必要なシーケンスを挿入し `fac` `fac.unshift` ます。 型の生成された各要素 `byte` **`char`** は、 `fp` フォームの連続する呼び出しの場合と同様に、ファイルポインターによって指定された関連するストリームに書き込まれ `fputc(byte, fp)` ます。 またはの書き込みに失敗した場合 `fac.unshift` 、関数は成功しません。

### <a name="example"></a>例

次の例では、現在のディレクトリの2つのファイルを前提としています。 *basic_filebuf_close.txt* (コンテンツは "テスト")、 *iotest.txt* (コンテンツは "ssss") です。

```cpp
// basic_filebuf_close.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main() {
   using namespace std;
   ifstream file;
   basic_ifstream <wchar_t> wfile;
   char c;
   // Open and close with a basic_filebuf
   file.rdbuf()->open( "basic_filebuf_close.txt", ios::in );
   file >> c;
   cout << c << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "iotest.txt" );
   file >> c;
   cout << c << endl;
   file.close( );

   // open a file with a wide character name
   wfile.open( L"iotest.txt" );

   // Open and close a nonexistent with a basic_filebuf
   file.rdbuf()->open( "ziotest.txt", ios::in );
   cout << file.fail() << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "ziotest.txt" );
   cout << file.fail() << endl;
   file.close( );
}
```

```Output
t
s
0
1
```

## <a name="basic_filebufint_type"></a><a name="int_type"></a>basic_filebuf:: int_type

スコープ内のこの型を、スコープ内の `basic_filebuf` 同じ名前の型と同じにし `Tr` ます。

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_filebufis_open"></a><a name="is_open"></a>basic_filebuf:: is_open

ファイルが開いているかどうかを示します。

```cpp
bool is_open() const;
```

### <a name="return-value"></a>戻り値

**`true`** ファイルポインターが null でない場合。

### <a name="example"></a>例

```cpp
// basic_filebuf_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   cout << boolalpha << file.rdbuf( )->is_open( ) << endl;

   file.open( "basic_filebuf_is_open.cpp" );
   cout << file.rdbuf( )->is_open( ) << endl;
}
```

```Output
false
true
```

## <a name="basic_filebufoff_type"></a><a name="off_type"></a>basic_filebuf:: off_type

スコープ内のこの型を、スコープ内の `basic_filebuf` 同じ名前の型と同じにし `Tr` ます。

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_filebufopen"></a><a name="open"></a>basic_filebuf:: open

ファイルを開きます。

```cpp
basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode);
```

### <a name="parameters"></a>パラメーター

*/db*\
開くファイルの名前。

*mode*\
の列挙体の1つ [`ios_base::openmode`](../standard-library/ios-base-class.md#openmode) 。

*protection*\
既定のファイルを開く保護。 _fsopen の*shflag*パラメーターに相当します。 [_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)。

### <a name="return-value"></a>戻り値

バッファーが既に開いている場合、またはファイルポインターが null ポインターの場合、関数は null ポインターを返します。 それ以外の場合はを返し **`this`** ます。

### <a name="remarks"></a>解説

この関数は、を使用し `FILE *` `basic_filebuf` てを呼び出した場合と同じようにを返し [`fopen/wfopen`](../c-runtime-library/reference/fopen-wfopen.md) `(filename, strmode)` ます。 `strmode`次のものから決定され `mode & ~(` [`ate`](../standard-library/ios-base-class.md#openmode) `|` [`binary`](../standard-library/ios-base-class.md#openmode) `)` ます。

- `ios_base::in``"r"`(読み取り用に既存のファイルを開く) になります。
- [ios_base:: out](../standard-library/ios-base-class.md#fmtflags)また `ios_base::out | ios_base::trunc` は `"w"` になります (既存のファイルを切り捨てるか、書き込み用に作成します)。
- `ios_base::out | app``"a"`はになります (すべての書き込みを追加するために既存のファイルを開きます)。
- `ios_base::in | ios_base::out``"r+"`(読み取りと書き込み用に既存のファイルを開く) になります。
- `ios_base::in | ios_base::out | ios_base::trunc``"w+"`はになります (既存のファイルを切り捨てるか、読み取りと書き込みのために作成します)。
- `ios_base::in | ios_base::out | ios_base::app`が `"a+"` になります (読み取り用に既存のファイルを開き、すべての書き込みを追加します)。

`mode & ios_base::binary`が0以外の場合、関数はをに追加して、 `b` テキストストリームでは `strmode` なくバイナリストリームを開きます。
`mode & ios_base::ate`が0以外で、ファイルが正常に開かれた場合は、ストリーム内の現在の位置がファイルの末尾に配置されます。 失敗した場合、ファイルは閉じられます。

上記の操作が正常に完了した場合、ファイル変換ファセットは `use_facet<codecvt<Char_T, char, traits_type::` [`state_type`](../standard-library/char-traits-struct.md#state_type) `> >(` [`getloc`](../standard-library/basic-streambuf-class.md#getloc) `)` 、[アンダーフロー](#underflow)および[オーバーフロー](#overflow)によって使用されると判断されます。

ファイルを正常に開くことができなかった場合は、null が返されます。

### <a name="example"></a>例

[`basic_filebuf::close`](#close)の使用例については、「」を参照してください `open` 。

## <a name="basic_filebufoperator"></a><a name="op_eq"></a>basic_filebuf:: operator =

このストリーム バッファー オブジェクトの内容を割り当てます。 これは、右辺値を使用してコピーを残さない、移動代入です。

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
[basic_filebuf](../standard-library/basic-filebuf-class.md) オブジェクトへの右辺値参照。

### <a name="return-value"></a>戻り値

__* This__を返します。

### <a name="remarks"></a>解説

メンバー演算子は、右辺値参照として扱われる*right*の内容を使用して、オブジェクトの内容を置き換えます。 詳細については、「[右辺値参照宣言子:  &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

## <a name="basic_filebufoverflow"></a><a name="overflow"></a>basic_filebuf:: overflow

いっぱいのバッファーに新しい文字が挿入されたときに呼び出されます。

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>パラメーター

*_Meta*\
バッファーに挿入する文字または `traits_type::eof` 。

### <a name="return-value"></a>戻り値

関数が成功しなかった場合は、を返し `traits_type::eof` ます。 それ以外の場合はを返し `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)` ます。

### <a name="remarks"></a>解説

`_Meta != traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) の場合、プロテクト仮想メンバー関数は、要素を出力バッファーに挿入しようと `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` します。 これはさまざまな方法で行うことができます。

- 書き込み位置が使用可能な場合は、書き込み位置に要素を格納し、出力バッファーの次のポインターをインクリメントできます。

- 新しい記憶域または追加の記憶域を出力バッファーに割り当てることで、書き込み位置を使用可能にすることができます。

- 必要に応じ `ch` て、ファイル変換ファセットを使用してを呼び出すことで、出力バッファー内の保留中の出力を変換でき `fac` `fac.out` ます。 `ch` *Char*型の生成された各要素は、 `fp` フォームの連続する呼び出しの場合と同様に、ファイルポインターによって指定された関連するストリームに書き込まれ `fputc(ch, fp)` ます。 任意の変換または書き込みに失敗した場合、関数は失敗します。

## <a name="basic_filebufpbackfail"></a><a name="pbackfail"></a>basic_filebuf::p backfail

要素を入力ストリームに戻そうと試み、その要素を現在の要素に (ネクスト ポインターによって指されるように) します。

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>パラメーター

*_Meta*\
バッファーに挿入する文字または `traits_type::eof`。

### <a name="return-value"></a>戻り値

関数が成功しなかった場合は、を返し `traits_type::eof` ます。 それ以外の場合はを返し `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)` ます。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は要素を入力バッファーに戻してから、その要素を現在の要素に (ネクスト ポインターによって指されるように) します。 の場合、 `_Meta == traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) プッシュバックする要素は、実際には、現在の要素の前に既にストリームにある要素です。 それ以外の場合、その要素はに置き換えられ `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` ます。 この関数は、さまざまな方法で要素を戻すことができます。

- `putback`位置が使用可能であり、格納されている要素がと等しい場合 `ch` 、入力バッファーの次のポインターをデクリメントできます。

- 関数で位置を使用できるようにするには、その位置を `putback` 指すように次のポインターを設定し、その位置に格納し `ch` ます。

- 関数が要素を入力ストリームにプッシュバックできる場合は、 `ungetc` 型の要素に対してを呼び出すなどして、この処理を実行でき **`char`** ます。

## <a name="basic_filebufpos_type"></a><a name="pos_type"></a>basic_filebuf::p os_type

スコープ内のこの型を、スコープ内の `basic_filebuf` 同じ名前の型と同じにし `Tr` ます。

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_filebufseekoff"></a><a name="seekoff"></a>basic_filebuf:: seekoff

制御されているストリームの現在の位置を変更しようと試みます。

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*_Off*\
*_Way*を基準にしてシークする位置。

*_Way*\
オフセット演算の開始位置。 有効値については、「[seekdir](../standard-library/ios-base-class.md#seekdir)」を参照してください。

*_Which*\
ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。

### <a name="return-value"></a>戻り値

新しい位置または無効なストリーム位置を返します。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、制御されたストリームの現在位置を変更しようとします。 クラスのオブジェクトの場合 [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>` 、ストリームの位置は、型のオブジェクトで表すことができ `fpos_t` ます。これには、オフセットとワイドストリームを解析するために必要なすべての状態情報が格納されます。 オフセット0は、ストリームの最初の要素を参照します。 (型のオブジェクトは [`pos_type`](../standard-library/basic-streambuf-class.md#pos_type) 、少なくとも `fpos_t` オブジェクトを格納します)。

読み取りと書き込みのために開かれたファイルの場合、入力と出力の両方のストリームが直列に配置されます。 挿入と抽出を切り替えるには、またはを呼び出す必要があり [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) ます。 `pubseekoff`(および) への呼び出しに `seekoff` は、[テキストストリーム](../c-runtime-library/text-and-binary-streams.md)、[バイナリストリーム](../c-runtime-library/text-and-binary-streams.md)、および[ワイドストリーム](../c-runtime-library/byte-and-wide-streams.md)に対するさまざまな制限があります。

ファイルポインター `fp` が null ポインターの場合、関数は失敗します。 それ以外の場合は、を呼び出してストリームの位置を変更しようと `fseek(fp, _Off, _Way)` します。 関数が成功し、結果として得られる位置がを `fposn` 呼び出すことによって判断できる場合 `fgetpos(fp, &fposn)` 、関数は成功します。 関数が成功した場合は、を含む型の値を返し `pos_type` `fposn` ます。 それ以外の場合は、無効なストリームの位置が返されます。

## <a name="basic_filebufseekpos"></a><a name="seekpos"></a>basic_filebuf:: seekpos

制御されているストリームの現在の位置を変更しようと試みます。

```cpp
virtual pos_type seekpos(
    pos_type _Sp,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*_Sp*\
シークする位置。

*_Which*\
ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。

### <a name="return-value"></a>戻り値

ファイルポインター `fp` が null ポインターの場合、関数は失敗します。 それ以外の場合は、を呼び出してストリームの位置を変更しようと `fsetpos(fp, &fposn)` `fposn` `fpos_t` します。ここで、はに格納されているオブジェクト `pos` です。 その関数が成功すると、関数は `pos` を返します。 それ以外の場合は、無効なストリームの位置が返されます。 ストリームの位置が無効であることを確認するには、戻り値と `pos_type(off_type(-1))` を比較します。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、制御されたストリームの現在位置を変更しようとします。 クラスのオブジェクトの場合 [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>` 、ストリームの位置は、型のオブジェクトで表すことができ `fpos_t` ます。これには、オフセットとワイドストリームを解析するために必要なすべての状態情報が格納されます。 オフセット0は、ストリームの最初の要素を参照します。 (型 `pos_type` のオブジェクトは、少なくとも `fpos_t` オブジェクトを格納します)。

読み取りと書き込みのために開かれたファイルの場合、入力と出力の両方のストリームが直列に配置されます。 挿入と抽出を切り替えるには、またはを呼び出す必要があり [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) ます。 `pubseekoff`(およびへ `seekoff` の) の呼び出しには、テキストストリーム、バイナリストリーム、およびワイドストリームに対するさまざまな制限があります。

ワイド ストリームの場合、ストリームが開いてから、または `streampos` への最後の呼び出し以降に挿入が発生した場合、関数は [overflow](#overflow) を呼び出します。 また、必要に応じて、ファイル変換ファセットを使用してを呼び出すことにより、初期の変換状態を復元するために必要なシーケンスを挿入し `fac` `fac.unshift` ます。 型の生成された各要素 `byte` **`char`** は、 `fp` フォームの連続する呼び出しの場合と同様に、ファイルポインターによって指定された関連するストリームに書き込まれ `fputc(byte, fp)` ます。 またはの書き込みに失敗した場合 `fac.unshift` 、関数は成功しません。

## <a name="basic_filebufsetbuf"></a><a name="setbuf"></a>basic_filebuf:: setbuf

各派生ストリーム バッファーに固有の操作を実行します。

```cpp
virtual basic_streambuf<Char_T, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>パラメーター

*_Buffer*\
バッファーへのポインター。

*数*\
バッファーのサイズ。

### <a name="return-value"></a>戻り値

プロテクト メンバー関数は、ファイル ポインター `fp` が Null ポインターの場合に、0 を返します。

### <a name="remarks"></a>解説

`setbuf`を呼び出すと、 `setvbuf( fp, (char*) _Buffer, _IOFBF, count * sizeof( Char_T))` `count` *_Buffer*で始まる要素の配列がストリームのバッファーとして提供されます。 その関数がゼロ以外の値を返す場合、関数は Null ポインターを返します。 それ以外の場合は、 **`this`** signal success に戻ります。

## <a name="basic_filebufswap"></a><a name="swap"></a>basic_filebuf:: swap

この `basic_filebuf` の内容を、指定された `basic_filebuf` の内容と交換します。

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
別のへの左辺値参照 `basic_filebuf` 。

## <a name="basic_filebufsync"></a><a name="sync"></a>basic_filebuf:: sync

制御されているストリームと、関連付けられている外部ストリームとを同期しようと試みます。

```cpp
virtual int sync();
```

### <a name="return-value"></a>戻り値

ファイルポインターが null ポインターの場合は0を返し `fp` ます。 それ以外の場合は、を呼び出しても[オーバーフロー](#overflow)が発生し、 `fflush(fp)` 保留中の出力がストリームにフラッシュされた場合にのみ、0を返します。

## <a name="basic_filebuftraits_type"></a><a name="traits_type"></a>basic_filebuf:: traits_type

型名を `Tr` テンプレート パラメーターに関連付けます。

```cpp
typedef Tr traits_type;
```

## <a name="basic_filebufunderflow"></a><a name="underflow"></a>basic_filebuf:: アンダーフロー

入力ストリームから現在の要素を抽出します。

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>戻り値

関数が成功しなかった場合は、を返し `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof) ます。 それ以外の場合は、「 `ch` 解説」の説明に従って変換されたを返します。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、入力ストリームから現在の要素を抽出 `ch` し、要素をとして返し `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(ch)` ます。 これはさまざまな方法で行うことができます。

- 読み取り位置が使用可能な場合は、 `ch` 読み取り位置に格納されている要素としてを受け取り、入力バッファーの次のポインターを進めます。

- このメソッドは、フォームの連続した呼び出しでのように、型の1つ以上の要素を読み取り、必要に応じ **`char`** `fgetc(fp)` `ch` `Char_T` てファイル変換ファセットを使用してを型の要素に変換し `fac` `fac.in` ます。 任意の読み取りまたは変換が失敗すると、関数は失敗します。

## <a name="see-also"></a>関連項目

[\<fstream>](../standard-library/fstream.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
