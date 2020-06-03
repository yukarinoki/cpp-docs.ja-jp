---
title: time_put クラス
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
helpviewer_keywords:
- std::time_put [C++]
- std::time_put [C++], char_type
- std::time_put [C++], iter_type
- std::time_put [C++], do_put
- std::time_put [C++], put
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
ms.openlocfilehash: 10691de0a583dc7d5a66c319968d90978bf59480
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367996"
---
# <a name="time_put-class"></a>time_put クラス

クラス テンプレートは、時刻値から型のシーケンスへの変換を制御するロケール ファセットとして機能するオブジェクトを表`CharType`します。

## <a name="syntax"></a>構文

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>パラメーター

*Chartype*\
文字をエンコードするためにプログラム内で使用される型。

*出力反復器*\
時刻の put 関数が出力を書き込む反復子の型。

## <a name="remarks"></a>解説

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[time_put](#time_put)|`time_put` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|出力反復子を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_put](#do_put)|時刻と日付の情報を `CharType` のシーケンスとして出力する仮想関数。|
|[置く](#put)|時刻と日付の情報を `CharType` のシーケンスとして出力します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="time_putchar_type"></a><a name="char_type"></a>time_put::char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `CharType` のシノニムです。

## <a name="time_putdo_put"></a><a name="do_put"></a>time_put::do_put

時刻と日付の情報を `CharType` のシーケンスとして出力する仮想関数。

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>パラメーター

*次に*\
時刻と日付を表す文字のシーケンスが挿入される出力反復子。

*_Iosbase*\
未使用。

*_Pt*\
出力される時刻と日付の情報。

*_Fmt*\
出力の形式。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

*_Mod*\
形式の修飾子。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

### <a name="return-value"></a>戻り値

最後に挿入された要素の後の最初の位置を指す反復子。

### <a name="remarks"></a>解説

仮想プロテクト メンバー関数は、 型の`next`オブジェクト\*`_Pt`に格納されている時刻値から始`tm`まる順次要素を生成します。 関数は、生成された出力を超える、次に要素を挿入する場所を指定する反復子を返します。

出力は、配列に一連の`strftime`**char**要素を生成するために、 で使用されるのと同じ規則で生成され、最後の引数は *_Pt。* このような**char**要素は、単純な 1 対`CharType`1 のマッピングによって、型の等価な要素にマップされると想定されます。 *_Mod*がゼロの場合、有効な形式は "%F" で、F は *_Fmt*に置き換えられます。 それ以外の場合、有効な形式は "%MF" で、M は *_Mod*に置き換えられます。

### <a name="example"></a>例

[put](#put) の例 (`do_put` を呼び出す) を参照してください。

## <a name="time_putiter_type"></a><a name="iter_type"></a>time_put::iter_type

出力反復子を表す型。

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `OutputIterator` のシノニムです。

## <a name="time_putput"></a><a name="put"></a>time_put::pット

時刻と日付の情報を `CharType` のシーケンスとして出力します。

```cpp
iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;

iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*次に*\
時刻と日付を表す文字のシーケンスが挿入される出力反復子。

*_Iosbase*\
未使用。

*_Fill*\
間隔に使用される`CharType`型の文字。

*_Pt*\
出力される時刻と日付の情報。

*_Fmt*\
出力の形式。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

*_Mod*\
形式の修飾子。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

*まずは*\
出力の書式設定文字列の先頭。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

*前の*\
出力の書式設定文字列の末尾。 有効な値については、「[strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。

### <a name="return-value"></a>戻り値

最後に挿入された要素の後の最初の位置を指す反復子。

### <a name="remarks"></a>解説

最初のメンバー関数は`next`[、do_put](#do_put)、 `_Fill` `_Pt`、 `_Fmt` `_Mod`、 `_Iosbase`、 、 、 を返します。 2 番目のメンバー関数\*`next`は、 % 以外の`first`間隔`last`[ , ) 内の要素を ++ にコピーします。 パーセントの後に、間隔*C*[ `first`, ]`last`の文字 C が`next` = `do_put`続`next`く`_Iosbase`場合`_Fill`、`_Pt`関数は ( , , , , , *,* C , 0) を評価し *、C*を超えてスキップします。ただし *、C*がセット EOQ# の修飾子文字で、その後に間隔`C2`[ , `first` `last`] の文字が続`next` = `do_put`く`next`場合`_Iosbase`、`_Fill`関数`_Pt`は`C2`( , , `C2`, , *,*, ) を評価し、 をスキップします。

### <a name="example"></a>例

```cpp
// time_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   t.tm_hour = 5;
   t.tm_min = 30;
   t.tm_sec = 40;
   t.tm_year = 00;
   t.tm_mday = 4;
   t.tm_mon = 6;

   pszPutI.imbue( loc );
   char *pattern = "x: %X %x";
   use_facet <time_put <char> >
   (loc).put(basic_ostream<char>::_Iter(pszPutI.rdbuf( )),
          pszPutI, ' ', &t, pattern, pattern+strlen(pattern));

      cout << "num_put( ) = " << pszPutI.rdbuf( )->str( ) << endl;

      char strftimebuf[255];
      strftime(&strftimebuf[0], 255, pattern, &t);
      cout << "strftime( ) = " << &strftimebuf[0] << endl;
}
```

```Output
num_put( ) = x: 05:30:40 07/04/00
strftime( ) = x: 05:30:40 07/04/00
```

## <a name="time_puttime_put"></a><a name="time_put"></a>time_put::time_put

`time_put` 型のオブジェクトのコンストラクター。

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

*_Refs*\
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>解説

*_Refs*パラメータとその有意性の値は次のとおりです。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \>1: これらの値は定義されていません。

コンストラクターは、基本オブジェクトを[locale::facet](../standard-library/locale-class.md#facet_class)(*_Refs*) で初期化します。

## <a name="see-also"></a>関連項目

[\<ロケール>](../standard-library/locale.md)\
[time_baseクラス](../standard-library/time-base-class.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
