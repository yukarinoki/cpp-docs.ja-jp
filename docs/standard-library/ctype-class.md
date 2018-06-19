---
title: ctype クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0668e10bb1e9ccb54e356451b7d4efb1a75b5ac8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848753"
---
# <a name="ctype-class"></a>ctype クラス

文字の分類、大文字と小文字の変換、およびネイティブ文字セットとロケールで使用される文字セットとの変換に使用されるふぁセットを提供するクラス。

## <a name="syntax"></a>構文

```cpp
template <class CharType>
class ctype : public ctype_base;
```

### <a name="parameters"></a>パラメーター

`CharType` プログラム内で文字をエンコードするために使用する型。

## <a name="remarks"></a>コメント

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。分類の条件は、基底クラス ctype_base の入れ子になったビットマスク型で提供されます。

C++ 標準ライブラリは、このテンプレート クラスの 2 つの明示的な特殊化を定義します。

- [ctype](../standard-library/ctype-char-class.md)< `char`>。違いが別個に記述される明示的な特殊化です。

- **ctype**< `wchar_t`>。要素をワイド文字として扱います。

テンプレート クラス **ctype**\< **CharType**> のその他の特殊化。

- 式 ( `char`) **ch** を使用して、**CharType** 型の値 ***ch*** を、`char` 型の値に変換します。

- 式 **CharType** ( **byte**) を使用して、`char` 型の値 ***byte*** を、**CharType** 型の値に変換します。

