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
ms.openlocfilehash: f162545f28af3e2720dceace6c604b5e2441cf48
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690020"
---
# <a name="basic_filebuf-class"></a>basic_filebuf クラス

文字の特徴がクラス*Tr*によって決定される*Elem*型の要素の転送を、外部ファイルに格納されている要素のシーケンスとの間で制御するストリームバッファーを記述します。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_filebuf : public basic_streambuf<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Elem* \
ファイル バッファーの基本要素。

*Tr* \
ファイル バッファーの基本要素の特徴 (通常は `char_traits`< `Elem`>)。

## <a name="remarks"></a>Remarks

クラステンプレートは、Elem 型の要素の転送を制御するストリームバッファーを記述します。 *Elem*型は、文字の特徴が*Tr*クラスによって決定され、外部ファイルに格納されている要素のシーケンスとの間で送受信されます。

> [!NOTE]
> @No__t_0 型のオブジェクトは、型パラメーター *Elem*によって指定された `char_type` に関係なく、`char *` 型の内部バッファーを使用して作成されます。 これは、内部バッファーに書き込まれる前に、Unicode 文字列 ( **wchar_t**文字を含む) が ANSI 文字列 ( **char**文字を含む) に変換されることを意味します。 Unicode 文字列をバッファーに格納するには、 **wchar_t**型の新しいバッファーを作成し、 [basic_streambuf::p ubsetbuf](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` メソッドを使用して設定します。 この動作を示す例については、以降のセクションを参照してください。

`basic_filebuf`< `Elem`, `Tr`> クラスのオブジェクトは、開いているファイルに関連付けられているストリームを制御する `FILE` オブジェクトを示すファイル ポインターを格納します。 さらに、プロテクト メンバー関数である [overflow](#overflow) と [underflow](#underflow) で使用される 2 つのファイル変換ファセットへのポインターも格納します。 詳細については、「[basic_filebuf::open](#open)」を参照してください。

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

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[char_type](#char_type)|型名を `Elem` テンプレート パラメーターに関連付けます。|
|[int_type](#int_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[off_type](#off_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[pos_type](#pos_type)|`basic_filebuf` のスコープ内のこの型を、`Tr` スコープ内の同じ名前の型と同等にします。|
|[traits_type](#traits_type)|型名を `Tr` テンプレート パラメーターに関連付けます。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[close](#close)|ファイルを閉じます。|
|[is_open](#is_open)|ファイルが開いているかどうかを示します。|
|[open](#open)|ファイルを開きます。|
|[overflow](#overflow)|いっぱいのバッファーに新しい文字が挿入されたときに呼び出すことができる、プロテクト仮想関数。|
|[pbackfail](#pbackfail)|プロテクト仮想メンバー関数が要素を入力ストリームに戻そうと試み、その要素を現在の要素に (次のポインターによって指されるように) します。|
|[seekoff](#seekoff)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|
|[seekpos](#seekpos)|プロテクト仮想メンバー関数が、制御されているストリームの現在の位置を変更しようと試みます。|
|[setbuf](#setbuf)|プロテクト仮想メンバー関数が、各派生ストリーム バッファーに固有の操作を実行します。|
|[Swap](#swap)|この `basic_filebuf` の内容を、指定された `basic_filebuf` パラメーターの内容と交換します。|
|[sync](#sync)|プロテクト仮想関数が、制御されているストリームと、関連付けられている外部ストリームとを同期しようと試みます。|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|
|[underflow](#underflow)|入力ストリームから現在の要素を抽出するプロテクト仮想関数。|

## <a name="requirements"></a>［要件］

**ヘッダー:** \<fstream>

**名前空間:** std

## <a name="basic_filebuf"></a>  basic_filebuf::basic_filebuf

`basic_filebuf` 型のオブジェクトを構築します。

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Remarks

最初のコンストラクターは、入力バッファーと出力バッファーを制御するすべてのポインターに Null ポインターを格納します。 また、ファイル ポインターにも Null ポインターを格納します。

2 番目のコンストラクターは、右辺値参照として扱われる `right` のコンテンツでオブジェクトを初期化します。

## <a name="char_type"></a>  basic_filebuf::char_type

型名を `Elem` テンプレート パラメーターに関連付けます。

```cpp
typedef Elem char_type;
```

## <a name="close"></a>  basic_filebuf::close

ファイルを閉じます。

```cpp
basic_filebuf<Elem, Tr> *close();
```

### <a name="return-value"></a>戻り値

メンバー関数は、ファイル ポインターが Null ポインターの場合に、Null ポインターを返します。

### <a name="remarks"></a>Remarks

`close` は `fclose` ( **fp**) を呼び出します。 その関数がゼロ以外の値を返す場合、関数は Null ポインターを返します。 それ以外の場合は、**this** を返してファイルが正常に閉じられたことを示します。

ワイド ストリームの場合、ストリームが開いてから、または `streampos` への最後の呼び出し以降に挿入が発生した場合、関数は [overflow](#overflow) を呼び出します。 また、必要に応じて、ファイル変換ファセット `fac` を使用して `fac.unshift` を呼び出すことにより、初期の変換状態を復元するために必要なシーケンスを挿入します。 生成された**char**型の各要素 `byte` は、ファイルポインターによって指定された関連付けられたストリームに書き込まれます。これは、フォーム `fputc` ( **byte**, **fp**) の連続した呼び出しによって `fp` ます。 @No__t_0 または書き込みに対する呼び出しが失敗した場合、関数は成功しません。

### <a name="example"></a>例

次の例は、現在のディレクトリ内の 2 つのファイル、basic_filebuf_close.txt (コンテンツは "testing") と iotest.txt (コンテンツは "ssss") を前提としています。

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

## <a name="int_type"></a>  basic_filebuf::int_type

@No__t_0 スコープ内の同じ名前の型と等価な basic_filebuf's スコープ内で、この型を作成します。

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="is_open"></a>  basic_filebuf::is_open

ファイルが開いているかどうかを示します。

```cpp
bool is_open() const;
```

### <a name="return-value"></a>戻り値

ファイル ポインターが Null ポインターでない場合は **true**。

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

## <a name="off_type"></a>  basic_filebuf::off_type

@No__t_0 スコープ内の同じ名前の型と等価な basic_filebuf's スコープ内で、この型を作成します。

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="open"></a>  basic_filebuf::open

ファイルを開きます。

```cpp
basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const char* _Filename,
    ios_base::openmode _Mode);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode,
    int _Prot = (int)ios_base::_Openprot);

