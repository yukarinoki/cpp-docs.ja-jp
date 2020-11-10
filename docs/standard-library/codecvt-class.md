---
title: '`codecvt` クラス'
description: Microsoft C ランタイムクラス API について説明します。 `codecvt`
ms.date: 11/09/2020
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
ms.openlocfilehash: 8d2970297cca199c70c101dca93f453c512317c4
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441282"
---
# <a name="codecvt-class"></a>`codecvt` クラス

ロケールファセットとして使用できるオブジェクトを表すクラステンプレート。 プログラム内で文字をエンコードするために使用される値のシーケンスと、プログラム外で文字をエンコードするために使用される値のシーケンスとの間の変換を制御できます。

## <a name="syntax"></a>構文

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>パラメーター

*`CharType`*\
文字をエンコードするためにプログラム内で使用される型。

*`Byte`*\
文字をエンコードするためにプログラム外で使用される型。

*`StateType`*\
文字表現の内部型と外部型との変換の中間状態を表すために使用できる型。

## <a name="remarks"></a>解説

クラステンプレートは、型の値のシーケンスと型の値のシーケンスとの間の変換を制御するために、 [ロケールファセット](../standard-library/locale-class.md#facet_class)として使用できるオブジェクトを表し *`CharType`* *`Byte`* ます。 クラスは *`StateType`* 変換を特徴とし、クラスのオブジェクトは *`StateType`* 変換中に必要な状態情報を格納します。

内部エンコーディングでは、1文字あたりのバイト数が固定された表現を使用します。通常、型 **`char`** または型のいずれか **`wchar_t`** です。

すべてのロケールのファセットと同様、静的オブジェクト `id` に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、`id` に一意の正の値が格納されます。

およびのテンプレートバージョンは、 [`do_in`](#do_in) [`do_out`](#do_out) 常にを返し `codecvt_base::noconv` ます。

C++ 標準ライブラリは複数の明示的な特殊化を定義します。

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

とシーケンス間の変換 **`wchar_t`** を **`char`** 行います。

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

UTF-16 としてエンコードされたシーケンスと UTF-8 としてエンコードされたシーケンスとの間で変換 **`char16_t`** を **`char`** 行います。

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

32 UTF-8 としてエンコードされたシーケンスと UTF-8 としてエンコードされたシーケンス **`char32_t`** を変換し **`char`** ます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[`codecvt`](#codecvt)|変換を処理するためにロケールのファセットとして機能する `codecvt` クラスのオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[`extern_type`](#extern_type)|外部表現に使用される文字型。|
|[`intern_type`](#intern_type)|内部表現に使用される文字型。|
|[`state_type`](#state_type)|内部表現と外部表現との変換時の中間状態を表すために使用される文字型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[`always_noconv`](#always_noconv)|変換を実行する必要がないかどうかをテストします。|
|[`do_always_noconv`](#do_always_noconv)|変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。|
|[`do_encoding`](#do_encoding)|ストリームのエンコーディング `Byte` が状態に依存するかどうか、 `Byte` 使用される値と生成される値の比率が一定であるかどうかをテストし、その `CharType` 場合はその比率の値を決定する仮想関数。|
|[`do_in`](#do_in)|内部値のシーケンスを `Byte` 外部値のシーケンスに変換するために呼び出される仮想関数 `CharType` 。|
|[`do_length`](#do_length)|特定の外部値のシーケンスから生成される値の数が、指定された数を超える `Byte` `Byte` 内部 `CharType` 値を取得し、その値を返す仮想関数 `Byte` 。|
|[`do_max_length`](#do_max_length)|1 つの内部 `CharType` を生成するために必要な最大外部 Byte 数を返す仮想関数。|
|[`do_out`](#do_out)|内部値のシーケンスを `CharType` 外部バイトのシーケンスに変換するために呼び出される仮想関数。|
|[`do_unshift`](#do_unshift)|`Byte`状態に依存する変換で、値のシーケンスの最後の文字を完了するために必要な値を提供するために呼び出される仮想関数 `Byte` 。|
|[`encoding`](#encoding)|ストリームのエンコード `Byte` が状態に依存するかどうか、 `Byte` 使用される値と生成される値の比率が一定であるかどうかをテスト `CharType` します。その場合は、その比率の値を決定します。|
|[`in`](#in)|値のシーケンスの外部表現を、 `Byte` 値のシーケンスの内部表現に変換し `CharType` ます。|
|[`length`](#length)|指定された `Byte` 一連の外部値から生成される内部値の数を超えない値の数を判断 `Byte` `CharType` し、その値の数を返し `Byte` ます。|
|[`max_length`](#max_length)|`Byte`1 つの内部を生成するために必要な外部値の最大数を返し `CharType` ます。|
|[`out`](#out)|内部値のシーケンスを `CharType` 外部値のシーケンスに変換 `Byte` します。|
|[`unshift`](#unshift)|`Byte`状態に依存する変換で、値のシーケンスの最後の文字を完了するために必要な外部の値を提供し `Byte` ます。|

## <a name="requirements"></a>必要条件

**ヘッダー:**`<locale>`

**名前空間:** `std`

## <a name="codecvtalways_noconv"></a><a name="always_noconv"></a> `codecvt::always_noconv`

変換を実行する必要がないかどうかをテストします。

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>戻り値

変換を実行する必要がない場合はのブール値。少なくとも **`true`** **`false`** 1 つを実行する必要がある場合は。

### <a name="remarks"></a>解説

このメンバー関数は、を返し [`do_always_noconv`](#do_always_noconv) ます。

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
   bool result1 = use_facet<codecvt<char, char, mbstate_t>>
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << '\n';
   else
      cout << "At least one conversion is required." << '\n';

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t>>
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << '\n';
   else
      cout << "At least one conversion is required." << '\n';
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvtcodecvt"></a><a name="codecvt"></a> `codecvt::codecvt`

変換を処理するためにロケール ファセットとして機能する codecvt クラスのオブジェクトのコンストラクター。

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>パラメーター

*`refs`*\
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>解説

パラメーターの有効な値 *`refs`* とその意味は次のとおりです。

- 0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。

- 1: オブジェクトの有効期間を手動で管理する必要があります。


- 2: これらの値は定義されていません。

コンストラクターは、 `locale::facet` を使用して、その基本オブジェクトを初期化し [`locale::facet`](../standard-library/locale-class.md#facet_class) `(refs)` ます。

## <a name="codecvtdo_always_noconv"></a><a name="do_always_noconv"></a> `codecvt::do_always_noconv`

変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>戻り値

プロテクト仮想メンバー関数は、 **`true`** またはを呼び出すたびにを返し [`do_in`](#do_in) [`do_out`](#do_out) `noconv` ます。

テンプレートバージョンは常にを返し **`true`** ます。

### <a name="example"></a>例

の例 [`always_noconv`](#always_noconv) (を呼び出す) を参照してください `do_always_noconv` 。

## <a name="codecvtdo_encoding"></a><a name="do_encoding"></a> `codecvt::do_encoding`

ストリームのエンコード `Byte` が状態に依存するかどうかをテストする仮想関数 `Byte` 。使用される値と生成される値の比率が一定であるかどうか、およびその `CharType` 比率の値を決定します。

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>戻り値

protected 仮想メンバー関数は次の値を返します。

- 型のシーケンスのエンコードが状態に依存する場合は-1 `extern_type` 。

- エンコードがさまざまな長さのシーケンスに関係する場合は、0。

- *`N`* (エンコーディングが長さのシーケンスのみを含む場合) *`N`*

### <a name="example"></a>例

[encoding](#encoding) の例 (`do_encoding` を呼び出す) を参照してください。

## <a name="codecvtdo_in"></a><a name="do_in"></a> codecvt::d o_in

外部値のシーケンス `Byte` を内部値のシーケンスに変換するために呼び出される仮想関数 `CharType` 。

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

*`state`*\
メンバー関数の呼び出し間で維持される変換の状態。

*`first1`*\
変換されるシーケンスの先頭へのポインター。

*`last1`*\
変換されるシーケンスの末尾へのポインター。

*`next1`*\
変換されたシーケンスの末尾の後の、最初の非変換文字へのポインター。

*`first2`*\
変換されたシーケンスの先頭へのポインター。

*`last2`*\
変換されたシーケンスの末尾へのポインター。

*`next2`*\
最後に変換されたの後にあるへのポインターを、 `CharType` `CharType` コピー先のシーケンス内の変更されていない最初の文字に移動します。

### <a name="return-value"></a>戻り値

操作の成功、一部成功、または失敗を示す戻り値。 この関数では次の値が返されます。

- `codecvt_base::error` ソースシーケンスの形式が正しくない場合は。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok` 変換が成功した場合は。

- `codecvt_base::partial` ソースが十分でない場合、または変換先のサイズが十分でない場合は、変換が成功します。

### <a name="remarks"></a>解説

*`state`* は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 それ以外の場合、格納されている値は指定されません。

### <a name="example"></a>例

の例 [`in`](#in) (を呼び出す) を参照してください `do_in` 。

## <a name="codecvtdo_length"></a><a name="do_length"></a> `codecvt::do_length`

特定の外部値のシーケンスから生成される値の数が、指定された数を超える `Byte` `Byte` 内部 `CharType` 値を取得し、その値を返す仮想関数 `Byte` 。

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>パラメーター

*`state`*\
メンバー関数の呼び出し間で維持される変換の状態。

*`first1`*\
外部シーケンスの先頭へのポインター。

*`last1`*\
外部シーケンスの末尾へのポインター。

*`len2`*\
`Byte`メンバー関数が返すことができる値の最大数。

### <a name="return-value"></a>戻り値

[,) の外部ソースシーケンスによって定義されている、 *len2* を超える変換の最大数を表す整数 `first1` `last1` 。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は `do_in( state, first1, last1, next1, buf, buf + len2, next2)` 、 *状態* (状態のコピー)、いくつかのバッファー、およびポインターを効果的に呼び出し `buf` `next1` `next2` ます。

その後 `next2` - `buf` を返します。 このメソッドは、ソースシーケンスで定義されている、 *len2* ではなく、変換の最大数 ([ `first1` ,) をカウント `last1` します。

テンプレートバージョンでは、常にとの小さい方が返され *`last1`*  -  *`first1`* *`len2`* ます。

### <a name="example"></a>例

の例 [`length`](#length) (を呼び出す) を参照してください `do_length` 。

## <a name="codecvtdo_max_length"></a><a name="do_max_length"></a> `codecvt::do_max_length`

`Byte`1 つの内部を生成するために必要な外部値の最大数を返す仮想関数。 `CharType`

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>戻り値

`Byte`1 つを生成するために必要な値の最大数 `CharType` 。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、 [`do_length`](#do_length) `( first1, last1, 1)` およびの任意の有効な値に対してから返すことができる最大許容値を返し *`first1`* *`last1`* ます。

### <a name="example"></a>例

の例 [`max_length`](#max_length) (を呼び出す) を参照してください `do_max_length` 。

## <a name="codecvtdo_out"></a><a name="do_out"></a> `codecvt::do_out`

内部値のシーケンスを `CharType` 外部値のシーケンスに変換するために呼び出される仮想関数 `Byte` 。

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

*`state`*\
メンバー関数の呼び出し間で維持される変換の状態。

*`first1`*\
変換されるシーケンスの先頭へのポインター。

*`last1`*\
変換されるシーケンスの末尾へのポインター。

*`next1`*\
最後に変換された後の、変換されていない最初のへのポインターへの参照 `CharType` `CharType` 。

*`first2`*\
変換されたシーケンスの先頭へのポインター。

*`last2`*\
変換されたシーケンスの末尾へのポインター。

*`next2`*\
最後に変換された後の、変換されていない最初のへのポインターへの参照 `Byte` `Byte` 。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error` ソースシーケンスの形式が正しくない場合は。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok` 変換が成功した場合は。

- `codecvt_base::partial` ソースが十分でない場合、または変換先が変換に成功するのに十分な大きさでない場合は。

### <a name="remarks"></a>解説

*`state`* は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 それ以外の場合、格納されている値は指定されません。

### <a name="example"></a>例

[out](#out) の例 (`do_out` を呼び出す) を参照してください。

## <a name="codecvtdo_unshift"></a><a name="do_unshift"></a> `codecvt::do_unshift`

`Byte`状態に依存する変換で、値のシーケンスの最後の文字を完了するために必要な値を提供するために呼び出される仮想関数 `Byte` 。

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*`state`*\
メンバー関数の呼び出し間で維持される変換の状態。

*`first2`*\
対象範囲内の最初の位置へのポインター。

*`last2`*\
対象範囲内の最後の位置へのポインター。

*`next2`*\
対象シーケンス内の変更されていない最初の要素へのポインター。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error`*state* が無効な状態を表す場合

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok` 変換が成功した場合

- `codecvt_base::partial` 変換先が、変換を成功させるのに十分な大きさでない場合

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、ソース要素 `CharType` (0) を、 `first2` `last2` 終了要素 (0) を除き、[,) 内に格納されているターゲットシーケンスに変換しようとし `Byte` ます。 このメソッドは、変換先シーケンス内の変更されていない最初の要素へのポインターを常に格納し *`next2`* ます。

*`State`* は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素 (0) を変換すると、 `CharType` 現在の状態は初期の変換状態のままになります。

### <a name="example"></a>例

の例 [`unshift`](#unshift) (を呼び出す) を参照してください `do_unshift` 。

## <a name="codecvtencoding"></a><a name="encoding"></a> `codecvt::encoding`

ストリームのエンコード `Byte` が状態に依存するかどうか、 `Byte` 使用される値と生成される値の比率が一定であるかどうかをテスト `CharType` します。その場合は、その比率の値を決定します。

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>戻り値

戻り値が正の値の場合、その値は文字を `Byte` 生成するために必要な定数の文字数になり `CharType` ます。

protected 仮想メンバー関数は次の値を返します。

- 型のシーケンスのエンコードが状態に依存する場合は-1 `extern_type` 。

- エンコードがさまざまな長さのシーケンスに関係する場合は、0。

- *`N`* エンコーディングが長さのシーケンスのみを含む場合は *`N`* 。

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
   int result1 = use_facet<codecvt<char, char, mbstate_t>> ( loc ).encoding ( );
   cout << result1 << '\n';
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t>> ( loc ).encoding( );
   cout << result1 << '\n';
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t>> ( loc ).encoding( );
   cout << result1 << '\n';
}
```

```Output
1
1
1
```

## <a name="codecvtextern_type"></a><a name="extern_type"></a> `codecvt::extern_type`

外部表現に使用される文字型。

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `Byte` のシノニムです。

## <a name="codecvtin"></a><a name="in"></a> codecvt:: in

値のシーケンスの外部表現を、 `Byte` 値のシーケンスの内部表現に変換し `CharType` ます。

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

*`state`*\
メンバー関数の呼び出し間で維持される変換の状態。

*`first1`*\
変換されるシーケンスの先頭へのポインター。

*`last1`*\
変換されるシーケンスの末尾へのポインター。

*`next1`*\
変換されたシーケンスの末尾の後の、最初の未変換文字へのポインター。

*`first2`*\
変換されたシーケンスの先頭へのポインター。

*`last2`*\
変換されたシーケンスの末尾へのポインター。

*`next2`*\
`CharType`ターゲットシーケンス内の変更されていない最初の文字に最後に変換された後のへのポインター `Chartype` 。

### <a name="return-value"></a>戻り値

操作の成功、一部成功、または失敗を示す戻り値。 この関数では次の値が返されます。

- `codecvt_base::error` ソースシーケンスの形式が正しくない場合は。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok` 変換が成功した場合は。

- `codecvt_base::partial` ソースが十分でない場合、または変換先が変換に成功するのに十分な大きさでない場合は。

### <a name="remarks"></a>解説

*`state`* は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 部分変換の後、 *`state`* 新しい文字が到着したときに変換を再開できるように、を設定する必要があります。

このメンバー関数は、を返し [`do_in`](#do_in) `( state, first1,  last1,  next1, first2, last2,  next2)` ます。

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
   const char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0}; // zero-initialization represents the initial conversion state for mbstate_t
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( res!=codecvt_base::error ?  L"It worked! " : L"It didn't work! " )
       << L"The converted string is:\n ["
       << &pwszInt[0]
       << L"]" << '\n';
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="codecvtintern_type"></a><a name="intern_type"></a> `codecvt::intern_type`

内部表現に使用される文字型。

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `CharType` のシノニムです。

## <a name="codecvtlength"></a><a name="length"></a> codecvt:: length

指定された `Byte` 一連の外部値から生成される内部値の数を超えない値の数を判断 `Byte` `CharType` し、その値の数を返し `Byte` ます。

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>パラメーター

*`state`*\
メンバー関数の呼び出し間で維持される変換の状態。

*`first1`*\
外部シーケンスの先頭へのポインター。

*`last1`*\
外部シーケンスの末尾へのポインター。

*`len2`*\
メンバー関数で返すことができる Byte の最大数。

### <a name="return-value"></a>戻り値

*`len2`* [,) の外部ソースシーケンスによって定義されている、より大きい変換の最大数を表す整数 `first1` `last1` 。

### <a name="remarks"></a>解説

このメンバー関数は、を返し [`do_length`](#do_length) `( state, first1, last1, len2)` ます。

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
   const char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0}; // zero-initialization represents the initial conversion state for mbstate_t
   locale loc("C"); // English_Britain"); //German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << '\n';
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="codecvtmax_length"></a><a name="max_length"></a> `codecvt::max_length`

`Byte`1 つの内部を生成するために必要な外部値の最大数を返し `CharType` ます。

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>戻り値

`Byte`1 つを生成するために必要な値の最大数 `CharType` 。

### <a name="remarks"></a>解説

このメンバー関数は、を返し [`do_max_length`](#do_max_length) ます。

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
   int res = use_facet<codecvt<char, char, mbstate_t>>
     ( loc ).max_length( );
   wcout << res << '\n';
}
```

```Output
1
```

## <a name="codecvtout"></a><a name="out"></a> `codecvt::out`

内部値のシーケンスを `CharType` 外部値のシーケンスに変換 `Byte` します。

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

*`state`*\
メンバー関数の呼び出し間で維持される変換の状態。

*`first1`*\
変換されるシーケンスの先頭へのポインター。

*`last1`*\
変換されるシーケンスの末尾へのポインター。

*`next1`*\
最後に変換された後の、最初の変換されていないへのポインターへの参照 `CharType` `CharType` 。

*`first2`*\
変換されたシーケンスの先頭へのポインター。

*`last2`*\
変換されたシーケンスの末尾へのポインター。

*`next2`*\
最後に変換された後の、最初の変換されていないへのポインターへの参照 `Byte` `Byte` 。

### <a name="return-value"></a>戻り値

このメンバー関数は、を返し [`do_out`](#do_out) `( state, first1, last1, next1, first2, last2, next2)` ます。

### <a name="remarks"></a>解説

詳細については、[`codecvt::do_out`](#do_out) をご覧ください。

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
    char pszExt[LEN + 1];
    const wchar_t* pwszInt = L"This is the wchar_t string to be converted.";
    memset(&pszExt[0], 0, (sizeof(char)) * (LEN + 1));
    char* pszNext;
    const wchar_t* pwszNext;
    mbstate_t state;
    locale loc("C");//English_Britain");//German_Germany
    int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
        (loc).out(state,
            pwszInt, &pwszInt[wcslen(pwszInt)], pwszNext,
            pszExt, &pszExt[wcslen(pwszInt)], pszNext);
    pszExt[wcslen(pwszInt)] = 0;
    cout << (res != codecvt_base::error ? "It worked: " : "It didn't work: ")
        << "The converted string is:\n ["
        << &pszExt[0]
        << "]" << '\n';

}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="codecvtstate_type"></a><a name="state_type"></a> `codecvt::state_type`

内部表現と外部表現との変換時の中間状態を表すために使用される文字型。

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `StateType` のシノニムです。

## <a name="codecvtunshift"></a><a name="unshift"></a> codecvt:: unshift

状態に `Byte` 依存する変換で、値のシーケンスの最後の文字を完了するために必要な値を提供し `Byte` ます。

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*`state`*\
メンバー関数の呼び出し間で維持される変換の状態。

*`first2`*\
対象範囲内の最初の位置へのポインター。

*`last2`*\
対象範囲内の最後の位置へのポインター。

*`next2`*\
対象シーケンス内の変更されていない最初の要素へのポインター。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error` state が無効な状態を表している場合。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok` 変換が成功した場合は。

- `codecvt_base::partial` 変換先が、変換を成功させるのに十分な大きさではない場合。

### <a name="remarks"></a>解説

プロテクト仮想メンバー関数は、ソース要素 `CharType` (0) を、 `first2` `last2` 終了要素 (0) を除き、[,) 内に格納されているターゲットシーケンスに変換しようとし `Byte` ます。 このメソッドは、変換先シーケンス内の変更されていない最初の要素へのポインターを常に格納し *`next2`* ます。

*`state`* は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素 (0) を変換すると、 `CharType` 現在の状態は初期の変換状態のままになります。

このメンバー関数は、を返し [`do_unshift`](#do_unshift) `( state, first2, last2, next2 )` ます。

## <a name="see-also"></a>関連項目

[`<locale>`](../standard-library/locale.md)\
[コードページ](../c-runtime-library/code-pages.md)\
[ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
