---
title: wstring_convert クラス
ms.date: 11/04/2016
f1_keywords:
- wstring/stdext::cvt::wstring_convert
- locale/std::wstring_convert::byte_string
- locale/std::wstring_convert::wide_string
- locale/std::wstring_convert::state_type
- locale/std::wstring_convert::int_type
- locale/std::wstring_convert::from_bytes
- locale/std::wstring_convert::to_bytes
- locale/std::wstring_convert::converted
- locale/std::wstring_convert::state
helpviewer_keywords:
- stdext::cvt [C++], wstring_convert
- std::wstring_convert [C++], byte_string
- std::wstring_convert [C++], wide_string
- std::wstring_convert [C++], state_type
- std::wstring_convert [C++], int_type
- std::wstring_convert [C++], from_bytes
- std::wstring_convert [C++], to_bytes
- std::wstring_convert [C++], converted
- std::wstring_convert [C++], state
ms.assetid: e34f5b65-d572-4bdc-ac69-20778712e376
ms.openlocfilehash: df3b003289dcd86e8033521d8cb0cacdbb7dfbd8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410799"
---
# <a name="wstringconvert-class"></a>wstring_convert クラス

テンプレート クラス `wstring_convert` は、ワイド文字列とバイト文字列の間の変換を実行します。

## <a name="syntax"></a>構文

```cpp
template <class Codecvt, class Elem = wchar_t>
class wstring_convert
```

### <a name="parameters"></a>パラメーター

*Codecvt*<br/>
変換オブジェクトを表す[ロケール](../standard-library/locale-class.md) ファセット。

*Elem*<br/>
ワイド文字要素型。

## <a name="remarks"></a>Remarks

このテンプレート クラスは、クラス `std::basic_string<Elem>` のワイド文字列オブジェクトとクラス `std::basic_string<char>` (`std::string` とも呼ばれます) のバイト文字列オブジェクトの間の変換を制御するオブジェクトを表します。 このテンプレート クラスは、`wide_string` 型と `byte_string` 型をこれら 2 つの型のシノニムとして定義します。 `Elem` 値のシーケンス (`wide_string` オブジェクトに格納) とマルチバイト シーケンス (`byte_string` オブジェクトに格納) の間の変換は、クラス `Codecvt<Elem, char, std::mbstate_t>` のオブジェクトによって実行されます。このことは、標準コード変換ファセット `std::codecvt<Elem, char, std::mbstate_t>` の要件を満たしています。

このテンプレート クラスのオブジェクトは、以下のものを格納します。

- エラーに表示するバイト文字列

- エラーに表示するワイド文字列

- 割り当てられた変換オブジェクトへのポインター (wbuffer_convert オブジェクトが破棄されると解放される)

