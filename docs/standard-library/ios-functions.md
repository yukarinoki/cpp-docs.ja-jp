---
title: '&lt;ios&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- xiosbase/std::defaultfloat
- xiosbase/std::boolalpha
- xiosbase/std::dec
- ios/std::fixed
- ios/std::hex
- ios/std::internal
- ios/std::left
- ios/std::noboolalpha
- ios/std::noshowbase
- ios/std::noshowpoint
- ios/std::noshowpos
- ios/std::noskipws
- ios/std::nounitbuf
- ios/std::nouppercase
- ios/std::oct
- ios/std::right
- ios/std::scientific
- ios/std::showbase
- ios/std::showpoint
- ios/std::showpos
- ios/std::skipws
- ios/std::unitbuf
- ios/std::uppercase
ms.assetid: 1382d53f-e531-4b41-adf6-6a1543512e51
helpviewer_keywords:
- std::defaultfloat [C++]
- std::boolalpha [C++]
- std::dec [C++]
- std::fixed [C++]
- std::hex [C++]
- std::internal [C++]
- std::left [C++]
- std::noboolalpha [C++]
- std::noshowbase [C++]
- std::noshowpoint [C++]
- std::noshowpos [C++]
- std::noskipws [C++]
- std::nounitbuf [C++]
- std::nouppercase [C++]
- std::oct [C++]
- std::right [C++]
- std::scientific [C++]
- std::showbase [C++]
- std::showpoint [C++]
- std::showpos [C++]
- std::skipws [C++]
- std::unitbuf [C++]
- std::uppercase [C++]
ms.openlocfilehash: a19d023400179e1e7e16541b7e3d7ef38ad963ba
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101094"
---
# <a name="ltiosgt-functions"></a>&lt;ios&gt; 関数

