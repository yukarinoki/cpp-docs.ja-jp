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
ms.openlocfilehash: 35bed08f2495c971df7f79f62e32b3ff68dfb3d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376881"
---
# <a name="basic_filebuf-class"></a>basic_filebuf クラス

外部ファイルに格納されている一連の要素との間で文字の特徴が決定される*Char_T型*の要素*Tr*の転送を制御するストリーム バッファーを記述します。

## <a name="syntax"></a>構文

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_filebuf : public basic_streambuf<Char_T, Tr>
```

### <a name="parameters"></a>パラメーター

*Char_T*\
ファイル バッファーの基本要素。

*Tr*\
ファイル バッファの基本要素の特性 (通常`char_traits<Char_T>`)

## <a name="remarks"></a>解説

クラス テンプレートは、Char_T*型の*要素の転送を制御するストリーム バッファーを表します。 *Tr*

> [!NOTE]
> 型`basic_filebuf`のオブジェクトは、*型パラメーター*Char_T で指定された値に`char_type`関係なく __、 char\*__ 型の内部バッファーを使用して作成されます。 つまり、Unicode 文字列 **(wchar_t**文字を含む) は、内部バッファに書き込まれる前に **、(文字を**含む) ANSI 文字列に変換されます。 Unicode 文字列をバッファに格納するには **、wchar_t**型の新しいバッファを作成し、[`basic_streambuf::pubsetbuf`](../standard-library/basic-streambuf-class.md#pubsetbuf)`()`メソッドを使用して設定します。 この動作を示す例については、以降のセクションを参照してください。

クラス`basic_filebuf<Char_T, Tr>`のオブジェクトは、開いているファイルに関連付けられたストリーム`FILE`を制御するオブジェクトを指定するファイル ポインタを格納します。 さらに、プロテクト メンバー関数である [overflow](#overflow) と [underflow](#underflow) で使用される 2 つのファイル変換ファセットへのポインターも格納します。 詳細については、「」を[`basic_filebuf::open`](#open)参照してください。

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

|Constructor|説明|
|-|-|
|[basic_filebuf](#basic_filebuf)|`basic_filebuf` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[char_type](#char_type)|型名を `Char_T` テンプレート パラメーターに関連付けます。|
|[int_type](#int_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[off_type](#off_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[pos_type](#pos_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[traits_type](#traits_type)|型名を `Tr` テンプレート パラメーターに関連付けます。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[閉じる](#close)|ファイルを閉じます。|
|[is_open](#is_open)|ファイルが開いているかどうかを示します。|
|[open](#open)|ファイルを開きます。|
|[オーバーフロー](#overflow)|いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。|
|[pbackfail](#pbackfail)|プロテクト仮想メンバー関数が要素を入力ストリームに戻そうと試み、その要素を現在の要素に (次のポインターによって指されるように) します。|
|[seekoff](#seekoff)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|
|[seekpos](#seekpos)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|
|[setbuf](#setbuf)|プロテクト仮想メンバー関数が、各派生ストリーム バッファーに固有の操作を実行します。|
|[スワップ](#swap)|この `basic_filebuf` の内容を、指定された `basic_filebuf` パラメーターの内容と交換します。|
|[同期](#sync)|プロテクト仮想関数が、制御されているストリームと、関連付けられている外部ストリームとを同期しようと試みます。|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|
|[アンダー フロー](#underflow)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<fstream>

**名前空間:** std

## <a name="basic_filebufbasic_filebuf"></a><a name="basic_filebuf"></a>basic_filebuf::basic_filebuf

`basic_filebuf` 型のオブジェクトを構築します。

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>解説

最初のコンストラクターは、入力バッファーと出力バッファーを制御するすべてのポインターに Null ポインターを格納します。 また、ファイル ポインターにも Null ポインターを格納します。

2 番目のコンストラクターは、右辺値参照として扱われる*right*の内容でオブジェクトを初期化します。

## <a name="basic_filebufchar_type"></a><a name="char_type"></a>basic_filebuf::char_type

型名を `Char_T` テンプレート パラメーターに関連付けます。

```cpp
typedef Char_T char_type;
```

## <a name="basic_filebufclose"></a><a name="close"></a>basic_filebuf::閉じる

ファイルを閉じます。

```cpp
basic_filebuf<Char_T, Tr> *close();
```

### <a name="return-value"></a>戻り値

メンバー関数は、ファイル ポインターが Null ポインターの場合に、Null ポインターを返します。

### <a name="remarks"></a>解説

`close` は `fclose(fp)` を呼び出します。 その関数がゼロ以外の値を返す場合、関数は Null ポインターを返します。 それ以外の場合は、**this** を返してファイルが正常に閉じられたことを示します。

ワイド ストリームの場合、ストリームが開かれてから、または最後に`streampos`呼び出された後に挿入が行われた場合[`overflow`](#overflow)、関数は を呼び出します。 また、ファイル変換ファセット`fac`を使用して必要に応じて呼び出`fac.unshift`すことによって、初期変換状態を復元するために必要なシーケンスも挿入します。 char 型`byte`の各**char**生成要素は、form`fputc(byte, fp)`の連続した呼び出し`fp`と同様に、ファイル ポインタによって指定された関連ストリームに書き込まれます。 呼び出し`fac.unshift`または書き込みが失敗した場合、関数は成功しません。

### <a name="example"></a>例

次のサンプルでは、現在のディレクトリ*basic_filebuf_close.txt* (内容は "テスト") と*iotest.txt* (内容は "ssss") の 2 つのファイルを想定しています。

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

## <a name="basic_filebufint_type"></a><a name="int_type"></a>basic_filebuf::int_type

スコープ内`basic_filebuf`のこの型は、スコープ内の同じ名前の型`Tr`と同じものにします。

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_filebufis_open"></a><a name="is_open"></a>basic_filebuf::is_open

ファイルが開いているかどうかを示します。

```cpp
bool is_open() const;
```

### <a name="return-value"></a>戻り値

ファイル ポインタが null でない場合は**true。**

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

## <a name="basic_filebufoff_type"></a><a name="off_type"></a>basic_filebuf::off_type

スコープ内`basic_filebuf`のこの型は、スコープ内の同じ名前の型`Tr`と同じものにします。

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_filebufopen"></a><a name="open"></a>basic_filebuf::オープン

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

*Filename*\
開くファイルの名前。

*モード*\
の列挙の 1[`ios_base::openmode`](../standard-library/ios-base-class.md#openmode)つ。

*保護*\
既定のファイルを開く保護は、_fsopenの*shflag*パラメーターと同等[_wfsopen。](../c-runtime-library/reference/fsopen-wfsopen.md)

### <a name="return-value"></a>戻り値

バッファーが既にオープンされている場合、またはファイル ポインターが null ポインターの場合、関数は null ポインターを返します。 それ以外の場合は、**this** を返します。

### <a name="remarks"></a>解説

メンバー関数は、 を呼び*filename*出[`fopen`](../c-runtime-library/reference/fopen-wfopen.md)`(filename, strmode)`してファイル名 filename を使用して開きます。 `strmode`はから決定`mode & ~(`[`ate`](../standard-library/ios-base-class.md#openmode)`|`[`binary`](../standard-library/ios-base-class.md#openmode)`)`されます。

- `ios_base::in`(`"r"`読み取り用に既存のファイルを開く)

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) `ios_base::out | ios_base::trunc`または`"w"`なり (既存のファイルを切り捨てるか、書き込みのために作成します)。

- `ios_base::out | app`(`"a"`すべての書き込みを追加するために既存のファイルを開く)。

- `ios_base::in | ios_base::out`(`"r+"`読み取りと書き込み用に既存のファイルを開く)

- `ios_base::in | ios_base::out | ios_base::trunc`(`"w+"`既存のファイルを切り捨てるか、読み取りと書き込みのために作成します)。

- `ios_base::in | ios_base::out | ios_base::app`(`"a+"`読み取り用とすべての書き込みを追加するために既存のファイルを開く)

0`mode & ios_base::binary`以外の場合、関数は、`b`テキスト`strmode`ストリームではなくバイナリ ストリームを開くために追加します。 次に、ファイル ポインタ`fopen``fp`に返された値を格納します。 0`mode & ios_base::ate`以外の場合、ファイル ポインターが null ポインターでない場合、関数`fseek(fp, 0, SEEK_END)`はストリームをファイルの末尾に配置する関数を呼び出します。 その位置決め操作が失敗した場合、[`close`](#close)`(fp)`関数は null ポインターを呼び出し、ファイル ポインターに格納します。

ファイル ポインタが null ポインタ`use_facet<codecvt<Char_T, char, traits_type::`[`state_type`](../standard-library/char-traits-struct.md#state_type)`> >(`[`getloc`](../standard-library/basic-streambuf-class.md#getloc)`)`でない場合、アンダー[フロー](#underflow)と[オーバーフロー](#overflow)で使用するファイル変換ファセット: が関数によって決定されます。

ファイル ポインターが Null ポインターの場合、関数は Null ポインターを返します。 それ以外の場合は、**this** を返します。

### <a name="example"></a>例

を[`basic_filebuf::close`](#close)使用する例については、「 `open`」を参照してください。

## <a name="basic_filebufoperator"></a><a name="op_eq"></a>basic_filebuf::演算子=

このストリーム バッファー オブジェクトの内容を割り当てます。 これは、コピーを残さない右辺値を含む移動代入です。

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
[basic_filebuf](../standard-library/basic-filebuf-class.md) オブジェクトへの右辺値参照。

### <a name="return-value"></a>戻り値

__*this__を返します。

### <a name="remarks"></a>解説

member 演算子は、右辺値参照として扱われる*right*の内容を使用して、オブジェクトの内容を置き換えます。 詳細については、「[右辺値参照宣言子: &&」](../cpp/rvalue-reference-declarator-amp-amp.md)を参照してください。

## <a name="basic_filebufoverflow"></a><a name="overflow"></a>basic_filebuf::オーバーフロー

いっぱいのバッファーに新しい文字が挿入されたときに呼び出されます。

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>パラメーター

*_Meta*\
バッファーに挿入する文字または`traits_type::eof`.

### <a name="return-value"></a>戻り値

関数が成功しない場合は、 を返`traits_type::eof`します。 それ以外の場合`traits_type::`[`not_eof`](../standard-library/char-traits-struct.md#not_eof)`(_Meta)`は、 を返します。

### <a name="remarks"></a>解説

場合`_Meta != traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof)、プロテクト仮想メンバー関数は、出力バッファーに要素`ch = traits_type::`[`to_char_type`](../standard-library/char-traits-struct.md#to_char_type)`(_Meta)`を挿入しようとします。 これはさまざまな方法で行うことができます。

- 書き込み位置が使用可能な場合は、書き込み位置に要素を格納し、出力バッファーの次のポインターをインクリメントできます。

- 新しい記憶域または追加の記憶域を出力バッファーに割り当てることで、書き込み位置を使用可能にすることができます。

- 必要に応`ch``fac``fac.out`じてファイル変換ファセットを使用して、出力バッファ内の任意の保留中の出力を変換できます。 char 型`ch`の各*char*生成要素は、form`fputc(ch, fp)`の連続した呼び出し`fp`と同様に、ファイル ポインタによって指定された関連ストリームに書き込まれます。 任意の変換または書き込みに失敗した場合、関数は失敗します。

## <a name="basic_filebufpbackfail"></a><a name="pbackfail"></a>basic_filebuf::pバックフェイル

要素を入力ストリームに戻そうと試み、その要素を現在の要素に (ネクスト ポインターによって指されるように) します。

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>パラメーター

*_Meta*\
バッファーに挿入する文字または `traits_type::eof`。

### <a name="return-value"></a>戻り値

関数が成功しない場合は、 を返`traits_type::eof`します。 それ以外の場合`traits_type::`[`not_eof`](../standard-library/char-traits-struct.md#not_eof)`(_Meta)`は、 を返します。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は要素を入力バッファーに戻してから、その要素を現在の要素に (ネクスト ポインターによって指されるように) します。 の`_Meta == traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof)場合、プッシュ バックする要素は、実質的に現在の要素の前に既にストリーム内にある要素です。 それ以外の場合、その要素`ch = traits_type::`[`to_char_type`](../standard-library/char-traits-struct.md#to_char_type)`(_Meta)`は に置き換えられます。 この関数は、さまざまな方法で要素を戻すことができます。

- 位置が`putback`使用可能で、そこに格納されている要素が`ch`と等しい場合、入力バッファーの次のポインターを減らすことができます。

- 関数がポジションを`putback`使用可能にできる場合は、その位置を指す次のポインタを設定し、その位置に格納`ch`します。

- 関数が要素を入力ストリームにプッシュバックできる場合は`ungetc`**、char**型の要素を呼び出すなどで行うことができます。

## <a name="basic_filebufpos_type"></a><a name="pos_type"></a>basic_filebuf::pos_type

スコープ内`basic_filebuf`のこの型は、スコープ内の同じ名前の型`Tr`と同じものにします。

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_filebufseekoff"></a><a name="seekoff"></a>basic_filebuf:シークオフ

制御されているストリームの現在の位置を変更しようと試みます。

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*_Off*\
*_Way*に対して相対的に求める位置。

*_Way*\
オフセット演算の開始位置。 有効値については、「[seekdir](../standard-library/ios-base-class.md#seekdir)」を参照してください。

*_Which*\
ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。

### <a name="return-value"></a>戻り値

新しい位置または無効なストリーム位置を返します。

### <a name="remarks"></a>解説

保護された仮想メンバー関数は、制御されたストリームの現在位置を変更しようとします。 class[`basic_filebuf`](../standard-library/basic-filebuf-class.md)`<Char_T, Tr>`のオブジェクトの場合、ストリーム位置は、幅の広いストリームを`fpos_t`解析するために必要なオフセットと状態情報を格納する type のオブジェクトによって表すことができます。 オフセットゼロは、ストリームの最初の要素を参照します。 (型[`pos_type`](../standard-library/basic-streambuf-class.md#pos_type)のオブジェクトは、少なくとも`fpos_t`1 つのオブジェクトを格納します。

読み取りと書き込みのために開かれたファイルの場合、入力と出力の両方のストリームが直列に配置されます。 挿入と抽出を切り替えるには、[`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff)または[`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)を呼び出す必要があります。 `pubseekoff`への呼び出しは`seekoff`[、テキスト ストリーム](../c-runtime-library/text-and-binary-streams.md)、[バイナリ ストリーム](../c-runtime-library/text-and-binary-streams.md)、ワイド[ストリーム](../c-runtime-library/byte-and-wide-streams.md)に対してさまざまな制限があります。

ファイル ポインタ`fp`が null ポインタの場合、関数は失敗します。 それ以外の場合は、 を呼び出`fseek(fp, _Off, _Way)`してストリームの位置を変更しようとします。 その関数が成功し、結果の位置`fposn`を呼び出`fgetpos(fp, &fposn)`すことによって決定できる場合、関数は成功します。 関数が成功すると、 を含む`pos_type``fposn`型の値が返されます。 それ以外の場合は、無効なストリームの位置が返されます。

## <a name="basic_filebufseekpos"></a><a name="seekpos"></a>basic_filebuf::シーポス

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

ファイル ポインタ`fp`が null ポインタの場合、関数は失敗します。 それ以外の場合は、 に格納されているオブジェクトを`fsetpos(fp, &fposn)`呼び`fposn`出すことによって`fpos_t`、ストリームの`pos`位置を変更しようとします。 その関数が成功すると、関数は `pos` を返します。 それ以外の場合は、無効なストリームの位置が返されます。 ストリームの位置が無効であることを確認するには、戻り値と `pos_type(off_type(-1))` を比較します。

### <a name="remarks"></a>解説

保護された仮想メンバー関数は、制御されたストリームの現在位置を変更しようとします。 class[`basic_filebuf`](../standard-library/basic-filebuf-class.md)`<Char_T, Tr>`のオブジェクトの場合、ストリーム位置は、幅の広いストリームを`fpos_t`解析するために必要なオフセットと状態情報を格納する type のオブジェクトによって表すことができます。 オフセットゼロは、ストリームの最初の要素を参照します。 (型 `pos_type` のオブジェクトは、少なくとも `fpos_t` オブジェクトを格納します)。

読み取りと書き込みのために開かれたファイルの場合、入力と出力の両方のストリームが直列に配置されます。 挿入と抽出を切り替えるには、[`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff)または[`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)を呼び出す必要があります。 `pubseekoff`への呼び出し`seekoff`には、テキスト ストリーム、バイナリ ストリーム、ワイド ストリームに対してさまざまな制限があります。

ワイド ストリームの場合、ストリームが開いてから、または `streampos` への最後の呼び出し以降に挿入が発生した場合、関数は [overflow](#overflow) を呼び出します。 また、ファイル変換ファセット`fac`を使用して必要に応じて呼び出`fac.unshift`すことによって、初期変換状態を復元するために必要なシーケンスも挿入します。 char 型`byte`の各**char**生成要素は、form`fputc(byte, fp)`の連続した呼び出し`fp`と同様に、ファイル ポインタによって指定された関連ストリームに書き込まれます。 呼び出し`fac.unshift`または書き込みが失敗した場合、関数は成功しません。

## <a name="basic_filebufsetbuf"></a><a name="setbuf"></a>basic_filebuf::セッターブフ

各派生ストリーム バッファーに固有の操作を実行します。

```cpp
virtual basic_streambuf<Char_T, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>パラメーター

*_Buffer*\
バッファーへのポインター。

*カウント*\
バッファーのサイズ。

### <a name="return-value"></a>戻り値

プロテクト メンバー関数は、ファイル ポインター `fp` が Null ポインターの場合に、0 を返します。

### <a name="remarks"></a>解説

`setbuf`_Buffer`setvbuf( fp, (char*) _Buffer, _IOFBF, count * sizeof( Char_T))`から始まる要素の`count`配列をストリームの*バッファーとして提供*する呼び出し。 その関数がゼロ以外の値を返す場合、関数は Null ポインターを返します。 それ以外の場合は、シグナルの成功に **this** を返します。

## <a name="basic_filebufswap"></a><a name="swap"></a>basic_filebuf::スワップ

この `basic_filebuf` の内容を、指定された `basic_filebuf` の内容と交換します。

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
別`basic_filebuf`の値への参照。

## <a name="basic_filebufsync"></a><a name="sync"></a>basic_filebuf::同期

制御されているストリームと、関連付けられている外部ストリームとを同期しようと試みます。

```cpp
virtual int sync();
```

### <a name="return-value"></a>戻り値

ファイル ポインタが null`fp`ポインタの場合は 0 を返します。 それ以外の場合は、[オーバーフロー](#overflow)と`fflush(fp)`ストリームへの保留中の出力のフラッシュに成功した場合にのみゼロを返します。

## <a name="basic_filebuftraits_type"></a><a name="traits_type"></a>basic_filebuf::traits_type

型名を `Tr` テンプレート パラメーターに関連付けます。

```cpp
typedef Tr traits_type;
```

## <a name="basic_filebufunderflow"></a><a name="underflow"></a>basic_filebuf::アンダーフロー

入力ストリームから現在の要素を抽出します。

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>戻り値

関数が成功しない場合は、 を返`traits_type::`[`eof`](../standard-library/char-traits-struct.md#eof)します。 それ以外の場合`ch`は、「解説」セクションの説明に従って変換された を返します。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、入力ストリームから現在の`ch`要素を抽出し、要素`traits_type::`[`to_int_type`](../standard-library/char-traits-struct.md#to_int_type)`(ch)`を として返そうとします。 これはさまざまな方法で行うことができます。

- 読み取り位置が使用可能な場合`ch`は、読み取り位置に格納されている要素として受け取り、入力バッファーの次のポインターを進めます。

- フォーム`fgetc(fp)`の連続した呼び出しと**同様に**char 型の 1 つ以上の要素`fac`を読み`ch`取り`Char_T`、必要に応じてファイル`fac.in`変換ファセットを使用して、それらを型の要素に変換できます。 任意の読み取りまたは変換が失敗すると、関数は失敗します。

## <a name="see-also"></a>関連項目

[\<フストリーム>](../standard-library/fstream.md)\
[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
