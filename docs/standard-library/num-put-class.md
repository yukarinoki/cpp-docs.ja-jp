---
title: num_put クラス
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::num_put
- locale/std::num_put::char_type
- locale/std::num_put::iter_type
- locale/std::num_put::do_put
- locale/std::num_put::put
helpviewer_keywords:
- std::num_put [C++]
- std::num_put [C++], char_type
- std::num_put [C++], iter_type
- std::num_put [C++], do_put
- std::num_put [C++], put
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
ms.openlocfilehash: 3f65d7140bb5c691fa58ec9d74ceda5573280ddb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373644"
---
# <a name="num_put-class"></a>num_put クラス

数値から型`CharType`への変換を制御するロケール ファセットとして使用できるオブジェクトを記述するクラス テンプレート。

## <a name="syntax"></a>構文

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class num_put : public locale::facet;
```

### <a name="parameters"></a>パラメーター

*Chartype*\
ロケールの文字をエンコードするためにプログラム内で使用される型。

*出力反復器*\
数値 put 関数が出力を書き込む反復子の型。

## <a name="remarks"></a>解説

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[num_put](#num_put)|`num_put` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|出力反復子を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_put](#do_put)|数値を、特定のロケールで書式設定された数値を表す `CharType` のシーケンスに変換するために呼び出される仮想関数。|
|[置く](#put)|数値を、特定のロケールで書式設定された数値を表す `CharType` のシーケンスに変換します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="num_putchar_type"></a><a name="char_type"></a>num_put::char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `CharType` のシノニムです。

## <a name="num_putdo_put"></a><a name="do_put"></a>num_put::do_put

数値を、特定のロケールで書式設定された数値を表す `CharType` のシーケンスに変換するために呼び出される仮想関数。

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

*次に*\
挿入された文字列の先頭の要素を示す反復子。

*_Iosbase*\
出力に句読点を付けるために使用される numpunct ファセットを持つロケールおよび出力を書式設定するためのフラグを含むストリームを指定します。

*_Fill*\
スペースに使用される文字。

*ヴァル*\
出力する数値またはブール型。

### <a name="return-value"></a>戻り値

生成される最後の要素を 1 つ超える位置を示す出力反復子。

### <a name="remarks"></a>解説

最初の仮想プロテクト メンバー関数は *、val*の値から整数出力フィールドを生成するために、次から始まる順次要素を*生成します。* 関数は、生成された出力フィールドを超える、次に要素を挿入する場所を指定する反復子を返します。

整数出力フィールドは、ファイルに一連の**char**要素を生成するために印刷関数で使用されるのと同じ規則によって生成されます。 このような char 要素は、単純な 1 対`CharType`1 のマッピングによって、型の等価な要素にマップされると想定されます。 ただし、印刷機能がフィールドにスペースまたは数字 0 を埋め込む`do_put`場合は`fill`、 の代わりに を使用します。 同等の出力変換仕様は次のように決定されます。

- **iosbase の**場合 . [flags](../standard-library/ios-base-class.md#flags) & フラグ == `lo`oct 、変換仕様は です。[oct](../standard-library/ios-functions.md#oct)`ios_base::basefield``ios_base::`

- **iosbase.flags** & **が ios_base::basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex)の`lx`場合、変換仕様は です。

- それ以外の場合、変換仕様は `ld` です。

**iosbase の**場合 . [width](../standard-library/ios-base-class.md#width)が 0 以外の場合、この値のフィールド幅が先頭に付加されます。 この関数は **、次に iosbase**を呼び出します。 **幅**(0) を指定すると、フィールドの幅がゼロにリセットされます。

パディングは、出力フィールドを指定するために必要な最小要素*N*が**iosbase**より少ない場合にのみ発生します。 [幅](../standard-library/ios-base-class.md#width)。 このようなパディングは、**塗りつぶし**の*N* - **幅**コピーのシーケンスで構成されます。 この場合、埋め込みは次のように発生します。

- **iosbase の**場合 . **flags** & フラグ`ios_base::adjustfield`**-** は左に表示され、フラグは先頭に付加されます。[left](../standard-library/ios-functions.md#left) == `ios_base::` (埋め込みは、生成されたテキストの後に発生します。)

- **iosbase.flags** & **ios_base::調整フィールド** == `ios_base::`[内部](../standard-library/ios-functions.md#internal)の場合、フラグ**0**が付加されます。 (数値出力フィールド場合、埋め込みは、出力関数が 0 で埋め込む状況でのみ発生します。)

- それ以外の場合、追加のフラグは先頭に付加されません。 (埋め込みは、生成されたシーケンスの前に発生します。)

最後に、次の操作を行います。

- **iosbase の**場合 . **flags** & フラグ`ios_base::`[showpos](../standard-library/ios-functions.md#showpos)は 0**+** 以外の値で、フラグは変換仕様の先頭に付加されます。

- **iosbase の**場合 . **フラグ** & **ios_base: :**[showbase](../standard-library/ios-functions.md#showbase)が**#** 0 以外の場合、フラグは変換仕様の先頭に付加されます。

整数出力フィールドの形式は[、numpunct](../standard-library/numpunct-class.md) \< **Elem**>( **iosbase**) [use_facet](../standard-library/locale-functions.md#use_facet) < 呼び出しによって返される[ロケールファセット](../standard-library/locale-class.md#facet_class)**fac**によってさらに決定されます。 [ゲロック](../standard-library/ios-base-class.md#getloc)ス)。 具体的な内容は次のとおりです。

- **ファク**. [グループ化](../standard-library/numpunct-class.md#grouping)は、小数点の左側に桁をグループ化する方法を決定します

- **ファク**. [thousands_sep](../standard-library/numpunct-class.md#thousands_sep)は、小数点の左側にある数字のグループを区切る順序を決定します。

グループ化制約が**fac**によって課されていない場合。 **グループ化**(その最初の要素にはCHAR_MAX値が含まれます) は **、次に fac**のインスタンスはありません。 `thousands_sep`は出力フィールドに生成されます。 それ以外の場合、出力変換が発生した後に区切り記号が挿入されます。

2 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    unsigned long val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `lu` に置き換えている点が異なります。

3 番目のプロテクト仮想メンバー関数：

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    double val) const;
```

