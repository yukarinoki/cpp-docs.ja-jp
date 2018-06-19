---
title: money_put クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_put
- xlocmon/std::money_put::char_type
- xlocmon/std::money_put::iter_type
- xlocmon/std::money_put::string_type
- xlocmon/std::money_put::do_put
- xlocmon/std::money_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::money_put [C++]
- std::money_put [C++], char_type
- std::money_put [C++], iter_type
- std::money_put [C++], string_type
- std::money_put [C++], do_put
- std::money_put [C++], put
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df8b872d9aeb718c1e86d460d8ef60beac8f3632
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862443"
---
# <a name="moneyput-class"></a>money_put クラス

このテンプレート クラスは、通貨値から `CharType` 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class money_put : public locale::facet;
```

### <a name="parameters"></a>パラメーター

`CharType` ロケールの文字をエンコードする、プログラム内で使用される型。

`OutputIterator` 通貨の put 関数が出力を書き込む反復子の型。

## <a name="remarks"></a>コメント

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[money_put](#money_put)|`money_put` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|出力反復子を表す型。|
|[string_type](#string_type)|`CharType` 型の文字を格納する文字列を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_put](#do_put)|通貨値を表す文字シーケンスから数値または文字列を抽出するために呼び出される仮想関数。|
|[put](#put)|数値または文字列を通貨値を表す文字シーケンスに変換します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="char_type"></a>  money_put::char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター **CharType** のシノニムです。

## <a name="do_put"></a>  money_put::do_put

通貨値を表す文字シーケンスから数値または文字列を抽出するために呼び出される仮想関数。

```cpp
virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;


virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>パラメーター

`next` 挿入された文字列の最初の要素を示す反復子。

`_Intl` シーケンス内の予想通貨記号の種類を示すブール値: **true**場合は、国際**false**国内場合。

`_Iosbase` 形式にフラグを設定すると、セットは、通貨記号が省略可能ですであることを示します。それ以外の場合、これが必要

`_Fill` スペースのために使用される文字。

`val` 変換する文字列オブジェクト。

### <a name="return-value"></a>戻り値

生成される最後の要素を 1 つ超える位置を示す出力反復子。

### <a name="remarks"></a>コメント

