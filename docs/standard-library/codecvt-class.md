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
ms.openlocfilehash: 936b3ab63b454e8f7e0490c2d155356a7c3b240f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459834"
---
# <a name="codecvt-class"></a>codecvt クラス

ロケールのファセットとして使用できるオブジェクトを表すテンプレート クラス。 プログラム内で文字をエンコードするために使用される値のシーケンスと、プログラム外で文字をエンコードするために使用される値のシーケンスとの変換を制御できます。

## <a name="syntax"></a>構文

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>パラメーター

*CharType*\
文字をエンコードするためにプログラム内で使用される型。

*バイト*\
文字をエンコードするためにプログラム外で使用される型。

*StateType*\
文字表現の内部型と外部型との変換の中間状態を表すために使用できる型。

## <a name="remarks"></a>Remarks

このテンプレートクラスは、 *Chartype*型の値のシーケンスと*Byte*型の値のシーケンスとの間の変換を制御するために、[ロケールファセット](../standard-library/locale-class.md#facet_class)として使用できるオブジェクトを表します。 *Statetype*クラスは変換を特徴とし、 *statetype*クラスのオブジェクトは変換中に必要な状態情報を格納します。

内部エンコードでは、1文字あたりのバイト数が固定された表現を使用します。通常は**char**型または**wchar_t**型です。

すべてのロケールのファセットと同様、静的オブジェクト `id` に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、`id` に一意の正の値が格納されます。

[do_in](#do_in) と [do_out](#do_out) のテンプレート バージョンでは、常に `codecvt_base::noconv` が返されます。

C++ 標準ライブラリは複数の明示的な特殊化を定義します。

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

**wchar_t**および**char**シーケンス間の変換を行います。

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

utf-16 としてエンコードされた シーケンスとutf-8としてエンコードされた文字シーケンスを変換し`char16_t`ます。

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

32 utf-8 としてエンコードされた シーケンスとutf-8としてエンコードされた文字シーケンスを変換し`char32_t`ます。

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[codecvt](#codecvt)|変換を処理するためにロケールのファセットとして機能する `codecvt` クラスのオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[extern_type](#extern_type)|外部表現に使用される文字型。|
|[intern_type](#intern_type)|内部表現に使用される文字型。|
|[state_type](#state_type)|内部表現と外部表現との変換時の中間状態を表すために使用される文字型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[always_noconv](#always_noconv)|変換を実行する必要がないかどうかをテストします。|
|[do_always_noconv](#do_always_noconv)|変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。|
|[do_encoding](#do_encoding)|`Byte` ストリームのエンコードが状態に依存する場合に、使用される `Byte` と生成される `CharType` との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定する仮想関数。|
|[do_in](#do_in)|内部の `Byte` のシーケンスを外部の `CharType` のシーケンスに変換するために呼び出される仮想関数。|
|[do_length](#do_length)|特定の外部 `Byte` シーケンスから生成された内部 `Byte` が特定の数を超えずに最大となる `CharType` 数を特定し、その `Byte` 数を返す仮想関数。|
|[do_max_length](#do_max_length)|1 つの内部 `CharType` を生成するために必要な最大外部 Byte 数を返す仮想関数。|
|[do_out](#do_out)|内部の `CharType` のシーケンスを外部の Byte のシーケンスに変換するために呼び出される仮想関数。|
|[do_unshift](#do_unshift)|状態に依存する変換で、`Byte` のシーケンスの最後の文字を完了するために必要な `Byte` を提供するために呼び出される仮想関数。|
|[encoding](#encoding)|`Byte` ストリームのエンコードが状態に依存する場合に、使用される `Byte` と生成される `CharType` との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定します。|
|[in](#in)|`Byte` のシーケンスの外部表現を、`CharType` のシーケンスの内部表現に変換します。|
|[length](#length)|特定の外部 `Byte` シーケンスから生成された内部 `Byte` が特定の数を超えずに最大となる `CharType` 数を特定し、その `Byte` 数を返します。|
|[max_length](#max_length)|1 つの内部 `Byte` を生成するために必要な最大外部 `CharType` 数を返します。|
|[out](#out)|内部の `CharType` のシーケンスを外部の `Byte` のシーケンスに変換します。|
|[unshift](#unshift)|状態に依存する変換で、`Byte` のシーケンスの最後の文字を完了するために必要な外部の `Byte` を提供します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="always_noconv"></a>  codecvt::always_noconv

変換を実行する必要がないかどうかをテストします。

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>戻り値

変換する必要がない場合は **true**、少なくとも 1 回は変換する必要がある場合は **false** のブール値。

### <a name="remarks"></a>Remarks

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

## <a name="codecvt"></a>  codecvt::codecvt

変換を処理するためにロケール ファセットとして機能する codecvt クラスのオブジェクトのコンストラクター。

```cpp
explicit codecvt(size_t _Refs = 0);
```

### <a name="parameters"></a>パラメーター

*参照 (_c)* \
オブジェクトのメモリ管理の種類を指定するために使用する整数値。

### <a name="remarks"></a>Remarks

*Refs*パラメーターに指定できる値とその意味は、次のとおりです。

- 0オブジェクトの有効期間は、オブジェクトが含まれているロケールによって管理されます。

- 1:オブジェクトの有効期間は、手動で管理する必要があります。

- 2:これらの値は定義されていません。

コンストラクターは、 `locale::facet` **locale::** [facet](../standard-library/locale-class.md#facet_class)(`_Refs`) を使用して、その基本オブジェクトを初期化します。

## <a name="do_always_noconv"></a>  codecvt::do_always_noconv

変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>戻り値

Protected 仮想メンバー関数は、 [do_in](#do_in)または[do_out](#do_out)のすべての呼び出しでが`noconv`返された場合にのみ**true**を返します。

テンプレート バージョンでは常に **true** が返されます。

### <a name="example"></a>例

[always_noconv](#always_noconv) の例 (`do_always_noconv` を呼び出す) を参照してください。

## <a name="do_encoding"></a>  codecvt::do_encoding

`Byte`ストリームのエンコードが状態に依存するかどうかをテストする仮想関数。使用され`Byte`たと生成さ`CharType`れたの比率が一定であるかどうか、およびその比率の値を決定します。

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>戻り値

protected 仮想メンバー関数は次の値を返します。

- 型`extern_type`のシーケンスのエンコードが状態に依存する場合は-1。

- エンコードがさまざまな長さのシーケンスに関係する場合は、0。

- エンコードが長さ *N* のシーケンスのみに関係する場合は、*N*。

### <a name="example"></a>例

[encoding](#encoding) の例 (`do_encoding` を呼び出す) を参照してください。

## <a name="do_in"></a>  codecvt::do_in

外部`Byte`ののシーケンスを内部`CharType`ののシーケンスに変換するために呼び出される仮想関数。

```cpp
virtual result do_in(
    StateType& _State,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>パラメーター

*状態 (_c)* \
メンバー関数の呼び出し間で維持される変換の状態。

*first1*\
変換されるシーケンスの先頭へのポインター。

*last1*\
変換されるシーケンスの末尾へのポインター。

*next1*\
変換されたシーケンスの末尾の後の、最初の非変換文字へのポインター。

*first2*\
変換されたシーケンスの先頭へのポインター。

*last2*\
変換されたシーケンスの末尾へのポインター。

*next2*\
最後に変換`CharType` `CharType`されたの後にあるへのポインターを、コピー先のシーケンス内の変更されていない最初の文字に移動します。

### <a name="return-value"></a>戻り値

操作の成功、一部成功、または失敗を示す戻り値。 この関数では次の値が返されます。

- `codecvt_base::error`ソースシーケンスの形式が正しくない場合は。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合は。

- `codecvt_base::partial`ソースが十分でない場合、または変換先のサイズが十分でない場合は、変換が成功します。

### <a name="remarks"></a>Remarks

状態は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります *(_c)* 。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 それ以外の場合、格納されている値は指定されません。

### <a name="example"></a>例

[in](#in) の例 (`do_in` を呼び出す) を参照してください。

## <a name="do_length"></a>  codecvt::do_length

特定の外部 `Byte` シーケンスから生成された内部 `Byte` が特定の数を超えずに最大となる `CharType` 数を特定し、その `Byte` 数を返す仮想関数。

```cpp
virtual int do_length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>パラメーター

*状態 (_c)* \
メンバー関数の呼び出し間で維持される変換の状態。

*first1*\
外部シーケンスの先頭へのポインター。

*last1*\
外部シーケンスの末尾へのポインター。

*_Len2*\
メンバー関数が返す`Byte`ことができるの最大数。

### <a name="return-value"></a>戻り値

[`first1` ,`last1`) の外部ソースシーケンスによって定義されている、 *_Len2*を超える変換の最大数を表す整数。

### <a name="remarks"></a>Remarks

プロテクト仮想メンバー関数は、 `do_in`_ を使用して、( `_Buf` `next1` `_Buf` `first1` `last1` `_State`,,  +  ,,,,)を実質的`next2`に呼び出します。 `_Len2` *状態*(状態のコピー)、いくつかの`_Buf`バッファー、および`next1`ポインター `next2`と。

その後、 `next2`を返し -  `buf`ます。 したがって、ソースシーケンス`first1` `last1`によって定義されている、 *_Len2*を超える変換の最大数をカウントします。

テンプレートバージョンでは、常に*last1* - *first1*と *_Len2*の小さい方が返されます。

### <a name="example"></a>例

[Length](#length)の例 (を呼び出す`do_length`) を参照してください。

## <a name="do_max_length"></a>  codecvt::do_max_length

1つの内部`Byte` `CharType`を生成するために必要な外部の最大数を返す仮想関数。

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>戻り値

`Byte`を`CharType`生成するために必要なの最大数。

### <a name="remarks"></a>Remarks

Protected 仮想メンバー関数は、 *first1*および*last1*の任意の有効な値に対し`first1`て`last1` [do_length](#do_length)(,, 1) が返すことができる最大許容値を返します。

### <a name="example"></a>例

[max_length](#max_length) の例 (`do_max_length` を呼び出す) を参照してください。

## <a name="do_out"></a>  codecvt::do_out

内部の `CharType` のシーケンスを外部の `Byte` のシーケンスに変換するために呼び出される仮想関数。

```cpp
virtual result do_out(
    StateType& _State,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*状態 (_c)* \
メンバー関数の呼び出し間で維持される変換の状態。

*first1*\
変換されるシーケンスの先頭へのポインター。

*last1*\
変換されるシーケンスの末尾へのポインター。

*next1*\
`CharType`最後`CharType`に変換された後の、変換されていない最初のへのポインターへの参照。

*first2*\
変換されたシーケンスの先頭へのポインター。

*last2*\
変換されたシーケンスの末尾へのポインター。

*next2*\
`Byte`最後`Byte`に変換された後の、変換されていない最初のへのポインターへの参照。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error`ソースシーケンスの形式が正しくない場合は。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合は。

- `codecvt_base::partial`ソースが十分でない場合、または変換先が変換に成功するのに十分な大きさでない場合は。

### <a name="remarks"></a>Remarks

状態は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります *(_c)* 。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 それ以外の場合、格納されている値は指定されません。

### <a name="example"></a>例

[out](#out) の例 (`do_out` を呼び出す) を参照してください。

## <a name="do_unshift"></a>  codecvt::do_unshift

状態に依存する変換で、`Byte` のシーケンスの最後の文字を完了するために必要な `Byte` を提供するために呼び出される仮想関数。

```cpp
virtual result do_unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*状態 (_c)* \
メンバー関数の呼び出し間で維持される変換の状態。

*first2*\
対象範囲内の最初の位置へのポインター。

*last2*\
対象範囲内の最後の位置へのポインター。

*next2*\
対象シーケンス内の変更されていない最初の要素へのポインター。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error`_ *state*が無効な状態を表す場合

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合

- `codecvt_base::partial`変換先が、変換を成功させるのに十分な大きさでない場合

### <a name="remarks"></a>Remarks

プロテクト仮想メンバー関数は、 `CharType`ソース要素 (0) を、終了要素`Byte`(0) を除き、[ `first2`, `last2`) 内に格納されているターゲットシーケンスに変換しようとします。 *Next2*には、変換先シーケンス内の変更されていない最初の要素へのポインターが常に格納されます。

_ *State* は、新しいソース シーケンスの先頭で最初の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素`CharType`(0) を変換すると、現在の状態は初期の変換状態のままになります。

### <a name="example"></a>例

[unshift](#unshift) の例 (`do_unshift` を呼び出す) を参照してください。

## <a name="encoding"></a>  codecvt::encoding

`Byte` ストリームのエンコードが状態に依存する場合に、使用される `Byte` と生成される `CharType` との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定します。

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>戻り値

戻り値が正の値の場合、その値は`Byte` `CharType`文字を生成するために必要な定数の文字数になります。

protected 仮想メンバー関数は次の値を返します。

- 型`extern_type`のシーケンスのエンコードが状態に依存する場合は-1。

- エンコードがさまざまな長さのシーケンスに関係する場合は、0。

- エンコードが長さ *N* のシーケンスのみに関係する場合は、*N*。

### <a name="remarks"></a>Remarks

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

## <a name="extern_type"></a>  codecvt::extern_type

外部表現に使用される文字型。

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `Byte` のシノニムです。

## <a name="in"></a>  codecvt::in

`Byte` のシーケンスの外部表現を、`CharType` のシーケンスの内部表現に変換します。

```cpp
result in(
    StateType& _State,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>パラメーター

*状態 (_c)* \
メンバー関数の呼び出し間で維持される変換の状態。

*first1*\
変換されるシーケンスの先頭へのポインター。

*last1*\
変換されるシーケンスの末尾へのポインター。

*next1*\
変換されたシーケンスの末尾の後の、最初の未変換文字へのポインター。

*first2*\
変換されたシーケンスの先頭へのポインター。

*last2*\
変換されたシーケンスの末尾へのポインター。

*next2*\
ターゲットシーケンス内`CharType`の変更されてい`Chartype`ない最初の文字に最後に変換された後のへのポインター。

### <a name="return-value"></a>戻り値

操作の成功、一部成功、または失敗を示す戻り値。 この関数では次の値が返されます。

- `codecvt_base::error`ソースシーケンスの形式が正しくない場合は。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合は。

- `codecvt_base::partial`ソースが十分でない場合、または変換先が変換に成功するのに十分な大きさでない場合は。

### <a name="remarks"></a>Remarks

状態は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります *(_c)* 。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 部分変換後に、新しい文字が到着したときに変換を再開できるように、*状態*を設定する必要があります。

メンバー関数は、[do_in](#do_in)( `_State`, _ *First1,  last1,  next1, First2, _Llast2,  next2*) を返します。

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

## <a name="intern_type"></a>  codecvt::intern_type

内部表現に使用される文字型。

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `CharType` のシノニムです。

## <a name="length"></a>  codecvt::length

特定の外部 `Byte` シーケンスから生成された内部 `Byte` が特定の数を超えずに最大となる `CharType` 数を特定し、その `Byte` 数を返します。

```cpp
int length(
    const StateType& _State,
    const Byte* first1,
    const Byte* last1,
    size_t _Len2) const;
```

### <a name="parameters"></a>パラメーター

*状態 (_c)* \
メンバー関数の呼び出し間で維持される変換の状態。

*first1*\
外部シーケンスの先頭へのポインター。

*last1*\
外部シーケンスの末尾へのポインター。

*_Len2*\
メンバー関数で返すことができる Byte の最大数。

### <a name="return-value"></a>戻り値

[`first1` ,`last1`) の外部ソースシーケンスによって定義されている、 *_Len2*を超える変換の最大数を表す整数。

### <a name="remarks"></a>Remarks

このメンバー関数は、[do_length](#do_length)( *_State,  first1*, `last1`, `_Len2`) を返します。

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

## <a name="max_length"></a>  codecvt::max_length

1 つの内部 `Byte` を生成するために必要な最大外部 `CharType` 数を返します。

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>戻り値

`Byte`を`CharType`生成するために必要なの最大数。

### <a name="remarks"></a>Remarks

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

## <a name="out"></a>  codecvt::out

内部の `CharType` のシーケンスを外部の `Byte` のシーケンスに変換します。

```cpp
result out(
    StateType& _State,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*状態 (_c)* \
メンバー関数の呼び出し間で維持される変換の状態。

*first1*\
変換されるシーケンスの先頭へのポインター。

*last1*\
変換されるシーケンスの末尾へのポインター。

*next1*\
`CharType` 最後`CharType`に変換された後の、最初の変換されていないへのポインターへの参照。

*first2*\
変換されたシーケンスの先頭へのポインター。

*last2*\
変換されたシーケンスの末尾へのポインター。

*next2*\
最後に変換され`Byte`た後の、最初の変換`Byte`されていないへのポインターへの参照。

### <a name="return-value"></a>戻り値

このメンバー関数は、[do_out](#do_out)( `_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`) を返します。

### <a name="remarks"></a>Remarks

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

## <a name="state_type"></a>  codecvt::state_type

内部表現と外部表現との変換時の中間状態を表すために使用される文字型。

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `StateType` のシノニムです。

## <a name="unshift"></a>  codecvt::unshift

状態に`Byte`依存する変換で、の`Byte`シーケンスの最後の文字を完了するために必要なを提供します。

```cpp
result unshift(
    StateType& _State,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>パラメーター

*状態 (_c)* \
メンバー関数の呼び出し間で維持される変換の状態。

*first2*\
対象範囲内の最初の位置へのポインター。

*last2*\
対象範囲内の最後の位置へのポインター。

*next2*\
対象シーケンス内の変更されていない最初の要素へのポインター。

### <a name="return-value"></a>戻り値

この関数では次の値が返されます。

- `codecvt_base::error`state が無効な状態を表している場合。

- 関数で変換が行われない場合は、`codecvt_base::noconv`。

- `codecvt_base::ok`変換が成功した場合は。

- `codecvt_base::partial`変換先が、変換を成功させるのに十分な大きさでない場合は。

### <a name="remarks"></a>Remarks

プロテクト仮想メンバー関数は、 `CharType`ソース要素 (0) を、終了要素`Byte`(0) を除き、[ `first2`, `last2`) 内に格納されているターゲットシーケンスに変換しようとします。 *Next2*には、変換先シーケンス内の変更されていない最初の要素へのポインターが常に格納されます。

状態は、新しいソースシーケンスの先頭にある最初の変換状態を表す必要があります *(_c)* 。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素`CharType`(0) を変換すると、現在の状態は初期の変換状態のままになります。

このメンバー関数は、[do_unshift](#do_unshift)( `_State`, `first2`, `last2`, `next2` ) を返します。

## <a name="see-also"></a>関連項目

[\<locale>](../standard-library/locale.md)\
[コード ページ](../c-runtime-library/code-pages.md)\
[ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