この関数の動作は 1 番目と同じですが、**val** の値から浮動小数点出力フィールドを生成している点が異なります。 **ファク**. [decimal_point](../standard-library/numpunct-class.md#decimal_point)は、整数の桁と小数の桁を区切る順序を決定します。 同等の出力変換仕様は次のように決定されます。

- **iosbase の**場合 . **flags** & フラグ`ios_base::floatfield``lf`が固定され、変換仕様は です。[fixed](../standard-library/ios-functions.md#fixed) == `ios_base::`

- **iosbase の**場合 . **フラグ** & **ios_base::浮動小数点フィールド** == `ios_base::`[科学](../standard-library/ios-functions.md#scientific)、変換仕様は`le`です。 **iosbase の**場合 . **flags** & flags`ios_base::`[大文字](../standard-library/ios-functions.md#uppercase)が 0`e`以外の場合`E`は、 に置き換えられます。

- それ以外の場合、変換仕様は **lg** です。 **iosbase の**場合 . **フラグ** & **ios_base::大文字**が 0`g`以外の場合`G`は、 に置き換えられます。

**iosbase の**場合 . **フラグ** & **ios_base::fixed**は 0 以外の場合、または**iosbase**の場合です。 [精度](../standard-library/ios-base-class.md#precision)はゼロより大きく、値**iosbase**の精度です。 **精度**は変換仕様の先頭に付加されます。 埋め込みの動作は整数出力フィールドの場合と同様です。 埋め込み文字は **fill** です。 最後に、次の操作を行います。

- **iosbase の**場合 . **flags** & フラグ`ios_base::`[showpos](../standard-library/ios-functions.md#showpos)は 0**+** 以外の値で、フラグは変換仕様の先頭に付加されます。

- **iosbase の**場合 . **flags** & **#** フラグ`ios_base::`[の showpoint](../standard-library/ios-functions.md#showpoint)が 0 以外の場合、フラグは変換仕様の先頭に付加されます。

4 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

変換仕様の修飾子`l`が . `L`

5 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    const void* val) const;
```

この関数の動作は 1 番目と同じですが、変換仕様が `p` と **、** 埋め込みを指定するために必要なすべての修飾子である点が異なります。

6 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,
    CharType _Fill,
    bool val) const;
```

*val*からブール型の出力フィールドを生成する点を除いて、最初のフィールドと同じように動作します。

ブール値出力フィールドは、次の 2 つの形式のいずれかになります。 `iosbase.flags & ios_base::` [boolalpha](../standard-library/ios-functions.md#boolalpha)が**false**の場合、`do_put(_Next, _Iosbase, _Fill, (long)val)`メンバー関数は返され、通常は 0 **(false**の場合) または 1 **(true**の場合) の生成シーケンスが生成されます。 それ以外の場合、生成されるシーケンスは*fac*のいずれかになります。[偽名](../standard-library/numpunct-class.md#falsename)(**偽**の場合) または*fac*。[truename](../standard-library/numpunct-class.md#truename) **(true**の場合)。

7 番目のプロテクト仮想メンバー関数:

```cpp
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,
    Elem fill,
    long long val) const;
```

この関数の動作は 1 番目と同じですが、`ld` の変換仕様を `lld` に置き換えている点が異なります。

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

## <a name="num_putiter_type"></a><a name="iter_type"></a>num_put::iter_type

出力反復子を表す型。

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター **OutputIterator** のシノニムです。

## <a name="num_putnum_put"></a><a name="num_put"></a>num_put::num_put

`num_put` 型のオブジェクトのコンストラクター。

```cpp
explicit num_put(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

*_Refs*\
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>解説

*_Refs*パラメータとその有意性の値は次のとおりです。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- \>1: これらの値は定義されていません。

デストラクターが保護されているため、利用できる直接的な例はありません。

コンストラクターは、基本オブジェクトを**locale:**[ファセット](../standard-library/locale-class.md#facet_class)(_ *Refs)* で初期化します。

## <a name="num_putput"></a><a name="put"></a>num_put::p

数値を、指定したロケールに`CharType`対して書式設定された数値を表す s のシーケンスに変換します。

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

*Dest*\
挿入された文字列の先頭の要素を示す反復子。

*_Iosbase*\
出力に句読点を付けるために使用される numpunct ファセットを持つロケールおよび出力を書式設定するためのフラグを含むストリームを指定します。

*_Fill*\
スペースに使用される文字。

*ヴァル*\
出力する数値またはブール型。

### <a name="return-value"></a>戻り値

生成される最後の要素を 1 つ超える位置を示す出力反復子。

### <a name="remarks"></a>解説

すべてのメンバー関数[は、do_put](#do_put) `next` `_Iosbase`( `_Fill` `val`, , , ) を返します。

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

[\<ロケール>](../standard-library/locale.md)\
[ファセットクラス](../standard-library/locale-class.md#facet_class)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
