---
title: ctype クラス
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype
- xlocale/std::ctype::char_type
- xlocale/std::ctype::do_is
- xlocale/std::ctype::do_narrow
- xlocale/std::ctype::do_scan_is
- xlocale/std::ctype::do_scan_not
- xlocale/std::ctype::do_tolower
- xlocale/std::ctype::do_toupper
- xlocale/std::ctype::do_widen
- xlocale/std::ctype::is
- xlocale/std::ctype::narrow
- xlocale/std::ctype::scan_is
- xlocale/std::ctype::scan_not
- xlocale/std::ctype::tolower
- xlocale/std::ctype::toupper
- xlocale/std::ctype::widen
helpviewer_keywords:
- std::ctype [C++]
- std::ctype [C++], char_type
- std::ctype [C++], do_is
- std::ctype [C++], do_narrow
- std::ctype [C++], do_scan_is
- std::ctype [C++], do_scan_not
- std::ctype [C++], do_tolower
- std::ctype [C++], do_toupper
- std::ctype [C++], do_widen
- std::ctype [C++], is
- std::ctype [C++], narrow
- std::ctype [C++], scan_is
- std::ctype [C++], scan_not
- std::ctype [C++], tolower
- std::ctype [C++], toupper
- std::ctype [C++], widen
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
ms.openlocfilehash: e7c474e9112acadc11af889471b1e126dfeeb23f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438952"
---
# <a name="ctype-class"></a>ctype クラス

文字の分類、大文字と小文字の変換、およびネイティブ文字セットとロケールで使用される文字セットとの変換に使用されるふぁセットを提供するクラス。

## <a name="syntax"></a>構文

```cpp
template <class CharType>
class ctype : public ctype_base;
```

### <a name="parameters"></a>パラメーター

*CharType*<br/>
文字をエンコードするためにプログラム内で使用される型。

## <a name="remarks"></a>Remarks

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、`id` に一意の正の値が格納されます。 分類の条件は、基底クラス ctype_base の入れ子になったビットマスク型で提供されます。

C++ 標準ライブラリは、このテンプレート クラスの 2 つの明示的な特殊化を定義します。

- `ctype<char>`、明示的な特殊化の違いは別々 に説明します。 詳細については、[ctype&lt;char&gt;クラス](../standard-library/ctype-char-class.md)を参照してください。

- `ctype<wchar_t>`、要素のワイド文字として扱います。

テンプレート クラスの他の特殊化`ctype<CharType>`:

- 値に変換する*ch*型の*CharType*型の値に**char**式`(char)ch`します。

- 値に変換する*バイト*型の**char**型の値に*CharType*式`CharType(byte)`します。

