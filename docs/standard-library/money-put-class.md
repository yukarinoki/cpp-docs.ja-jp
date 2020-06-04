---
title: money_put クラス
ms.date: 11/01/2018
f1_keywords:
- xlocmon/std::money_put
- xlocmon/std::money_put::char_type
- xlocmon/std::money_put::iter_type
- xlocmon/std::money_put::string_type
- xlocmon/std::money_put::do_put
- xlocmon/std::money_put::put
helpviewer_keywords:
- std::money_put [C++]
- std::money_put [C++], char_type
- std::money_put [C++], iter_type
- std::money_put [C++], string_type
- std::money_put [C++], do_put
- std::money_put [C++], put
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
ms.openlocfilehash: 035cc4e7b9cfac262979509bf7b4570e2c55336c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377422"
---
# <a name="money_put-class"></a>money_put クラス

クラス テンプレートは、通貨値から型のシーケンスへの変換を制御するロケール ファセットとして機能するオブジェクトを表`CharType`します。

## <a name="syntax"></a>構文

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class money_put : public locale::facet;
```

### <a name="parameters"></a>パラメーター

*Chartype*\
ロケールの文字をエンコードするためにプログラム内で使用される型。

*出力反復器*\
通貨の put 関数が出力を書き込む反復子の型。

## <a name="remarks"></a>解説

すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[money_put](#money_put)|`money_put` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[char_type](#char_type)|ロケールによって使用される文字を表すために使用される型。|
|[iter_type](#iter_type)|出力反復子を表す型。|
|[string_type](#string_type)|`CharType` 型の文字を格納する文字列を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[do_put](#do_put)|通貨値を表す文字シーケンスから数値または文字列を抽出するために呼び出される仮想関数。|
|[置く](#put)|数値または文字列を通貨値を表す文字シーケンスに変換します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="money_putchar_type"></a><a name="char_type"></a>money_put::char_type

ロケールによって使用される文字を表すために使用される型。

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター **CharType** のシノニムです。

## <a name="money_putdo_put"></a><a name="do_put"></a>money_put::do_put

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

*次に*\
挿入された文字列の先頭の要素を示す反復子。

*_Intl*\
シーケンスで期待される通貨記号の種類を示すブール値。国際通貨の場合は **true**、国内通貨の場合は **false**。

*_Iosbase*\
書式設定フラグ。これが設定されている場合、通貨記号は省略可能です。それ以外の場合は必須です

*_Fill*\
スペースに使用される文字。

*ヴァル*\
変換される文字列オブジェクト。

### <a name="return-value"></a>戻り値

生成される最後の要素を 1 つ超える位置を示す出力反復子。

### <a name="remarks"></a>解説

最初の仮想プロテクト メンバー関数は、*次*から始まる順次要素を生成し[、string_type](#string_type)オブジェクト*val*から通貨出力フィールドを生成します。 *val*によって制御されるシーケンスは、1 つ以上の 10 進数で始まらなければなりません。 関数は、生成された通貨出力フィールドを超える先頭の要素を指す反復子を返します。

2 番目の仮想プロテクト メンバー関数は最初の関数と同じ動作をしますが、最初に*val*を 10 進数のシーケンスに変換する場合は、オプションで負符号が付き、そのシーケンスを上記の順序に変換します。

通貨出力フィールドの形式は[、moneypunct](../standard-library/moneypunct-class.md) \< **Char> >Type** [use_facet](../standard-library/locale-functions.md#use_facet) < の (有効な) 呼び出しによって返**intl**される[ロケール ファセット](../standard-library/locale-class.md#facet_class)fac によって決定**されます。** [ゲロック](../standard-library/ios-base-class.md#getloc)ス)。

具体的な内容は次のとおりです。

- **ファク**. [pos_format、](../standard-library/moneypunct-class.md#pos_format)フィールドのコンポーネントが負でない値に対して生成される順序を決定します。

- **ファク**. [neg_format](../standard-library/moneypunct-class.md#neg_format)は、負の値に対してフィールドのコンポーネントが生成される順序を決定します。

- **ファク**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol)通貨記号に対して生成する要素の順序を決定します。

- **ファク**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign)は、正の符号に対して生成する要素のシーケンスを決定します。

- **ファク**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign)は、負の符号に対して生成する要素のシーケンスを決定します。

- **ファク**. [グループ化](../standard-library/moneypunct-class.md#grouping)によって、小数点の左側に桁をグループ化する方法が決まります。

- **ファク**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep)小数点の左側にある数字のグループを区切る要素を決定します。

- **ファク**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point)は、整数の桁と任意の小数の桁を区切る要素を決定します。

- **ファク**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits)小数点の右側の有効小数部桁数を決定します。

符号文字列 ( **fac**. `negative_sign`または**fac**. `positive_sign`) には複数の要素があり、最初の要素だけが生成され **、money_base::sign**に等しい要素が書式パターン ( **fac**) に表示されます。 `neg_format`または**fac**. `pos_format`). 残りの要素は、通貨出力フィールドの末尾に生成されます。

**iosbase の**場合 . [フラグ](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase)は 0 以外の文字列**です**。 `curr_symbol`は **、money_base::symbol**に等しい要素がフォーマットパターンに現れる場所で生成されます。 それ以外の場合、通貨記号は生成されません。

グループ化制約が**fac**によって課されていない場合。 **グループ化**(その最初の要素にはCHAR_MAX値が含まれます) は **、次に fac**のインスタンスはありません。 `thousands_sep`は、通貨出力フィールドの値部分に生成されます (要素は**money_base::value**に等しい形式パターンで表示されます)。 **fac**の場合. `frac_digits`はゼロで、その後**fac**のインスタンスはありません。 `decimal_point`は、10 進数の後に生成されます。 それ以外の場合、結果の通貨出力フィールドは下位**の fac**を配置します。 `frac_digits`小数点の右側の 10 進数。

パディングは **、iosbase**の場合を除いて、任意の数値出力フィールドに対して発生します。 **フラグ** & **iosbase**. [internal](../standard-library/ios-functions.md#internal)が 0 以外の場合、要素が**money_base::space**に等しい場合は、その要素がフォーマット パターンに表示される場合は、内部の埋め込みが生成されます。 それ以外の場合、内部の埋め込みは生成されたシーケンスの前に発生します。 埋め込み文字は **fill** です。

この関数は**iosbase**を呼び出します。 **幅**(0) を指定すると、フィールドの幅がゼロにリセットされます。

### <a name="example"></a>例

[put](#put) の例 (仮想メンバー関数が **put** で呼び出される) を参照してください。

## <a name="money_putiter_type"></a><a name="iter_type"></a>money_put::iter_type

出力反復子を表す型。

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター **OutputIterator** のシノニムです。

## <a name="money_putmoney_put"></a><a name="money_put"></a>money_put::money_put

`money_put` 型のオブジェクトのコンストラクター。

```cpp
explicit money_put(size_t _Refs = 0);
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

