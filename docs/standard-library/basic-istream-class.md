---
title: basic_istream クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- istream/std::basic_istream
- istream/std::basic_istream::gcount
- istream/std::basic_istream::get
- istream/std::basic_istream::getline
- 'istream/std::basic_istream::'
- istream/std::basic_istream::peek
- istream/std::basic_istream::putback
- istream/std::basic_istream::read
- istream/std::basic_istream::readsome
- istream/std::basic_istream::seekg
- istream/std::basic_istream::sentry
- istream/std::basic_istream::swap
- istream/std::basic_istream::sync
- istream/std::basic_istream::tellg
- istream/std::basic_istream::unget
dev_langs:
- C++
helpviewer_keywords:
- std::basic_istream [C++]
- std::basic_istream [C++], gcount
- std::basic_istream [C++], get
- std::basic_istream [C++], getline
- std::basic_istream [C++], OVERWRITE
- std::basic_istream [C++], peek
- std::basic_istream [C++], putback
- std::basic_istream [C++], read
- std::basic_istream [C++], readsome
- std::basic_istream [C++], seekg
- std::basic_istream [C++], sentry
- std::basic_istream [C++], swap
- std::basic_istream [C++], sync
- std::basic_istream [C++], tellg
- std::basic_istream [C++], unget
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51dc841efa3e9f64a106002945c07ce10bcf7565
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102617"
---
# <a name="basicistream-class"></a>basic_istream クラス