basic_filebuf<Elem, Tr> *open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>パラメーター

*ファイル名 (_d)* \
開くファイルの名前。

*_Mode* \
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) の列挙値のうちの 1 つ。

*_Prot* \
既定のファイルを開く保護。 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)の*shflag*パラメーターと同じです。

### <a name="return-value"></a>戻り値

ファイル ポインターが Null ポインターの場合、関数は Null ポインターを返します。 それ以外の場合は、**this** を返します。

### <a name="remarks"></a>Remarks

メンバー関数は、[fopen](../c-runtime-library/reference/fopen-wfopen.md)( *filename*, **strmode**) を呼び出すことで、ファイル名が *filename* のファイルを開きます。 `strmode` は、**モード &** ~ ( [ate](../standard-library/ios-base-class.md#openmode) & &#124; [バイナリ](../standard-library/ios-base-class.md#openmode)) から決定されます。

- `ios_base::in` が **"r"** になります (読み取り用に既存のファイルを開きます)。

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) または **ios_base::out &#124; ios_base::trunc** は **"w"** になります (書き込み用に既存のファイルを切り捨てるまたは作成します)。

- **ios_base::out &#124; app** は **"a"** になります (すべての書き込みを追加するために既存のファイルを開きます)。

- **ios_base::in &#124; ios_base::out** は **"r+"** になります (読み取りと書き込み用に既存のファイルを開きます)。

- **ios_base::in &#124; ios_base::out &#124; ios_base::trunc** は **"w+"** になります (読み取りと書き込み用に既存のファイルを切り捨てるまたは作成します)。

- **ios_base::in &#124; ios_base::out &#124; ios_base::app** は **"a+"** になります (読み取りと用とすべての書き込みを追加するために既存のファイルを開きます)。

**Mode & ios_base:: binary**が0以外の場合、関数は `strmode` に `b` を追加して、テキストストリームではなくバイナリストリームを開きます。 次に、`fopen` によって返された値をファイルポインター `fp` に格納します。 **mode & ios_base::ate** が 0 以外の値で、ファイル ポインターがNull ポインターでない場合、関数は `fseek`( **fp**, 0, `SEEK_END`) を呼び出してファイルの終端にストリームを配置します。 この位置指定操作が失敗した場合、関数は[close](#close)(`fp`) を呼び出し、ファイルポインターに null ポインターを格納します。

ファイル ポインターが Null ポインターでない場合、関数は[underflow](#underflow) と [overflow](#overflow) で使用するために、ファイル変換ファセット `use_facet`< `codecvt`< **Elem**, `char`, **traits_type::** [state_type](../standard-library/char-traits-struct.md#state_type)> >( [getloc](../standard-library/basic-streambuf-class.md#getloc)) を決定します。

ファイル ポインターが Null ポインターの場合、関数は Null ポインターを返します。 それ以外の場合は、**this** を返します。

### <a name="example"></a>例

`open` の使用例については、「[basic_filebuf::close](#close)」を参照してください。

## <a name="op_eq"></a>  basic_filebuf::operator=

このストリーム バッファー オブジェクトの内容を割り当てます。 これは、右辺値が関係する移動代入で、コピーを残しません。

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>パラメーター

*右*\
[basic_filebuf](../standard-library/basic-filebuf-class.md) オブジェクトへの右辺値参照。

### <a name="return-value"></a>戻り値

*this を返します。

### <a name="remarks"></a>Remarks

メンバー演算子は、右辺値参照として扱われる*right*の内容を使用して、オブジェクトの内容を置き換えます。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

## <a name="overflow"></a>  basic_filebuf::overflow

いっぱいのバッファーに新しい文字が挿入されたときに呼び出されます。

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>パラメーター

*メタ \ (_s)*
バッファーまたは `traits_type::eof` に挿入する文字。

### <a name="return-value"></a>戻り値

関数が成功しない場合は、`traits_type::eof` が返されます。 それ以外の場合は、**traits_type::** [not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) を返します。

### <a name="remarks"></a>Remarks

**Traits_type::** [eof](../standard-library/char-traits-struct.md#eof)の場合、プロテクト仮想メンバー*関数は、* 要素**ch = traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type) *()* を出力バッファーに挿入しようとします。 これはさまざまな方法で行うことができます。

- 書き込み位置が使用可能な場合は、書き込み位置に要素を格納し、出力バッファーのネクスト ポインターをインクリメントできます。

- 新しい記憶域または追加の記憶域を出力バッファーに割り当てることで、書き込み位置を使用可能にすることができます。

- 必要に応じて、ファイル変換ファセット `fac` を使用して `fac.out` を呼び出すことで、出力バッファー内の保留中の出力を変換した後、`ch` を変換できます。 生成された*char*型の各要素 `ch` は、ファイルポインターによって指定された関連付けられたストリームに書き込まれます。これは、フォーム `fputc` ( **ch**, **fp**) の連続した呼び出しによって `fp` ます。 任意の変換または書き込みに失敗した場合、関数は失敗します。

## <a name="pbackfail"></a>  basic_filebuf::pbackfail

要素を入力ストリームに戻そうと試み、その要素を現在の要素に (ネクスト ポインターによって指されるように) します。

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>パラメーター

*メタ \ (_s)*
バッファーに挿入する文字または `traits_type::eof`。

### <a name="return-value"></a>戻り値

関数が成功しない場合は、`traits_type::eof` が返されます。 それ以外の場合は、 **traits_type::** [not_eof](../standard-library/char-traits-struct.md#not_eof)( *\_Meta*) を返します。

### <a name="remarks"></a>Remarks

プロテクト仮想メンバー関数は要素を入力バッファーに戻してから、その要素を現在の要素に (ネクスト ポインターによって指されるように) します。 *@No__t_1Meta* **= = traits_type::** [eof](../standard-library/char-traits-struct.md#eof)の場合、プッシュバックする要素は、実際には、現在の要素の前に既にストリームにある要素です。 それ以外の場合、その要素は**ch = traits_type::** [to_char_type](../standard-library/char-traits-struct.md#to_char_type)( *\_Meta*) に置き換えられます。 この関数は、さまざまな方法で要素を戻すことができます。

- 戻り位置が使用可能であり、格納されている要素が `ch` と等しい場合、入力バッファーの次のポインターをデクリメントできます。

- 関数で `putback` 位置を使用できるようにする場合は、その位置を指すように次のポインターを設定し、その位置に `ch` を格納することができます。

- 関数が要素を入力ストリームにプッシュバックできる場合、 **char**型の要素に対して `ungetc` を呼び出すことによって、この処理を実行できます。

## <a name="pos_type"></a>  basic_filebuf::pos_type

@No__t_0 スコープ内の同じ名前の型と等価な basic_filebuf's スコープ内で、この型を作成します。

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="seekoff"></a>  basic_filebuf::seekoff

制御されているストリームの現在の位置を変更しようと試みます。

```cpp
virtual pos_type seekoff(off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*オフ \ (_r)*
に対して相対的にシークする*位置。*

@No__t_1*方法 (_d)*
オフセット演算の開始位置。 有効値については、「[seekdir](../standard-library/ios-base-class.md#seekdir)」を参照してください。

*@No__t_1*
ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。

### <a name="return-value"></a>戻り値

新しい位置または無効なストリーム位置を返します。

### <a name="remarks"></a>Remarks

プロテクト仮想メンバー関数が、制御対象ストリームの現在の位置を変更しようと試みます。 クラス [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> のオブジェクトの場合、ストリームの位置は、型 `fpos_t` のオブジェクトで表現できます。これにはオフセットとワイド ストリームを解析するために必要なすべての状態情報が格納されます。 オフセット ゼロは、ストリームの最初の要素を指定します (型 [pos_type](../standard-library/basic-streambuf-class.md#pos_type) のオブジェクトは、少なくとも `fpos_t` オブジェクトを格納します)。

読み取りと書き込みのために開かれたファイルの場合、入力と出力の両方のストリームが直列に配置されます。 挿入と抽出を切り替えるには、[pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) または [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos) のいずれかを呼び出す必要があります。 `pubseekoff` (および `seekoff`) への呼び出しには、[テキスト ストリーム](../c-runtime-library/text-and-binary-streams.md)、[バイナリ ストリーム](../c-runtime-library/text-and-binary-streams.md)、および[ワイド ストリーム](../c-runtime-library/byte-and-wide-streams.md) に対するさまざまな制限があります。

@No__t_0 ファイルポインターが null ポインターの場合、関数は失敗します。 それ以外の場合、関数は `fseek`( **fp**, `_Off`, `_Way`) を呼び出してストリームの位置を変更しようとします。 その関数が成功し、結果の位置 `fposn` が `fgetpos` ( **fp**、 **& fposn**) を呼び出すことによって判断できる場合、関数は成功します。 関数が成功した場合は、`fposn` を含む `pos_type` 型の値を返します。 それ以外の場合は、無効なストリームの位置が返されます。

## <a name="seekpos"></a>  basic_filebuf::seekpos

制御されているストリームの現在の位置を変更しようと試みます。

```cpp
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>パラメーター

*Sp \ (_s)*
シークする位置。

*@No__t_1*
ポインター位置のモードを指定します。 既定では、読み取り位置および書き込み位置を変更できます。

### <a name="return-value"></a>戻り値

@No__t_0 ファイルポインターが null ポインターの場合、関数は失敗します。 それ以外の場合は、`fsetpos` ( **fp**、 **& fposn**) を呼び出すことによってストリームの位置を変更しようとします。 `fposn` は `pos` に格納されている `fpos_t` のオブジェクトです。 その関数が成功すると、関数は `pos` を返します。 それ以外の場合は、無効なストリームの位置が返されます。 ストリームの位置が無効であることを確認するには、戻り値と `pos_type(off_type(-1))` を比較します。

### <a name="remarks"></a>Remarks

プロテクト仮想メンバー関数が、制御対象ストリームの現在の位置を変更しようと試みます。 クラス [basic_filebuf](../standard-library/basic-filebuf-class.md)\< **Elem**, **Tr**> のオブジェクトの場合、ストリームの位置は、型 `fpos_t` のオブジェクトで表現できます。これにはオフセットとワイド ストリームを解析するために必要なすべての状態情報が格納されます。 オフセット ゼロは、ストリームの最初の要素を指定します (型 `pos_type` のオブジェクトは、少なくとも `fpos_t` オブジェクトを格納します)。

読み取りと書き込みのために開かれたファイルの場合、入力と出力の両方のストリームが直列に配置されます。 挿入と抽出を切り替えるには、[pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff) または [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos) のいずれかを呼び出す必要があります。 `pubseekoff` (および `seekoff`) への呼び出しには、テキスト ストリーム、バイナリ ストリーム、およびワイド ストリームに対するさまざまな制限があります。

ワイド ストリームの場合、ストリームが開いてから、または `streampos` への最後の呼び出し以降に挿入が発生した場合、関数は [overflow](#overflow) を呼び出します。 また、必要に応じて、ファイル変換ファセット `fac` を使用して**fac.** `.unshift` を呼び出すことにより、初期の変換状態を復元するために必要なシーケンスを挿入します。 生成された**char**型の各要素 `byte` は、ファイルポインターによって指定された関連付けられたストリームに書き込まれます。これは、フォーム `fputc` ( **byte**, **fp**) の連続した呼び出しによって `fp` ます。 @No__t_0 または書き込みに対する呼び出しが失敗した場合、関数は成功しません。

## <a name="setbuf"></a>  basic_filebuf::setbuf

各派生ストリーム バッファーに固有の操作を実行します。

```cpp
virtual basic_streambuf<Elem, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>パラメーター

*バッファーの \ (_l)*
バッファーへのポインター。

*カウント*\
バッファーのサイズ。

### <a name="return-value"></a>戻り値

プロテクト メンバー関数は、ファイル ポインター `fp` が Null ポインターの場合に、0 を返します。

### <a name="remarks"></a>Remarks

`setbuf` は `setvbuf`( **fp**, ( `char`\*) `_Buffer`, `_IOFBF`, `count`\*`sizeof` ( **Elem**) ) を呼び出して、_ *Buffer* で始まる `count` 要素の配列をストリームのバッファーとして提供します。 その関数がゼロ以外の値を返す場合、関数は Null ポインターを返します。 それ以外の場合は、シグナルの成功に **this** を返します。

## <a name="swap"></a>  basic_filebuf::swap

この `basic_filebuf` の内容を、指定された `basic_filebuf` の内容と交換します。

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>パラメーター

*右*\
別の `basic_filebuf` への `lvalue` 参照。

## <a name="sync"></a>  basic_filebuf::sync

制御されているストリームと、関連付けられている外部ストリームとを同期しようと試みます。

```cpp
virtual int sync();
```

### <a name="return-value"></a>戻り値

@No__t_0 ファイルポインターが null ポインターの場合は0を返します。 それ以外の場合は、保留中の出力のストリームへのフラッシュで、[overflow](#overflow) と `fflush`( **fp**) の両方の呼び出しが成功した場合にのみ 0 を返します。

## <a name="traits_type"></a>  basic_filebuf::traits_type

型名を `Tr` テンプレート パラメーターに関連付けます。

```cpp
typedef Tr traits_type;
```

## <a name="underflow"></a>  basic_filebuf::underflow

入力ストリームから現在の要素を抽出します。

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>戻り値

関数が失敗すると、**traits_type::** [eof](../standard-library/char-traits-struct.md#eof) が返されます。 それ以外の場合は、「解説」の説明に従って変換された `ch` を返します。

### <a name="remarks"></a>Remarks

プロテクト仮想メンバー関数は、入力ストリームから現在の要素 `ch` を抽出し、要素を**traits_type::** [to_int_type](../standard-library/char-traits-struct.md#to_int_type)(`ch`) として返します。 これはさまざまな方法で行うことができます。

- 読み取り位置が使用可能な場合は、読み取り位置に格納されている要素として `ch` を実行し、入力バッファーの次のポインターを進めます。

- これにより、 **char**型の1つ以上の要素を読み取ることができます。これは、フォーム `fgetc` (**fp**) の連続した呼び出しの場合と同様に、ファイル変換ファセット fac. を使用して、必要に応じて `fac.in` を呼び出すことによって、型を `Elem` の要素**ch**に変換します。 任意の読み取りまたは変換が失敗すると、関数は失敗します。

## <a name="see-also"></a>関連項目

[\<fstream>](../standard-library/fstream.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
