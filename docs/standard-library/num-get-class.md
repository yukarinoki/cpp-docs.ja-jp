---
title: num_get クラス
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::num_get
- locale/std::num_get::char_type
- locale/std::num_get::iter_type
- locale/std::num_get::do_get
- locale/std::num_get::get
helpviewer_keywords:
- std::num_get [C++]
- std::num_get [C++], char_type
- std::num_get [C++], iter_type
- std::num_get [C++], do_get
- std::num_get [C++], get
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
ms.openlocfilehash: d5a88e904c437e79eabfa854a196aa48dbad955e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228168"
---
# <a name="num_get-class"></a>num_get クラス

型のシーケンスから数値への変換を制御するためにロケールファセットとして使用できるオブジェクトを表すクラステンプレート。 `CharType`

## <a name="syntax"></a>構文

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class num_get : public locale::facet;
```

### <a name="parameters"></a>パラメーター

*CharType*\
ロケールの文字をエンコードするためにプログラム内で使用される型。

*InputIterator*\
数値の get 関数が入力を読み取る反復子の型。

## <a name="remarks"></a>解説

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|[説明]|
|-|-|
|[num_get](#num_get)|シーケンスから数値を抽出するために使用される `num_get` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|入力反復子を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|[説明]|
|-|-|
|[do_get](#do_get)|文字シーケンスから数値またはブール値を抽出するために呼び出される仮想関数。|
|[get](#get)|文字シーケンスから数値のまたはブール値を抽出します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<locale>

**名前空間:** std

## <a name="num_getchar_type"></a><a name="char_type"></a>num_get:: char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター **CharType** のシノニムです。

## <a name="num_getdo_get"></a><a name="do_get"></a>num_get::d o_get

文字シーケンスから数値またはブール値を抽出するために呼び出される仮想関数。

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

### <a name="parameters"></a>パラメーター

*まずは*\
数値を読み取る文字の範囲の開始位置。

*前の*\
数値を読み取る文字の範囲の終了位置。

*iosbase. flags*\
変換で使用されるフラグが含まれる [Ios_base](../standard-library/ios-base-class.md)。

*状態*\
失敗した場合に failbit が追加される状態 (「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照)。

*val*\
読み取られた値。

### <a name="return-value"></a>戻り値

値が読み取られた後の反復子。

### <a name="remarks"></a>解説

1 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;
```

*first* `[first, last)` 空でない完全な整数入力フィールドを認識するまで、シーケンスの先頭から始まる連続する要素に一致します。 成功した場合、このフィールドを型と同等の値に変換 **`long`** し、結果を*val*に格納します。 これは、数値入力フィールドを超える先頭の要素を指す反復子を返します。 それ以外の場合、関数は、 *val*に何も格納せず、にを設定し `ios_base::failbit` `state` ます。 これは、有効な整数入力フィールドのプレフィックスを超える先頭の要素を指す反復子を返します。 いずれの場合も、戻り値が `last` と等しい場合、関数は `state` に `ios_base::eofbit` を設定します。

整数入力フィールドは、ファイルから一連の要素を照合して変換するために、スキャン機能によって使用されるのと同じ規則によって変換され **`char`** ます。 (このような各 **`char`** 要素は、 `Elem` 単純な一対一のマッピングによって型の同等の要素にマップされると見なされます)。同等のスキャン変換仕様は、次のように決定されます。