`Elem` 型の要素を含むストリーム バッファーからの要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。この型は [char_type](../standard-library/basic-ios-class.md#char_type) とも呼ばれ、その文字特性は、[traits_type](../standard-library/basic-ios-class.md#traits_type) とも呼ばれるクラス *Tr* によって決定されます。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_istream : virtual public basic_ios<Elem, Tr>
```

## <a name="remarks"></a>Remarks

[operator>>](#op_gt_gt) をオーバーロードするメンバー関数のほとんどは、書式設定された入力関数です。 これらは以下のパターンに従います。

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```

その他のメンバー関数の多くは、書式が設定されていない入力関数です。 これらは以下のパターンに従います。

```cpp
iostate state = goodbit;
count = 0;    // the value returned by gcount
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```

関数呼び出しの両方のグループ[setstate](../standard-library/basic-ios-class.md#setstate)(`eofbit`) 要素を抽出中にファイルの終わりが発生した場合。

クラス `basic_istream`< `Elem`, *Tr*> のオブジェクトは次のものを格納します。

- クラス [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, *Tr*> `.` の仮想パブリック基本オブジェクト

- 最後の書式設定されていない入力操作の抽出カウント (と呼ばれる`count`上記のコードで)。

## <a name="example"></a>例

入力ストリームの詳細は、[basic_ifstream クラス](../standard-library/basic-ifstream-class.md)の例を参照してください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_istream](#basic_istream)|`basic_istream` 型のオブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[gcount](#gcount)|書式設定されていない最後の入力中に読まれた文字数を返します。|
|[get](#get)|入力ストリームから 1 つ以上の文字を読み取ります。|
|[getline](#getline)|入力ストリームから行を読み取ります。|
|[ignore](#ignore)|複数の要素を、現在読み取った位置からスキップさせます。|
|[peek](#peek)|読み取る次の文字を返します。|
|[putback](#putback)|ストリームに指定された文字を配置します。|
|[read](#read)|指定された数の文字をストリームから読み取り、配列に保存します。|
|[readsome](#readsome)|バッファーからのみ読み取ります。|
|[seekg](#seekg)|ストリームでの読み取り位置を移動させます。|
|[sentry](#sentry)|この入れ子になったクラスは、オブジェクトの宣言が書式設定された入力関数と書式設定されていない入力関数を構築するオブジェクトについて記述します。|
|[swap](#swap)|この `basic_istream` オブジェクトを、指定した `basic_istream` オブジェクト パラメーターと交換します。|
|[sync](#sync)|ストリームのバッファー付のストリームと関連付けられている入力デバイスを同期します。|
|[tellg](#tellg)|ストリーム内の現在の読み取り位置を報告します。|
|[unget](#unget)|最後に読み取った文字をストリームに戻します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator>>](#op_gt_gt)|入力ストリームで関数を呼び出すか、または入力ストリームから書式設定されたデータを読み取ります。|
|[operator=](#op_eq)|演算子の右辺の `basic_istream` をこのオブジェクトに代入します。 これは、コピーを残さない `rvalue` 参照を伴う移動代入です。|

## <a name="requirements"></a>要件

**ヘッダー:** \<istream>

**名前空間:** std

## <a name="basic_istream"></a>  basic_istream::basic_istream

`basic_istream` 型のオブジェクトを構築します。

```cpp
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>パラメーター

*strbuf*<br/>
[basic_streambuf](../standard-library/basic-streambuf-class.md) 型のオブジェクト。

*_Isstd*<br/>
**true**場合、これは、標準的なストリームです。 それ以外の場合、 **false**します。

*right*<br/>
コピーする `basic_istream` オブジェクト。

### <a name="remarks"></a>Remarks

最初のコンストラクターが [init](../standard-library/basic-ios-class.md#init)(_S `trbuf`) を呼び出して基底クラスを初期化します。 ゼロも抽出カウントに格納されます。 この抽出カウントの詳細については、「[basic_istream クラス](../standard-library/basic-istream-class.md)」の概要トピックの「コメント」セクションを参照してください。

2 番目のコンストラクターが `move( right)` を呼び出して基底クラスを初期化します。 _R `ight.gcount()` も抽出カウントに格納し、ゼロを _R `ight` の抽出カウントに格納します。

### <a name="example"></a>例

入力ストリームの詳細は、[basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream) の例を参照してください。

## <a name="gcount"></a>  basic_istream::gcount

書式設定されていない最後の入力中に読まれた文字数を返します。

```cpp
streamsize gcount() const;
```

### <a name="return-value"></a>戻り値

抽出カウント。

### <a name="remarks"></a>Remarks

書式設定されていない文字を読み取るには、[basic_istream::get](#get) を使用します。

### <a name="example"></a>例

```cpp
// basic_istream_gcount.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   cout << "Type the letter 'a': ";

   ws( cin );
   char c[10];

   cin.get( &c[0],9 );
   cout << c << endl;

   cout << cin.gcount( ) << endl;
}
```

```Output

a

```

```Output

      aType the letter 'a':
a
1
```

## <a name="get"></a>  basic_istream::get

入力ストリームから 1 つ以上の文字を読み取ります。

```cpp
int_type get();

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```

### <a name="parameters"></a>パラメーター

*count*<br/>
`strbuf` から読み取る文字の数。

*delim*<br/>
前にこれが発生した場合、読み取りを終了する文字*カウント*します。

*str*<br/>
書き込み先の文字列。

*ch*<br/>
取得する文字。

*strbuf*<br/>
書き込み先のバッファー。

### <a name="return-value"></a>戻り値

get のパラメーターなしの形式は、整数またはファイルの終わりとして読み取られる要素を返します。 残りの形式はストリーム (* `this`) を返します。

### <a name="remarks"></a>Remarks

これらの書式設定されていない 1 番目の入力関数は、可能であれば、`rdbuf`-> `sbumpc` を返す場合と同じように、要素を抽出します。 それ以外の場合は、**traits_type::**[eof](../standard-library/char-traits-struct.md#eof) を返します。 呼び出す関数が要素を抽出しなかった場合[setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)。

2 番目の関数は、同じ方法で [int_type](../standard-library/basic-ios-class.md#int_type) 要素 `meta` を抽出します。 `meta` が **traits_type::eof** と等しい場合、関数は `setstate`( **failbit**) を呼び出します。 それ以外の場合は、**traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)( `meta`) を `Ch` に格納します。 関数は **\*this** を返します。

3 番目の関数は、**get**(_ *Str*, `count`, `widen`('\ **n**')) を返します。

4 番目の関数を抽出して最大*カウント*- 1 要素 _ で始まる配列に格納および*Str*します。 これは格納する抽出した要素の後に常に `char_type` を格納します。 テストの順に抽出は停止します。

- ファイルの終わり。

- 関数と等しい要素を抽出後*Delim*、被制御シーケンスへの要素の再度の検疫場合。

- 関数抽出後*カウント*- 1 要素。

関数が要素を抽出しなかった場合、`setstate`( **failbit**) を呼び出します。 いずれの場合も、**\*this** を返します。

5 番目の関数は、**get**( **strbuf**, `widen`('\ **n**')) を返します。

6 番目の関数が要素を抽出し、それらで挿入`strbuf`します。 抽出は、ファイルの終わりまたは _ *Delim* と等しい要素で停止し、抽出はされません。 また、挿入が失敗した場合または (キャッチされるが再スローされない) 例外をスローする場合は、対象の要素を抽出せずに停止します。 関数が要素を抽出しなかった場合、`setstate`( **failbit**) を呼び出します。 いずれの場合も関数は **\*this** を返します。

### <a name="example"></a>例

```cpp
// basic_istream_get.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   c[0] = cin.get( );
   cin.get( c[1] );
   cin.get( &c[2],3 );
   cin.get( &c[4], 4, '7' );

   cout << c << endl;
}
```

```Output

1111
```

## <a name="getline"></a>  basic_istream::getline

入力ストリームから行を取得します。

```cpp
basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,
    streamsize count,
    char_type Delim);
```

### <a name="parameters"></a>パラメーター

*count*<br/>
`strbuf` から読み取る文字の数。

*delim*<br/>
前にこれが発生した場合、読み取りを終了する文字*カウント*します。

*str*<br/>
書き込み先の文字列。

### <a name="return-value"></a>戻り値

ストリーム ( **\*this**)。

### <a name="remarks"></a>Remarks

これらの書式設定されていない最初の入力関数は、**getline**(_ *Str*, `count`, `widen`(' `\`**n**')) を返します。

2 番目の関数を抽出して最大*カウント*- 1 要素 _ で始まる配列に格納し、 *Str*します。 これは格納する抽出した要素の後に常に文字列終端文字を格納します。 テストの順に抽出は停止します。

- ファイルの終わり。

- 関数と等しい要素を抽出後*Delim*、その場合、要素が戻されたり、被制御シーケンスに追加されます。

- 関数抽出後*カウント*- 1 要素。

関数が要素を抽出しなかった場合または*カウント*- 1 要素を呼び出す[setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)。 いずれの場合も、**\*this** を返します。

### <a name="example"></a>例

```cpp
// basic_istream_getline.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   cin.getline( &c[0], 5, '2' );
   cout << c << endl;
}
```

```Output

121
```

## <a name="ignore"></a>  basic_istream::ignore

複数の要素を、現在読み取った位置からスキップさせます。

```cpp
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,
    int_type Delim = traits_type::eof());
```

### <a name="parameters"></a>パラメーター

*count*<br/>
現在の読み取り位置からスキップする要素の数。

*delim*<br/>
Before count、発生した場合に発生する要素`ignore`を返すの後にすべての要素を許可して*Delim*を読み取る。

### <a name="return-value"></a>戻り値

ストリーム ( **\*this**)。

### <a name="remarks"></a>Remarks

書式設定されていない入力関数が最大を抽出*カウント*要素と、これらを破棄します。 場合*カウント*equals **numeric_limits\<int >:: max**、任意の大きさとしてただし、作成します。 ファイルの終わりまたは要素の抽出を早期停止`Ch`ように**traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( `Ch`) と同じ*Delim* (抽出されます)。 関数は **\*this** を返します。

### <a name="example"></a>例

```cpp
// basic_istream_ignore.cpp
// compile with: /EHsc
#include <iostream>
int main( )
{
   using namespace std;
   char chararray[10];
   cout << "Type 'abcdef': ";
   cin.ignore( 5, 'c' );
   cin >> chararray;
   cout << chararray;
}
```

```Output
Type 'abcdef': abcdef
def
```

## <a name="op_gt_gt"></a>  basic\_istream::operator>>

入力ストリームで関数を呼び出すか、または入力ストリームから書式設定されたデータを読み取ります。

```cpp
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));
basic_istream& operator>>(basic_streambuf<Elem, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

### <a name="parameters"></a>パラメーター

*pfn*<br/>
関数ポインター。

*strbuf*<br/>
`stream_buf` 型のオブジェクト。

*val*<br/>
ストリームから読み取る値。

### <a name="return-value"></a>戻り値

ストリーム ( **\*this**)。

### <a name="remarks"></a>Remarks

\<Istream > ヘッダーでは、いくつかのグローバル抽出演算子も定義します。 詳細については、「[operator>> (\<istream>)](../standard-library/istream-operators.md#op_gt_gt)」を参照してください。

最初のメンバー関数は、**istr** >> `ws` 形式の式が [ws](../standard-library/istream-functions.md#ws)( **istr**) を呼び出し、**\*this** を返すことを保証します。 2 番目と 3 番目の関数は、[hex](../standard-library/ios-functions.md#hex) などの他のマニピュレーターが同じように動作することを保証します。 残りの関数は、書式設定された入力関数を構成します。

関数:

```cpp
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```

場合、要素を抽出します _ *Strbuf*が null ポインターの場合とでそれらを挿入*strbuf*します。 抽出は、ファイルの終わりで停止します。 また、挿入が失敗した場合または (キャッチされるが再スローされない) 例外をスローする場合は、対象の要素を抽出せずに停止します。 呼び出す関数が要素を抽出しなかった場合[setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)。 いずれの場合も関数は **\*this** を返します。

関数:

```cpp
basic_istream& operator>>(bool& val);
```

フィールドを抽出し、[use_facet](../standard-library/basic-filebuf-class.md#open) < `num_get`\< **Elem**, **InIt**>( [getloc](../standard-library/ios-base-class.md#getloc)). [get](../standard-library/ios-base-class.md#getloc)( **InIt**( [rdbuf](../standard-library/basic-ios-class.md#rdbuf)), `Init`(0), **\*this**, `getloc`, `val`) を呼び出して、それをブール値に変換します。 ここで、**InIt** は [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)\< **Elem**, **Tr**> として定義されます。 関数は **\*this** を返します。

関数:

```cpp
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
```

それぞれがフィールドを抽出し、`use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). [get](#get)( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, `val`) を呼び出して、それを数値に変換します。 ここでは、 **InIt**として定義されます`istreambuf_iterator` \< **Elem**、 **Tr**>、および`val`型を持つ**長い**、 **unsigned long**、または**void** <strong>\*</strong>に応じて。

変換後の値の型として表すことができないかどうか`val`、関数呼び出し[setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)。 いずれの場合も関数は **\*this** を返します。

関数:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

それぞれがフィールドを抽出し、`use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). **get**( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, `val`) を呼び出して、それを数値に変換します。 ここでは、`InIt`として定義されます`istreambuf_iterator` \< **Elem**、 **Tr**>、および`val`型を持つ**二重**または**長二重**に応じて。

変換後の値を `val` の型として表すことができない場合、関数は `setstate`( **failbit**) を呼び出します。 いずれの場合も、**\*this** を返します。

### <a name="example"></a>例

```cpp
// istream_basic_istream_op_is.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)
{
   if ( i == cin )
   {
      cerr << "i is cin" << endl;
   }
   return i;
}

int main( )
{
   int i = 0;
   cin >> somefunc;
   cin >> i;
   cout << i << endl;
   cin >> hex2;
   cin >> i;
   cout << i << endl;
}
```

## <a name="op_eq"></a>  basic_istream::operator=

演算子の右辺の `basic_istream` をこのオブジェクトに代入します。 これは、コピーを残さない `rvalue` 参照を伴う移動代入です。

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
`basic_ifstream` オブジェクトへの `rvalue` 参照。

### <a name="return-value"></a>戻り値

*this を返します。

### <a name="remarks"></a>Remarks

このメンバー演算子は、swap `( right)` を呼び出します。

## <a name="peek"></a>  basic_istream::peek

読み取る次の文字を返します。

```cpp
int_type peek();
```

### <a name="return-value"></a>戻り値

読み取る次の文字。

### <a name="remarks"></a>Remarks

これらの書式設定されていない入力関数は、可能であれば、`rdbuf` -> [sgetc](../standard-library/basic-streambuf-class.md#sgetc) を返すように、要素を抽出します。 それ以外の場合は、**traits_type::**[eof](../standard-library/char-traits-struct.md#eof) を返します。

### <a name="example"></a>例

```cpp
// basic_istream_peek.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;
   cout << "Type 'abcde': ";

   c2 = cin.peek( );
   cin.getline( &c[0], 9 );

   cout << c2 << " " << c << endl;
}
```

```Output

abcde

```

```Output

      abcdeType 'abcde': abcde
a abcde
```

## <a name="putback"></a>  basic_istream::putback

ストリームに指定された文字を配置します。

```cpp
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
ストリームに戻す文字。

### <a name="return-value"></a>戻り値

ストリーム ( **\*this**)。

### <a name="remarks"></a>Remarks

[書式設定されていない入力関数](../standard-library/basic-istream-class.md)戻す*Ch*を呼び出した場合、可能な場合、 [rdbuf](../standard-library/basic-ios-class.md#rdbuf)`->`[sputbackc](../standard-library/basic-streambuf-class.md#sputbackc)します。 Rdbuf が null ポインターの場合、または場合に呼び出し`sputbackc`返します**traits_type::**[eof](../standard-library/char-traits-struct.md#eof)、関数呼び出し[setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`)。 いずれの場合も、**\*this** を返します。

### <a name="example"></a>例

```cpp
// basic_istream_putback.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2, c3;

   c2 = cin.get( );
   c3 = cin.get( );
   cin.putback( c2 );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Output

qwq
```

## <a name="read"></a>  basic_istream::read

指定された数の文字をストリームから読み取り、配列に保存します。

渡された値が正しいことの確認を呼び出し元に依存するため、このメソッドは安全ではない可能性があります。

```cpp
basic_istream<Elem, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
文字の読み取り先の配列。

*count*<br/>
読み取る文字の数。

### <a name="return-value"></a>戻り値

ストリーム ( `*this`)。

### <a name="remarks"></a>Remarks

書式設定されていない入力関数を抽出して最大*カウント*要素 _ で始まる配列に格納および`Str`します。 抽出は、ファイルの終わりで、関数の呼び出しを早い段階は停止します[setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)。 いずれの場合も、`*this` を返します。

### <a name="example"></a>例

```cpp
// basic_istream_read.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
    char c[10];
    int count = 5;

    cout << "Type 'abcde': ";

    // Note: cin::read is potentially unsafe, consider
    // using cin::_Read_s instead.
    cin.read(&c[0], count);
    c[count] = 0;

    cout << c << endl;
}
```

```Output

abcde

```

```Output

      abcdeType 'abcde': abcde
abcde
```

## <a name="readsome"></a>  basic_istream::readsome

指定した文字の値の数を読み取ります。

渡された値が正しいことの確認を呼び出し元に依存するため、このメソッドは安全ではない可能性があります。

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
`readsome` が読み取る文字を格納する配列。

*count*<br/>
読み取る文字の数。

### <a name="return-value"></a>戻り値

実際に読み取った文字数、[gcount](#gcount)。

### <a name="remarks"></a>Remarks

この書式設定されていない入力関数を抽出して最大*カウント*入力からの要素はストリームし、配列に格納*str*します。

この関数は入力を待機しません。 使用できる任意のデータを読み取ります。

### <a name="example"></a>例

```cpp
// basic_istream_readsome.cpp
// compile with: /EHsc /W3
#include <iostream>
using namespace std;

int main( )
{
   char c[10];
   int count = 5;

   cout << "Type 'abcdefgh': ";

   // cin.read blocks until user types input.
   // Note: cin::read is potentially unsafe, consider
   // using cin::_Read_s instead.
   cin.read(&c[0], 2);

   // Note: cin::readsome is potentially unsafe, consider
   // using cin::_Readsome_s instead.
   int n = cin.readsome(&c[0], count);  // C4996
   c[n] = 0;
   cout << n << " characters read" << endl;
   cout << c << endl;
}
```

## <a name="seekg"></a>  basic_istream::seekg

ストリームでの読み取り位置を移動させます。

```cpp
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
読み取りポインターの移動先の絶対位置。

*オフ*<br/>
に対して相対的に読み取りポインターを移動するオフセット*方法*します。

*方法*<br/>
[ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) 列挙体のうちの 1 つ。

### <a name="return-value"></a>戻り値

ストリーム ( **\*this**)。

### <a name="remarks"></a>Remarks

1 つ目のメンバー関数は絶対シークを実行し、2 つ目のメンバー関数は相対シークを実行します。

> [!NOTE]
> 標準 C++ ではテキスト ファイルでの相対シークをサポートしていないため、2 つ目のメンバー関数をテキスト ファイルで使用しないでください。

場合[失敗](../standard-library/basic-ios-class.md#fail)が false の場合、最初のメンバー関数は**newpos** = [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)( `pos`)、一部の`pos_type`一時オブジェクト`newpos`します。 場合`fail`が false の場合、2 番目の関数は**newpos** = **rdbuf** -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)( `off`、 `way`). いずれの場合も場合、( `off_type`) **newpos** = = ( `off_type`)(-1) (、位置指定操作が失敗)、関数呼び出し`istr`します。 [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)。 どちらの関数も **\*this** を返します。

[fail](../standard-library/basic-ios-class.md#fail) が true の場合、メンバー関数は何もしません。

### <a name="example"></a>例

```cpp
// basic_istream_seekg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
   using namespace std;
   ifstream file;
   char c, c1;

   file.open( "basic_istream_seekg.txt" );
   file.seekg(2);   // seek to position 2
   file >> c;
   cout << c << endl;
}
```

## <a name="sentry"></a>  basic_istream::sentry

この入れ子になったクラスは、オブジェクトの宣言が書式設定された入力関数と書式設定されていない入力関数を構築するオブジェクトについて記述します。

クラスの sentry {パブリック: 明示的な sentry (basic_istream\<Elem, Tr > & _Istr、bool _Noskip = false); 演算子 bool() const;};

### <a name="remarks"></a>Remarks

`_Istr.`[good](../standard-library/basic-ios-class.md#good) が true の場合、コンストラクターは以下を実行します。

- `_Istr`. [tie](../standard-library/basic-ios-class.md#tie) -> [flush](../standard-library/basic-ostream-class.md#flush) を呼び出す (`_Istr`. `tie` が Null ポインターでない場合)

- [ws](../standard-library/istream-functions.md#ws)( `_Istr`) を効果的に呼び出す (`_Istr`. [flags](../standard-library/ios-base-class.md#flags)**&**[skipws](../standard-library/ios-functions.md#skipws) がゼロ以外の場合)

このような準備作業の後に、`_Istr`. `good` false の場合、コンス トラクターは`_Istr`します。 [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`)。 いずれの場合も、コンストラクターは `_Istr`. `good` `status`します。 以降の呼び出し`operator bool`この格納されている値を提供します。

## <a name="swap"></a>  basic_istream::swap

2 つの `basic_istream` オブジェクトの内容を交換します。

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>パラメーター

*right*<br/>
`basic_istream` オブジェクトへの左辺値参照。

### <a name="remarks"></a>Remarks

メンバー関数は [basic_ios::swap](../standard-library/basic-ios-class.md#swap)`(right)` を呼び出します。 抽出カウントの抽出カウントと交換*右*します。

## <a name="sync"></a>  basic_istream::sync

ストリームのバッファー付のストリームと関連付けられている入力デバイスを同期します。

```cpp
int sync();
```

### <a name="return-value"></a>戻り値

[rdbuf](../standard-library/basic-ios-class.md#rdbuf) が Null ポインターの場合、この関数は -1 を返します。 そうでない場合は、`rdbuf` -> [pubsync](../standard-library/basic-streambuf-class.md#pubsync) を呼び出します。 -1 を返す場合、関数は[setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`)-1 を返します。 それ以外の場合、関数は 0 を返します。

## <a name="tellg"></a>  basic_istream::tellg

ストリーム内の現在の読み取り位置を報告します。

```cpp
pos_type tellg();
```

### <a name="return-value"></a>戻り値

ストリームの現在の位置。

### <a name="remarks"></a>Remarks

[fail](../standard-library/basic-ios-class.md#fail) が false の場合、メンバー関数は [rdbuf](../standard-library/basic-ios-class.md#rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur`, **in**) を返します。 それ以外の場合は、`pos_type`(-1) を返します。

### <a name="example"></a>例

```cpp
// basic_istream_tellg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;
    ifstream file;
    char c;
    streamoff i;

    file.open("basic_istream_tellg.txt");
    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;

    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;
}
```

## <a name="unget"></a>  basic_istream::unget

最後に読み取った文字をストリームに戻します。

```cpp
basic_istream<Elem, Tr>& unget();
```

### <a name="return-value"></a>戻り値

ストリーム ( **\*this**)。

### <a name="remarks"></a>Remarks

[書式設定されていない入力関数](../standard-library/basic-istream-class.md)は、可能であれば、`rdbuf` -> [sungetc](../standard-library/basic-streambuf-class.md#sungetc) を呼び出した場合と同じように、前の要素をストリームに戻します。 場合[rdbuf](../standard-library/basic-ios-class.md#rdbuf)が null ポインターの場合、またはへの呼び出し`sungetc`返します**traits_type::**[eof](../standard-library/basic-ios-class.md#eof)、関数呼び出し[setstate](../standard-library/basic-ios-class.md#setstate)(`badbit`). いずれの場合も、**\*this** を返します。

`unget` がどのように失敗する可能性があるかについては、「[basic_streambuf::sungetc](../standard-library/basic-streambuf-class.md#sungetc)」を参照してください。

### <a name="example"></a>例

```cpp
// basic_istream_unget.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;

   cout << "Type 'abc': ";
   c2 = cin.get( );
   cin.unget( );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Output

abc

```

```Output

      abcType 'abc': abc
abc
```

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream プログラミング](../standard-library/iostream-programming.md)<br/>
[iostreams の規則](../standard-library/iostreams-conventions.md)<br/>