コンストラクターは、**locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`) を使用してその基本オブジェクトを初期化します。

## <a name="money_putput"></a><a name="put"></a>money_put::p

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

*次に*\
挿入された文字列の先頭の要素を示す反復子。

*_Intl*\
シーケンスで期待される通貨記号の種類を示すブール値。国際通貨の場合は **true**、国内通貨の場合は **false**。

*_Iosbase*\
書式設定フラグ。これが設定されている場合、通貨記号は省略可能です。それ以外の場合は必須です

*_Fill*\
スペースに使用される文字。

*ヴァル*\
変換される文字列オブジェクト。

### <a name="return-value"></a>戻り値

生成される最後の要素を 1 つ超える位置を示す出力反復子。

### <a name="remarks"></a>解説

両方のメンバ関数[は、do_put](#do_put) `_Iosbase`、 `_Fill` `val` `next`、 `_Intl`、 、 を返します。

### <a name="example"></a>例

```cpp
// money_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

int main()
{
    std::locale loc( "german_germany" );
    std::basic_stringstream<char> psz;

    psz.imbue(loc);
    psz.flags(psz.flags() | std::ios_base::showbase); // force the printing of the currency symbol
    std::use_facet<std::money_put<char> >(loc).put(std::basic_ostream<char>::_Iter(psz.rdbuf()), true, psz, ' ', 100012);
    if (psz.fail())
        std::cout << "money_put() FAILED" << std::endl;
    else
        std::cout << "money_put() = \"" << psz.rdbuf()->str() << "\"" << std::endl;
}
```

```Output
money_put() = "EUR1.000,12"
```

## <a name="money_putstring_type"></a><a name="string_type"></a>money_put::string_type

`CharType` 型の文字を格納する文字列を表す型。

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>解説

この型は、ソース シーケンスの要素のシーケンスを格納できるオブジェクトを持つクラス テンプレート[basic_string](../standard-library/basic-string-class.md)の特殊化を表します。

## <a name="see-also"></a>関連項目

[\<ロケール>](../standard-library/locale.md)\
[ファセットクラス](../standard-library/locale-class.md#facet_class)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
