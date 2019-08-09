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
ms.openlocfilehash: 67aef1ce52b6717ce6d6381429982cf660aa5e20
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457641"
---
# <a name="numget-class"></a>num_get クラス

`CharType` 型のシーケンスから数値への変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。

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

## <a name="remarks"></a>Remarks

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[num_get](#num_get)|シーケンスから数値を抽出するために使用される `num_get` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|入力反復子を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_get](#do_get)|文字シーケンスから数値またはブール値を抽出するために呼び出される仮想関数。|
|[get](#get)|文字シーケンスから数値のまたはブール値を抽出します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="char_type"></a>  num_get::char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター **CharType** のシノニムです。

## <a name="do_get"></a>  num_get::do_get

文字シーケンスから数値またはブール値を抽出するために呼び出される仮想関数。

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

### <a name="parameters"></a>パラメーター

*まずは*\
数値を読み取る文字の範囲の開始位置。

*前の*\
数値を読み取る文字の範囲の終了位置。

*_Iosbase*\
変換で使用されるフラグが含まれる [Ios_base](../standard-library/ios-base-class.md)。

*状態 (_c)* \
失敗した場合に failbit が追加される状態 (「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照)。

*val*\
読み取られた値。

### <a name="return-value"></a>戻り値

値が読み取られた後の反復子。

### <a name="remarks"></a>Remarks

1 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;
```

空でない完全な整数入力フィールドを`[first, last)`認識するまで、シーケンスの先頭から始まる連続する要素に一致します。 成功した場合は、このフィールドを**long**型と同等の値に変換し、結果を*val*に格納します。 これは、数値入力フィールドを超える先頭の要素を指す反復子を返します。 それ以外の場合、関数は、 *val*に`ios_base::failbit`何`state`も格納せず、にを設定します。 これは、有効な整数入力フィールドのプレフィックスを超える先頭の要素を指す反復子を返します。 いずれの場合も、戻り値が `last` と等しい場合、関数は `state` に `ios_base::eofbit` を設定します。

整数入力フィールドは、ファイルから一連の**char**要素を照合して変換するために、スキャン機能によって使用されるのと同じ規則によって変換されます。 (このような**char**要素は、単純な一対一のマッピングに`Elem`よって型の同等の要素にマップされると想定されます)。同等のスキャン変換仕様は次のように決定されます。

`iosbase.`[ios_base::flags](../standard-library/ios-base-class.md#flags)`() & ios_base::basefield == ios_base::`[oct](../standard-library/ios-functions.md#oct) の場合、変換仕様は `lo` です。

`iosbase.flags() & ios_base::basefield == ios_base::`[hex](../standard-library/ios-functions.md#hex) の場合、変換仕様は `lx` です。

`iosbase.flags() & ios_base::basefield == 0` の場合、変換仕様は `li` です。

それ以外の場合、変換仕様は `ld` です。

整数入力フィールドの形式は、さらに、[ロケール ファセット](../standard-library/locale-class.md#facet_class) `fac` で決定されます。これは、[use_facet](../standard-library/locale-functions.md#use_facet) `<`[numpunct](../standard-library/numpunct-class.md)`<Elem>(iosbase.` [ios_base::getloc](../standard-library/ios-base-class.md#getloc)`())` の呼び出しによって返されます。 具体的には、次のように使用します。

`fac.` [numpunct::grouping](../standard-library/numpunct-class.md#grouping) `()` は、小数点の左側の数字をグループ化する方法を決定します。

`fac.` [numpunct::thousands_sep](../standard-library/numpunct-class.md#thousands_sep) `()` は、小数点の左側にある数字のグループを区切るシーケンスを決定します。

数値入力フィールドに `fac.thousands_sep()` のインスタンスがない場合、グループ化の制約は強制されません。 それ以外の場合は、`fac.grouping()` によって強制されたグループ化の制約が適用され、スキャンの変換が行われる前に区切り記号が削除されます。

4 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `lu` に置き換えている点が異なります。 成功した場合は、数値入力フィールドを**unsigned long**型の値に変換し、その値を*val*に格納します。

5 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `lld` に置き換えている点が異なります。 成功した場合は、数値入力フィールドを**long**型の値に変換し、その値を*val*に格納します。

6 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `llu` に置き換えている点が異なります。 成功した場合は、数値入力フィールドを**unsigned long long**型の値に変換し、その値を*val*に格納します。

7 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#decimal_point)`()` は、整数桁と小数桁を区切るシーケンスを決定します。 同等のスキャン変換指定子は `lf` です。

8 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#decimal_point)`()` は、整数桁と小数桁を区切るシーケンスを決定します。 同等のスキャン変換指定子は `lf` です。

9 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

この関数の動作は 8 番目と同じですが、同等のスキャン変換指定子が `Lf` である点が異なります。

10番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

この関数の動作は 1 番目と同じですが、同等のスキャン変換指定子が `p` である点が異なります。

最後 (11 番目) のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全なブール値入力フィールドとの一致を試みる点が異なります。 成功した場合は、ブール型の入力フィールドを**bool**型の値に変換し、その値を*val*に格納します。

ブール値入力フィールドは、次の 2 つの形式のいずれかになります。 `iosbase.flags() & ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) が false の場合、これは整数入力フィールドと同じですが、変換後の値が 0 (false の場合) または 1 (true の場合) のいずれかである必要がある点が異なります。 それ以外の場合、シーケンスは `fac.`[numpunct::falsename](../standard-library/numpunct-class.md#falsename)`()` (false の場合) または `fac.`[numpunct::truename](../standard-library/numpunct-class.md#truename)`()` (true の場合) のいずれかに一致する必要があります。

### <a name="example"></a>例

[get](#get) の例 (仮想メンバー関数が `do_get` で呼び出される) を参照してください。

## <a name="get"></a>  num_get::get

文字シーケンスから数値のまたはブール値を抽出します。

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

### <a name="parameters"></a>パラメーター

*まずは*\
数値を読み取る文字の範囲の開始位置。

*前の*\
数値を読み取る文字の範囲の終了位置。

*_Iosbase*\
変換で使用されるフラグが含まれる [Ios_base](../standard-library/ios-base-class.md)。

*状態 (_c)* \
失敗した場合に failbit が追加される状態 (「[ios_base::iostate](../standard-library/ios-base-class.md#iostate)」を参照)。

*val*\
読み取られた値。

### <a name="return-value"></a>戻り値

値が読み取られた後の反復子。

### <a name="remarks"></a>Remarks

すべてのメンバー関数が [do_get](#do_get)( `first`, `last`, `_Iosbase`, `_State`, `val`) を返します。

1 番目のプロテクト仮想メンバー関数は、シーケンス [ `first`, `last`) の先頭から始め、空でない完全な整数入力フィールドを認識するまで、連続した要素との一致を試みます。 成功した場合は、このフィールドを**long**型と同等の値に変換し、結果を*val*に格納します。 これは、数値入力フィールドを超える先頭の要素を指す反復子を返します。 それ以外の場合、関数は、 *val*に`ios_base::failbit` nothing を格納し、を _ *State*に設定します。 これは、有効な整数入力フィールドのプレフィックスを超える先頭の要素を指す反復子を返します。 どちらの場合も、戻り値が*last*と等しい場合、関数`ios_base::eofbit`は状態を設定します *(_s)* 。

整数入力フィールドは、ファイルから一連の**char**要素を照合して変換するために、スキャン機能によって使用されるのと同じ規則によって変換されます。 このような**char**要素は、単純な1対1のマッピング`CharType`によって、型の同等の要素にマップされると見なされます。 同等のスキャン変換仕様は次のように決定されます。

- `iosbase` [フラグ](../standard-library/ios-base-class.md#flags) & 10月、[](../standard-library/ios-functions.md#oct)変換仕様は`lo`です。`ios_base::basefield` == `ios_base::`

- **Iosbase. flags** & **ios_base:: basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex)の場合、変換仕様は`lx`です。

- **iosbase.flags** & **ios_base::basefield** == 0 の場合、変換仕様は `li` です。

- それ以外の場合、変換仕様は `ld` です。

整数入力フィールドの形式は、 [use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase. flags**) の呼び出しによって返される[ロケールファセット](../standard-library/locale-class.md#facet_class)**fac.** によってさらに決定されます。 [getloc](../standard-library/ios-base-class.md#getloc))。 具体的には、次のように使用します。

- **fac.** 。 [グループ化](../standard-library/numpunct-class.md#grouping)は、小数点の左側に桁をグループ化する方法を決定します。

- **fac.** 。 [thousands_sep](../standard-library/numpunct-class.md#thousands_sep)は、小数点の左側にある数字のグループを区切るシーケンスを決定します。

**Fac.** のインスタンスが存在しない場合。 `thousands_sep`数値入力フィールドでは、グループ化の制約は適用されません。 それ以外の場合は、 **fac.** によって課せられるグループ化の制約です。 **グループ化**が適用され、スキャン変換が行われる前に区切り記号が削除されます。

2 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `lu` に置き換えている点が異なります。 成功した場合は、数値入力フィールドを**unsigned long**型の値に変換し、その値を*val*に格納します。

3 番目のプロテクト仮想メンバー関数：

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 **fac.** 。 [decimal_point](../standard-library/numpunct-class.md#decimal_point)は、小数部の桁を区切るシーケンスを決定します。 同等のスキャン変換指定子は `lf` です。

4 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```

同等のスキャン変換指定子が`Lf`である点を除いて、3番目と同じ動作をします。

5 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```

この関数の動作は 1 番目と同じですが、同等のスキャン変換指定子が `p` である点が異なります。

6 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```

この関数の動作は 1 番目と同じですが、空でない完全なブール値入力フィールドとの一致を試みる点が異なります。 成功した場合は、ブール型の入力フィールドを**bool**型の値に変換し、その値を*val*に格納します。

ブール値入力フィールドは、次の 2 つの形式のいずれかになります。 **Iosbase. flags**の場合。 **フラグ**   [](../standard-library/ios-functions.md#boolalpha)のブール値は false です。これは整数入力フィールドと同じですが、変換後の値は 0 (false の場合) または 1 (true の場合) のいずれかである必要があります。 & `ios_base::` それ以外の場合、シーケンスはいずれかの**fac.** に一致する必要があります。 [falsename](../standard-library/numpunct-class.md#falsename)( **false**の場合)、または**fac.** です。 [](../standard-library/numpunct-class.md#truename) ○( **true**の場合)。

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

## <a name="iter_type"></a>  num_get::iter_type

入力反復子を表す型。

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `InputIterator` のシノニムです。

## <a name="num_get"></a>  num_get::num_get

シーケンスから数値を抽出するために使用される `num_get` 型のオブジェクトのコンストラクター。

```cpp
explicit num_get(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

*参照 (_c)* \
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>Remarks

*Refs*パラメーターに指定できる値とその意味は、次のとおりです。

- 0オブジェクトの有効期間は、オブジェクトが含まれているロケールによって管理されます。

- 1:オブジェクトの有効期間は、手動で管理する必要があります。

- \>1:これらの値は定義されていません。

デストラクターが保護されているため、利用できる直接的な例はありません。

コンストラクターは、**locale::** [facet](../standard-library/locale-class.md#facet_class)( `_Refs`) を使用して、その基本オブジェクトを初期化します。

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)\
[facet クラス](../standard-library/locale-class.md#facet_class)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
