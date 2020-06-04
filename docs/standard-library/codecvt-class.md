---
title: codecvt クラス
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: 3dba971b112c23325e0529e53746cbee827df5e9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371953"
---
# <a name="codecvt-class"></a>codecvt クラス

ロケール ファセットとして使用できるオブジェクトを記述するクラス テンプレート。 プログラム内で文字をエンコードするために使用される値のシーケンスと、プログラム外で文字をエンコードするために使用される値のシーケンスとの変換を制御できます。

## <a name="syntax"></a>構文

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>パラメーター

*Chartype*\
文字をエンコードするためにプログラム内で使用される型。

*バイト*\
文字をエンコードするためにプログラム外で使用される型。

*ステートタイプ*\
文字表現の内部型と外部型との変換の中間状態を表すために使用できる型。

## <a name="remarks"></a>解説

クラス テンプレートは *、CharType*型の値のシーケンスと型の値のシーケンスの間の変換を制御する[ロケール ファセット](../standard-library/locale-class.md#facet_class)として機能できるオブジェクトを*記述します*。 クラス*StateType*は変換を特徴付け、クラス*StateType*のオブジェクトは変換中に必要な状態情報を格納します。

内部エンコーディングでは**wchar_t、** 文字ごとの固定バイト数を持つ表現を使用します**char**。

すべてのロケールのファセットと同様、静的オブジェクト `id` に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、`id` に一意の正の値が格納されます。

[do_in](#do_in) と [do_out](#do_out) のテンプレート バージョンでは、常に `codecvt_base::noconv` が返されます。

C++ 標準ライブラリは複数の明示的な特殊化を定義します。

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

**wchar_t**と**char**シーケンスの間の変換を行います。

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

は、UTF-16 としてエンコードされたシーケンスと、UTF-8 としてエンコードされた`char16_t`**char**シーケンス間の変換を行います。

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

は、UTF-32 (UCS-4) としてエンコードされたシーケンスと、UTF-8 としてエンコードされた`char32_t`**char**シーケンスの間で変換されます。

### <a name="constructors"></a>コンストラクター

|Constructor|説明|
|-|-|
|[Codecvt](#codecvt)|変換を処理するためにロケールのファセットとして機能する `codecvt` クラスのオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|種類の名前。|説明|
|-|-|
|[extern_type](#extern_type)|外部表現に使用される文字型。|
|[intern_type](#intern_type)|内部表現に使用される文字型。|
|[state_type](#state_type)|内部表現と外部表現との変換時の中間状態を表すために使用される文字型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[always_noconv](#always_noconv)|変換を実行する必要がないかどうかをテストします。|
|[do_always_noconv](#do_always_noconv)|変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。|
|[do_encoding](#do_encoding)|`Byte`ストリームのエンコーディングが状態依存であるかどうか、使用される`Byte`値と生成される`CharType`値の比率が一定であるかどうかをテストする仮想関数。|
|[do_in](#do_in)|内部`Byte`値のシーケンスを外部`CharType`値のシーケンスに変換するために呼び出される仮想関数。|
|[do_length](#do_length)|特定`Byte`の外部`Byte`値のシーケンスから何個の値が生成されるかを決定する仮想関数は、特定の数の`CharType`内部値を生成し、`Byte`その数の値を返します。|
|[do_max_length](#do_max_length)|1 つの内部 `CharType` を生成するために必要な最大外部 Byte 数を返す仮想関数。|
|[do_out](#do_out)|内部`CharType`値のシーケンスを外部バイトのシーケンスに変換するために呼び出される仮想関数。|
|[do_unshift](#do_unshift)|一連の値の最後の`Byte`文字を完了するために状態依存変換で必要な`Byte`値を提供するために呼び出される仮想関数。|
|[エンコーディング](#encoding)|`Byte`ストリームのエンコーディングが状態依存であるかどうか、使用される`Byte`値と生成される`CharType`値の比率が一定であるかどうかをテストし、その値が一定である場合は、その比率の値を決定します。|
|[in](#in)|値のシーケンスの外部表現を、値`Byte`のシーケンスの内部表現に変換`CharType`します。|
|[length](#length)|特定の外部`Byte``Byte`値のシーケンスから、特定の数の内部`CharType`値を生成する値の数を決定し、その値`Byte`の数を返します。|
|[max_length](#max_length)|1 つの内部`Byte``CharType`を生成するために必要な外部値の最大数を返します。|
|[乙](#out)|内部`CharType`値のシーケンスを外部`Byte`値のシーケンスに変換します。|
|[unshift](#unshift)|値のシーケンス`Byte`の最後の文字を完了するために、状態依存変換で必要な外部値`Byte`を提供します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="codecvtalways_noconv"></a><a name="always_noconv"></a>always_noconv

変換を行う必要がないかどうかをテストします。

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>戻り値

変換を行う必要がない場合は**true**のブール値。少なくとも 1 つを実行する必要がある場合は**false。**

### <a name="remarks"></a>解説

このメンバー関数は、[do_always_noconv](#do_always_noconv) を返します。

### <a name="example"></a>例

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvtcodecvt"></a><a name="codecvt"></a>コードクスト::コードクスト

変換を処理するためにロケール ファセットとして機能する codecvt クラスのオブジェクトのコンストラクター。

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>パラメーター

*Refs*\
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>解説

*refs*パラメーターとその有意性の値は次のとおりです。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。

- 2: これらの値は定義されていません。

コンストラクターは、基本オブジェクト`locale::facet`を[locale::facet](../standard-library/locale-class.md#facet_class)`(refs)`で初期化します。

## <a name="codecvtdo_always_noconv"></a><a name="do_always_noconv"></a>:do_always_noconv

変換を行う必要がないかどうかをテストするために呼び出される仮想関数。

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>戻り値

プロテクト仮想メンバー関数は[、do_in](#do_in)または[do_out](#do_out)へのすべての呼び出し`noconv`が戻された場合にのみ**true**を返します。

テンプレート バージョンでは常に **true** が返されます。

### <a name="example"></a>例

[always_noconv](#always_noconv) の例 (`do_always_noconv` を呼び出す) を参照してください。

## <a name="codecvtdo_encoding"></a><a name="do_encoding"></a>コードクスト::do_エンコーディング

`Byte`ストリームのエンコーディングが状態依存であるかどうかをテストする仮想関数で、使用された`Byte`値と生成される`CharType`値の比率が一定であるかどうか、また、その値が一定である場合は、その比率の値が決定されます。

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>戻り値

protected 仮想メンバー関数は次の値を返します。

- -1 (型`extern_type`のシーケンスのエンコーディングが状態依存の場合)。

- エンコードがさまざまな長さのシーケンスに関係する場合は、0。

- *N*(エンコーディングに長さ*N*のシーケンスのみが含まれる場合)

### <a name="example"></a>例

[encoding](#encoding) の例 (`do_encoding` を呼び出す) を参照してください。

## <a name="codecvtdo_in"></a><a name="do_in"></a>:d

外部`Byte`値のシーケンスを内部`CharType`値のシーケンスに変換するために呼び出される仮想関数。

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>パラメーター

*状態*\
メンバー関数の呼び出し間で維持される変換の状態。

*最初の1*\
変換されるシーケンスの先頭へのポインター。

*ラスト1*\
変換されるシーケンスの末尾へのポインター。

*次1*\
変換されたシーケンスの末尾の後の、最初の非変換文字へのポインター。

*最初の2*\
変換されたシーケンスの先頭へのポインター。

*ラスト2*\
変換されたシーケンスの末尾へのポインター。

*次2*\
最後に変換`CharType``CharType`された後の、変換先シーケンスの最初の変更されていない文字へのポインター。

### <a name="return-value"></a>戻り値

操作の成功、一部成功、または失敗を示す戻り値。 この関数では次の値が返されます。

- `codecvt_base::error`ソースシーケンスが正しくない形式の場合。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合。

- `codecvt_base::partial`ソースが不十分な場合、または変換先が十分でない場合は、変換が成功します。

### <a name="remarks"></a>解説

*state*は、新しいソース シーケンスの先頭の初期変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 それ以外の場合、格納されている値は指定されません。

### <a name="example"></a>例

[in](#in) の例 (`do_in` を呼び出す) を参照してください。

## <a name="codecvtdo_length"></a><a name="do_length"></a>コードクスト::do_長さ

特定`Byte`の外部`Byte`値のシーケンスから何個の値が生成されるかを決定する仮想関数は、特定の数の`CharType`内部値を生成し、`Byte`その数の値を返します。

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>パラメーター

*状態*\
メンバー関数の呼び出し間で維持される変換の状態。

*最初の1*\
外部シーケンスの先頭へのポインター。

*ラスト1*\
外部シーケンスの末尾へのポインター。

*len2*\
メンバー関数から返`Byte`される値の最大数。

### <a name="return-value"></a>戻り値

[ `first1`] の外部ソース シーケンスで定義された`last1`*len2*より大きくない変換の最大数のカウントを表す整数。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、`do_in( state, first1, last1, next1, buf, buf + len2, next2)`状態 (*状態*のコピー)、バッファ、`buf`およびポインタとを`next1`効果的`next2`に呼び出します。

その後 `next2` - `buf` を返します。 したがって、 [ `first1`, ] のソース シーケンスで定義された*len2*より大きくならない`last1`変換の最大数をカウントします。

テンプレートバージョンは常に*last1* - *first1*と*len2*の小さい方を返します。

### <a name="example"></a>例

[長](#length)さの例を参照してください`do_length`。

## <a name="codecvtdo_max_length"></a><a name="do_max_length"></a>:d数の長さ

内部`CharType`1 つのを生成するために必要な`Byte`外部値の最大数を返す仮想関数。

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>戻り値

1 つを`CharType`生成`Byte`するために必要な値の最大数。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は *、first1*と*last1*の任意の有効な値に対して[do_length](#do_length)`( first1, last1, 1)`で返すことができる最大許容値を返します。

### <a name="example"></a>例

[max_length](#max_length) の例 (`do_max_length` を呼び出す) を参照してください。

## <a name="codecvtdo_out"></a><a name="do_out"></a>:d

内部`CharType`値のシーケンスを外部`Byte`値のシーケンスに変換するために呼び出される仮想関数。

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*状態*\
メンバー関数の呼び出し間で維持される変換の状態。

*最初の1*\
変換されるシーケンスの先頭へのポインター。

*ラスト1*\
変換されるシーケンスの末尾へのポインター。

*次1*\
最後`CharType`に変換された後の最初の変換`CharType`されていないへのポインターへの参照。

*最初の2*\
変換されたシーケンスの先頭へのポインター。

*ラスト2*\
変換されたシーケンスの末尾へのポインター。

*次2*\
最後`Byte`に変換された後の最初の変換`Byte`されていないへのポインターへの参照。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error`ソースシーケンスが正しくない形式の場合。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合。

- `codecvt_base::partial`変換元が不十分な場合、または変換先が変換に十分でない場合。

### <a name="remarks"></a>解説

*state*は、新しいソース シーケンスの先頭の初期変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 それ以外の場合、格納されている値は指定されません。

### <a name="example"></a>例

[out](#out) の例 (`do_out` を呼び出す) を参照してください。

## <a name="codecvtdo_unshift"></a><a name="do_unshift"></a>:do_アンシフト

一連の値の最後の`Byte`文字を完了するために状態依存変換で必要な`Byte`値を提供するために呼び出される仮想関数。

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*状態*\
メンバー関数の呼び出し間で維持される変換の状態。

*最初の2*\
対象範囲内の最初の位置へのポインター。

*ラスト2*\
対象範囲内の最後の位置へのポインター。

*次2*\
対象シーケンス内の変更されていない最初の要素へのポインター。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error`*状態*が無効な状態を表す場合

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合

- `codecvt_base::partial`変換先が十分な大きさでない場合、変換が成功する

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、`CharType`終了要素`first2``last2``Byte`(0) を除いて、 ソース要素 (0) を 、 [ , ) 内に格納する変換先シーケンスに変換しようとします。 常に*next2*に、変換先シーケンスの最初の変更されていない要素へのポインターを格納します。

_ *State* は、新しいソース シーケンスの先頭で最初の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素`CharType`(0) を変換すると、現在の状態は初期変換状態のままとなります。

### <a name="example"></a>例

[unshift](#unshift) の例 (`do_unshift` を呼び出す) を参照してください。

## <a name="codecvtencoding"></a><a name="encoding"></a>コードクスト::エンコーディング

`Byte`ストリームのエンコーディングが状態依存であるかどうか、使用される`Byte`値と生成される`CharType`値の比率が一定であるかどうかをテストし、その値が一定である場合は、その比率の値を決定します。

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>戻り値

戻り値が正の場合、その値は文字を生成`Byte`するために必要な一定`CharType`の文字数です。

protected 仮想メンバー関数は次の値を返します。

- -1 (型`extern_type`のシーケンスのエンコーディングが状態依存の場合)。

- エンコードがさまざまな長さのシーケンスに関係する場合は、0。

- エンコードが長さ *N* のシーケンスのみに関係する場合は、*N*。

### <a name="remarks"></a>解説

このメンバー関数は、[do_encoding](#do_encoding) を返します。

### <a name="example"></a>例

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
}
```

```Output
1
1
1
```

## <a name="codecvtextern_type"></a><a name="extern_type"></a>コードクスト::extern_type

外部表現に使用される文字型。

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `Byte` のシノニムです。

## <a name="codecvtin"></a><a name="in"></a>コードクスト::イン

値のシーケンスの外部表現を、値`Byte`のシーケンスの内部表現に変換`CharType`します。

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>パラメーター

*状態*\
メンバー関数の呼び出し間で維持される変換の状態。

*最初の1*\
変換されるシーケンスの先頭へのポインター。

*ラスト1*\
変換されるシーケンスの末尾へのポインター。

*次1*\
変換されたシーケンスの末尾の後の、最初の未変換文字へのポインター。

*最初の2*\
変換されたシーケンスの先頭へのポインター。

*ラスト2*\
変換されたシーケンスの末尾へのポインター。

*次2*\
最後に`CharType`変換先シーケンスの最初の変更`Chartype`されていない文字に変換された後に来るポインター。

### <a name="return-value"></a>戻り値

操作の成功、一部成功、または失敗を示す戻り値。 この関数では次の値が返されます。

- `codecvt_base::error`ソースシーケンスが正しくない形式の場合。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合。

- `codecvt_base::partial`変換元が不十分な場合、または変換先が変換に十分でない場合。

### <a name="remarks"></a>解説

*state*は、新しいソース シーケンスの先頭の初期変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 部分的な変換の後、新しい文字が到着したときに変換を再開できるように*状態*を設定する必要があります。

メンバー関数は[do_in](#do_in)`( state, first1,  last1,  next1, first2, last2,  next2)`を返します。

### <a name="example"></a>例

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="codecvtintern_type"></a><a name="intern_type"></a>コードクスト::intern_type

内部表現に使用される文字型。

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `CharType` のシノニムです。

## <a name="codecvtlength"></a><a name="length"></a>コードクスト::長さ

特定の外部`Byte``Byte`値のシーケンスから、特定の数の内部`CharType`値を生成する値の数を決定し、その値`Byte`の数を返します。

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>パラメーター

*状態*\
メンバー関数の呼び出し間で維持される変換の状態。

*最初の1*\
外部シーケンスの先頭へのポインター。

*ラスト1*\
外部シーケンスの末尾へのポインター。

*len2*\
メンバー関数で返すことができる Byte の最大数。

### <a name="return-value"></a>戻り値

[ `first1`] の外部ソース シーケンスで定義された`last1`*len2*より大きくない変換の最大数のカウントを表す整数。

### <a name="remarks"></a>解説

メンバー関数は[do_length](#do_length)`( state, first1, last1, len2)`を返します。

### <a name="example"></a>例

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << endl;
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="codecvtmax_length"></a><a name="max_length"></a>コードクスト::max_length

1 つの内部`Byte``CharType`を生成するために必要な外部値の最大数を返します。

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>戻り値

1 つを`CharType`生成`Byte`するために必要な値の最大数。

### <a name="remarks"></a>解説

このメンバー関数は、[do_max_length](#do_max_length) を返します。

### <a name="example"></a>例

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t> >
     ( loc ).max_length( );
   wcout << res << endl;
}
```

```Output
1
```

## <a name="codecvtout"></a><a name="out"></a>コードクスト::アウト

内部`CharType`値のシーケンスを外部`Byte`値のシーケンスに変換します。

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*状態*\
メンバー関数の呼び出し間で維持される変換の状態。

*最初の1*\
変換されるシーケンスの先頭へのポインター。

*ラスト1*\
変換されるシーケンスの末尾へのポインター。

*次1*\
最後`CharType`に変換された後の最初の変換`CharType`されなかったポインターへの参照。

*最初の2*\
変換されたシーケンスの先頭へのポインター。

*ラスト2*\
変換されたシーケンスの末尾へのポインター。

*次2*\
最後に変換`Byte`された後の最初の変換`Byte`されていないへのポインターへの参照。

### <a name="return-value"></a>戻り値

メンバー関数は[do_out](#do_out)`( state, first1, last1, next1, first2, last2, next2)`を返します。

### <a name="remarks"></a>解説

詳細については、「[codecvt::do_out](#do_out)」を参照してください。

### <a name="example"></a>例

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
   char pszExt[LEN+1];
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );
   char* pszNext;
   const wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).out( state,
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );
   pszExt[wcslen( pwszInt )] = 0;
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )
   << "The converted string is:\n ["
   << &pszExt[0]
   << "]" << endl;
}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="codecvtstate_type"></a><a name="state_type"></a>コードクスト::state_type

内部表現と外部表現との変換時の中間状態を表すために使用される文字型。

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `StateType` のシノニムです。

## <a name="codecvtunshift"></a><a name="unshift"></a>コードクスト::シフト解除

一連`Byte`の値の最後の文字を完了するために状態依存変換で必要な`Byte`値を提供します。

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*状態*\
メンバー関数の呼び出し間で維持される変換の状態。

*最初の2*\
対象範囲内の最初の位置へのポインター。

*ラスト2*\
対象範囲内の最後の位置へのポインター。

*次2*\
対象シーケンス内の変更されていない最初の要素へのポインター。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error`状態が無効な状態を表す場合。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合。

- `codecvt_base::partial`変換先が十分な大きさでない場合は、変換が成功します。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、`CharType`終了要素`first2``last2``Byte`(0) を除いて、 ソース要素 (0) を 、 [ , ) 内に格納する変換先シーケンスに変換しようとします。 常に*next2*に、変換先シーケンスの最初の変更されていない要素へのポインターを格納します。

*state*は、新しいソース シーケンスの先頭の初期変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素`CharType`(0) を変換すると、現在の状態は初期変換状態のままとなります。

メンバー関数は[、 do_unshift](#do_unshift)`( state, first2, last2, next2 )`を返します。

## <a name="see-also"></a>関連項目

[\<ロケール>](../standard-library/locale.md)\
[コード ページ](../c-runtime-library/code-pages.md)\
[ロケール名、言語、国/地域の文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
