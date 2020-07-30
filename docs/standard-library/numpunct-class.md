---
title: numpunct クラス
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct
- xlocnum/std::numpunct::char_type
- xlocnum/std::numpunct::string_type
- xlocnum/std::numpunct::decimal_point
- xlocnum/std::numpunct::do_decimal_point
- xlocnum/std::numpunct::do_falsename
- xlocnum/std::numpunct::do_grouping
- xlocnum/std::numpunct::do_thousands_sep
- xlocnum/std::numpunct::do_truename
- xlocnum/std::numpunct::falsename
- xlocnum/std::numpunct::grouping
- xlocnum/std::numpunct::thousands_sep
- xlocnum/std::numpunct::truename
helpviewer_keywords:
- std::numpunct [C++]
- std::numpunct [C++], char_type
- std::numpunct [C++], string_type
- std::numpunct [C++], decimal_point
- std::numpunct [C++], do_decimal_point
- std::numpunct [C++], do_falsename
- std::numpunct [C++], do_grouping
- std::numpunct [C++], do_thousands_sep
- std::numpunct [C++], do_truename
- std::numpunct [C++], falsename
- std::numpunct [C++], grouping
- std::numpunct [C++], thousands_sep
- std::numpunct [C++], truename
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
ms.openlocfilehash: 602d8edef80f0e4d4abe4cb6773b774d174e1cbe
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202819"
---
# <a name="numpunct-class"></a>numpunct クラス

`CharType`数値とブール式の書式設定および区切りに関する情報を表すために使用される型のシーケンスを記述するローカルファセットとして使用できるオブジェクトを表すクラステンプレート。

## <a name="syntax"></a>構文

```cpp
template <class CharType>
class numpunct : public locale::facet;
```

### <a name="parameters"></a>パラメーター

*CharType*\
ロケールの文字をエンコードするためにプログラム内で使用される型。

