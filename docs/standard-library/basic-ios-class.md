---
title: basic_ios クラス
ms.date: 11/04/2016
f1_keywords:
- ios/std::basic_ios
- ios/std::basic_ios::char_type
- ios/std::basic_ios::int_type
- ios/std::basic_ios::off_type
- ios/std::basic_ios::pos_type
- ios/std::basic_ios::traits_type
- ios/std::basic_ios::bad
- ios/std::basic_ios::clear
- ios/std::basic_ios::copyfmt
- ios/std::basic_ios::eof
- ios/std::basic_ios::exceptions
- ios/std::basic_ios::fail
- ios/std::basic_ios::fill
- ios/std::basic_ios::good
- ios/std::basic_ios::imbue
- ios/std::basic_ios::init
- ios/std::basic_ios::move
- ios/std::basic_ios::narrow
- ios/std::basic_ios::rdbuf
- ios/std::basic_ios::rdstate
- ios/std::basic_ios::set_rdbuf
- ios/std::basic_ios::setstate
- ios/std::basic_ios::swap
- ios/std::basic_ios::tie
- ios/std::basic_ios::widen
- ios/std::basic_ios::explicit operator bool
helpviewer_keywords:
- std::basic_ios [C++]
- std::basic_ios [C++], char_type
- std::basic_ios [C++], int_type
- std::basic_ios [C++], off_type
- std::basic_ios [C++], pos_type
- std::basic_ios [C++], traits_type
- std::basic_ios [C++], bad
- std::basic_ios [C++], clear
- std::basic_ios [C++], copyfmt
- std::basic_ios [C++], eof
- std::basic_ios [C++], exceptions
- std::basic_ios [C++], fail
- std::basic_ios [C++], fill
- std::basic_ios [C++], good
- std::basic_ios [C++], imbue
- std::basic_ios [C++], init
- std::basic_ios [C++], move
- std::basic_ios [C++], narrow
- std::basic_ios [C++], rdbuf
- std::basic_ios [C++], rdstate
- std::basic_ios [C++], set_rdbuf
- std::basic_ios [C++], setstate
- std::basic_ios [C++], swap
- std::basic_ios [C++], tie
- std::basic_ios [C++], widen
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
ms.openlocfilehash: c8f883dd4f946c03aaa22dffcf5a3164a539d041
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364921"
---
# <a name="basic_ios-class"></a>basic_ios クラス

