---
title: num_put クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocnum/std::num_put
- locale/std::num_put::char_type
- locale/std::num_put::iter_type
- locale/std::num_put::do_put
- locale/std::num_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::num_put [C++]
- std::num_put [C++], char_type
- std::num_put [C++], iter_type
- std::num_put [C++], do_put
- std::num_put [C++], put
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a860f7c266685e7e10f9b4cbe46c280c356f2681
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="numput-class"></a>num_put クラス

数値から `CharType` 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。

## <a name="syntax"></a>構文

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>パラメーター

`CharType` ロケールの文字をエンコードする、プログラム内で使用される型。

`OutputIterator` 数値 put 関数が出力を書き込む反復子の型。

## <a name="remarks"></a>コメント

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[num_put](#num_put)|`num_put` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|出力反復子を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_put](#do_put)|数値を、特定のロケールで書式設定された数値を表す `CharType` のシーケンスに変換するために呼び出される仮想関数。|
|[put](#put)|数値を、特定のロケールで書式設定された数値を表す `CharType` のシーケンスに変換します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="char_type"></a>  num_put::char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター **CharType** のシノニムです。

## <a name="do_put"></a>  num_put::do_put

数値を、特定のロケールで書式設定された数値を表す **CharType** のシーケンスに変換するために呼び出される仮想関数。

```cpp
virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;


virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const unsigned long long val) const;
```

### <a name="parameters"></a>パラメーター

`next` 挿入された文字列の最初の要素を示す反復子。

`_Iosbase` ためには、出力と出力を書式設定するためのフラグを punctuate numpunct ファセットとロケールを含むストリームを指定します。

`_Fill` 間隔に使用される文字。

`val` 出力するブール型または数。

### <a name="return-value"></a>戻り値

生成される最後の要素を 1 つ超える位置を示す出力反復子。

### <a name="remarks"></a>コメント

1 番目のプロテクト仮想メンバー関数は、`next` 以降の連続した要素を生成し、`val` の値から整数出力フィールドを生成します。 関数は、生成された出力フィールドを超える、次に要素を挿入する場所を指定する反復子を返します。

整数出力フィールドは、一連の `char` 要素をファイルに生成するために出力関数によって使用されるルールと同じルールで生成されます。 このような char 要素は、単純な一対一のマッピングで **CharType** 型の同等の要素にマップされると想定されます。 出力関数はフィールドを埋めるのにスペースと数字の 0 のいずれかを使用しますが、`do_put` は代わりに **fill** を使用します。 同等の出力変換仕様は次のように決定されます。

- 場合**iosbase**です。 [フラグ](../standard-library/ios-base-class.md#flags) & `ios_base::basefield` == `ios_base::`[oct](../standard-library/ios-functions.md#oct)、変換の仕様は**lo**です。

- **iosbase.flags** & **ios_base::basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex) の場合、変換仕様は **lx** です。

- それ以外の場合、変換仕様は **ld** です。

場合**iosbase**です。 [幅](../standard-library/ios-base-class.md#width)は 0 以外、この値のフィールドの幅が先頭に付加します。 関数を呼び出すし**iosbase**です。 **幅**フィールドの幅を 0 にリセットするには、(0) です。

場合にのみ、余白が発生する要素の最小数*N*出力フィールドを指定するために必要な未満**iosbase**です。 [幅](../standard-library/ios-base-class.md#width)です。 このような余白のシーケンスから成る*N* - **幅**のコピー **fill**です。 この場合、埋め込みは次のように発生します。

- 場合**iosbase**です。 **フラグ** & `ios_base::adjustfield` == `ios_base::`[左](../standard-library/ios-functions.md#left)、フラグ**-** 前付けられます。 (埋め込みは、生成されたテキストの後に発生します。)

- **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[internal](../standard-library/ios-functions.md#internal) の場合、**0** フラグが先頭に付加されます。 (数値出力フィールド場合、埋め込みは、出力関数が 0 で埋め込む状況でのみ発生します。)

- それ以外の場合、追加のフラグは先頭に付加されません。 (埋め込みは、生成されたシーケンスの前に発生します。)

最後に次のようになります。

- 場合**iosbase**です。 **フラグ** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) 0 以外の場合は、フラグ**+** は前の変換指定に付加します。

- 場合**iosbase**です。 **フラグ** & **ios_base::**[showbase](../standard-library/ios-functions.md#showbase) 0 以外の場合は、フラグ**#** は前の変換指定に付加します。

整数値の形式の出力フィールドによって決定、[ロケールのファセット](../standard-library/locale-class.md#facet_class)**要素**呼び出しによって返される[use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase**です。 [getloc](../standard-library/ios-base-class.md#getloc))。 具体的には、次のように使用します。

- **要素**です。 [グループ化](../standard-library/numpunct-class.md#grouping)桁の数字が小数点の左側にグループ化する方法を決定

- **要素**です。 [thousands_sep](../standard-library/numpunct-class.md#thousands_sep)小数点の左側にある数字のグループを区切る順序を決定

グループ化の制約が課せられなかった場合**要素**です。 **グループ化**(先頭の要素値を持つ CHAR_MAX) のインスタンスがしない**要素**です。 `thousands_sep` 出力フィールドで生成されます。 それ以外の場合、出力変換が発生した後に区切り記号が挿入されます。

2 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

この関数の動作は 1 番目と同じですが、**ld** の変換仕様を **lu** に置き換えている点が異なります。

3 番目のプロテクト仮想メンバー関数：

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

この関数の動作は 1 番目と同じですが、**val** の値から浮動小数点出力フィールドを生成している点が異なります。 **要素**です。 [decimal_point](../standard-library/numpunct-class.md#decimal_point)整数部の桁数を小数点以下桁数から分離する順序を決定します。 同等の出力変換仕様は次のように決定されます。

- 場合**iosbase**です。 **フラグ** & `ios_base::floatfield` == `ios_base::`[固定](../standard-library/ios-functions.md#fixed)、変換の仕様は**lf**です。

- 場合**iosbase**です。 **flags** & **ios_base::floatfield** == `ios_base::`[scientific](../standard-library/ios-functions.md#scientific), the conversion specification is `le`. 場合**iosbase**です。 **フラグ** & `ios_base::`[大文字](../standard-library/ios-functions.md#uppercase)がゼロ以外、 **e**に置き換えられます**E**です。

- それ以外の場合、変換仕様は **lg** です。 場合**iosbase**です。 **フラグ** & **ios_base::uppercase**がゼロ以外、 **g**に置き換えられます**G**です。

場合**iosbase**です。 **フラグ** & **ios_base::fixed**が 0 でない場合、または**iosbase**です。 [有効桁数](../standard-library/ios-base-class.md#precision)が 0 の場合、値を持つ有効桁数よりも大きい**iosbase**です。 **有効桁数**は前の変換指定に付加します。 埋め込みの動作は整数出力フィールドの場合と同様です。 埋め込み文字は **fill** です。 最後に次のようになります。

- 場合**iosbase**です。 **フラグ** & `ios_base::`[showpos](../standard-library/ios-functions.md#showpos) 0 以外の場合は、フラグ**+** は前の変換指定に付加します。

- 場合**iosbase**です。 **フラグ** & `ios_base::`[showpoint](../standard-library/ios-functions.md#showpoint) 0 以外の場合は、フラグ**#** は前の変換指定に付加します。

4 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

この関数の動作は 3 番目と同じですが、変換仕様内の修飾子 **l** が **L** に置き換えられている点が異なります。

5 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

この関数の動作は 1 番目と同じですが、変換仕様が `p` と**、**埋め込みを指定するために必要なすべての修飾子である点が異なります。

6 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

この関数の動作は 1 番目と同じですが、`val` からブール値出力フィールドを生成している点が異なります。

ブール値出力フィールドは、次の 2 つの形式のいずれかになります。 場合**iosbase**です。 **フラグ** & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha)は**false**、メンバー関数を返します`do_put`(_*次*、 \_*Iosbase*、 \_ *塗りつぶし*、(**長い**) `val`)、通常 0 の生成されたシーケンスが生成されます (の**false**) または 1 (の**true**)。 それ以外の場合、生成されたシーケンスであるか、**要素**です。 [falsename](../standard-library/numpunct-class.md#falsename) `)` (の**false**)、または**要素**です。 [truename](../standard-library/numpunct-class.md#truename) (の**true**)。

7 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

この関数の動作は 1 番目と同じですが、**ld** の変換仕様を **lld** に置き換えている点が異なります。

8 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    unsigned long long val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `llu` に置き換えている点が異なります。

### <a name="example"></a>例

[put](#put) の例 (`do_put` を呼び出す) を参照してください。

## <a name="iter_type"></a>  num_put::iter_type

出力反復子を表す型。

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター **OutputIterator** のシノニムです。

## <a name="num_put"></a>  num_put::num_put

`num_put` 型のオブジェクトのコンストラクター。

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

`_Refs` オブジェクトのメモリ管理の種類を指定するために使用する整数値です。

### <a name="remarks"></a>コメント

`_Refs` パラメーターの可能な値とその重要性は次のとおりです。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \> 1: これらの値が定義されていません。

デストラクターが保護されているため、利用できる直接的な例はありません。

コンストラクターは、**locale::**[facet](../standard-library/locale-class.md#facet_class)(_ *Refs*) を使用して、その基本オブジェクトを初期化します。

## <a name="put"></a>  num_put::put

数値を、特定のロケールで書式設定された数値を表す **CharType** のシーケンスに変換します。

```cpp
iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    bool val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    unsigned long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Long long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    Unsigned long long val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    double val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    long double val) const;


iter_type put(
    iter_type dest,
    ios_base& _Iosbase,
    _Elem _Fill,
    const void* val) const;
```

### <a name="parameters"></a>パラメーター

`dest` 挿入された文字列の最初の要素を示す反復子。

`_Iosbase` ためには、出力と出力を書式設定するためのフラグを punctuate numpunct ファセットとロケールを格納しているストリームを指定します。

`_Fill` 間隔に使用される文字。

`val` 出力するブール型または数。

### <a name="return-value"></a>戻り値

生成される最後の要素を 1 つ超える位置を示す出力反復子。

### <a name="remarks"></a>コメント

すべてのメンバー関数が [do_put](#do_put)( `next`, `_Iosbase`, `_Fill`, `val`) を返します。

### <a name="example"></a>例

```cpp
// num_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );
   basic_stringstream<char> psz2;
   ios_base::iostate st = 0;
   long double fVal;
   cout << "The thousands separator is: "
        << use_facet < numpunct <char> >(loc).thousands_sep( )
        << endl;

   psz2.imbue( loc );
   use_facet < num_put < char > >
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),
                    psz2, ' ', fVal=1000.67);

   if ( st & ios_base::failbit )
      cout << "num_put( ) FAILED" << endl;
   else
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;
}
```

```Output
The thousands separator is: .
num_put( ) = 1.000,67
```

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)<br/>
[facet クラス](../standard-library/locale-class.md#facet_class)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