## <a name="remarks"></a>解説

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[numpunct](#numpunct)|`numpunct` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[string_type](#string_type)|`CharType` 型の文字を格納する文字列を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[decimal_point](#decimal_point)|小数点として使用するロケール固有の要素を返します。|
|[do_decimal_point](#do_decimal_point)|小数点として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。|
|[do_falsename](#do_falsename)|値のテキスト表現として使用する文字列を返すために呼び出されるプロテクト仮想メンバー関数 **`false`** 。|
|[do_grouping](#do_grouping)|小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返すために呼び出されるプロテクト仮想メンバー関数。|
|[do_thousands_sep](#do_thousands_sep)|桁区切り記号として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。|
|[do_truename](#do_truename)|値のテキスト表現として使用する文字列を返すために呼び出されるプロテクト仮想メンバー関数 **`true`** 。|
|[falsename](#falsename)|値のテキスト表現として使用する文字列を返し **`false`** ます。|
|[分類](#grouping)|小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。|
|[thousands_sep](#thousands_sep)|桁区切り記号として使用するロケール固有の要素を返します。|
|[truename](#truename)|値のテキスト表現として使用する文字列を返し **`true`** ます。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="numpunctchar_type"></a><a name="char_type"></a>numpunct:: char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター **Chartype**のシノニムです。

## <a name="numpunctdecimal_point"></a><a name="decimal_point"></a>numpunct::d ecimal_point

小数点として使用するロケール固有の要素を返します。

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>戻り値

小数点として使用するロケール固有の要素。

### <a name="remarks"></a>解説

このメンバー関数は、[do_decimal_point](#do_decimal_point) を返します。

### <a name="example"></a>例

```cpp
// numpunct_decimal_point.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const numpunct <char> &npunct =
   use_facet <numpunct <char> >( loc);
   cout << loc.name( ) << " decimal point "<<
   npunct.decimal_point( ) << endl;
   cout << loc.name( ) << " thousands separator "
   << npunct.thousands_sep( ) << endl;
};
```

```Output
German_Germany.1252 decimal point ,
German_Germany.1252 thousands separator .
```

## <a name="numpunctdo_decimal_point"></a><a name="do_decimal_point"></a>numpunct::d o_decimal_point

小数点として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>戻り値

小数点として使用するロケール固有の要素。

### <a name="example"></a>例

[decimal_point](#decimal_point) の例 (仮想メンバー関数が `decimal_point` で呼び出される) を参照してください。

## <a name="numpunctdo_falsename"></a><a name="do_falsename"></a>numpunct::d o_falsename

プロテクト仮想メンバー関数は、値のテキスト表現として使用するシーケンスを返し **`false`** ます。

```cpp
virtual string_type do_falsename() const;
```

### <a name="return-value"></a>戻り値

値のテキスト表現として使用するシーケンスを格納している文字列 **`false`** 。

### <a name="remarks"></a>解説

このメンバー関数は、すべてのロケールの値を表す文字列 "false" を返し **`false`** ます。

### <a name="example"></a>例

[falsename](#falsename) の例 (仮想メンバー関数が `falsename` で呼び出される) をご覧ください。

## <a name="numpunctdo_grouping"></a><a name="do_grouping"></a>numpunct::d o_grouping

小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返すために呼び出されるプロテクト仮想メンバー関数。

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>戻り値

小数点の左側の数字をグループ化する方法を決定するロケール固有の規則。

### <a name="remarks"></a>解説

このプロテクト仮想メンバー関数は、小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。 エンコーディングは **lconv::grouping** の場合と同じです。

### <a name="example"></a>例

[グループ化](#grouping)の例を参照してください。ここで、仮想メンバー関数はによって呼び出され `grouping` ます。

## <a name="numpunctdo_thousands_sep"></a><a name="do_thousands_sep"></a>numpunct::d o_thousands_sep

桁区切り記号として使用するロケール固有の要素を返すために呼び出されるプロテクト仮想メンバー関数。

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>戻り値

桁区切り記号として使用するロケール固有の要素を返します。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、 `CharType` 小数点の左側にある桁区切り記号として使用する型のロケール固有の要素を返します。

### <a name="example"></a>例

[thousands_sep](#thousands_sep) の例 (仮想メンバー関数が `thousands_sep` で呼び出される) を参照してください。

## <a name="numpunctdo_truename"></a><a name="do_truename"></a>numpunct::d o_truename

値のテキスト表現として使用する文字列を返すために呼び出されるプロテクト仮想メンバー関数 **`true`** 。

```cpp
virtual string_type do_truename() const;
```

### <a name="remarks"></a>解説

値のテキスト表現として使用する文字列 **`true`** 。

すべてのロケールは、値を表す文字列 "true" を返し **`true`** ます。

### <a name="example"></a>例

[truename](#truename) の例 (仮想メンバー関数が `truename` で呼び出される) をご覧ください。

## <a name="numpunctfalsename"></a><a name="falsename"></a>numpunct:: falsename

値のテキスト表現として使用する文字列を返し **`false`** ます。

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>戻り値

`CharType`値のテキスト表現として使用するのシーケンスを格納している文字列 **`false`** 。

### <a name="remarks"></a>解説

このメンバー関数は、すべてのロケールの値を表す文字列 "false" を返し **`false`** ます。

このメンバー関数は、[do_falsename](#do_falsename) を返します。

### <a name="example"></a>例

```cpp
// numpunct_falsename.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "English" );

   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;

   locale loc2( "French" );
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;
}
```

```Output
English_United States.1252 truename true
English_United States.1252 falsename false
French_France.1252 truename true
French_France.1252 falsename false
```

## <a name="numpunctgrouping"></a><a name="grouping"></a>numpunct:: grouping

小数点の左側の数字をグループ化する方法を決定するロケール固有の規則を返します。

```cpp
string grouping() const;
```

### <a name="return-value"></a>戻り値

小数点の左側の数字をグループ化する方法を決定するロケール固有の規則。

### <a name="remarks"></a>解説

このメンバー関数は、[do_grouping](#do_grouping) を返します。

### <a name="example"></a>例

```cpp
// numpunct_grouping.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany");

   const numpunct <char> &npunct =
       use_facet < numpunct <char> >( loc );
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(npunct.grouping ( )[i])
           << endl;
   }
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
```

## <a name="numpunctnumpunct"></a><a name="numpunct"></a>numpunct:: numpunct

`numpunct` 型のオブジェクトのコンストラクター。

```cpp
explicit numpunct(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

*_Refs*\
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>解説

*_Refs*パラメーターに指定できる値とその意味は次のとおりです。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \>1: これらの値は定義されていません。

デストラクターが保護されているため、利用できる直接的な例はありません。

コンストラクターは、 **locale::**[facet](../standard-library/locale-class.md#facet_class)() を使用して、その基本オブジェクトを初期化し `_Refs` ます。

## <a name="numpunctstring_type"></a><a name="string_type"></a>numpunct:: string_type

**CharType** 型の文字を格納する文字列を表す型。

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>解説

この型は、区切り記号のコピーを格納できるオブジェクトを持つクラステンプレート[basic_string](../standard-library/basic-string-class.md)の特殊化を表します。

## <a name="numpunctthousands_sep"></a><a name="thousands_sep"></a>numpunct:: thousands_sep

桁区切り記号として使用するロケール固有の要素を返します。

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>戻り値

桁区切り記号として使用するロケール固有の要素。

### <a name="remarks"></a>解説

このメンバー関数は、[do_thousands_sep](#do_thousands_sep) を返します。

### <a name="example"></a>例

```cpp
// numpunct_thou_sep.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const numpunct <char> &npunct =
   use_facet < numpunct < char > >( loc );
   cout << loc.name( ) << " decimal point "<<
   npunct.decimal_point( ) << endl;
   cout << loc.name( ) << " thousands separator "
   << npunct.thousands_sep( ) << endl;
};
```

```Output
German_Germany.1252 decimal point ,
German_Germany.1252 thousands separator .
```

## <a name="numpuncttruename"></a><a name="truename"></a>numpunct::

値のテキスト表現として使用する文字列を返し **`true`** ます。

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>戻り値

値のテキスト表現として使用する文字列 **`true`** 。

### <a name="remarks"></a>解説

このメンバー関数は、[do_truename](#do_truename) を返します。

すべてのロケールは、値を表す文字列 "true" を返し **`true`** ます。

### <a name="example"></a>例

```cpp
// numpunct_truename.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "English" );

   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;

   locale loc2("French");
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;
}
```

```Output
English_United States.1252 truename true
English_United States.1252 falsename false
French_France.1252 truename true
French_France.1252 falsename false
```

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)\
[ファセットクラス](../standard-library/locale-class.md#facet_class)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