||||
|-|-|-|
|[defaultfloat](#ios_defaultfloat)|[boolalpha](#boolalpha)|[dec](#dec)|
|[fixed](#fixed)|[hex](#hex)|[internal](#internal)|
|[left](#left)|[noboolalpha](#noboolalpha)|[noshowbase](#noshowbase)|
|[noshowpoint](#noshowpoint)|[noshowpos](#noshowpos)|[noskipws](#noskipws)|
|[nounitbuf](#nounitbuf)|[nouppercase](#nouppercase)|[oct](#oct)|
|[right](#right)|[scientific](#scientific)|[showbase](#showbase)|
|[showpoint](#showpoint)|[showpos](#showpos)|[skipws](#skipws)|
|[unitbuf](#unitbuf)|[uppercase](#uppercase)|

## <a name="boolalpha"></a>  boolalpha

[bool](../cpp/bool-cpp.md) 型の変数をストリームで **true** または **false** として表示するように指定します。

```cpp
ios_base& boolalpha(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

既定では、型の変数によって**bool**は 1 または 0 として表示されます。

`boolalpha` 効果的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::boolalpha`)、し、返します*str*します。

[noboolalpha](../standard-library/ios-functions.md#noboolalpha) は `boolalpha` の実行結果を元に戻します。

### <a name="example"></a>例

```cpp
// ios_boolalpha.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   bool b = true;
   cout << b << endl;
   boolalpha( cout );
   cout << b << endl;
   noboolalpha( cout );
   cout << b << endl;
   cout << boolalpha << b << endl;
}
```

```Output
1
true
1
true
```

## <a name="dec"></a>  dec

整数変数を 10 進表記で表示するように指定します。

```cpp
ios_base& dec(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

既定では、整数変数は、10 進表記で表示されます。

`dec` 効果的に呼び出す`str.` [setf](../standard-library/ios-base-class.md#setf)( `ios_base::dec`、 `ios_base::basefield`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_dec.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 100;

   cout << i << endl;   // Default is base 10
   cout << hex << i << endl;
   dec( cout );
   cout << i << endl;
   oct( cout );
   cout << i << endl;
   cout << dec << i << endl;
}
```

```Output
100
64
100
144
100
```

## <a name="ios_defaultfloat"></a>  &lt;ios&gt; defaultfloat

浮動小数値に既定の表示形式を使用するように、`ios_base` オブジェクトのフラグを構成します。

```cpp
ios_base& defaultfloat(ios_base& _Iosbase);
```

### <a name="parameters"></a>パラメーター

*されている _Iosbase*<br/>
`ios_base` オブジェクト。

### <a name="remarks"></a>Remarks

マニピュレーターは実質的に _I `osbase.`[ios_base::unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::floatfield)` を呼び出し、_I `osbase` を返します。

## <a name="fixed"></a>  fixed

浮動小数点数を固定 10 進表記で表示するように指定します。

```cpp
ios_base& fixed(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

`fixed` 浮動小数点数の既定の表示の表記です。 [scientific](../standard-library/ios-functions.md#scientific) は、浮動小数点数を指数表記を使用して表示します。

マニピュレーターは実質的に呼び出す * str.*[setf](../standard-library/ios-base-class.md#setf)( `ios_base::fixed`、 `ios_base::floatfield`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_fixed.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 1.1F;

   cout << i << endl;   // fixed is the default
   cout << scientific << i << endl;
   cout.precision( 1 );
   cout << fixed << i << endl;
}
```

```Output
1.1
1.100000e+000
1.1
```

## <a name="hex"></a>  hex

整数変数を 16 進表記で表示するように指定します。

```cpp
ios_base& hex(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

既定では、整数変数は、10 進表記で表示されます。 [dec](../standard-library/ios-functions.md#dec) および [oct](../standard-library/ios-functions.md#oct) も整数変数の表示方法を変更します。

マニピュレーターは実質的に呼び出す`str` **.**[setf](../standard-library/ios-base-class.md#setf)( `ios_base::hex`、 `ios_base::basefield`)、し、返します*str*します。

### <a name="example"></a>例

参照してください[dec](../standard-library/ios-functions.md#dec)を使用する方法の例については`hex`します。

## <a name="internal"></a>  internal

数値の符号を左揃え、数値を右揃えにします。

```cpp
ios_base& internal(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

元のオブジェクトへの参照*str*が派生します。

### <a name="remarks"></a>Remarks

[showpos](../standard-library/ios-functions.md#showpos) によって、正の数値に符号が表示されます。

マニピュレーターは実質的に呼び出す`str`します。 [setf](../standard-library/ios-base-class.md#setf)( [ios_base::internal](../standard-library/ios-base-class.md#fmtflags)、 [ios_base::adjustfield](../standard-library/ios-base-class.md#fmtflags))、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_internal.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( void )
{
   using namespace std;
   float i = -123.456F;
   cout.fill( '.' );
   cout << setw( 10 ) << i << endl;
   cout << setw( 10 ) << internal << i << endl;
}
```

```Output
..-123.456
-..123.456
```

## <a name="left"></a>  left

出力幅に満たないテキストをストリーム フラッシュで左揃えに表示します。

```cpp
ios_base& left(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::left`、 `ios_base::adjustfield`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_left.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout.width( 20 );
   cout << f1 << endl;
   cout << left << f1 << endl;
}
```

```Output
                   5
5
```

## <a name="noboolalpha"></a>  noboolalpha

[bool](../cpp/bool-cpp.md) 型の変数をストリームで 1 または 0 として表示するように指定します。

```cpp
ios_base& noboolalpha(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

既定では、`noboolalpha` は有効です。

`noboolalpha` 効果的に呼び出す`str`.[unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::boolalpha`)、し、返します*str*します。

[boolalpha](../standard-library/ios-functions.md#boolalpha) は `noboolalpha` の実行結果を元に戻します。

### <a name="example"></a>例

`noboolalpha` の使用例については、「[boolalpha](../standard-library/ios-functions.md#boolalpha)」を参照してください。

## <a name="noshowbase"></a>  noshowbase

指定している数値表記の基底の設定をオフにします。

```cpp
ios_base& noshowbase(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

`noshowbase` は既定でオンになります。 [showbase](../standard-library/ios-functions.md#showbase) を使用して、数値表記の基底を示します。

マニピュレーターは実質的に呼び出す`str`.[unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showbase`)、し、返します*str*します。

### <a name="example"></a>例

`noshowbase` の使用例については、「[showbase](../standard-library/ios-functions.md#showbase)」を参照してください。

## <a name="noshowpoint"></a>  noshowpoint

小数部分が 0 の浮動小数点数の整数部分のみを表示します。

```cpp
ios_base& noshowpoint(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

`noshowpoint` は既定ではオンです。[showpoint](../standard-library/ios-functions.md#showpoint) と [precision](../standard-library/ios-base-class.md#precision) を使用して、小数点の後に 0 を表示します。

マニピュレーターは実質的に呼び出す`str`.[unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showpoint`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_noshowpoint.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.000;
   cout << f1 << endl;   // noshowpoint is default
   cout.precision( 4 );
   cout << showpoint << f1 << endl;
   cout << noshowpoint << f1 << endl;
}
```

```Output
5
5.000
5
```

## <a name="noshowpos"></a>  noshowpos

正の数値に明示的に符号を付けないようにします。

```cpp
ios_base& noshowpos(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

`noshowpos` は既定でオンになります。

マニピュレーターは実質的に呼び出す`str`.[unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::showps`)、戻ります*str*します。

### <a name="example"></a>例

`noshowpos` の使用例については、「[showpos](../standard-library/ios-functions.md#showpos)」を参照してください。

## <a name="noskipws"></a>  noskipws

入力ストリームで空白を読み取るようにします。

```cpp
ios_base& noskipws(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

既定では、[skipws](../standard-library/ios-functions.md#skipws) は有効です。 入力ストリームでスペースが読み込まれると、バッファーの終了を通知します。

マニピュレーターは実質的に呼び出す`str`.[unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::skipws`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_noskipws.cpp
// compile with: /EHsc
#include <iostream>
#include <string>

int main() {
   using namespace std;
   string s1, s2, s3;
   cout << "Enter three strings: ";
   cin >> noskipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

## <a name="nounitbuf"></a>  nounitbuf

出力をバッファーし、バッファーが一杯になると、出力を処理します。

```cpp
ios_base& nounitbuf(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

[unitbuf](../standard-library/ios-functions.md#unitbuf) はバッファーが空ではないときに、バッファーを処理します。

マニピュレーターは実質的に呼び出す`str`.[unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::unitbuf`)、し、返します*str*します。

## <a name="nouppercase"></a>  nouppercase

16 進数と指数表記の指数を小文字で表示します。

```cpp
ios_base& nouppercase(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

マニピュレーターは実質的に呼び出す`str`.[unsetf](../standard-library/ios-base-class.md#unsetf)( `ios_base::uppercase`)、し、返します*str*します。

### <a name="example"></a>例

`nouppercase` の使用例については、「[uppercase](../standard-library/ios-functions.md#uppercase)」を参照してください。

## <a name="oct"></a>  oct

整数変数を 8 進表記で表示するように指定します。

```cpp
ios_base& oct(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

元のオブジェクトへの参照*str*が派生します。

### <a name="remarks"></a>Remarks

既定では、整数変数は、10 進表記で表示されます。 [dec](../standard-library/ios-functions.md#dec) および [hex](../standard-library/ios-functions.md#hex) も整数変数の表示方法を変更します。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::oct`、 `ios_base::basefield`)、し、返します*str*します。

### <a name="example"></a>例

参照してください[dec](../standard-library/ios-functions.md#dec)を使用する方法の例については`oct`します。

## <a name="right"></a>  right

出力幅に満たないテキストをストリーム フラッシュで右揃えに表示します。

```cpp
ios_base& right(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

元のオブジェクトへの参照*str*が派生します。

### <a name="remarks"></a>Remarks

[left](../standard-library/ios-functions.md#left) もテキストの両端揃えを変更します。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::right`、 `ios_base::adjustfield`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_right.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << left << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << right << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
}
```

```Output
5
                   5
5
5
                   5
                   5
```

## <a name="scientific"></a>  scientific

浮動小数点数を指数表記を使用して表示します。

```cpp
ios_base& scientific(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

既定では、[fixed](../standard-library/ios-functions.md#fixed) 表記は浮動小数点数に対して有効です。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::scientific`、 `ios_base::floatfield`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_scientific.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 100.23F;

   cout << i << endl;
   cout << scientific << i << endl;
}
```

```Output
100.23
1.002300e+002
```

## <a name="showbase"></a>  showbase

数値表記の基底を指定します。

```cpp
ios_base& showbase(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

数値表記の基底は、[dec](../standard-library/ios-functions.md#dec)、[oct](../standard-library/ios-functions.md#oct)、または [hex](../standard-library/ios-functions.md#hex) を使用して変更できます。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::showbase`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_showbase.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int j = 100;

   cout << showbase << j << endl;   // dec is default
   cout << hex << j << showbase << endl;
   cout << oct << j << showbase << endl;

   cout << dec << j << noshowbase << endl;
   cout << hex << j << noshowbase << endl;
   cout << oct << j << noshowbase << endl;
}
```

```Output
100
0x64
0144
100
64
144
```

## <a name="showpoint"></a>  showpoint

小数部分が 0 のときも浮動小数点数の整数部分と小数点の右側にある数字を表示します。

```cpp
ios_base& showpoint(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

既定では、[noshowpoint](../standard-library/ios-functions.md#noshowpoint) は有効です。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::showpoint`)、し、返します*str*します。

### <a name="example"></a>例

`showpoint` の使用例については、「[noshowpoint](../standard-library/ios-functions.md#noshowpoint)」を参照してください。

## <a name="showpos"></a>  showpos

正の数値に明示的に符号を付けます。

```cpp
ios_base& showpos(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

[noshowpos](../standard-library/ios-functions.md#noshowpos) が既定の設定です。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::showpos`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_showpos.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 1;

   cout << noshowpos << i << endl;   // noshowpos is default
   cout << showpos << i << endl;
}
```

```Output
1
+1
```

## <a name="skipws"></a>  skipws

入力ストリームで空白を読み飛ばします。

```cpp
ios_base& skipws(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

_ *Str* の派生元となるオブジェクトへの参照。

### <a name="remarks"></a>Remarks

既定では、`skipws` は有効です。 [noskipws](../standard-library/ios-functions.md#noskipws) は、入力ストリームから空白を読み取るようにします。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( `ios_base::skipws`)、し、返します*str*します。

### <a name="example"></a>例

```cpp
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   char s1, s2, s3;
   cout << "Enter three characters: ";
   cin >> skipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

```Output

1 2 3

```

```Output

      1 2 3.1.
.2.
.3.
```

## <a name="unitbuf"></a>  unitbuf

バッファーが空ではないときに、出力を処理します。

```cpp
ios_base& unitbuf(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

元のオブジェクトへの参照*str*が派生します。

### <a name="remarks"></a>Remarks

`endl` もバッファーをフラッシュします。

既定では、[nounitbuf](../standard-library/ios-functions.md#nounitbuf) は有効です。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( [ios_base::unitbuf](../standard-library/ios-base-class.md#fmtflags))、し、返します*str*します。

## <a name="uppercase"></a>  uppercase

16 進数と指数表記の指数を大文字で表示します。

```cpp
ios_base& uppercase(ios_base& str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
[ios_base](../standard-library/ios-base-class.md) 型のオブジェクトまたは `ios_base` から継承した型への参照。

### <a name="return-value"></a>戻り値

元のオブジェクトへの参照*str*が派生します。

### <a name="remarks"></a>Remarks

既定では、[nouppercase](../standard-library/ios-functions.md#nouppercase) は有効です。

マニピュレーターは実質的に呼び出す`str`.[setf](../standard-library/ios-base-class.md#setf)( [ios_base::uppercase](../standard-library/ios-base-class.md#fmtflags))、し、返します*str*します。

### <a name="example"></a>例

```cpp
// ios_uppercase.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
   using namespace std;

   double i = 1.23e100;
   cout << i << endl;
   cout << uppercase << i << endl;

   int j = 10;
   cout << hex << nouppercase << j << endl;
   cout << hex << uppercase << j << endl;
}
```

```Output
1.23e+100
1.23E+100
a
A
```

## <a name="see-also"></a>関連項目

[\<ios>](../standard-library/ios.md)<br/>
