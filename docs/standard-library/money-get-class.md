---
title: money_get クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_get
- xlocmon/std::money_get::char_type
- xlocmon/std::money_get::iter_type
- xlocmon/std::money_get::string_type
- xlocmon/std::money_get::do_get
- xlocmon/std::money_get::get
dev_langs:
- C++
helpviewer_keywords:
- std::money_get [C++]
- std::money_get [C++], char_type
- std::money_get [C++], iter_type
- std::money_get [C++], string_type
- std::money_get [C++], do_get
- std::money_get [C++], get
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b6043da3945b36bd756714049b2bb6c91a32bd4
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966551"
---
# <a name="moneyget-class"></a>money_get クラス

このテンプレート クラスは、`CharType` 型のシーケンスから通貨値への変換を制御するためにロケール ファセットとして使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class money_get : public locale::facet;
```

### <a name="parameters"></a>パラメーター

*CharType*ロケールの文字をエンコードする、プログラム内で使用される型。

*InputIterator* get 関数が入力の読み取り元の反復子の型。

## <a name="remarks"></a>Remarks

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[money_get](#money_get)|通貨値を表すシーケンスから数値を抽出するために使用される `money_get` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|入力反復子を表す型。|
|[string_type](#string_type)|`CharType` 型の文字を格納する文字列を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_get](#do_get)|通貨値を表す文字シーケンスから数値を抽出するために呼び出される仮想関数。|
|[get](#get)|通貨値を表す文字シーケンスから数値を抽出します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="char_type"></a>  money_get::char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター *CharType* のシノニムです。

## <a name="do_get"></a>  money_get::do_get

通貨値を表す文字シーケンスから数値を抽出するために呼び出される仮想関数。

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const
```

### <a name="parameters"></a>パラメーター

*最初*変換されるシーケンスの先頭を示す入力反復子。

*最後*変換されるシーケンスの末尾を示す入力反復子。

*Intl*を示すブール値のシーケンスで期待される通貨記号の種類を示す: **true**場合、国際**false**国内場合。

*Iosbase*形式にフラグを設定すると設定は、通貨記号が省略可能であることを示します。 それ以外の場合、これが必要です。

*状態*かどうか、操作が成功したかどうかに従って、ストリームの状態の適切なビットマスク要素を設定します。

*val*変換されたシーケンスを格納する文字列。

### <a name="return-value"></a>戻り値

通貨入力フィールドを超える先頭の要素を示す入力反復子。

### <a name="remarks"></a>Remarks

