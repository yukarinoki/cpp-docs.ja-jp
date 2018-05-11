---
title: '&lt;iomanip&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iomanip/std::get_money
- iomanip/std::get_time
- iomanip/std::put_money
- iomanip/std::put_time
- iomanip/std::quoted
- iomanip/std::resetiosflags
- iomanip/std::setbase
- iomanip/std::setfill
- iomanip/std::setiosflags
- iomanip/std::setprecision
- iomanip/std::setw
ms.assetid: 3ddde610-70cc-4cfa-8a89-3e83d1d356a8
helpviewer_keywords:
- std::get_money [C++]
- std::get_time [C++]
- std::put_money [C++]
- std::put_time [C++]
- std::quoted [C++]
- std::resetiosflags [C++]
- std::setbase [C++]
- std::setfill [C++]
- std::setiosflags [C++]
- std::setprecision [C++]
- std::setw [C++]
ms.openlocfilehash: 5e491b9dc5035435fce16b704d28a71a1b0644de
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ltiomanipgt-functions"></a>&lt;iomanip&gt; 関数

||||
|-|-|-|
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|
|[put_time](#iomanip_put_time)|[quoted](#quoted)|[resetiosflags](#resetiosflags)|
|[setbase](#setbase)|[setfill](#setfill)|[setiosflags](#setiosflags)|
|[setprecision](#setprecision)|[setw](#setw)|

## <a name="iomanip_get_money"></a>  get_money

目的の形式を使用して、ストリームから通貨値を抽出し、パラメーターの値を返します。

```cpp
template <class Money>
T7 get_money(Money& _Amount, bool _Intl);
```

### <a name="parameters"></a>パラメーター

_Amount 抽出する通貨値。

_Intl 場合`true`、国際化の形式を使用します。 既定値は `false` です。

### <a name="remarks"></a>コメント

マニピュレーターは、ストリーム `str` から抽出されたときに、国際対応形式を示す `_Intl` を使用して、`str` に関連付けられているロケール ファセット `money_get` のメンバー関数 `get` を呼び出す `formatted input function` として動作するオブジェクトを返します。 成功すると、この呼び出しによって、抽出された通貨値が `_Amount` に格納されます。 その後、マニピュレーターが `str` を返します。

`Money` は `long double` 型であるか、`str` と同じ要素および特徴パラメーターを持つ `basic_string` のインスタンス化である必要があります。

## <a name="iomanip_get_time"></a>  get_time

目的の形式を使用して、ストリームから時刻値を抽出します。 時間構造体として、パラメーターの値を返します。

```cpp
template <class Elem>
T10 put_time(struct tm *_Tptr, const Elem *_Fmt);
```

### <a name="parameters"></a>パラメーター

`_Tptr` 時間の構造体の形式の時間です。

`_Fmt` 目的の形式を使用して、時刻の値を取得します。

### <a name="remarks"></a>コメント

マニピュレーターは、ストリーム `str` から抽出されたときに、時間構造体を示す `tptr` および null で終わる書式文字列の先頭を示す `fmt` を使用して、`str` に関連付けられているロケール ファセット `time_get` のメンバー関数 `get` を呼び出す `formatted input function` として動作するオブジェクトを返します。 成功した場合、この呼び出しによって、抽出された時刻フィールドに関連付けられている値が時間構造体に格納されます。 その後、マニピュレーターが `str` を返します。

## <a name="iomanip_put_money"></a>  put_money

目的の形式を使用してストリームに金額を挿入します。

```cpp
template <class Money>
T8 put_money(const Money& _Amount, bool _Intl);
```

### <a name="parameters"></a>パラメーター

`_Amount` ストリームに挿入する金額です。

`_Intl` 設定`true`マニピュレーターは、国際化の形式を使用する必要がある場合`false`が不要な場合です。

### <a name="return-value"></a>戻り値

`str` を返します。

### <a name="remarks"></a>コメント

マニピュレーターは、ストリーム `str` に挿入されたときに、`str` に関連付けられているロケール ファセット `money_put` のメンバー関数 `put` を呼び出す書式付き出力関数として動作するオブジェクトを返します。 成功した場合、この呼び出しは、充てん要素として国際対応形式および `str.fill()` を示す `_Intl` を使用して、適切に書式設定された `amount` を挿入します。 その後、マニピュレーターが `str` を返します。

`Money` は `long double` 型であるか、`str` と同じ要素および特徴パラメーターを持つ `basic_string` のインスタンス化である必要があります。

## <a name="iomanip_put_time"></a>  put_time

指定された形式を使用して、時間構造体内の時刻値をストリームに書き込みます。

```cpp
template <class Elem>
T10 put_time(struct tm* _Tptr, const Elem* _Fmt);
```

### <a name="parameters"></a>パラメーター

`_Tptr` 時間の構造体で提供される、ストリームに書き込む時間値です。

`_Fmt` 時刻値の書き込みに必要な形式です。

### <a name="remarks"></a>コメント

マニピュレーターは、ストリーム `str` に挿入されるときに、`formatted output function` として動作するオブジェクトを返します。 出力関数は、`str` に関連付けられているロケール ファセット `time_put` のメンバー関数 `put` を呼び出します。 出力関数は、`_Tptr` を使用して時間構造体を示し、`_Fmt` を使用して NUL で終わる書式文字列の先頭を示します。 成功した場合、この呼び出しは、書式文字列からのリテラル テキストと時間構造体からの変換された値を挿入します。 その後、マニピュレーターが `str` を返します。

## <a name="quoted"></a>  quoted

**(C++14 の新機能)** >> 演算子と << 演算子を使用したストリームとの文字列のラウンド トリップを有効にする、便利な iostream マニピュレーター。

```cpp
quoted(std::string str) // or wstring
quoted(const char* str) //or wchar_t*
quoted(std::string str, char delimiter, char escape) // or wide versions
quoted(const char* str, char delimiter, char escape) // or wide versions
```

### <a name="parameters"></a>パラメーター

`str` Std::string、char *、文字列リテラルまたは未加工文字列リテラル、またはこれらの様々 なバージョン (例えば std::wstring, wchar_t\*)。

`delimiter` ユーザー指定の文字またはワイド文字、先頭と文字列の末尾の区切り記号として使用します。

`escape` ユーザー指定の文字またはワイド文字、文字列内のエスケープ シーケンスのエスケープ文字として使用します。

### <a name="remarks"></a>コメント

「[挿入演算子と制御形式の使用](../standard-library/using-insertion-operators-and-controlling-format.md)」を参照してください。

### <a name="example"></a>例

この例では、ナロー文字列を使用した既定の区切り文字とエスケープ文字と共に `quoted` を使用する方法を示します。 ワイド文字列は、同様にサポートされています。

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_quoted_v_nonquoted()
{
    // Results are identical regardless of input string type:
    // string inserted { R"(This is a "sentence".)" }; // raw string literal
    // string inserted { "This is a \"sentence\"." };  // regular string literal
    const char* inserted = "This is a \"sentence\".";  // const char*
    stringstream ss, ss_quoted;
    string extracted, extracted_quoted;

    ss << inserted;
    ss_quoted << quoted(inserted);

    cout << "ss.str() is storing       : " << ss.str() << endl;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl << endl;

    // Round-trip the strings
    ss >> extracted;
    ss_quoted >> quoted(extracted_quoted);

    cout << "After round trip: " << endl;
    cout << "Non-quoted      : " << extracted << endl;
    cout << "Quoted          : " << extracted_quoted << endl;
}

void main(int argc, char* argv[])
{
    show_quoted_v_nonquoted();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}

/* Output:
ss.str() is storing       : This is a "sentence".
ss_quoted.str() is storing: "This is a \"sentence\"."

After round trip:
Non-quoted      : This
Quoted          : This is a "sentence".

Press Enter to exit
*/
```

### <a name="example"></a>例

カスタムの区切り記号やエスケープ文字を指定する方法を次に示します。

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_custom_delimiter()
{
    string inserted{ R"("This" "is" "a" "heavily-quoted" "sentence".)" };
    // string inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    // const char* inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    stringstream ss, ss_quoted;
    string extracted;

    ss_quoted << quoted(inserted, '*');
    ss << inserted;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl;
    cout << "ss.str() is storing       : " << ss.str() << endl << endl;

    // Use the same quoted arguments as on insertion.
    ss_quoted >> quoted(extracted, '*');

    cout << "After round trip: " << endl;
    cout << "Quoted          : " << extracted << endl;

    extracted = {};
    ss >> extracted;
    cout << "Non-quoted      : " << extracted << endl << endl;
}

void show_custom_escape()
{
    string inserted{ R"(\\root\trunk\branch\nest\egg\yolk)" };
    // string inserted{ "\\\\root\\trunk\\branch\\nest\\egg\\yolk" };
    stringstream ss, ss_quoted, ss_quoted_custom;
    string extracted;

    // Use '"' as delimiter and '~' as escape character.
    ss_quoted_custom << quoted(inserted, '"', '~');
    ss_quoted << quoted(inserted);
    ss << inserted;
    cout << "ss_quoted_custom.str(): " << ss_quoted_custom.str() << endl;
    cout << "ss_quoted.str()       : " << ss_quoted.str() << endl;
    cout << "ss.str()              : " << ss.str() << endl << endl;

    // No spaces in this string, so non-quoted behaves same as quoted
    // after round-tripping.
}

void main(int argc, char* argv[])
{
    cout << "Custom delimiter:" << endl;
    show_custom_delimiter();
    cout << "Custom escape character:" << endl;
    show_custom_escape();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}
/* Output:
Custom delimiter:
ss_quoted.str() is storing: *"This" "is" "a" "heavily-quoted" "sentence".*
ss.str() is storing       : "This" "is" "a" "heavily-quoted" "sentence".

After round trip:
Quoted          : "This" "is" "a" "heavily-quoted" "sentence".
Non-quoted      : "This"

Custom escape character:
ss_quoted_custom.str(): "\\root\trunk\branch\nest\egg\yolk"
ss_quoted.str()       : "\\\\root\\trunk\\branch\\nest\\egg\\yolk"
ss.str()              : \\root\trunk\branch\nest\egg\yolk

Press Enter to exit
*/

```

## <a name="resetiosflags"></a>  resetiosflags

指定したフラグをクリアします。

```cpp
T1 resetiosflags(ios_base::fmtflags Mask);
```

### <a name="parameters"></a>パラメーター

`Mask` オフにするフラグ。

### <a name="return-value"></a>戻り値

マニピュレーター オブジェクトを返しますから取り出した、またはストリームに挿入されたときに**str**、呼び出し**str**です。 [setf](../standard-library/ios-base-class.md#setf)( `ios_base::` [fmtflags](../standard-library/ios-base-class.md#fmtflags)、_*マスク*)、しを返します**str**です。

### <a name="example"></a>例

`resetiosflags` の使用例については、「[setw](../standard-library/iomanip-functions.md#setw)」を参照してください。

## <a name="setbase"></a>  setbase

整数の基数を設定します。

```cpp
T3 setbase(int _Base);
```

### <a name="parameters"></a>パラメーター

`_Base` 数値の底です。

### <a name="return-value"></a>戻り値

マニピュレーター オブジェクトを返しますから取り出した、またはストリームに挿入されたときに**str**、呼び出し**str**です。 `setf`(**マスク**、 [ios_base::basefield](../standard-library/ios-base-class.md#fmtflags))、しを返します**str**です。 ここで、**mask** は、次のように判断されます。

- _ *Base* が 8 の場合、**mask** は `ios_base::`[oct](../standard-library/ios-functions.md#oct) になります。

- _ *Base* が 10 の場合、mask は `ios_base::`[dec](../standard-library/ios-functions.md#dec) になります。

- _ *Base* が 16 の場合、**mask** は `ios_base::`[hex](../standard-library/ios-functions.md#hex) になります。

- _ *Base* がその他の値の場合、mask は `ios_base::`[fmtflags](../standard-library/ios-base-class.md#fmtflags)(0) になります。

### <a name="example"></a>例

`setbase` の使用例については、「[setw](../standard-library/iomanip-functions.md#setw)」を参照してください。

## <a name="setfill"></a>  setfill

右揃えの表示でスペースを埋めるために使用する文字を設定します。

```cpp
template <class Elem>
T4 setfill(Elem Ch);
```

### <a name="parameters"></a>パラメーター

`Ch` 右揃えの表示でスペースを埋めるために使用する文字。

### <a name="return-value"></a>戻り値

テンプレート マニピュレーター オブジェクトを返しますから取り出した、またはストリームに挿入されたときに**str**、呼び出し**str**です。 [塗りつぶし](../standard-library/basic-ios-class.md#fill)( `Ch`)、しを返します**str**です。 **Elem** 型は、ストリーム **str** の要素型と同じである必要があります。

### <a name="example"></a>例

`setfill` の使用例については、「[setw](../standard-library/iomanip-functions.md#setw)」を参照してください。

## <a name="setiosflags"></a>  setiosflags

指定したフラグを設定します。

```cpp
T2 setiosflags(ios_base::fmtflags Mask);
```

### <a name="parameters"></a>パラメーター

`Mask` 設定するフラグ。

### <a name="return-value"></a>戻り値

マニピュレーター オブジェクトを返しますから取り出した、またはストリームに挿入されたときに**str**、呼び出し**str**です。 [setf](../standard-library/ios-base-class.md#setf)(_*マスク*)、しを返します**str**です。

### <a name="example"></a>例

`setiosflags` の使用例については、「[setw](../standard-library/iomanip-functions.md#setw)」を参照してください。

## <a name="setprecision"></a>  setprecision

浮動小数点値の有効桁数を設定します。

```cpp
T5 setprecision(streamsize Prec);
```

### <a name="parameters"></a>パラメーター

`Prec` 浮動小数点値の有効桁数です。

### <a name="return-value"></a>戻り値

マニピュレーター オブジェクトを返しますから取り出した、またはストリームに挿入されたときに**str**、呼び出し**str**です。 [有効桁数](../standard-library/ios-base-class.md#precision)( `Prec`)、しを返します**str**です。

### <a name="example"></a>例

`setprecision` の使用例については、「[setw](../standard-library/iomanip-functions.md#setw)」を参照してください。

## <a name="setw"></a>  setw

ストリーム内の次の要素に対して表示フィールドの幅を指定します。

```cpp
T6 setw(streamsize Wide);
```

### <a name="parameters"></a>パラメーター

`Wide` 表示フィールドの幅。

### <a name="return-value"></a>戻り値

マニピュレーター オブジェクトを返しますから取り出した、またはストリームに挿入されたときに**str**、呼び出し**str**です。 [幅](../standard-library/ios-base-class.md#width)(_*ワイド*)、しを返します**str**です。

### <a name="remarks"></a>コメント

setw は、ストリーム内の次の要素についてのみ幅を設定します。幅を指定する各要素の前に setw を挿入する必要があります。

### <a name="example"></a>例

```cpp
// iomanip_setw.cpp
// compile with: /EHsc
// Defines the entry point for the console application.
//
// Sample use of the following manipulators:
//   resetiosflags
//   setiosflags
//   setbase
//   setfill
//   setprecision
//   setw

#include <iostream>
#include <iomanip>

using namespace std;

const double   d1 = 1.23456789;
const double   d2 = 12.3456789;
const double   d3 = 123.456789;
const double   d4 = 1234.56789;
const double   d5 = 12345.6789;
const long      l1 = 16;
const long      l2 = 256;
const long      l3 = 1024;
const long      l4 = 4096;
const long      l5 = 65536;
int         base = 10;

void DisplayDefault( )
{
   cout << endl << "default display" << endl;
   cout << "d1 = " << d1 << endl;
   cout << "d2 = " << d2 << endl;
   cout << "d3 = " << d3 << endl;
   cout << "d4 = " << d4 << endl;
   cout << "d5 = " << d5 << endl;
}

void DisplayWidth( int n )
{
   cout << endl << "fixed width display set to " << n << ".\n";
   cout << "d1 = " << setw(n) << d1 << endl;
   cout << "d2 = " << setw(n) << d2 << endl;
   cout << "d3 = " << setw(n) << d3 << endl;
   cout << "d4 = " << setw(n) << d4 << endl;
   cout << "d5 = " << setw(n) << d5 << endl;
}

void DisplayLongs( )
{
   cout << setbase(10);
   cout << endl << "setbase(" << base << ")" << endl;
   cout << setbase(base);
   cout << "l1 = " << l1 << endl;
   cout << "l2 = " << l2 << endl;
   cout << "l3 = " << l3 << endl;
   cout << "l4 = " << l4 << endl;
   cout << "l5 = " << l5 << endl;
}

int main( int argc, char* argv[] )
{
   DisplayDefault( );

   cout << endl << "setprecision(" << 3 << ")" << setprecision(3);
   DisplayDefault( );

   cout << endl << "setprecision(" << 12 << ")" << setprecision(12);
   DisplayDefault( );

   cout << setiosflags(ios_base::scientific);
   cout << endl << "setiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << resetiosflags(ios_base::scientific);
   cout << endl << "resetiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << endl << "setfill('" << 'S' << "')" << setfill('S');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setfill('" << ' ' << "')" << setfill(' ');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setprecision(" << 8 << ")" << setprecision(8);
   DisplayWidth(10);
   DisplayDefault( );

   base = 16;
   DisplayLongs( );

   base = 8;
   DisplayLongs( );

   base = 10;
   DisplayLongs( );

   return   0;
}
```

```Output

default display
d1 = 1.23457
d2 = 12.3457
d3 = 123.457
d4 = 1234.57
d5 = 12345.7

setprecision(3)
default display
d1 = 1.23
d2 = 12.3
d3 = 123
d4 = 1.23e+003
d5 = 1.23e+004

setprecision(12)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setiosflags(4096)
default display
d1 = 1.234567890000e+000
d2 = 1.234567890000e+001
d3 = 1.234567890000e+002
d4 = 1.234567890000e+003
d5 = 1.234567890000e+004

resetiosflags(4096)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill('S')
fixed width display set to 15.
d1 = SSSSS1.23456789
d2 = SSSSS12.3456789
d3 = SSSSS123.456789
d4 = SSSSS1234.56789
d5 = SSSSS12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill(' ')
fixed width display set to 15.
d1 =      1.23456789
d2 =      12.3456789
d3 =      123.456789
d4 =      1234.56789
d5 =      12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setprecision(8)
fixed width display set to 10.
d1 =  1.2345679
d2 =  12.345679
d3 =  123.45679
d4 =  1234.5679
d5 =  12345.679

default display
d1 = 1.2345679
d2 = 12.345679
d3 = 123.45679
d4 = 1234.5679
d5 = 12345.679

setbase(16)
l1 = 10
l2 = 100
l3 = 400
l4 = 1000
l5 = 10000

setbase(8)
l1 = 20
l2 = 400
l3 = 2000
l4 = 10000
l5 = 200000

setbase(10)
l1 = 16
l2 = 256
l3 = 1024
l4 = 4096
l5 = 65536
```

## <a name="see-also"></a>関連項目

[\<iomanip>](../standard-library/iomanip.md)<br/>
