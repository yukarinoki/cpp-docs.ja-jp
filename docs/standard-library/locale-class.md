---
title: locale クラス
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::locale
- xlocale/std::locale::category
- xlocale/std::locale::combine
- xlocale/std::locale::name
- xlocale/std::locale::classic
- xlocale/std::locale::global
- xlocale/std::locale::operator( )
- xlocale/std::locale::facet
- xlocale/std::locale::id
helpviewer_keywords:
- std::locale [C++]
- std::locale [C++], category
- std::locale [C++], combine
- std::locale [C++], name
- std::locale [C++], classic
- std::locale [C++], global
- std::locale [C++], facet
- std::locale [C++], id
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
ms.openlocfilehash: 888aeff3e8661338d1a017c06325108a4240ace3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677917"
---
# <a name="locale-class"></a>locale クラス

特定のローカライズされた環境を集合的に定義する一連のファセットとして、カルチャ固有の情報をカプセル化するロケール オブジェクトを表すクラス。

## <a name="syntax"></a>構文

```cpp
class locale;
```

## <a name="remarks"></a>Remarks

ファセットは、次の形式のパブリック オブジェクトがある、[facet](#facet_class) クラスから派生したクラスのオブジェクトへのポインターです。

```cpp
static locale::id id;
```

制約のない一連のファセットを定義できます。 任意の数のファセットを指定するロケール オブジェクトを構築することもできます。

これらのファセットの定義済みのグループは、従来の標準 C ライブラリでは `setlocale` 関数で管理されていた[ロケールのカテゴリ](#category)を表します。

collate カテゴリ (LC_COLLATE) には、次のファセットが含まれます。

```cpp
collate<char>
collate<wchar_t>
```

ctype カテゴリ (LC_CTYPE) には、次のファセットが含まれます。

```cpp
ctype<char>
ctype<wchar_t>
codecvt<char, char, mbstate_t>
codecvt<wchar_t, char, mbstate_t>
codecvt<char16_t, char, mbstate_t>
codecvt<char32_t, char, mbstate_t>
```

monetary カテゴリ (LC_MONETARY) には、次のファセットが含まれます。

```cpp
moneypunct<char, false>
moneypunct<wchar_t, false>
moneypunct<char, true>
moneypunct<wchar_t, true>
money_get<char, istreambuf_iterator<char>>
money_get<wchar_t, istreambuf_iterator<wchar_t>>
money_put<char, ostreambuf_iterator<char>>
money_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

numeric カテゴリ (LC_NUMERIC) には、次のファセットが含まれます。

```cpp
num_get<char, istreambuf_iterator<char>>
num_get<wchar_t, istreambuf_iterator<wchar_t>>
num_put<char, ostreambuf_iterator<char>>
num_put<wchar_t, ostreambuf_iterator<wchar_t>>
numpunct<char>
numpunct<wchar_t>
```

time カテゴリ (LC_TIME) には、次のファセットが含まれます。

```cpp
time_get<char, istreambuf_iterator<char>>
time_get<wchar_t, istreambuf_iterator<wchar_t>>
time_put<char, ostreambuf_iterator<char>>
time_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

messages カテゴリ (LC_MESSAGES) には、次のファセットが含まれます。

```cpp
messages<char>
messages<wchar_t>
```

(最後のカテゴリは Posix で必要ですが、C 標準では必要ありません。)

これらの定義済みのファセットの一部は、数値とテキスト シーケンスとの変換を制御するために、iostreams クラスによって使用されます。

クラス ロケールのオブジェクトは、ロケール名を [string](../standard-library/string-typedefs.md#string) クラスのオブジェクトとして格納します。 無効なロケール名を使用してロケールのファセットまたはロケール オブジェクトを構築すると、[runtime_error](../standard-library/runtime-error-class.md) クラスのオブジェクトがスローされます。 ロケール オブジェクトで、C スタイルのロケールがオブジェクトによって表されるロケールに正確に対応するかどうかを確認できない場合、格納されるロケール名は `"*"` です。 それ以外の場合、ロケール オブジェクト用の標準 C ライブラリ内で一致するロケールを設定できます`Loc`、呼び出して`setlocale`(LC_ALL `,` `Loc`します。 [名前](#name)`().c_str()`)。

この実装では、次の静的メンバー関数を呼び出すことによって、

```cpp
static locale empty();
```

ファセットがないロケール オブジェクトを構築することもできます。 このロケールは透過的ロケールでもあります。テンプレート関数 [has_facet](../standard-library/locale-functions.md#has_facet) と [use_facet](../standard-library/locale-functions.md#use_facet) で要求されたファセットを透過的ロケール内で見つけることができなかった場合、最初にグローバル ロケールを参照し、次にクラシック ロケールを参照します (透過的な場合)。 したがって、次のように記述できます。

```cpp
cout.imbue(locale::empty());
```

[cout](../standard-library/iostream.md#cout) への以降の挿入は、グローバル ロケールの現在の状態に基づいて仲介されます。 次のように記述することもできます。

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

`cout` への以降の挿入についての数値書式設定規則は、グローバル ロケールで日付や金額の挿入についての変更規則が提供されている場合でも、C のロケールの場合と同様です。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[locale](#locale)|ロケール、ロケールのコピー、またはファセットやカテゴリが別のロケールのファセットやカテゴリで置換されたロケールのコピーを作成します。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[category](#category)|標準ファセット ファミリを示すビットマスク値を指定する整数型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[combine](#combine)|ターゲット ロケールに指定されたロケールのファセットを挿入します。|
|[name](#name)|格納されているロケール名を返します。|

### <a name="static-functions"></a>静的関数

|||
|-|-|
|[classic](#classic)|この静的メンバー関数は、クラシック C ロケールを表すロケール オブジェクトを返します。|
|[global](#global)|プログラムの既定のロケールをリセットします。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator!=](#op_neq)|2 つのロケールが等しくないかどうかをテストします。|
|[operator( )](#op_call)|2 つの `basic_string` オブジェクトを比較します。|
|[operator==](#op_eq_eq)|2 つのロケールが等しいかどうかをテストします。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[facet](#facet_class)|すべてのロケールのファセットの基底クラスとして機能するクラス。|
|[ID](#id_class)|このメンバー クラスは、ロケール内でファセットを検索するためのインデックスとして使用される一意のファセット ID を提供します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="category"></a>  locale::category

標準ファセット ファミリを示すビットマスク値を指定する整数型。

```cpp
typedef int category;
static const int collate = LC_COLLATE;
static const int ctype = LC_CTYPE;
static const int monetary = LC_MONETARY;
static const int numeric = LC_NUMERIC;
static const int time = LC_TIME;
static const int messages = LC_MESSAGES;
static const int all = LC_ALL;
static const int none = 0;
```

### <a name="remarks"></a>Remarks

型がのシノニム、 **int**ビットマスクの個別の要素のグループを表すことのできる型がクラス ロケールを入力または対応する C ロケールのカテゴリのいずれかを表すために使用できます。 要素は次のとおりです。

- `collate`、C カテゴリ LC_COLLATE に対応します。

- `ctype`、C カテゴリ LC_CTYPE に対応します。

- `monetary`、C カテゴリ LC_MONETARY に対応します。

- `numeric`、C カテゴリ LC_NUMERIC に対応します。

- `time`、: C カテゴリ LC_TIME に対応します。

- `messages`、Posix カテゴリ LC_MESSAGES に対応します。

さらに、次の 2 つの値も役立ちます。

- `none`、C カテゴリの [なし] に対応します。

- `all`、のすべてのカテゴリ LC_ALL C の共用体に対応します。

使用してカテゴリの任意のグループを表すことができます`OR`に示すように、これらの定数`monetary` &#124; `time`します。

## <a name="classic"></a>  locale::classic

この静的メンバー関数は、クラシック C ロケールを表すロケール オブジェクトを返します。

```cpp
static const locale& classic();
```

### <a name="return-value"></a>戻り値

C ロケールへの参照。

### <a name="remarks"></a>Remarks

クラシック C ロケールは、米国です。国際化されていないプログラムで暗黙的に使用される標準 C ライブラリ内で英語の ASCII ロケール。

### <a name="example"></a>例

```cpp
// locale_classic.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: " << loc2.name( )
        << "." << endl;
   cout << "The name of the current locale is: " << loc1.name( )
        << "." << endl;

   if (loc2 == locale::classic( ) )
      cout << "The previous locale was classic." << endl;
   else
      cout << "The previous locale was not classic." << endl;

   if (loc1 == locale::classic( ) )
      cout << "The current locale is classic." << endl;
   else
      cout << "The current locale is not classic." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
The previous locale was classic.
The current locale is not classic.
```

## <a name="combine"></a>  locale::combine

ターゲット ロケールに指定されたロケールのファセットを挿入します。

```cpp
template <class Facet>
locale combine(const locale& Loc) const;
```

### <a name="parameters"></a>パラメーター

*Loc*<br/>
ターゲット ロケールに挿入されるファセットを含むロケール。

### <a name="return-value"></a>戻り値

メンバー関数で置き換えるかに追加するロケール オブジェクトを返します**\*この**ファセット`Facet`記載*Loc*します。

### <a name="example"></a>例

```cpp
// locale_combine.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;
}
```

## <a name="facet_class"></a>  facet クラス

すべてのロケールのファセットの基底クラスとして機能するクラス。

```cpp
class facet {
protected:
    explicit facet(size_t _Refs = 0);
   virtual ~facet();
private:
   facet(const facet&)
   // not defined void operator=(const facet&)
     // not defined
};
```

### <a name="remarks"></a>Remarks

クラスのファセットのオブジェクトをコピーまたは割り当てることはできません。 クラス `locale::facet` から派生したオブジェクトは構築および破棄できますが、厳密な意味での基底クラスのオブジェクトは構築および破棄できません。 通常は、**localeloc**( `locale::classic`( ), **new**`_Myfac`); でのように、ロケールを構築するときに、ファセットから派生したオブジェクト `_Myfac` を構築します。

このような場合、基底クラスのファセットのコンストラクターには、 0 の `_Refs` 引数が必要です。 オブジェクトは不要になったときに削除されます。 このため、オブジェクトの有効期間に責任を持つまれなケースでのみ、0 以外の _*Refs* 引数を指定します。

## <a name="global"></a>  locale::global

プログラムの既定のロケールをリセットします。 これは、C と C++ の両方のグローバル ロケールに影響します。

```cpp
static locale global(const locale& Loc);
```

### <a name="parameters"></a>パラメーター

*Loc*<br/>
プログラムによって既定のロケールとして使用されるロケール。

### <a name="return-value"></a>戻り値

既定のロケールがリセットされる前の以前のロケール。

### <a name="remarks"></a>Remarks

プログラムの起動時には、グローバル ロケールはクラシック ロケールと同じです。 `global()` 関数は `setlocale( LC_ALL, loc.name. c_str())` を呼び出して、標準 C ライブラリ内で一致するロケールを設定します。

### <a name="example"></a>例

```cpp
// locale_global.cpp
// compile by using: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   locale loc1;
   cout << "The initial locale is: " << loc1.name( ) << endl;
   locale loc2 = locale::global ( loc );
   locale loc3;
   cout << "The current locale is: " << loc3.name( ) << endl;
   cout << "The previous locale was: " << loc2.name( ) << endl;
}
```

```Output
The initial locale is: C
The current locale is: German_Germany.1252
The previous locale was: C
```

## <a name="id_class"></a>  id クラス

このメンバー クラスは、ロケール内でファセットを検索するためのインデックスとして使用される一意のファセット ID を提供します。

class id { protected:    id(); private:    id(const id&) // not defined void operator=(const id&)  // not defined    };

### <a name="remarks"></a>Remarks

このメンバー クラスは、一意の各ロケール ファセットに必要な静的メンバー オブジェクトを表します。 コピーまたはクラスのオブジェクトを割り当てることはできません注`id`します。

## <a name="locale"></a>  locale::locale

ロケール、ロケールのコピー、またはファセットやカテゴリが別のロケールのファセットやカテゴリで置換されたロケールのコピーを作成します。

```cpp
locale();

explicit locale(const char* Locname, category Cat = all);
explicit locale(const string& Locname);
locale( const locale& Loc);
locale(const locale& Loc, const locale& Other, category Cat);
locale(const locale& Loc, const char* Locname, category Cat);

template <class Facet>
locale(const locale& Loc, const Facet* Fac);
```

### <a name="parameters"></a>パラメーター

*Locname*<br/>
ロケールの名前。

*Loc*<br/>
新しいロケールを構築する際にコピーされるロケール。

*その他*<br/>
カテゴリの選択元となるロケール。

*Cat*<br/>
構築されるロケール内での置換後のカテゴリ。

*Fac*<br/>
構築されるロケール内での置換後のファセット。

### <a name="remarks"></a>Remarks

最初のコンストラクターは、グローバル ロケールと一致するようにオブジェクトを初期化します。 2 番目と 3 番目のコンス トラクターは、ロケール名に一貫性のある動作をすべてのロケールのカテゴリを初期化します。 *Locname*します。 残りのコンス トラクターのコピー *Loc*、例外について。

`locale(const locale& Loc, const locale& Other, category Cat);`

置換*他*どの C カテゴリ C に対応するファセット & *Cat*が 0 以外。

`locale(const locale& Loc, const char* Locname, category Cat);`

`locale(const locale& Loc, const string& Locname, category Cat);`

置換`locale(Locname, _All)`どの C カテゴリ C に対応するファセット & *Cat*が 0 以外。

`template<class Facet> locale(const locale& Loc, Facet* Fac);`

置換 (またはに追加します) *Loc*ファセット*Fac*場合は、 *Fac* null ポインターではありません。

場合、ロケール名*Locname* null ポインターまたはそれ以外の場合に無効な関数のスロー [runtime_error](../standard-library/runtime-error-class.md)します。

### <a name="example"></a>例

```cpp
// locale_locale.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( ) {

   // Second constructor
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   // The first (default) constructor
   locale loc2;
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   // Third constructor
   locale loc3 (loc2,loc, _M_COLLATE );
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;

   // Fourth constructor
   locale loc4 (loc2, "German_Germany", _M_COLLATE );
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;
}
```

## <a name="name"></a>  locale::name

格納されているロケール名を返します。

```cpp
string name() const;
```

### <a name="return-value"></a>戻り値

ロケールの名前を指定する文字列。

### <a name="example"></a>例

```cpp
// locale_name.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: "
        << loc2.name( ) << "." << endl;
   cout << "The name of the current locale is: "
        << loc1.name( ) << "." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
```

## <a name="op_neq"></a>  locale::operator!=

2 つのロケールが等しくないかどうかをテストします。

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
不等性をテストする一方のロケール。

### <a name="return-value"></a>戻り値

ロケールが同じロケールのコピーでない場合は **true**、ロケールが同じロケールのコピーである場合は **false** を示すブール値。

### <a name="remarks"></a>Remarks

2 つのロケールが同じロケールである場合、片方がもう片方のコピーである場合、または 2 つが同じ名前を持つ場合、この 2 つのロケールは等しいです。

### <a name="example"></a>例

```cpp
// locale_op_ne.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 != loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;

   if ( loc1 != loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;
}
```

```Output
locales loc1 (German_Germany.1252) and
loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252) and
loc3 (English_United States.1252) are not equal.
```

## <a name="op_call"></a>  locale::operator()

2 つの `basic_string` オブジェクトを比較します。

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>パラメーター

*left*<br/>
左側の文字列。

*right*<br/>
右側の文字列。

### <a name="return-value"></a>戻り値

このメンバー関数は、以下の値を返します。

- 最初のシーケンスが 2 番目のシーケンスより小さい場合は、-1。

- 2 番目のシーケンスが最初のシーケンスより小さい場合は、+1。

- シーケンスが等しい場合は 0。

### <a name="remarks"></a>Remarks

このメンバー関数は、実質的に次の内容を実行します。

```cpp
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```

したがって、ロケール オブジェクトを関数オブジェクトとして使用できます。

### <a name="example"></a>例

```cpp
// locale_op_compare.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

int main( )
{
   using namespace std;
   wchar_t *sa = L"ztesting";
   wchar_t *sb = L"\0x00DFtesting";
   basic_string<wchar_t> a( sa );
   basic_string<wchar_t> b( sb );

   locale loc( "German_Germany" );
   cout << loc( a,b ) << endl;

   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );
   cout << ( fac.compare( sa, sa + a.length( ),
       sb, sb + b.length( ) ) < 0) << endl;
}
```

```Output
0
0
```

## <a name="op_eq_eq"></a>  locale::operator==

2 つのロケールが等しいかどうかをテストします。

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>パラメーター

*right*<br/>
等しいかどうかをテストする一方のロケール。

### <a name="return-value"></a>戻り値

ロケールが同じロケールのコピーである場合は **true**、ロケールが同じロケールのコピーでない場合は **false** を示すブール値。

### <a name="remarks"></a>Remarks

2 つのロケールが同じロケールである場合、片方がもう片方のコピーである場合、または 2 つが同じ名前を持つ場合、この 2 つのロケールは等しいです。

### <a name="example"></a>例

```cpp
// locale_op_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 == loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."
      << endl;

   if ( loc1 == loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."
      << endl;
}
```

```Output
locales loc1 (German_Germany.1252)
and loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252)
and loc3 (English_United States.1252) are not equal.
```

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)<br/>
[コード ページ](../c-runtime-library/code-pages.md)<br/>
[ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