その他のすべての操作に対して実行される**char**明示的な特殊化と同じ方法で値`ctype<char>`します。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[ctype](#ctype)|文字のロケール ファセットとして機能する `ctype` クラスのオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_is](#do_is)|1 つの文字が特定の属性を持つかどうかをテストしたり、範囲内の各文字の属性を分類して配列に格納したりするために呼び出される仮想関数。|
|[do_narrow](#do_narrow)|型の文字に変換する仮想関数が呼び出された`CharType`を型の対応する文字のロケールで使用される**char**ネイティブ文字セットにします。|
|[do_scan_is](#do_scan_is)|指定されたマスクに一致する範囲内の最初の文字を検索するために呼び出される仮想関数。|
|[do_scan_not](#do_scan_not)|指定されたマスクに一致しない範囲内の最初の文字を検索するために呼び出される仮想関数。|
|[do_tolower](#do_tolower)|文字または文字の範囲を小文字に変換するために呼び出される仮想関数。|
|[do_toupper](#do_toupper)|文字または文字の範囲を大文字に変換するために呼び出される仮想関数。|
|[do_widen](#do_widen)|呼び出される仮想関数が型の文字に変換します**char**ネイティブ文字型の対応する文字セットで`CharType`ロケールで使用します。|
|[is](#is)|1 つの文字が特定の属性を持つかどうかをテストするか、範囲内の各文字の属性を分類して配列に格納します。|
|[narrow](#narrow)|ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの char 型の対応する文字に変換します。|
|[scan_is](#scan_is)|指定されたマスクに一致する範囲内の最初の文字を検索します。|
|[scan_not](#scan_not)|指定されたマスクに一致しない範囲内の最初の文字を検索します。|
|[tolower](#tolower)|文字または文字の範囲を小文字に変換します。|
|[toupper](#toupper)|文字または文字の範囲を大文字に変換します。|
|[widen](#widen)|型の文字に変換します**char**ネイティブ文字型の対応する文字セットで`CharType`ロケールで使用します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="char_type"></a>  ctype::char_type

ロケールによって使用される文字を表す型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター *CharType* のシノニムです。

### <a name="example"></a>例

戻り値として `char_type` を使用する例については、メンバー関数 [widen](#widen) をご覧ください。

## <a name="ctype"></a>  ctype::ctype

文字のロケール ファセットとして機能する ctype クラスのオブジェクトのコンストラクター。

```cpp
explicit ctype(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

*_Refs*<br/>
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>Remarks

使用可能な値を *_Refs*パラメーターとその重要性は。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \> 1: これらの値が定義されていません。

デストラクターが保護されているため、利用できる直接的な例はありません。

コンストラクターは、**locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`) を使用して、その `locale::facet` 基本オブジェクトを初期化します。

## <a name="do_is"></a>  ctype::do_is

1 つの文字が特定の属性を持つかどうかをテストしたり、範囲内の各文字の属性を分類して配列に格納したりするために呼び出される仮想関数。

```cpp
virtual bool do_is(
    mask maskVal,
    CharType ch) const;

virtual const CharType *do_is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>パラメーター

*maskVal*<br/>
文字をテストするマスク値。

*ch*<br/>
属性をテストする文字。

*first*<br/>
属性を分類する範囲の最初の文字を示すポインター。

*last*<br/>
属性を分類する範囲の最初の文字の直後に続く文字を示すポインター。

*dest*<br/>
各文字の属性の特徴になるマスク値を格納する配列の先頭を示すポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、テストされた文字にマスク値により表される属性が含まれる場合、ブール値 **true** を返します。そのような属性が含まれない場合、**false** を返します。

2 番目のメンバー関数は、範囲内の各文字の属性を特徴付けるマスク値を含む配列を返します。

### <a name="remarks"></a>Remarks

文字の属性を分類するマスク値は、ctype の派生元である、クラス [ctype_base](../standard-library/ctype-base-class.md) により提供されます。 最初のメンバー関数は、ビットマスクと呼ばれ、ビット単位の論理演算子 (&#124;、&、^、~) によりマスク値の組み合わせから形成されるその最初のパラメーターの式を受け取ります。

### <a name="example"></a>例

[is](#is) の例 (`do_is` を呼び出す) を参照してください。

## <a name="do_narrow"></a>  ctype::do_narrow

型の文字に変換する仮想関数が呼び出された`CharType`を型の対応する文字のロケールで使用される**char**ネイティブ文字セットにします。

```cpp
virtual char do_narrow(
    CharType ch,
    char default = '\0') const;

virtual const CharType* do_narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
変換されるロケールにより使用される型 `Chartype` の文字。

*default*<br/>
文字型のメンバー関数によって割り当てられる既定値`CharType`型の対応する文字を持たない**char**します。

*first*<br/>
変換の対象となる一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
変換の対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

*dest*<br/>
型の最初の文字への const ポインター **char**変換後の文字の範囲を格納する宛先範囲。

### <a name="return-value"></a>戻り値

最初のプロテクト メンバー関数は、型のパラメーター文字に対応する型 char のネイティブ文字を返します`CharType`または*既定*片方が定義されていない場合。

保護されている 2 番目のメンバー関数は、型 `CharType` の文字から変換されたネイティブ文字の宛先範囲を示すポインターを返します。

### <a name="remarks"></a>Remarks

2 つ目の保護でメンバー テンプレート関数は`dest`[ `I`] 値`do_narrow`( `first` [ `I`]、 `default`) の`I`、間隔 [0、 `last`  - `first`).

### <a name="example"></a>例

[narrow](#narrow) の例 (`do_narrow` を呼び出す) を参照してください。

## <a name="do_scan_is"></a>  ctype::do_scan_is

指定されたマスクに一致する範囲内の最初の文字を検索するために呼び出される仮想関数。

```cpp
virtual const CharType *do_scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*maskVal*<br/>
文字により照合されるマスク値。

*first*<br/>
スキャンの対象となる一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
スキャンの対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

### <a name="return-value"></a>戻り値

指定されたマスクに一致する範囲内の最初の文字を示すポインター。 このような値が存在しないかどうか、関数を返します*最後*します。

### <a name="remarks"></a>Remarks

プロテクト メンバー関数は、最小のポインターを返します`ptr`範囲 [ `first`、 `last`) を[do_is](#do_is)( `maskVal`、 \* `ptr`) は true。

### <a name="example"></a>例

[scan_is](#scan_is) の例 (`do_scan_is` を呼び出す) を参照してください。

## <a name="do_scan_not"></a>  ctype::do_scan_not

指定されたマスクに一致しない範囲内の最初の文字を検索するために呼び出される仮想関数。

```cpp
virtual const CharType *do_scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*maskVal*<br/>
文字により照合されないマスク値。

*first*<br/>
スキャンの対象となる一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
スキャンの対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

### <a name="return-value"></a>戻り値

指定されたマスクに一致しない範囲内の最初の文字を示すポインター。 このような値が存在しないかどうか、関数を返します*最後*します。

### <a name="remarks"></a>Remarks

プロテクト メンバー関数は、最小のポインターを返します`ptr`範囲 [ `first`、 `last`) を[do_is](#do_is)( `maskVal`、 \* `ptr`) は false です。

### <a name="example"></a>例

[scan_not](#scan_not) の例 (`do_scan_not` を呼び出す) を参照してください。

## <a name="do_tolower"></a>  ctype::do_tolower

文字または文字の範囲を小文字に変換するために呼び出される仮想関数。

```cpp
virtual CharType do_tolower(CharType ch) const;

virtual const CharType *do_tolower(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
小文字に変換される文字。

*first*<br/>
大文字/小文字を変換する一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
大文字/小文字を変換する一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

### <a name="return-value"></a>戻り値

最初のプロテクト メンバー関数のパラメーターの小文字で返します*ch*します。 小文字の形態が存在しないかどうか、それを返します*ch*します。 メンバー関数の戻り値が 2 番目に保護されている*最後*します。

### <a name="remarks"></a>Remarks

2 番目のプロテクト メンバー テンプレート関数は、各要素を置換`first`[ `I`] の`I`、間隔 [0、 `last`  -  `first`) と`do_tolower`( `first` [ `I`]).

### <a name="example"></a>例

[tolower](#tolower) の例 (`do_tolower` を呼び出す) を参照してください。

## <a name="do_toupper"></a>  ctype::do_toupper

文字または文字の範囲を大文字に変換するために呼び出される仮想関数。

```cpp
virtual CharType do_toupper(CharType ch) const;

virtual const CharType *do_toupper(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
大文字に変換される文字。

*first*<br/>
大文字/小文字を変換する一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
大文字/小文字を変換する一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

### <a name="return-value"></a>戻り値

最初のプロテクト メンバー関数のパラメーターの大文字で返します*ch*します。 大文字の形態が存在しないかどうか、それを返します*ch*します。 メンバー関数の戻り値が 2 番目に保護されている*最後*します。

### <a name="remarks"></a>Remarks

2 番目のプロテクト メンバー テンプレート関数は、各要素を置換`first`[ `I`] の`I`、間隔 [0、 `last`  -  `first`) と`do_toupper`( `first` [ `I`]).

### <a name="example"></a>例

[toupper](#toupper) の例 (`do_toupper` を呼び出す) を参照してください。

## <a name="do_widen"></a>  ctype::do_widen

呼び出される仮想関数が型の文字に変換します**char**ネイティブ文字型の対応する文字セットで`CharType`ロケールで使用します。

```cpp
virtual CharType do_widen(char byte) const;

virtual const char *do_widen(
    const char* first,
    const char* last,
    CharType* dest) const;
```

### <a name="parameters"></a>パラメーター

*byte*<br/>
型の文字**char**でネイティブ文字セットに変換します。

*first*<br/>
変換の対象となる一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
変換の対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

*dest*<br/>
変換後の文字範囲を格納する宛先範囲のうち、型 `CharType` の最初の文字を示すポインター。

### <a name="return-value"></a>戻り値

最初のプロテクト メンバー関数は、型の文字を返します`CharType`ネイティブ型のパラメーター文字に対応する**char**します。

2 番目のプロテクト メンバー関数では、ポインターを返しますの種類の文字の宛先範囲を`CharType`型のネイティブ文字から変換されたロケールで使用される**char**します。

### <a name="remarks"></a>Remarks

保護されている 2 番目のメンバー テンプレート関数は、値 `do_widen`( `first`[ `I`]) を `dest`[ `I`] に格納します。`I` の間隔は [0, `last` - `first`) です。

### <a name="example"></a>例

[widen](#widen) の例 (`do_widen` を呼び出す) を参照してください。

## <a name="is"></a>  ctype::is

1 つの文字が特定の属性を持つかどうかをテストするか、範囲内の各文字の属性を分類して配列に格納します。

```cpp
bool is(mask maskVal, CharType ch) const;

const CharType *is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>パラメーター

*maskVal*<br/>
文字をテストするマスク値。

*ch*<br/>
属性をテストする文字。

*first*<br/>
属性を分類する範囲の最初の文字を示すポインター。

*last*<br/>
属性を分類する範囲の最初の文字の直後に続く文字を示すポインター。

*dest*<br/>
各文字の属性の特徴になるマスク値を格納する配列の先頭を示すポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数を返します**true**テストされた文字にマスク値で説明されている属性が設定されている場合**false**属性を持つ失敗した場合。

2 番目のメンバー関数は、属性を分類する範囲の最後の文字を示すポインターを返します。

### <a name="remarks"></a>Remarks

文字の属性を分類するマスク値は、ctype の派生元である、クラス [ctype_base クラス](../standard-library/ctype-base-class.md)により提供されます。 最初のメンバー関数は、ビットマスクと呼ばれ、ビット単位の論理演算子 (&#124;、&、^、~) によりマスク値の組み合わせから形成されるその最初のパラメーターの式を受け取ります。

### <a name="example"></a>例

```cpp
// ctype_is.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main() {
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );

   if (use_facet<ctype<char> > ( loc1 ).is( ctype_base::alpha, 'a' ))
      cout << "The character 'a' in locale loc1 is alphabetic."
           << endl;
   else
      cout << "The character 'a' in locale loc1 is not alphabetic."
           << endl;

   if (use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!' ))
      cout << "The character '!' in locale loc2 is alphabetic."
           << endl;
   else
      cout << "The character '!' in locale loc2 is not alphabetic."
           << endl;

   char *string = "Hello, my name is John!";
   ctype<char>::mask maskarray[30];
   use_facet<ctype<char> > ( loc2 ).is(
      string, string + strlen(string), maskarray );
   for (unsigned int i = 0; i < strlen(string); i++) {
      cout << string[i] << ": "
           << (maskarray[i] & ctype_base::alpha  "alpha"
                                                : "not alpha")
           << endl;;
   };
}
```

## <a name="narrow"></a>  ctype::narrow

型の文字に変換します`CharType`型の対応する文字のロケールで使用される**char**ネイティブ文字セットにします。

```cpp
char narrow(CharType ch, char default = '\0') const;

const CharType* narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
変換されるロケールにより使用される型 `Chartype` の文字。

*default*<br/>
文字型のメンバー関数によって割り当てられる既定値`CharType`型の対応する文字を持たない**char**します。

*first*<br/>
変換の対象となる一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
変換の対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

*dest*<br/>
型の最初の文字への const ポインター **char**変換後の文字の範囲を格納する宛先範囲。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、型のネイティブ文字を返します**char**型のパラメーター文字に対応する`CharType default`認識されていないが定義されている場合。

2 番目のメンバー関数は、型 `CharType` の文字から変換されたネイティブ文字の宛先範囲を示すポインターを返します。

### <a name="remarks"></a>Remarks

最初のメンバー関数を返します[do_narrow](#do_narrow)(`ch`、 `default`)。 2 番目のメンバー関数を返します[do_narrow](#do_narrow) (`first`、 `last`、 `default`、 `dest`)。 基本ソース文字にのみ、`narrow` の下で一意の逆像 `CharType` が与えられることが約束されます。 これの基本ソース文字については、`narrow` ( [widen](#widen) ( **c** ), 0 ) == **c** という不変式が適用されます。

### <a name="example"></a>例

```cpp
// ctype_narrow.cpp
// compile with: /EHsc /W3
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "english" );
   wchar_t *str1 = L"\x0392fhello everyone";
   char str2 [16];
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).narrow
      ( str1, str1 + wcslen(str1), 'X', &str2[0] ) != 0);  // C4996
   str2[wcslen(str1)] = '\0';
   wcout << str1 << endl;
   cout << &str2[0] << endl;
}
```

```Output
Xhello everyone
```

## <a name="scan_is"></a>  ctype::scan_is

指定されたマスクに一致する範囲内の最初の文字を検索します。

```cpp
const CharType *scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*maskVal*<br/>
文字により照合されるマスク値。

*first*<br/>
スキャンの対象となる一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
スキャンの対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

### <a name="return-value"></a>戻り値

指定されたマスクに一致する範囲内の最初の文字を示すポインター。 このような値が存在しないかどうか、関数を返します*最後*します。

### <a name="remarks"></a>Remarks

メンバー関数を返します[do_scan_is](#do_scan_is)(`maskVal`、 `first`、 `last`)。

### <a name="example"></a>例

```cpp
// ctype_scan_is.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char *string = "Hello, my name is John!";

   const char* i = use_facet<ctype<char> > ( loc1 ).scan_is
      ( ctype_base::punct, string, string + strlen(string) );
   cout << "The first punctuation is \"" << *i << "\" at position: "
      << i - string << endl;
}
```

```Output
The first punctuation is "," at position: 5
```

## <a name="scan_not"></a>  ctype::scan_not

指定されたマスクに一致しない範囲内の最初の文字を検索します。

```cpp
const CharType *scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*maskVal*<br/>
文字により照合されないマスク値。

*first*<br/>
スキャンの対象となる一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
スキャンの対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

### <a name="return-value"></a>戻り値

指定されたマスクに一致しない範囲内の最初の文字を示すポインター。 このような値が存在しないかどうか、関数を返します*最後*します。

### <a name="remarks"></a>Remarks

メンバー関数を返します[do_scan_not](#do_scan_not)(`maskVal`、 `first`、 `last`)。

### <a name="example"></a>例

```cpp
// ctype_scan_not.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char *string = "Hello, my name is John!";

   const char* i = use_facet<ctype<char> > ( loc1 ).scan_not
      ( ctype_base::alpha, string, string + strlen(string) );
   cout << "First nonalpha character is \"" << *i << "\" at position: "
      << i - string << endl;
}
```

```Output
First nonalpha character is "," at position: 5
```

## <a name="tolower"></a>  ctype::tolower

文字または文字の範囲を小文字に変換します。

```cpp
CharType tolower(CharType ch) const;

const CharType *tolower(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
小文字に変換される文字。

*first*<br/>
大文字/小文字を変換する一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
大文字/小文字を変換する一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数のパラメーターの小文字で返します*ch*します。 小文字の形態が存在しないかどうか、それを返します*ch*します。

2 番目のメンバー関数を返します*最後*します。

### <a name="remarks"></a>Remarks

最初のメンバー関数を返します[do_tolower](#do_tolower)(`ch`)。 2 番目のメンバー関数を返します[do_tolower](#do_tolower)(`first`、 `last`)。

### <a name="example"></a>例

```cpp
// ctype_tolower.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char string[] = "HELLO, MY NAME IS JOHN";

   use_facet<ctype<char> > ( loc1 ).tolower
      ( string, string + strlen(string) );
   cout << "The lowercase string is: " << string << endl;
}
```

```Output
The lowercase string is: hello, my name is john
```

## <a name="toupper"></a>  ctype::toupper

文字または文字の範囲を大文字に変換します。

```cpp
CharType toupper(CharType ch) const;
const CharType *toupper(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>パラメーター

*ch*<br/>
大文字に変換される文字。

*first*<br/>
大文字/小文字を変換する一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
大文字/小文字を変換する一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数のパラメーターの大文字で返します*ch*します。 大文字の形態が存在しないかどうか、それを返します*ch*します。

2 番目のメンバー関数を返します*最後*します。

### <a name="remarks"></a>Remarks

最初のメンバー関数を返します[do_toupper](#do_toupper)(`ch`)。 2 番目のメンバー関数は、[do_toupper](#do_toupper)( `first`, `last`) を返します。

### <a name="example"></a>例

```cpp
// ctype_toupper.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char string[] = "Hello, my name is John";

   use_facet<ctype<char> > ( loc1 ).toupper
      ( string, string + strlen(string) );
   cout << "The uppercase string is: " << string << endl;
}
```

```Output
The uppercase string is: HELLO, MY NAME IS JOHN
```

## <a name="widen"></a>  ctype::widen

型の文字に変換します**char**ネイティブ文字型の対応する文字セットで`CharType`ロケールで使用します。

```cpp
CharType widen(char byte) const;
const char *widen(const char* first, const char* last, CharType* dest) const;
```

### <a name="parameters"></a>パラメーター

*byte*<br/>
変換するネイティブ文字セットのうち、型 char の文字。

*first*<br/>
変換の対象となる一定範囲の文字のうち、最初の文字を示すポインター。

*last*<br/>
変換の対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。

*dest*<br/>
変換後の文字範囲を格納する宛先範囲のうち、型 `CharType` の最初の文字を示すポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、型の文字を返します`CharType`ネイティブ型のパラメーター文字に対応する**char**します。

2 番目のメンバー関数では、ポインターを返しますの種類の文字の宛先範囲を`CharType`型のネイティブ文字から変換されたロケールで使用される**char**します。

### <a name="remarks"></a>Remarks

最初のメンバー関数を返します[do_widen](#do_widen)(`byte`)。 2 番目のメンバー関数を返します[do_widen](#do_widen)(`first`、 `last`、 `dest`)。

### <a name="example"></a>例

```cpp
// ctype_widen.cpp
// compile with: /EHsc /W3
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "English" );
   char *str1 = "Hello everyone!";
   wchar_t str2 [16];
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).widen
      ( str1, str1 + strlen(str1), &str2[0] ) != 0);  // C4996
   str2[strlen(str1)] = '\0';
   cout << str1 << endl;
   wcout << &str2[0] << endl;

   ctype<wchar_t>::char_type charT;
   charT = use_facet<ctype<char> > ( loc1 ).widen( 'a' );
}
```

```Output
Hello everyone!
Hello everyone!
```

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