`iosbase.` [Ios_base:: flags](../standard-library/ios-base-class.md#flags) `() & ios_base::basefield == ios_base::` [oct](../standard-library/ios-functions.md#oct)の場合、変換仕様は `lo` です。

`iosbase.flags() & ios_base::basefield == ios_base::`[hex](../standard-library/ios-functions.md#hex) の場合、変換仕様は `lx` です。

`iosbase.flags() & ios_base::basefield == 0` の場合、変換仕様は `li` です。

それ以外の場合、変換仕様は `ld` です。

整数入力フィールドの形式は、 [locale facet](../standard-library/locale-class.md#facet_class) `fac` [use_facet](../standard-library/locale-functions.md#use_facet) `<` [numpunct](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [ios_base:: getloc](../standard-library/ios-base-class.md#getloc)use_facet の呼び出しによって返されるロケールファセットによってさらに決定され `())` ます。 具体的には次のとおりです。

`fac.`[numpunct:: grouping](../standard-library/numpunct-class.md#grouping) `()`小数点の左側に桁をグループ化する方法を決定します

`fac.`[numpunct:: thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()`小数点の左側にある数字のグループを区切るシーケンスを決定します。

数値入力フィールドに `fac.thousands_sep()` のインスタンスがない場合、グループ化の制約は強制されません。 それ以外の場合は、`fac.grouping()` によって強制されたグループ化の制約が適用され、スキャンの変換が行われる前に区切り記号が削除されます。

4 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `lu` に置き換えている点が異なります。 成功した場合は、数値入力フィールドを型の値に変換 **`unsigned long`** し、その値を*val*に格納します。

5 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `lld` に置き換えている点が異なります。 成功した場合は、数値入力フィールドを型の値に変換 **`long long`** し、その値を*val*に格納します。

6 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `llu` に置き換えている点が異なります。 成功した場合は、数値入力フィールドを型の値に変換 **`unsigned long long`** し、その値を*val*に格納します。

7 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 `fac.`[numpunct::d ecimal_point](../standard-library/numpunct-class.md#decimal_point) `()`小数点以下の桁数と整数の桁を区切るシーケンスを決定します。 同等のスキャン変換指定子は `lf` です。

8 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 `fac.`[numpunct::d ecimal_point](../standard-library/numpunct-class.md#decimal_point) `()`小数点以下の桁数と整数の桁を区切るシーケンスを決定します。 同等のスキャン変換指定子は `lf` です。

9 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

この関数の動作は 8 番目と同じですが、同等のスキャン変換指定子が `Lf` である点が異なります。

10番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

この関数の動作は 1 番目と同じですが、同等のスキャン変換指定子が `p` である点が異なります。

最後 (11 番目) のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全なブール値入力フィールドとの一致を試みる点が異なります。 成功した場合は、ブール型の入力フィールドを型の値に変換 **`bool`** し、その値を*val*に格納します。

ブール値入力フィールドは、次の 2 つの形式のいずれかになります。 `iosbase.flags() & ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) が false の場合、これは整数入力フィールドと同じですが、変換後の値が 0 (false の場合) または 1 (true の場合) のいずれかである必要がある点が異なります。 それ以外の場合、シーケンスは `fac.` [numpunct:: falsename](../standard-library/numpunct-class.md#falsename) `()` (false の場合) または `fac.` [numpunct:: ename](../standard-library/numpunct-class.md#truename) (true の場合) のいずれかと一致する必要があり `()` ます。

### <a name="example"></a>例

[get](#get) の例 (仮想メンバー関数が `do_get` で呼び出される) を参照してください。

## <a name="num_getget"></a><a name="get"></a>num_get:: get

文字シーケンスから数値のまたはブール値を抽出します。

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

### <a name="parameters"></a>パラメーター

*まずは*\
数値を読み取る文字の範囲の開始位置。

*前の*\
数値を読み取る文字の範囲の終了位置。

*iosbase. flags*\
変換で使用されるフラグが含まれる [Ios_base](../standard-library/ios-base-class.md)。

*状態*\
失敗した場合に failbit が追加される状態 (「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照)。

*val*\
読み取られた値。

### <a name="return-value"></a>戻り値

値が読み取られた後の反復子。

### <a name="remarks"></a>解説

すべてのメンバー関数は[do_get](#do_get) `( first, last, iosbase, state, val)` を返します。

1 番目のプロテクト仮想メンバー関数は、シーケンス [ `first`, `last`) の先頭から始め、空でない完全な整数入力フィールドを認識するまで、連続した要素との一致を試みます。 成功した場合、このフィールドを型と同等の値に変換 **`long`** し、結果を*val*に格納します。 これは、数値入力フィールドを超える先頭の要素を指す反復子を返します。 それ以外の場合、関数は、 *val*に nothing を格納し、 `ios_base::failbit` *状態*をに設定します。 これは、有効な整数入力フィールドのプレフィックスを超える先頭の要素を指す反復子を返します。 どちらの場合も、戻り値が*last*と等しい場合、関数 `ios_base::eofbit` は*状態*をに設定します。

整数入力フィールドは、ファイルから一連の要素を照合して変換するために、スキャン機能によって使用されるのと同じ規則によって変換され **`char`** ます。 これらの各 **`char`** 要素は `CharType` 、単純な1対1のマッピングによって、型の同等の要素にマップされると見なされます。 同等のスキャン変換仕様は次のように決定されます。

- `iosbase.`[フラグ](../standard-library/ios-base-class.md#flags) `& ios_base::basefield == ios_base::` [10 月](../standard-library/ios-functions.md#oct)の場合、変換仕様は `lo` です。

- `iosbase.flags & ios_base::basefield == ios_base::`[hex](../standard-library/ios-functions.md#hex) の場合、変換仕様は `lx` です。

- `iosbase.flags & ios_base::basefield == 0` の場合、変換仕様は `li` です。

- それ以外の場合、変換仕様は `ld` です。

整数入力フィールドの形式は、 [locale facet](../standard-library/locale-class.md#facet_class) `fac` getloc [use_facet](../standard-library/locale-functions.md#use_facet)の呼び出しによって返されるロケールファセットによってさらに決定され `<` [`numpunct`](../standard-library/numpunct-class.md) `<Elem>(iosbase.` [getloc](../standard-library/ios-base-class.md#getloc) `())` ます。 具体的には次のとおりです。

- `fac.`[グループ化](../standard-library/numpunct-class.md#grouping)は、小数点の左側に桁をグループ化する方法を決定します。

- `fac.`[thousands_sep](../standard-library/numpunct-class.md#thousands_sep)は、小数点の左側にある数字のグループを区切るシーケンスを決定します。

数値入力フィールドに `fac.thousands_sep` のインスタンスがない場合、グループ化の制約は強制されません。 そうしないと、によって課されるグループ化の制約が適用され、 `fac.grouping` スキャン変換が行われる前に区切り記号が削除されます。

2 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    unsigned long& val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `lu` に置き換えている点が異なります。 成功した場合は、数値入力フィールドを型の値に変換 **`unsigned long`** し、その値を*val*に格納します。

3 番目のプロテクト仮想メンバー関数：

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    double& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 `fac.`[decimal_point](../standard-library/numpunct-class.md#decimal_point)は、小数点以下の桁数と整数の桁を区切るシーケンスを決定します。 同等のスキャン変換指定子は `lf` です。

4 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    long double& val) const;
```

同等のスキャン変換指定子がである点を除いて、3番目と同じ動作をし `Lf` ます。

5 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    void *& val) const;
```

この関数の動作は 1 番目と同じですが、同等のスキャン変換指定子が `p` である点が異なります。

6 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    bool& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全なブール値入力フィールドとの一致を試みる点が異なります。 成功した場合は、ブール型の入力フィールドを型の値に変換 **`bool`** し、その値を*val*に格納します。

ブール値入力フィールドは、次の 2 つの形式のいずれかになります。 `iosbase.flags & ios_base::`[ブール](../standard-library/ios-functions.md#boolalpha)値がの場合 **`false`** 、整数入力フィールドと同じですが、変換後の値は 0 (の場合 **`false`** ) または 1 (の場合) のいずれかである必要があり **`true`** ます。 それ以外の場合、シーケンスは `fac.` [falsename](../standard-library/numpunct-class.md#falsename) (の場合 **`false`** ) または `fac.` [truename](../standard-library/numpunct-class.md#truename) (の場合) のいずれかに一致する必要があり **`true`** ます。

### <a name="example"></a>例

```cpp
// num_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   basic_stringstream<char> psz, psz2;
   psz << "-1000,56";

   ios_base::iostate st = 0;
   long double fVal;
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;

   psz.imbue( loc );
   use_facet <num_get <char> >
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter(0), psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get( ) FAILED" << endl;
   else
      cout << "money_get( ) = " << fVal << endl;
}
```

## <a name="num_getiter_type"></a><a name="iter_type"></a>num_get:: iter_type

入力反復子を表す型。

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `InputIterator` のシノニムです。

## <a name="num_getnum_get"></a><a name="num_get"></a>num_get:: num_get

シーケンスから数値を抽出するために使用される `num_get` 型のオブジェクトのコンストラクター。

```cpp
explicit num_get(size_t refs = 0);
```

### <a name="parameters"></a>パラメーター

*refs*\
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>解説

*Refs*パラメーターに指定できる値とその意味は次のとおりです。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \>1: これらの値は定義されていません。

デストラクターが保護されているため、利用できる直接的な例はありません。

コンストラクターは、ファセットを使用してその基本オブジェクトを初期化し `locale::` [facet](../standard-library/locale-class.md#facet_class) `(refs)` ます。

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)\
[ファセットクラス](../standard-library/locale-class.md#facet_class)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