1 番目のプロテクト仮想メンバー関数は、シーケンス [ `first`, `last`) の先頭から始め、空でない完全な通貨入力フィールドを認識するまで、連続した要素との一致を試みます。 かどうかは成功すると、このフィールドに変換の一連の 1 つまたは複数 10 進数字、必要に応じて頭にマイナス記号 ( `-`)、金額を表すために結果を格納し、 [string_type](#string_type)オブジェクト*val*. そして、通貨入力フィールドを超える先頭の要素を指す反復子を返します。 関数に空のシーケンスを格納する場合は、 *val*設定と`ios_base::failbit`で*状態*します。 そして、有効な通貨入力フィールドのプレフィックスを超える先頭の要素を指す反復子を返します。 いずれの場合も、戻り値が `last` と等しい場合、関数は `State` に `ios_base::eofbit` を設定します。

2 番目のプロテクト仮想メンバー関数動作は 1 番目と同じ型の値を必要に応じて符号を付けた数字シーケンス成功した場合に変換する点を除いて**long double**でその値を格納および*val*.

通貨入力フィールドの形式が定め、[ロケール ファセット](../standard-library/locale-class.md#facet_class)**fac**実質的な呼び出しによって返される[use_facet](../standard-library/locale-functions.md#use_facet)  <  [moneypunct](../standard-library/moneypunct-class.md) \< **CharType**、 **intl**>> ( **iosbase**します。 [getloc](../standard-library/ios-base-class.md#getloc))。

具体的には、次のように使用します。

- **fac**します。 [neg_format](../standard-library/moneypunct-class.md#neg_format)フィールドのコンポーネントが発生する順序を決定します。

- **fac**します。 [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol)通貨記号を構成する要素のシーケンスを決定します。

- **fac**します。 [positive_sign](../standard-library/moneypunct-class.md#positive_sign)正符号を構成する要素のシーケンスを決定します。

- **fac**します。 [negative_sign](../standard-library/moneypunct-class.md#negative_sign)負の符号を構成する要素のシーケンスを決定します。

- **fac**します。 [グループ化](../standard-library/moneypunct-class.md#grouping)小数点の左側の数字をグループ化する方法を決定します。

- **fac**します。 [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep)小数点の左側にある数字のグループを区切る要素を決定します。

- **fac**します。 [decimal_point](../standard-library/moneypunct-class.md#decimal_point)を小数桁の整数の桁を区切る要素を決定します。

- **fac**します。 [frac_digits](../standard-library/moneypunct-class.md#frac_digits)小数点の右側に有効小数桁の数を決定します。 `frac_digits` によって要求される小数桁数を上回る桁数の値を解析する場合、`do_get` は最大で `frac_digits` 文字を処理した後、解析を停止します。

場合、符号の文字列 ( **fac**します。 `negative_sign` または**fac**します。 `positive_sign`) が 1 つ以上の要素、最初の要素のみが一致した場所に等しい要素**money_base::sign**書式パターンが表示されます ( **fac**します。 `neg_format`) 残りの要素は、通貨入力フィールドの末尾で一致します。 いずれの文字列も通貨入力フィールド内の先頭の要素が次の要素と一致していない場合、符号文字列は空と見なされ、符号は正になります。

場合**iosbase**します。 [フラグ](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) 0 以外の場合、文字列**fac**します。 `curr_symbol` 場所に一致する必要がありますに等しい要素**money_base::symbol**形式パターンに出現します。 このようにしないと、書式パターンの末尾に **money_base::symbol** が出現する場合、および一致せずに残っている符号文字列の要素がない場合に、通貨記号は一致しません。 それ以外の場合は、必要に応じて通貨記号が一致します。

インスタンスがない場合**fac**します。 `thousands_sep` 通貨入力フィールドの値の部分で発生する (ここに等しい要素**money_base::value**書式パターンが表示されます)、グループ化の制約は強制されません。 によってグループ化の制約が課される場合は、 **fac**します。 **グループ化**が適用されます。 結果の数字シーケンスを表す整数の下位注**fac**します。 `frac_digits` 10 進数字が小数点の右側と見なされます。

任意の余白は、書式パターンの末尾以外に出現する場合、**money_base::space** と等しい要素が書式パターンに出現しているときに一致します。 それ以外の場合、内部の余白は一致しません。 要素*ch*場合、空白文字とみなされます[use_facet](../standard-library/locale-functions.md#use_facet) < [ctype](../standard-library/ctype-class.md) \< **CharType**>> (**iosbase**します。 [getloc](../standard-library/ios-base-class.md#getloc))。 [は](../standard-library/ctype-class.md#is)( **ctype_base::space**、 *ch*) は**true**します。

### <a name="example"></a>例

[get](#get) の例 (`do_get` を呼び出す) を参照してください。

## <a name="get"></a>  money_get::get

通貨値を表す文字シーケンスから数値を抽出します。

```cpp
iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const;
```

### <a name="parameters"></a>パラメーター

*最初*変換されるシーケンスの先頭を示す入力反復子。

*最後*変換されるシーケンスの末尾を示す入力反復子。

*Intl*を示すブール値のシーケンスで期待される通貨記号の種類を示す: **true**場合、国際**false**国内場合。

*Iosbase*形式にフラグを設定すると設定は、通貨記号が省略可能であることを示しますこれは必要な場合は、。

*状態*操作が成功するかどうかに従って、ストリームの状態の適切なビットマスク要素を設定します。

*val*変換されたシーケンスを格納する文字列。

### <a name="return-value"></a>戻り値

通貨入力フィールドを超える先頭の要素を示す入力反復子。

### <a name="remarks"></a>Remarks

両方のメンバー関数が返す[do_get](#do_get)`(first, last, Intl, Iosbase, State, val)`します。

### <a name="example"></a>例

```cpp
// money_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;

int main( )
{
   locale loc( "german_germany" );

   basic_stringstream< char > psz;
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";
   basic_stringstream< char > psz2;
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();

   ios_base::iostate st = 0;
   long double fVal;

   psz.flags( psz.flags( )|ios_base::showbase );
   // Which forced the READING the currency symbol
   psz.imbue(loc);
   use_facet < money_get < char > >( loc ).
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"
           << endl;
   else
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "
           << fVal/100.0 << endl;

   use_facet < money_get < char > >( loc ).
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"
           << endl;
   else
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "
           << fVal/100.0 << endl;
};
```

## <a name="iter_type"></a>  money_get::iter_type

入力反復子を表す型。

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター **InputIterator** のシノニムです。

## <a name="money_get"></a>  money_get::money_get

通貨値を表すシーケンスから数値を抽出するために使用される `money_get` 型のオブジェクトのコンストラクター。

```cpp
explicit money_get(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

*_Refs*オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>Remarks

使用可能な値を *_Refs*パラメーターとその重要性は。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \> 1: これらの値が定義されていません。

デストラクターが保護されているため、利用できる直接的な例はありません。

コンス トラクターを使用してその基本オブジェクトを初期化します**ロケール::**[ファセット](../standard-library/locale-class.md#facet_class)(**_ * * * Refs*)。

## <a name="string_type"></a>  money_get::string_type

**CharType** 型の文字を格納する文字列を表す型。

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Remarks

この型は、特殊化したテンプレート クラス [basic_string](../standard-library/basic-string-class.md) を表します。

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)<br/>
[facet クラス](../standard-library/locale-class.md#facet_class)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