他の操作はすべて明示的な特殊化 **ctype**< `char`> の場合と同様に `char` 値に対して実行されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[ctype](#ctype)|文字のロケール ファセットとして機能する `ctype` クラスのオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_is](#do_is)|1 つの文字が特定の属性を持つかどうかをテストしたり、範囲内の各文字の属性を分類して配列に格納したりするために呼び出される仮想関数。|
|[do_narrow](#do_narrow)|ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの `char` 型の対応する文字に変換するために呼び出される仮想関数。|
|[do_scan_is](#do_scan_is)|指定されたマスクに一致する範囲内の最初の文字を検索するために呼び出される仮想関数。|
|[do_scan_not](#do_scan_not)|指定されたマスクに一致しない範囲内の最初の文字を検索するために呼び出される仮想関数。|
|[do_tolower](#do_tolower)|文字または文字の範囲を小文字に変換するために呼び出される仮想関数。|
|[do_toupper](#do_toupper)|文字または文字の範囲を大文字に変換するために呼び出される仮想関数。|
|[do_widen](#do_widen)|ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換するために呼び出される仮想関数。|
|[is](#is)|1 つの文字が特定の属性を持つかどうかをテストするか、範囲内の各文字の属性を分類して配列に格納します。|
|[narrow](#narrow)|ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの char 型の対応する文字に変換します。|
|[scan_is](#scan_is)|指定されたマスクに一致する範囲内の最初の文字を検索します。|
|[scan_not](#scan_not)|指定されたマスクに一致しない範囲内の最初の文字を検索します。|
|[tolower](#tolower)|文字または文字の範囲を小文字に変換します。|
|[toupper](#toupper)|文字または文字の範囲を大文字に変換します。|
|[widen](#widen)|ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="char_type"></a>  ctype::char_type

ロケールによって使用される文字を表す型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター **CharType** のシノニムです。

### <a name="example"></a>例

戻り値として `char_type` を使用する例については、メンバー関数 [widen](#widen) をご覧ください。

## <a name="ctype"></a>  ctype::ctype

文字のロケール ファセットとして機能する ctype クラスのオブジェクトのコンストラクター。

```cpp
explicit ctype(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

`_Refs` オブジェクトのメモリ管理の種類を指定するために使用する整数値です。

### <a name="remarks"></a>コメント

`_Refs` パラメーターの可能な値とその重要性は次のとおりです。

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

`maskVal` 文字をテストするマスク値。

`ch` 属性をテストする文字。

`first` 属性が分類される範囲の最初の文字へのポインター。

`last` 属性が分類される範囲の最後の文字の直後の文字へのポインター。

`dest` 各文字の属性を特徴付けるマスクの値が格納される配列の先頭へのポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、テストされた文字にマスク値により表される属性が含まれる場合、ブール値 **true** を返します。そのような属性が含まれない場合、**false** を返します。

2 番目のメンバー関数は、範囲内の各文字の属性を特徴付けるマスク値を含む配列を返します。

### <a name="remarks"></a>コメント

文字の属性を分類するマスク値は、ctype の派生元である、クラス [ctype_base](../standard-library/ctype-base-class.md) により提供されます。 最初のメンバー関数は、ビットマスクと呼ばれ、ビット単位の論理演算子 (&#124;、&、^、~) によりマスク値の組み合わせから形成されるその最初のパラメーターの式を受け取ります。

### <a name="example"></a>例

[is](#is) の例 (`do_is` を呼び出す) を参照してください。

## <a name="do_narrow"></a>  ctype::do_narrow

ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの `char` 型の対応する文字に変換するために呼び出される仮想関数。

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

`ch` 型の文字`Chartype`ロケールで変換するために使用します。

`default` 文字型のメンバー関数によって割り当てられる既定値`CharType`型の対応する文字を持たない`char`です。

`first` 変換する文字の範囲の最初の文字へのポインター。

`last` 変換する文字の範囲の最後の文字の直後の文字へのポインター。

`dest` 型の最初の文字への const ポインター`char`範囲内で、変換先を変換後の範囲の文字を格納します。

### <a name="return-value"></a>戻り値

保護されている最初のメンバー関数は、対になる片方が定義されていない場合、型 `CharType` または `default` のパラメーター文字に対応する型 char のネイティブ文字を返します。

保護されている 2 番目のメンバー関数は、型 `CharType` の文字から変換されたネイティブ文字の宛先範囲を示すポインターを返します。

### <a name="remarks"></a>コメント

メンバー テンプレート関数のストアが 2 番目に保護されている`dest`[ `I`] 値`do_narrow`( `first` [ `I`]、 `default`) の`I`の間隔 [0, `last`  - `first`).

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

`maskVal` 文字が一致するマスクの値。

`first` スキャンする範囲の最初の文字へのポインター。

`last` スキャンする範囲の最後の文字の直後の文字へのポインター。

### <a name="return-value"></a>戻り値

指定されたマスクに一致する範囲内の最初の文字を示すポインター。 そのような値が存在しない場合、この関数は `last.` を返します。

### <a name="remarks"></a>コメント

保護されているメンバー関数は、[do_is](#do_is)( `maskVal`, * `ptr`) が true となっている範囲 [ `first`, `last`) 内の最小ポインター `ptr` を返します。

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

`maskVal` 文字が一致しないようにマスクの値。

`first` スキャンする範囲の最初の文字へのポインター。

`last` スキャンする範囲の最後の文字の直後の文字へのポインター。

### <a name="return-value"></a>戻り値

指定されたマスクに一致しない範囲内の最初の文字を示すポインター。 そのような値が存在しない場合、この関数は `last` を返します。

### <a name="remarks"></a>コメント

保護されているメンバー関数は、[do_is](#do_is)( `maskVal`, * `ptr`) が false となっている範囲 [ `first`, `last`) 内の最小ポインター `ptr` を返します。

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

`ch` 小文字に変換する文字。

`first` 場合は、変換する文字の範囲の最初の文字へのポインター。

`last` 場合は、変換する文字の範囲の最後の文字の直後の文字へのポインター。

### <a name="return-value"></a>戻り値

保護されている最初のメンバー関数は、パラメーター `ch` を小文字で返します。 小文字の形態が存在しない場合、`ch` を返します。 保護されている 2 番目のメンバー関数は `last` を返します。

### <a name="remarks"></a>コメント

2 番目のプロテクト メンバー テンプレート関数は、各要素を置き換えます`first`[ `I`] の`I`の間隔 [0、 `last`  -  `first`) と`do_tolower`( `first` [ `I`]).

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

`ch` 大文字に変換する文字。

`first` 場合は、変換する文字の範囲の最初の文字へのポインター。

`last` 場合は、変換する文字の範囲の最後の文字の直後の文字へのポインター。

### <a name="return-value"></a>戻り値

保護されている最初のメンバー関数は、パラメーター `ch` を大文字で返します。 大文字の形態が存在しない場合、`ch` を返します。 保護されている 2 番目のメンバー関数は `last` を返します。

### <a name="remarks"></a>コメント

2 番目のプロテクト メンバー テンプレート関数は、各要素を置き換えます`first`[ `I`] の`I`の間隔 [0、 `last`  -  `first`) と`do_toupper`( `first` [ `I`]).

### <a name="example"></a>例

[toupper](#toupper) の例 (`do_toupper` を呼び出す) を参照してください。

## <a name="do_widen"></a>  ctype::do_widen

ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換するために呼び出される仮想関数。

```cpp
virtual CharType do_widen(char byte) const;


virtual const char *do_widen(
    const char* first,
    const char* last,
    CharType* dest) const;
```

### <a name="parameters"></a>パラメーター

`byte` 型の文字`char`でネイティブ文字セットに変換します。

`first` 変換する文字の範囲の最初の文字へのポインター。

`last` 変換する文字の範囲の最後の文字の直後の文字へのポインター。

`dest` 型の最初の文字へのポインター`CharType`範囲内で、変換先を変換後の範囲の文字を格納します。

### <a name="return-value"></a>戻り値

保護されている最初のメンバー関数は、ネイティブ型 `char` のパラメーター文字に対応する型 `CharType` の文字を返します。

保護されている 2 番目のメンバー関数は、型 `char` のネイティブ文字から変換されたロケールで使用される型 `CharType` の文字の宛先範囲を示すポインターを返します。

### <a name="remarks"></a>コメント

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

`maskVal` 文字をテストするマスク値。

`ch` 属性をテストする文字。

`first` 属性が分類される範囲の最初の文字へのポインター。

`last` 属性が分類される範囲の最後の文字の直後の文字へのポインター。

`dest` 各文字の属性を特徴付けるマスクの値が格納される配列の先頭へのポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、テストされた文字にマスク値により表される属性が含まれる場合、`true` を返します。そのような属性が含まれない場合、`false` を返します。

2 番目のメンバー関数は、属性を分類する範囲の最後の文字を示すポインターを返します。

### <a name="remarks"></a>コメント

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

ロケールにより使用される型 `CharType` の文字を、ネイティブ文字セットの型 `char` の該当文字に変換します。

```cpp
char narrow(CharType ch, char default = '\0') const;


const CharType* narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>パラメーター

`ch` 型の文字`Chartype`ロケールで変換するために使用します。

`default` 文字型のメンバー関数によって割り当てられる既定値`CharType`型の対応する文字を持たない`char`です。

`first` 変換する文字の範囲の最初の文字へのポインター。

`last` 変換する文字の範囲の最後の文字の直後の文字へのポインター。

`dest` 型の最初の文字への const ポインター`char`範囲内で、変換先を変換後の範囲の文字を格納します。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、対になる片方が定義されていない場合、型 `CharType default` のパラメーター文字に対応する型 `char` のネイティブ文字を返します。

2 番目のメンバー関数は、型 `CharType` の文字から変換されたネイティブ文字の宛先範囲を示すポインターを返します。

### <a name="remarks"></a>コメント

最初のメンバー関数は、[do_narrow](#do_narrow)( `ch`, `default`) を返します。 2 番目のメンバー関数は、[do_narrow](#do_narrow) ( `first`, `last`, `default`, `dest`) を返します。 基本ソース文字にのみ、`narrow` の下で一意の逆像 `CharType` が与えられることが約束されます。 これの基本ソース文字については、`narrow` ( [widen](#widen) ( **c** ), 0 ) == **c** という不変式が適用されます。

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

`maskVal` 文字が一致するマスクの値。

`first` スキャンする範囲の最初の文字へのポインター。

`last` スキャンする範囲の最後の文字の直後の文字へのポインター。

### <a name="return-value"></a>戻り値

指定されたマスクに一致する範囲内の最初の文字を示すポインター。 そのような値が存在しない場合、この関数は `last.` を返します。

### <a name="remarks"></a>コメント

メンバー関数は、[do_scan_is](#do_scan_is)( `maskVal`, `first`, `last`) を返します。

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

`maskVal` 文字が一致しないようにマスクの値。

`first` スキャンする範囲の最初の文字へのポインター。

`last` スキャンする範囲の最後の文字の直後の文字へのポインター。

### <a name="return-value"></a>戻り値

指定されたマスクに一致しない範囲内の最初の文字を示すポインター。 そのような値が存在しない場合、この関数は `last` を返します。

### <a name="remarks"></a>コメント

メンバー関数は、[do_scan_not](#do_scan_not)( `maskVal`, `first`, `last`) を返します。

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

`ch` 小文字に変換する文字。

`first` 場合は、変換する文字の範囲の最初の文字へのポインター。

`last` 場合は、変換する文字の範囲の最後の文字の直後の文字へのポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、パラメーター `ch` を小文字で返します。 小文字の形態が存在しない場合、`ch` を返します。

2 番目のメンバー関数は `last` を返します。

### <a name="remarks"></a>コメント

最初のメンバー関数は、[do_tolower](#do_tolower)( `ch`) を返します。 2 番目のメンバー関数は、[do_tolower](#do_tolower)( `first`, `last`) を返します。

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

`ch` 大文字に変換する文字。

`first` 場合は、変換する文字の範囲の最初の文字へのポインター。

`last` 場合は、変換する文字の範囲の最後の文字の直後の文字へのポインター。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、パラメーター `ch` を大文字で返します。 大文字の形態が存在しない場合、`ch` を返します。

2 番目のメンバー関数は `last` を返します。

### <a name="remarks"></a>コメント

最初のメンバー関数は、[do_toupper](#do_toupper)( `ch`) を返します。 2 番目のメンバー関数は、[do_toupper](#do_toupper)( `first`, `last`) を返します。

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

ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換します。

```cpp
CharType widen(char byte) const;
const char *widen(const char* first, const char* last, CharType* dest) const;
```

### <a name="parameters"></a>パラメーター

`byte` ネイティブの文字の char 型の文字は、変換に設定されます。

`first` 変換する文字の範囲の最初の文字へのポインター。

`last` 変換する文字の範囲の最後の文字の直後の文字へのポインター。

`dest` 型の最初の文字へのポインター`CharType`範囲内で、変換先を変換後の範囲の文字を格納します。

### <a name="return-value"></a>戻り値

最初のメンバー関数は、ネイティブ型 `char` のパラメーター文字に対応する型 `CharType` の文字を返します。

2 番目のメンバー関数は、型 `char` のネイティブ文字から変換されたロケールで使用される型 `CharType` の文字の宛先範囲を示すポインターを返します。

### <a name="remarks"></a>コメント

最初のメンバー関数は、[do_widen](#do_widen)( `byte`) を返します。 2 番目のメンバー関数は、[do_widen](#do_widen)( `first`, `last`, `dest`) を返します。

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
