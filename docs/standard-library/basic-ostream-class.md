---
description: '詳細情報: basic_ostream クラス'
title: basic_ostream クラス
ms.date: 03/27/2019
f1_keywords:
- ostream/std::basic_ostream
- ostream/std::basic_ostream::flush
- ostream/std::basic_ostream::put
- ostream/std::basic_ostream::seekp
- ostream/std::basic_ostream::sentry
- ostream/std::basic_ostream::swap
- ostream/std::basic_ostream::tellp
- ostream/std::basic_ostream::write
helpviewer_keywords:
- std::basic_ostream [C++]
- std::basic_ostream [C++], flush
- std::basic_ostream [C++], put
- std::basic_ostream [C++], seekp
- std::basic_ostream [C++], sentry
- std::basic_ostream [C++], swap
- std::basic_ostream [C++], tellp
- std::basic_ostream [C++], write
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
ms.openlocfilehash: 19bcc5fddd7ae73a77492f88ed516beb03182839
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325655"
---
# <a name="basic_ostream-class"></a>basic_ostream クラス

このクラステンプレートは、要素とエンコードされたオブジェクトを、char_type とも呼ばれる型の要素を使用してストリームバッファーに挿入する操作を制御するオブジェクトを記述し `Elem` ます。このオブジェクトは、 [](../standard-library/basic-ios-class.md#char_type) `Tr` [traits_type](../standard-library/basic-ios-class.md#traits_type)とも呼ばれるクラスによって決まります。

## <a name="syntax"></a>構文

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>パラメーター

*Elem*\
`char_type`。

*Tr*\
文字 `traits_type`。

## <a name="remarks"></a>解説

[operator<<](#basic_ostream_operator_lt_lt) をオーバーロードするメンバー関数のほとんどは、書式が設定されている出力関数です。 これらは以下のパターンに従います。

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{try
{<convert and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
width(0);
// Except for operator<<(Elem)
setstate(state);

return (*this);
```

他の 2 つのメンバー関数は、書式が設定されていない出力関数です。 これらは以下のパターンに従います。

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (!ok)
    state |= badbit;
else
{try
{<obtain and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
setstate(state);

return (*this);
```

要素の挿入中にエラーが発生した場合、どちらの関数グループも [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**) を呼び出します。

クラス basic_istream のオブジェクトは、 \< **Elem**, **Tr**> クラス [basic_ios](../standard-library/basic-ios-class.md)の仮想パブリック基本オブジェクトのみを格納 **\<Elem**, **Tr>** します。

## <a name="example"></a>例

出力ストリームの詳細については、「[basic_ofstream クラス](../standard-library/basic-ofstream-class.md)」の例をご覧ください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[basic_ostream](#basic_ostream)|`basic_ostream` オブジェクトを構築します。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[揃える](#flush)|バッファーをフラッシュします。|
|[投入](#put)|ストリームに 1 文字渡します。|
|[seekp](#seekp)|出力ストリーム内の位置をリセットします。|
|[sentry](#sentry)|この入れ子になったクラスは、宣言によって書式設定された出力関数と書式設定されていない出力関数を構成するオブジェクトを記述します。|
|[スワップ](#swap)|`basic_ostream` オブジェクトの値を、指定した `basic_ostream` オブジェクトの値と交換します。|
|[tellp](#tellp)|出力ストリーム内の位置を報告します。|
|[企画](#write)|ストリームに文字を渡します。|

### <a name="operators"></a>オペレーター

|演算子|説明|
|-|-|
|[operator =](#op_eq)|指定された `basic_ostream` オブジェクト パラメーターの値をこのオブジェクトに代入します。|
|[<<演算子 ](#basic_ostream_operator_lt_lt)|ストリームに書き込みます。|

## <a name="requirements"></a>要件

**ヘッダー:**\<ostream>

**名前空間:** std

## <a name="basic_ostreambasic_ostream"></a><a name="basic_ostream"></a> basic_ostream:: basic_ostream

`basic_ostream` オブジェクトを構築します。

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>パラメーター

*strbuf*\
[basic_streambuf](../standard-library/basic-streambuf-class.md) 型のオブジェクト。

*_Isstd*\
**`true`** これが標準ストリームの場合は。それ以外の場合は **`false`** 。

*そうです*\
`basic_ostream` 型のオブジェクトへの右辺値参照。

### <a name="remarks"></a>解説

最初のコンストラクターは、 [init](../standard-library/basic-ios-class.md#init)() を呼び出すことによって基底クラスを初期化し `strbuf` ます。 2番目のコンストラクターは、 [basic_ios:: move](../standard-library/basic-ios-class.md#move)を呼び出して基底クラスを初期化し `(right)` ます。

### <a name="example"></a>例

出力ストリームの詳細については、「[basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream)」の例をご覧ください。

## <a name="basic_ostreamflush"></a><a name="flush"></a> basic_ostream:: flush

バッファーをフラッシュします。

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>戻り値

basic_ostream オブジェクトへの参照。

### <a name="remarks"></a>解説

[rdbuf](../standard-library/basic-ios-class.md#rdbuf) が Null ポインターではない場合、関数は **rdbuf->**[pubsync](../standard-library/basic-streambuf-class.md#pubsync) を呼び出します。 -1 を返す場合、関数は [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**) を呼び出します。 これは、 **\* これ** を返します。

### <a name="example"></a>例

```cpp
// basic_ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "test";
   cout.flush();
}
```

```Output
test
```

## <a name="basic_ostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt"></a> basic_ostream:: operator&lt;&lt;

ストリームに書き込みます。

```cpp
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

### <a name="parameters"></a>パラメーター

*Pfn*\
関数ポインター。

*strbuf*\
`stream_buf` オブジェクトを指すポインターです。

*val*\
ストリームに書き込む要素。

### <a name="return-value"></a>戻り値

basic_ostream オブジェクトへの参照。

### <a name="remarks"></a>解説

\<ostream> ヘッダーは複数のグローバル挿入演算子も定義します。 詳細については、「 [operator<<](../standard-library/ostream-operators.md#op_lt_lt)」を参照してください。

最初のメンバー関数は、フォームの式が `ostr << endl` [endl](../standard-library/ostream-functions.md#endl)**(ostr)** を呼び出し、 **\* これ** を返すことを保証します。 2 番目と 3 番目の関数は、[hex](../standard-library/ios-functions.md#hex) などの他のマニピュレーターが同じように動作することを保証します。 残りの関数はすべて書式付き出力関数です。

関数

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

strbuf が null ポインターではない場合、 *strbuf* から要素を抽出して挿入します。 抽出は、ファイルの終わりで、または抽出が (再スローされた) 例外をスローする場合に停止します。 また、挿入が失敗した場合は、対象の要素を抽出せずに停止します。 関数が要素を挿入しない場合、または抽出が例外をスローする場合、関数は [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**) を呼び出します。 いずれの場合も、関数は **\* this** を返します。

関数

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

`_Val`ブール値フィールドに変換し、 [use_facet](../standard-library/basic-filebuf-class.md#open) **<num_put \<Elem, OutIt>** `(` [getloc](../standard-library/ios-base-class.md#getloc)) を呼び出すことによって挿入します。 [put](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)), **\*this**, `getloc`, **val**) を呼び出します。 ここで `OutIt` は、は [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)として定義されてい **\<Elem, Tr>** ます。 関数は、 **\* これ** を返します。

関数

```cpp
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

各は、 *val* を数値フィールドに変換し、 **use_facet<num_put \<Elem, OutIt>**() を呼び出すことによって挿入し `getloc` ます。 **put**(**OutIt**( `rdbuf` )、 **\* this**、 `getloc` 、 **val**)。 ここでは、 **OutIt** は **ostreambuf_iterator \<Elem, Tr>** として定義されています。 関数は、 **\* これ** を返します。

関数

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

それぞれが *val* を数値フィールドに変換し、 **use_facet<num_put \<Elem, OutIt>**( `getloc` )**. put**(**OutIt**( `rdbuf` )、 **\* this**、 `getloc` 、 **val**) を呼び出すことによって挿入します。 ここでは、 **OutIt** は **ostreambuf_iterator \<Elem, Tr>** として定義されています。 関数は、 **\* これ** を返します。

### <a name="example"></a>例

```cpp
// basic_ostream_op_write.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```

## <a name="basic_ostreamoperator"></a><a name="op_eq"></a> basic_ostream:: operator =

指定された `basic_ostream` オブジェクト パラメーターの値をこのオブジェクトに代入します。

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`basic_ostream` オブジェクトへの `rvalue` 参照。

### <a name="remarks"></a>解説

このメンバー演算子は、swap `(right)` を呼び出します。

## <a name="basic_ostreamput"></a><a name="put"></a> basic_ostream::p ut

ストリームに 1 文字渡します。

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>パラメーター

*_Ch*\
単一の文字。

### <a name="return-value"></a>戻り値

basic_ostream オブジェクトへの参照。

### <a name="remarks"></a>解説

書式設定されていない出力関数は *_Ch* 要素を挿入します。 これは、 **\* これ** を返します。

### <a name="example"></a>例

```cpp
// basic_ostream_put.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout.put( 'v' );
   cout << endl;
   wcout.put( L'l' );
}
```

```Output
v
l
```

## <a name="basic_ostreamseekp"></a><a name="seekp"></a> basic_ostream:: seekp

出力ストリーム内の位置をリセットします。

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>パラメーター

*_Pos*\
ストリーム内の位置。

*_Off*\
*_Way* を基準としたオフセット。

*_Way*\
[ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) 列挙体のうちの 1 つ。

### <a name="return-value"></a>戻り値

basic_ostream オブジェクトへの参照。

### <a name="remarks"></a>解説

[Fail](../standard-library/basic-ios-class.md#fail)がの場合 **`false`** 、1つ目のメンバー関数は、一部の一時オブジェクトに対して **newpos =** [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos*) を呼び出し `pos_type` `newpos` ます。 `fail`が false の場合、2番目の関数は **newpos = rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(*_Off, _Way*) を呼び出します。 どちらの場合も、( `off_type` )**newpos = =** ( `off_type` ) (-1) (位置指定操作が失敗) の場合、関数は **istr を呼び出します。**[setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**)。 どちらの関数も、 **\* これ** を返します。

### <a name="example"></a>例

```cpp
// basic_ostream_seekp.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main()
{
    using namespace std;
    ofstream x("basic_ostream_seekp.txt");
    streamoff i = x.tellp();
    cout << i << endl;
    x << "testing";
    i = x.tellp();
    cout << i << endl;
    x.seekp(2);   // Put char in third char position in file
    x << " ";

    x.seekp(2, ios::end);   // Put char two after end of file
    x << "z";
}
```

```Output
0
7
```

## <a name="basic_ostreamsentry"></a><a name="sentry"></a> basic_ostream:: sentry

この入れ子になったクラスは、宣言によって書式設定された出力関数と書式設定されていない出力関数を構成するオブジェクトを記述します。

クラス sentry {public: explicit sentry (basic_ostream \<Elem, Tr>& _Ostr); 演算子 bool () const; ~ sentry ();};

### <a name="remarks"></a>解説

この入れ子になったクラスは、宣言によって書式設定された出力関数と書式設定されていない出力関数を構成するオブジェクトを記述します。 **Ostr の場合。**[すばらしい](../standard-library/basic-ios-class.md#good)のは **`true`** 、 **ostr です。**[関連付け](../standard-library/basic-ios-class.md#tie)が null ポインターではありません。コンストラクターは、 **>の**[フラッシュ](#flush)を呼び出します。 次に、コンストラクターは、によって返された値をに格納し `ostr.good` `status` ます。 後でを呼び出すと、 `operator bool` この格納された値が配信されます。

が `uncaught_exception` を返し、 **`false`** [flags](../standard-library/ios-base-class.md#flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf) が0以外の場合、デストラクターは [flush](#flush)を呼び出します。

## <a name="basic_ostreamswap"></a><a name="swap"></a> basic_ostream:: swap

`basic_ostream` オブジェクトの値を、指定した `basic_ostream` の値と交換します。

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
`basic_ostream` オブジェクトへの参照です。

### <a name="remarks"></a>解説

このメンバー関数は、 [basic_ios:: swap](../standard-library/basic-ios-class.md#swap)を呼び出して、 `(right)` このオブジェクトの内容を *右* の内容と交換します。

## <a name="basic_ostreamtellp"></a><a name="tellp"></a> basic_ostream:: tellp

出力ストリーム内の位置を報告します。

```cpp
pos_type tellp();
```

### <a name="return-value"></a>戻り値

出力ストリーム内の位置。

### <a name="remarks"></a>解説

[Fail](../standard-library/basic-ios-class.md#fail)がの場合 **`false`** 、メンバー関数は [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur` , **in**) を返します。 それ以外の場合は、`pos_type`(-1) を返します。

### <a name="example"></a>例

`tellp` の使用例は、「[seekp](#seekp)」を参照してください。

## <a name="basic_ostreamwrite"></a><a name="write"></a> basic_ostream:: write

ストリームに文字を渡します。

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>パラメーター

*数*\
ストリームに渡す文字の数。

*引数*\
ストリームに渡す文字。

### <a name="return-value"></a>戻り値

basic_ostream オブジェクトへの参照。

### <a name="remarks"></a>解説

書式設定されていない [出力関数](../standard-library/basic-ostream-class.md)は、 *str* から始まる *カウント* 要素のシーケンスを挿入します。

### <a name="example"></a>例

`write` の使用例は、「[streamsize](../standard-library/ios-typedefs.md#streamsize)」を参照してください。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream プログラミング](../standard-library/iostream-programming.md)\
[iostreams の規則](../standard-library/iostreams-conventions.md)