クラス テンプレートは、(クラス テンプレート[basic_istream](../standard-library/basic-istream-class.md)) 入力ストリームと、テンプレート パラメータに依存する (クラス テンプレート[basic_ostream](../standard-library/basic-ostream-class.md)) の出力ストリームの両方に共通するストレージ関数とメンバー関数を記述します。 (クラス[ios_base](../standard-library/ios-base-class.md)は、テンプレート パラメーターに依存しない共通の内容を記述します。クラス**basic_ios\<クラス Elem のオブジェクトであるクラス Traits>は**、クラスによって`Elem`文字の特徴が決定される型の要素を`Traits`使用してストリームを制御するのに役立ちます。

## <a name="syntax"></a>構文

```cpp

template <class Elem, class Traits>
class basic_ios : public ios_base
```

### <a name="parameters"></a>パラメーター

*Elem*\
型。

*特徴*\
`char_traits` 型の変数。

## <a name="remarks"></a>解説

**basic_ios\<class Elem, class Traits>** クラスのオブジェクトは以下を格納します。

- **\<エレム、トレイト**[>basic_istream型の](../standard-library/basic-istream-class.md)オブジェクトへのタイ ポインタ。

- Elem、Traits >basic_streambuf型[の](../standard-library/basic-streambuf-class.md)オブジェクトへのストリーム バッファ ポインタ。**\< **

- [書式設定情報](../standard-library/ios-base-class.md)。

- [ios_base](../standard-library/ios-base-class.md) 型のベース オブジェクトの[ストリームの状態情報](../standard-library/ios-base-class.md)。

- `char_type` 型のオブジェクトの充てん文字。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[basic_ios](#basic_ios)|`basic_ios` クラスを構築します。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[char_type](#char_type)|テンプレート パラメーター `Elem` のシノニム。|
|[int_type](#int_type)|`Traits::int_type` と同義。|
|[off_type](#off_type)|`Traits::off_type` と同義。|
|[pos_type](#pos_type)|`Traits::pos_type` と同義。|
|[traits_type](#traits_type)|テンプレート パラメーター `Traits` のシノニム。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[悪い](#bad)|ストリーム バッファーの整合性の損失を示します。|
|[クリア](#clear)|すべてのエラー フラグをクリアします。|
|[copyfmt](#copyfmt)|1 つのストリームから別のストリームにフラグをコピーします。|
|[eof](#eof)|ストリームの末尾に達しているかどうかを示します。|
|[例外](#exceptions)|ストリームによってどの例外がスローされるかを示します。|
|[失敗](#fail)|ストリームからの有効フィールドの抽出エラーを示します。|
|[埋める](#fill)|テキストがストリームの幅に満たない場合に使用される文字を指定するか、返します。|
|[よし](#good)|ストリームの状態が良好であることを示します。|
|[imbue](#imbue)|ロケールを変更します。|
|[Init](#init)|`basic_ios` コンストラクターによって呼び出されます。|
|[移動](#move)|ストリーム バッファーへのポインターを除くすべての値を、パラメーターから現在のオブジェクトに移動します。|
|[narrow](#narrow)|指定された `char_type` と同等の文字を検索します。|
|[rdbuf](#rdbuf)|指定したバッファーにストリームをルーティングします。|
|[rdstate](#rdstate)|フラグのビットの状態を読み取ります。|
|[set_rdbuf](#set_rdbuf)|ストリーム バッファーを割り当てて、このストリーム オブジェクトの読み取りバッファーとして使用します。|
|[setstate](#setstate)|追加のフラグを設定します。|
|[スワップ](#swap)|`basic_ios` オブジェクトの値を別の `basic_ios` オブジェクトの値と交換します。 ストリーム バッファーへのポインターは交換されません。|
|[tie](#tie)|1 つのストリームが別のストリームの前に処理されるようにします。|
|[widen](#widen)|指定された char と同等の `char_type` を検索します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[explicit operator bool](#op_bool)|オブジェクトを`basic_ios` **bool**として使用できます。 しばしば発生する意図しない副作用を防ぐため、自動型変換は無効になっています。|
|[operator void *](#op_void_star)|ストリームが依然として良好かどうかを示します。|
|[演算子！](#op_not)|ストリームが悪化していないかどうかを示します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<ios>

**名前空間:** std

## <a name="basic_iosbad"></a><a name="bad"></a>basic_ios::悪い

ストリーム バッファーの整合性の損失を示します。

```cpp
bool bad() const;
```

### <a name="return-value"></a>戻り値

**0** `rdstate & badbit`以外の場合は true。それ以外**の場合は false。**

`badbit` の詳細については、「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照してください。

### <a name="example"></a>例

```cpp
// basic_ios_bad.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
    using namespace std;
    bool b = cout.bad( );
    cout << boolalpha;
    cout << b << endl;

    b = cout.good( );
    cout << b << endl;
}
```

## <a name="basic_iosbasic_ios"></a><a name="basic_ios"></a>basic_ios::basic_ios

basic_ios クラスを構築します。

```cpp
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```

### <a name="parameters"></a>パラメーター

*Sb*\
入力要素または出力要素を格納する標準のバッファー。

### <a name="remarks"></a>解説

最初のコンストラクターは、[init](#init)(_ *Sb*) を呼び出すことによってそのメンバー オブジェクトを初期化します。 2 つ目の (保護された) コンストラクターは、そのメンバー オブジェクトを初期化前の状態のままにします。 後の呼び`init`出しは、オブジェクトを安全に破棄する前に初期化する必要があります。

## <a name="basic_ioschar_type"></a><a name="char_type"></a>basic_ios::char_type

テンプレート パラメーター `Elem` のシノニム。

```cpp
typedef Elem char_type;
```

## <a name="basic_iosclear"></a><a name="clear"></a>basic_ios::クリア

すべてのエラー フラグをクリアします。

```cpp
void clear(iostate state = goodbit, bool reraise = false);
void clear(io_state state);
```

### <a name="parameters"></a>パラメーター

*状態*\
(オプション)すべてのフラグをクリアした後に設定するフラグ。 既定値は `goodbit` です。

*再発生*\
(オプション)例外を再発生させるかどうかを指定します。 既定値は**false**です (例外は再発生しません)。

### <a name="remarks"></a>解説

フラグは`goodbit`、 `failbit`、 `eofbit`、 `badbit`、 、 です。 [good](#good)、[bad](#bad)、[eof](#eof)、および [fail](#fail) で、これらのフラグをテストします。

このメンバー関数は、格納されているストリームの状態情報を次のものに置き換えます。

`state` &#124; `(`[rdbuf](#rdbuf) != 0 **goodbit** : **badbit**)

`state`**&**[例外が](#exceptions)0 以外の場合は、クラス[の失敗](../standard-library/ios-base-class.md#failure)のオブジェクトをスローします。

### <a name="example"></a>例

を使用する例については[、rdstate](#rdstate) `clear`と[getline](../standard-library/string-functions.md#getline)を参照してください。

## <a name="basic_ioscopyfmt"></a><a name="copyfmt"></a>basic_ios::コピーfmt

1 つのストリームから別のストリームにフラグをコピーします。

```cpp
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
フラグをコピーするストリーム。

### <a name="return-value"></a>戻り値

フラグをコピーするストリームの **this** オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は、コールバック**イベント\_消去イベント**を報告します。 次に**\****、右*からこの塗りつぶし文字、タイ ポインタ、および書式設定情報にコピーします。 例外マスクを変更する前に、コールバック イベント`copyfmt_event`を報告します。 コピーの完了後、**state &**[exceptions](#exceptions) が 0 以外の場合、関数は引数 [rdstate](#rdstate) を使って効果的に [clear](#clear) を呼び出します。 この値**\*を**返します。

### <a name="example"></a>例

```cpp
// basic_ios_copyfmt.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;
    ofstream x( "test.txt" );
    int i = 10;

    x << showpos;
    cout << i << endl;
    cout.copyfmt( x );
    cout << i << endl;
}
```

## <a name="basic_ioseof"></a><a name="eof"></a>basic_ios::eof

ストリームの末尾に達しているかどうかを示します。

```cpp
bool eof() const;
```

### <a name="return-value"></a>戻り値

ストリームの末尾に到達した場合は**true、** それ以外の場合は**false。**

### <a name="remarks"></a>解説

[rdstate](#rdstate)`& eofbit`が 0 以外の場合、メンバー関数は**true**を返します。 `eofbit` の詳細については、「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照してください。

### <a name="example"></a>例

```cpp
// basic_ios_eof.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

int main( int argc, char* argv[] )
{
    fstream   fs;
    int n = 1;
    fs.open( "basic_ios_eof.txt" );   // an empty file
    cout << boolalpha
    cout << fs.eof() << endl;
    fs >> n;   // Read the char in the file
    cout << fs.eof() << endl;
}
```

## <a name="basic_iosexceptions"></a><a name="exceptions"></a>basic_ios::例外

ストリームによってどの例外がスローされるかを示します。

```cpp
iostate exceptions() const;
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```

### <a name="parameters"></a>パラメーター

*新規除く*\
例外をスローするフラグ。

### <a name="return-value"></a>戻り値

ストリームに対して例外をスローするように現在指定されているフラグ。

### <a name="remarks"></a>解説

1 つ目のメンバー関数は、格納されている例外マスクを返します。 2 つ目のメンバー関数は、*_Except* を例外マスクに格納し、その前に格納されていた値を返します。 新しい例外マスクを格納することで、[clear](#clear)( [rdstate](#rdstate) ) の呼び出しと同じように例外をスローできます。

### <a name="example"></a>例

```cpp
// basic_ios_exceptions.cpp
// compile with: /EHsc /GR
#include <iostream>

int main( )
{
    using namespace std;

    cout << cout.exceptions( ) << endl;
    cout.exceptions( ios::eofbit );
    cout << cout.exceptions( ) << endl;
    try
    {
        cout.clear( ios::eofbit );   // Force eofbit on
    }
    catch ( exception &e )
    {
        cout.clear( );
        cout << "Caught the exception." << endl;
        cout << "Exception class: " << typeid(e).name()  << endl;
        cout << "Exception description: " << e.what() << endl;
    }
}
```

```Output
0
1
Caught the exception.
Exception class: class std::ios_base::failure
Exception description: ios_base::eofbit set
```

## <a name="basic_iosfail"></a><a name="fail"></a>basic_ios::失敗

ストリームからの有効フィールドの抽出エラーを示します。

```cpp
bool fail() const;
```

### <a name="return-value"></a>戻り値

[rdstate](#rdstate)`& (badbit|failbit)`がゼロ以外の場合は**true、** それ以外の場合は**false。**

`failbit` の詳細については、「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照してください。

### <a name="example"></a>例

```cpp
// basic_ios_fail.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
    using namespace std;
    bool b = cout.fail( );
    cout << boolalpha;
    cout << b << endl;
}
```

## <a name="basic_iosfill"></a><a name="fill"></a>basic_ios::フィル

テキストがストリームの幅に満たない場合に使用される文字を指定するか、返します。

```cpp
char_type fill() const;
char_type fill(char_type Char);
```

### <a name="parameters"></a>パラメーター

*Char*\
充填文字として必要な文字。

### <a name="return-value"></a>戻り値

現在の充填文字。

### <a name="remarks"></a>解説

1 つ目のメンバー関数は、格納されている充填文字を返します。 2 番目のメンバー関数は *、Fill*文字に Char を格納し、以前に格納された値を返します。

### <a name="example"></a>例

```cpp
// basic_ios_fill.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( )
{
    using namespace std;

    cout << setw( 5 ) << 'a' << endl;
    cout.fill( 'x' );
    cout << setw( 5 ) << 'a' << endl;
    cout << cout.fill( ) << endl;
}
```

```Output
a
xxxxa
x
```

## <a name="basic_iosgood"></a><a name="good"></a>basic_ios::良い

ストリームの状態が良好であることを示します。

```cpp
bool good() const;
```

### <a name="return-value"></a>戻り値

[rdstate](#rdstate) `== goodbit` (状態フラグが設定されていない) の場合は**true、** それ以外の場合は**false。**

`goodbit` の詳細については、「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照してください。

### <a name="example"></a>例

`good` の使用例については、「[basic_ios::bad](#bad)」を参照してください。

## <a name="basic_iosimbue"></a><a name="imbue"></a>basic_ios::インビュー

ロケールを変更します。

```cpp
locale imbue(const locale& Loc);
```

### <a name="parameters"></a>パラメーター

*Loc*\
ロケールの文字列。

### <a name="return-value"></a>戻り値

以前のロケール。

### <a name="remarks"></a>解説

[rdbuf](#rdbuf) が Null ポインターではない場合、メンバー関数は以下を呼び出します。

`rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#pubimbue)(_ *Loc*)

いずれの場合も、[ios_base::imbue](../standard-library/ios-base-class.md#imbue)(_ *Loc*) を返します。

### <a name="example"></a>例

```cpp
// basic_ios_imbue.cpp
// compile with: /EHsc
#include <iostream>
#include <locale>

int main( )
{
    using namespace std;

    cout.imbue( locale( "french_france" ) );
    double x = 1234567.123456;
    cout << x << endl;
}
```

## <a name="basic_iosinit"></a><a name="init"></a>basic_ios::イニト

basic_ios コンストラクターによって呼び出されます。

```cpp
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```

### <a name="parameters"></a>パラメーター

*_Sb*\
入力要素または出力要素を格納する標準のバッファー。

*_Isstd*\
これが標準のストリームかどうかを指定します。

### <a name="remarks"></a>解説

メンバー関数は、以下のようにするため、すべてのメンバー オブジェクトに値を格納します。

- [rdbuf](#rdbuf) が *_Sb* を返す。

- [tie](#tie) が Null ポインターを返す。

- [rdstate](#rdstate)は *、_Sb*がゼロ以外の場合は[goodbit](../standard-library/ios-base-class.md#iostate)を返します。それ以外の場合は[、badbit](../standard-library/ios-base-class.md#iostate)を返します。

- [例外は](#exceptions)`goodbit`を返します。

- [flags](../standard-library/ios-base-class.md#flags) が [skipws](../standard-library/ios-base-class.md#fmtflags) &#124; [dec](../standard-library/ios-base-class.md#fmtflags) を返す。

- [width](../standard-library/ios-base-class.md#width) が 0 を返す。

- [precision](../standard-library/ios-base-class.md#precision) が 6 を返す。

- [fill](#fill) が空白文字を返す。

- [getloc](../standard-library/ios-base-class.md#getloc) が `locale::classic` を返す。

- [iword](../standard-library/ios-base-class.md#iword) が 0 を返し、[pword](../standard-library/ios-base-class.md#pword) がすべての引数値に Null ポインターを返す。

## <a name="basic_iosint_type"></a><a name="int_type"></a>basic_ios::int_type

`traits_type::int_type` と同義。

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_iosmove"></a><a name="move"></a>basic_ios::移動

ストリーム バッファーへのポインターを除くすべての値を、パラメーターから現在のオブジェクトに移動します。

```cpp
void move(basic_ios&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
値の移動元となる `ios_base` オブジェクト。

### <a name="remarks"></a>解説

プロテクト メンバー関数は *、右*に格納されているすべての値`*this`を、右`stream buffer pointer`に変更されずに格納された*値に移動*し、 で`*this`null ポインターに設定します。 格納された`tie pointer`値は *、右*の null ポインタに設定されます。

## <a name="basic_iosnarrow"></a><a name="narrow"></a>basic_ios::狭い

指定された `char_type` と同等の文字を検索します。

```cpp
char narrow(char_type Char, char Default = '\0') const;
```

### <a name="parameters"></a>パラメーター

*Char*\
変換する**文字**。

*既定*\
対応する文字が見つからない場合に返される**文字**。

### <a name="return-value"></a>戻り値

指定された**char**`char_type`.

### <a name="remarks"></a>解説

メンバー関数は[、ctype](../standard-library/basic-filebuf-class.md#open)\<\<E use_facet> > ( [getloc](../standard-library/ios-base-class.md#getloc)( ) を返します。`narrow`( `Char`, `Default`).

### <a name="example"></a>例

```cpp
// basic_ios_narrow.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <wchar.h>

int main( )
{
    using namespace std;
    wchar_t *x = L"test";
    char y[10];
    cout << x[0] << endl;
    wcout << x << endl;
    y[0] = wcout.narrow( x[0] );
    cout << y[0] << endl;
}
```

## <a name="basic_iosoff_type"></a><a name="off_type"></a>basic_ios::off_type

`traits_type::off_type` と同義。

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_iosoperator-void-"></a><a name="op_void_star"></a>basic_ios::オペレーターボイド *

ストリームが依然として良好かどうかを示します。

```cpp
operator void *() const;
```

### <a name="return-value"></a>戻り値

演算子は [fail](#fail) の場合にのみ Null ポインターを返します。

### <a name="example"></a>例

```cpp
// basic_ios_opgood.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << (bool)(&cout != 0) << endl;   // Stream is still good
}
```

```Output
1
```

## <a name="basic_iosoperator"></a><a name="op_not"></a>basic_ios::オペレーター!

ストリームが悪化していないかどうかを示します。

```cpp
bool operator!() const;
```

### <a name="return-value"></a>戻り値

[fail](#fail) を返します。

### <a name="example"></a>例

```cpp
// basic_ios_opbad.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << !cout << endl;   // Stream is not bad
}
```

```Output
0
```

## <a name="basic_iosoperator-bool"></a><a name="op_bool"></a>basic_ios::オペレーターブール

オブジェクトを`basic_ios` **bool**として使用できます。 しばしば発生する意図しない副作用を防ぐため、自動型変換は無効になっています。

```cpp
explicit operator bool() const;
```

### <a name="remarks"></a>解説

演算子は、場合にのみ**false**に変換可能`fail()`な値を返します。 戻り値の型は **、bool**にのみ変換可能`void *`で、他の既知のスカラー型には変換されません。

## <a name="basic_iospos_type"></a><a name="pos_type"></a>basic_ios::pos_type

`traits_type::pos_type` と同義。

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_iosrdbuf"></a><a name="rdbuf"></a>basic_ios::rdbuf

指定したバッファーにストリームをルーティングします。

```cpp
basic_streambuf<Elem, Traits> *rdbuf() const;
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```

### <a name="parameters"></a>パラメーター

*_Sb*\
ストリーム。

### <a name="remarks"></a>解説

1 つ目のメンバー関数は、格納されているストリーム バッファー ポインターを返します。

2 番目のメンバー関数は *、_Sb*を格納されたストリーム バッファー ポインターに格納し、以前に格納された値を返します。

### <a name="example"></a>例

```cpp
// basic_ios_rdbuf.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;
    ofstream file( "rdbuf.txt" );
    streambuf *x = cout.rdbuf( file.rdbuf( ) );
    cout << "test" << endl;   // Goes to file
    cout.rdbuf(x);
    cout << "test2" << endl;
}
```

```Output
test2
```

## <a name="basic_iosrdstate"></a><a name="rdstate"></a>basic_ios::rdstate

フラグのビットの状態を読み取ります。

```cpp
iostate rdstate() const;
```

### <a name="return-value"></a>戻り値

格納されているストリームの状態情報。

### <a name="example"></a>例

```cpp
// basic_ios_rdstate.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>
using namespace std;

void TestFlags( ios& x )
{
    cout << ( x.rdstate( ) & ios::badbit ) << endl;
    cout << ( x.rdstate( ) & ios::failbit ) << endl;
    cout << ( x.rdstate( ) & ios::eofbit ) << endl;
    cout << endl;
}

int main( )
{
    fstream x( "c:\test.txt", ios::out );
    x.clear( );
    TestFlags( x );
    x.clear( ios::badbit | ios::failbit | ios::eofbit );
    TestFlags( x );
}
```

```Output
0
0
0

4
2
1
```

## <a name="basic_iossetstate"></a><a name="setstate"></a>basic_ios::設定状態

追加のフラグを設定します。

```cpp
void setstate(iostate _State);
```

### <a name="parameters"></a>パラメーター

*_state*\
設定する追加のフラグ。

### <a name="remarks"></a>解説

メンバー関数は効果的に [clear](#clear)(_ *State* &#124; [rdstate](#rdstate)) を呼び出します。

### <a name="example"></a>例

```cpp
// basic_ios_setstate.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
using namespace std;

int main( )
{
    bool b = cout.bad( );
    cout << b << endl;   // Good
    cout.clear( ios::badbit );
    b = cout.bad( );
    // cout.clear( );
    cout << b << endl;   // Is bad, good
    b = cout.fail( );
    cout << b << endl;   // Not failed
    cout.setstate( ios::failbit );
    b = cout.fail( );
    cout.clear( );
    cout << b << endl;   // Is failed, good
    return 0;
}
```

```Output
0
1
```

## <a name="basic_iosset_rdbuf"></a><a name="set_rdbuf"></a>basic_ios::set_rdbuf

ストリーム バッファーを割り当てて、このストリーム オブジェクトの読み取りバッファーとして使用します。

```cpp
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)
```

### <a name="parameters"></a>パラメーター

*ストルブフ*\
読み取りバッファーになるストリーム バッファー。

### <a name="remarks"></a>解説

プロテクト メンバー関数は*strbuf*を に格納します`stream buffer pointer`。は呼び出`clear`しません。

## <a name="basic_iostie"></a><a name="tie"></a>basic_ios::ネクタイ

1 つのストリームが別のストリームの前に処理されるようにします。

```cpp
basic_ostream<Elem, Traits> *tie() const;
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```

### <a name="parameters"></a>パラメーター

*Str*\
ストリーム。

### <a name="return-value"></a>戻り値

1 つ目のメンバー関数は、格納されているリンク付けポインターを返します。 2 番目のメンバー関数は *、str*を tie ポインターに格納し、以前に格納された値を返します。

### <a name="remarks"></a>解説

`tie` は 2 つのストリームを同期させて、一方のストリームでの操作が完了すると、もう一方のストリームで操作が行われるようにします。

### <a name="example"></a>例

この例では、cout に cin にリンクすることで、"Enter a number:" 文字列がコンソールに移動した後で、数字が cin から抽出されることを保証します。 これにより、数値の読み取り時に "Enter a number:" 文字列がバッファーにまだ残っている可能性を排除して、ユーザーが応答するプロンプトが必ずいくつかあるようにします。 既定では、cin と cout は関連付けられています。

```cpp
#include <ios>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    cin.tie( &cout );
    cout << "Enter a number:";
    cin >> i;
}
```

## <a name="basic_iostraits_type"></a><a name="traits_type"></a>basic_ios::traits_type

テンプレート パラメーター `Traits` のシノニム。

```cpp
typedef Traits traits_type;
```

## <a name="basic_ioswiden"></a><a name="widen"></a>basic_ios::拡幅

指定された`char_type`char と等価な**値**を検索します。

```cpp
char_type widen(char Char) const;
```

### <a name="parameters"></a>パラメーター

*Char*\
変換する文字。

### <a name="return-value"></a>戻り値

指定された`char_type`char と等価な**値**を検索します。

### <a name="remarks"></a>解説

メンバー関数は **、ctype** \< **E**> >( [getloc](../standard-library/ios-base-class.md#getloc)) [use_facet](../standard-library/basic-filebuf-class.md#open)< 返します。 `widen`( `Char`).

### <a name="example"></a>例

```cpp
// basic_ios_widen.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <wchar.h>

int main( )
{
    using namespace std;
    char *z = "Hello";
    wchar_t y[2] = {0,0};
    cout << z[0] << endl;
    y[0] = wcout.widen( z[0] );
    wcout << &y[0] << endl;
}
```

## <a name="basic_iosswap"></a><a name="swap"></a>basic_ios::スワップ

`basic_ios` オブジェクトの値を別の `basic_ios` オブジェクトの値と交換します。 ただし、ストリーム バッファーへのポインターは交換されません。

```cpp
void swap(basic_ios&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
値を交換するために使用される `basic_ios` オブジェクト。

### <a name="remarks"></a>解説

プロテクト メンバー関数は、格納されている値を格納済`*this`み以外の`stream buffer pointer`*、右*に格納されているすべての値を交換します。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリにおけるスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[ioストリームの規約](../standard-library/iostreams-conventions.md)