- 型 [state_type](#state_type) の変換状態オブジェクト。

- 変換の数

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[wstring_convert](#wstring_convert)|`wstring_convert` 型のオブジェクトを構築します。|

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[byte_string](#byte_string)|バイト文字列を表す型。|
|[wide_string](#wide_string)|ワイド文字列を表す型。|
|[state_type](#state_type)|変換状態を表す型。|
|[int_type](#int_type)|整数を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[from_bytes](#from_bytes)|バイト文字列をワイド文字列に変換します。|
|[to_bytes](#to_bytes)|ワイド文字列をバイト文字列に変換します。|
|[converted](#converted)|成功した変換の数を返します。|
|[state](#state)|変換の状態を表すオブジェクトを返します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<locale>

**名前空間:** std

## <a name="byte_string"></a>  wstring_convert::byte_string

バイト文字列を表す型。

```cpp
typedef std::basic_string<char> byte_string;
```

### <a name="remarks"></a>Remarks

この型は `std::basic_string<char>` の同意語です。

## <a name="converted"></a>  wstring_convert::converted

成功した変換の数を返します。

```cpp
size_t converted() const;
```

### <a name="return-value"></a>戻り値

成功した変換の数。

### <a name="remarks"></a>Remarks

成功した変換の数は、変換数オブジェクトに格納されます。

## <a name="from_bytes"></a>  wstring_convert::from_bytes

バイト文字列をワイド文字列に変換します。

```cpp
wide_string from_bytes(char Byte);
wide_string from_bytes(const char* ptr);
wide_string from_bytes(const byte_string& Bstr);
wide_string from_bytes(const char* first, const char* last);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Byte*|変換される単一の要素のバイト シーケンス。|
|*ptr*|文字が null で終わり、変換の対象となる C スタイルのシーケンス。|
|*bstr*|変換される [byte_string](#byte_string)。|
|*first*|変換の対象となる一定範囲の文字のうち、最初の文字。|
|*last*|変換の対象となる一定範囲の文字のうち、最後の文字。|

### <a name="return-value"></a>戻り値

変換により作成されるワイド文字列オブジェクト。

### <a name="remarks"></a>Remarks

場合、[変換状態](../standard-library/wstring-convert-class.md)オブジェクトが*いない*明示的な値を使用して構築、既定値 (初期の変換状態) に設定されて、変換を開始する前にします。 それ以外の場合は変更されません。

正常に変換された入力要素の数が変換数オブジェクトに格納されます。 変換エラーが発生しなかった場合、メンバー関数は、変換されたワイド文字列を返します。 エラーが発生した場合、ワイド文字列エラー メッセージの初期化子を使用してオブジェクトが構築されていれば、メンバー関数は、ワイド文字列エラー メッセージ オブジェクトを返します。 それ以外の場合、メンバー関数は、クラス [range_error](../standard-library/range-error-class.md) のオブジェクトをスローします。

## <a name="int_type"></a>  wstring_convert::int_type

整数を表す型。

```cpp
typedef typename wide_string::traits_type::int_type int_type;
```

### <a name="remarks"></a>Remarks

この型は `wide_string::traits_type::int_type` の同意語です。

## <a name="state"></a>  wstring_convert::state

変換の状態を表すオブジェクトを返します。

```cpp
state_type state() const;
```

### <a name="return-value"></a>戻り値

変換の状態を表す[変換状態](../standard-library/wstring-convert-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

## <a name="state_type"></a>  wstring_convert::state_type

変換状態を表す型。

```cpp
typedef typename Codecvt::state_type state_type;
```

### <a name="remarks"></a>Remarks

この型は、変換状態を表すことができるオブジェクトを表します。 この型は `Codecvt::state_type` の同意語です。

## <a name="to_bytes"></a>  wstring_convert::to_bytes

ワイド文字列をバイト文字列に変換します。

```cpp
byte_string to_bytes(Elem Char);
byte_string to_bytes(const Elem* Wptr);
byte_string to_bytes(const wide_string& Wstr);
byte_string to_bytes(const Elem* first, const Elem* last);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Char*|変換されるワイド文字。|
|*Wptr*|変換される C スタイル、`wptr` から始まり、null で終わるシーケンス。|
|*Wstr*|変換される [wide_string](#wide_string)。|
|*first*|変換される要素範囲の最初の要素。|
|*last*|変換される要素範囲の最後の要素。|

### <a name="remarks"></a>Remarks

場合、[変換状態](../standard-library/wstring-convert-class.md)オブジェクトが*いない*明示的な値を使用して構築、既定値 (初期の変換状態) に設定されて、変換を開始する前にします。 それ以外の場合は変更されません。

正常に変換された入力要素の数が変換数オブジェクトに格納されます。 変換エラーが発生しなかった場合、メンバー関数は、変換されたバイト文字列を返します。 エラーが発生した場合、バイト文字列エラー メッセージの初期化子を使用してオブジェクトが構築されていれば、メンバー関数は、バイト文字列エラー メッセージ オブジェクトを返します。 それ以外の場合、メンバー関数は、クラス [range_error](../standard-library/range-error-class.md) のオブジェクトをスローします。

## <a name="wide_string"></a>  wstring_convert::wide_string

ワイド文字列を表す型。

```cpp
typedef std::basic_string<Elem> wide_string;
```

### <a name="remarks"></a>Remarks

この型は `std::basic_string<Elem>` の同意語です。

## <a name="wstring_convert"></a>  wstring_convert::wstring_convert

`wstring_convert` 型のオブジェクトを構築します。

```cpp
wstring_convert(Codecvt *Pcvt = new Codecvt);
wstring_convert(Codecvt *Pcvt, state_type _State);
wstring_convert(const byte_string& _Berr, const wide_string& Werr = wide_string());
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*\*Pcvt*|変換を行う、型 `Codecvt` のオブジェクト。|
|*_State*|変換状態を表す、型 [state_type](#state_type) のオブジェクト。|
|*_Berr*|エラーに表示される [byte_string](#byte_string)。|
|*Werr*|エラーに表示される [wide_string](#wide_string)。|

### <a name="remarks"></a>Remarks

1 つめのコンストラクターは、*Pcvt_arg* を[変換オブジェクト](../standard-library/wstring-convert-class.md)に格納します。