1 番目のプロテクト仮想メンバー関数は、`next` 以降の連続した要素を生成し、[string_type](#string_type) オブジェクト `val` から通貨出力フィールドを生成します。 によって制御されるシーケンス`val`1 つ以上の 10 進、金額を表す負符号 (-) に続くで始まる必要があります。 関数は、生成された通貨出力フィールドを超える先頭の要素を指す反復子を返します。

2 番目のプロテクト仮想メンバー関数は 1 番目と同様に動作します。ただし、最初に `val` を 10 進数字のシーケンス (必要に応じて頭にマイナス記号が付く) に実質的に変換し、その後でこのシーケンスを上記のように変換します。

通貨出力フィールドの形式は、によって決まりますが、[ロケールのファセット](../standard-library/locale-class.md#facet_class)(有効) の呼び出しによって返された要素[use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md) \< **CharType**、 **intl**>> ( **iosbase**です。 [getloc](../standard-library/ios-base-class.md#getloc))。

具体的には、次のように使用します。

- **要素**です。 [pos_format](../standard-library/moneypunct-class.md#pos_format)負でない値のフィールドのコンポーネントを生成する順序を決定します。

- **要素**です。 [neg_format](../standard-library/moneypunct-class.md#neg_format)負の値のフィールドのコンポーネントを生成する順序を決定します。

- **要素**です。 [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol)通貨記号を生成する要素のシーケンスを決定します。

- **要素**です。 [positive_sign](../standard-library/moneypunct-class.md#positive_sign)正の符号を生成する要素のシーケンスを決定します。

- **要素**です。 [negative_sign](../standard-library/moneypunct-class.md#negative_sign)に負の符号を生成する要素のシーケンスを決定します。

- **要素**です。 [グループ化](../standard-library/moneypunct-class.md#grouping)桁の数字が小数点の左側にグループ化する方法を決定します。

- **要素**です。 [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep)小数点の左側にある数字のグループを区切る要素を決定します。

- **要素**です。 [decimal_point](../standard-library/moneypunct-class.md#decimal_point)要素を区切る整数部の桁数、小数点以下桁数を決定します。

- **要素**です。 [frac_digits](../standard-library/moneypunct-class.md#frac_digits)小数点の右側に大幅な小数点以下桁数の数を決定します。

場合、記号の文字列 (**要素**です。 `negative_sign` または**要素**です。 `positive_sign`) に複数の要素、最初の要素のみがある場所に生成されると等しい要素**money_base::sign**形式パターンに表示されます (**要素**です。 `neg_format` または**要素**です。 `pos_format`) 残りの要素は、通貨出力フィールドの末尾に生成されます。

場合**iosbase**です。 [フラグ](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) 0 以外の場合は、文字列**要素**です。 `curr_symbol` ここで生成される要素と等しい**money_base::symbol**形式パターンに表示されます。 それ以外の場合、通貨記号は生成されません。

グループ化の制約が課せられなかった場合**要素**です。 **グループ化**(先頭の要素値を持つ CHAR_MAX) のインスタンスがしない**要素**です。 `thousands_sep` 通貨出力フィールドの値の部分で生成されます (ここで、要素と等しい**money_base::value**形式パターンに表示されます)。 場合**要素**です。 `frac_digits` インスタンスはされません**要素**です。 `decimal_point` 10 進数字の後に生成されます。 それ以外の場合、結果として得られる通貨出力フィールド、注文低 -**要素**です。 `frac_digits` 小数点の右側に 10 進数字。

パディングが発生する場合を除く、任意の数値出力フィールドと**iosbase**です。 **フラグ** & **iosbase**です。 [内部](../standard-library/ios-functions.md#internal)0 以外の任意の内部の余白は、ここで生成されると等しい要素**money_base::space**表示する場合は、形式パターンに表示されます。 それ以外の場合、内部の埋め込みは生成されたシーケンスの前に発生します。 埋め込み文字は **fill** です。

関数呼び出し**iosbase**です。 **幅**フィールドの幅を 0 にリセットするには、(0) です。

### <a name="example"></a>例

[put](#put) の例 (仮想メンバー関数が **put** で呼び出される) を参照してください。

## <a name="iter_type"></a>  money_put::iter_type

出力反復子を表す型。

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター **OutputIterator** のシノニムです。

## <a name="money_put"></a>  money_put::money_put

`money_put` 型のオブジェクトのコンストラクター。

```cpp
explicit money_put(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

`_Refs` オブジェクトのメモリ管理の種類を指定するために使用する整数値です。

### <a name="remarks"></a>コメント

`_Refs` パラメーターの可能な値とその重要性は次のとおりです。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \> 1: これらの値が定義されていません。

デストラクターが保護されているため、利用できる直接的な例はありません。

コンストラクターは、**locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`) を使用して、その基本オブジェクトを初期化します。

## <a name="put"></a>  money_put::put

数値または文字列を通貨値を表す文字シーケンスに変換します。

```cpp
iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;


iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>パラメーター

`next` 挿入された文字列の最初の要素を示す反復子。

`_Intl` シーケンス内の予想通貨記号の種類を示すブール値: **true**場合は、国際**false**国内場合。

`_Iosbase` 形式にフラグを設定すると、セットは、通貨記号が省略可能ですであることを示します。それ以外の場合、これが必要

`_Fill` スペースのために使用される文字。

`val` 変換する文字列オブジェクト。

### <a name="return-value"></a>戻り値

生成される最後の要素を 1 つ超える位置を示す出力反復子。

### <a name="remarks"></a>コメント

どちらのメンバー関数も [do_put](#do_put)( `next`, `_Intl`, `_Iosbase`, `_Fill`, `val`) を返します。

### <a name="example"></a>例

```cpp
// money_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
//   locale loc( "german_germany" );
   locale loc( "english_canada" );
   basic_stringstream<char> psz, psz2;
   ios_base::iostate st = 0;

   psz2.imbue( loc );
   psz2.flags( psz2.flags( )|ios_base::showbase ); // force the printing of the currency symbol
   use_facet < money_put < char > >(loc).put(basic_ostream<char>::_Iter( psz2.rdbuf( ) ), true, psz2, st, 100012);
   if (st & ios_base::failbit)
      cout << "money_put( ) FAILED" << endl;
   else
      cout << "money_put( ) = \"" << psz2.rdbuf( )->str( ) <<"\""<< endl;

   st = 0;
};
```

```Output
money_put( ) = "CAD1,000.12"
```

## <a name="string_type"></a>  money_put::string_type

**CharType** 型の文字を格納する文字列を表す型。

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>コメント

この型は、オブジェクトにソース シーケンスからの要素のシーケンスを格納できるテンプレート クラス [basic_string](../standard-library/basic-string-class.md) の特殊化を表します。

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)<br/>
[facet クラス](../standard-library/locale-class.md#facet_class)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
