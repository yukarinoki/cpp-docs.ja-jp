---
description: '詳細については、「_variant_t:: operator =」を参照してください。'
title: '_variant_t:: operator ='
ms.date: 03/23/2021
f1_keywords:
- _variant_t::operator=
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.openlocfilehash: c1cd581b386a3cf5d551fe8341ba588fc56b9c2e
ms.sourcegitcommit: bb35a6c22d896c4640cff00a7321442c544ca219
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "105744765"
---
# `_variant_t::operator=`

インスタンスに新しい値を割り当て `_variant_t` ます。

`_variant_t`クラスとその `operator=` メンバーは、 **Microsoft 固有** のものです。

## <a name="syntax"></a>構文

```cpp
_variant_t& operator=( const VARIANT& varSrc );
_variant_t& operator=( const VARIANT* pVarSrc );
_variant_t& operator=( const _variant_t& var_t_Src );
_variant_t& operator=( short sSrc );
_variant_t& operator=( long lSrc );
_variant_t& operator=( float fltSrc );
_variant_t& operator=( double dblSrc );
_variant_t& operator=( const CY& cySrc );
_variant_t& operator=( const _bstr_t& bstrSrc );
_variant_t& operator=( const wchar_t* wstrSrc );
_variant_t& operator=( const char* strSrc );
_variant_t& operator=( IDispatch* pDispSrc );
_variant_t& operator=( bool bSrc );
_variant_t& operator=( IUnknown* pSrc );
_variant_t& operator=( const DECIMAL& decSrc );
_variant_t& operator=( BYTE byteSrc );
_variant_t& operator=( char cSrc );
_variant_t& operator=( unsigned short usSrc );
_variant_t& operator=( unsigned long ulSrc );
_variant_t& operator=( int iSrc );
_variant_t& operator=( unsigned int uiSrc );
_variant_t& operator=( __int64 i8Src );
_variant_t& operator=( unsigned __int64 ui8Src );
```

### <a name="parameters"></a>パラメーター

*`varSrc`*\
`VARIANT`コンテンツと型のコピー元のへの参照 `VT_*` 。

*`pVarSrc`*\
`VARIANT`コンテンツと型のコピー元のへのポインター `VT_*` 。

*`var_t_Src`*\
`_variant_t`コンテンツと型のコピー元のへの参照 `VT_*` 。

*`sSrc`*\
**`short`** コピーする整数値。 `VT_BOOL` `*this` が型の場合、指定された型 `VT_BOOL` 。 それ以外の場合は、型として指定され `VT_I2` ます。

*`lSrc`*\
**`long`** コピーする整数値。 `VT_BOOL` `*this` が型の場合、指定された型 `VT_BOOL` 。 `VT_ERROR` `*this` が型の場合、指定された型 `VT_ERROR` 。 それ以外の場合は、指定された型 `VT_I4` です。

*`fltSrc`*\
**`float`** コピーする数値。 指定された型 `VT_R4` 。

*`dblSrc`*\
**`double`** コピーする数値。 `VT_DATE` `this` が型の場合、指定された型 `VT_DATE` 。 それ以外の場合は、指定された型 `VT_R8` です。

*`cySrc`*\
コピーする `CY` オブジェクト。 指定された型 `VT_CY` 。

*`bstrSrc`*\
コピーする `BSTR` オブジェクト。 指定された型 `VT_BSTR` 。

*`wstrSrc`*\
および指定した型として格納されている、コピーする Unicode 文字列 `BSTR` `VT_BSTR` 。

*`strSrc`*\
および指定した型として格納されている、コピーするマルチバイト文字列 `BSTR` `VT_BSTR` 。

*`pDispSrc`*\
`IDispatch`を呼び出すことによってコピーするポインター `AddRef` 。 指定された型 `VT_DISPATCH` 。

*`bSrc`*\
**`bool`** コピーする値。 指定された型 `VT_BOOL` 。

*`pSrc`*\
`IUnknown`を呼び出すことによってコピーするポインター `AddRef` 。 指定された型  `VT_UNKNOWN` 。

*`decSrc`*\
コピーする `DECIMAL` オブジェクト。 指定された型 `VT_DECIMAL` 。

*`byteSrc`*\
`BYTE`コピーする値。 指定された型 `VT_UI1` 。

*`cSrc`*\
**`char`** コピーする値。 指定された型 `VT_I1` 。

*`usSrc`*\
**`unsigned short`** コピーする値。 指定された型 `VT_UI2` 。

*`ulSrc`*\
**`unsigned long`** コピーする値。 指定された型 `VT_UI4` 。

*`iSrc`*\
**`int`** コピーする値。 指定された型 `VT_INT` 。

*`uiSrc`*\
**`unsigned int`** コピーする値。 指定された型 `VT_UINT` 。

*`i8Src`*\
**`__int64`** **`long long`** コピーするまたは値。 指定された型 `VT_I8` 。

*`ui8Src`*\
**`unsigned __int64`** **`unsigned long long`** コピーするまたは値。 指定された型 `VT_UI8` 。

## <a name="remarks"></a>解説

`operator=`代入演算子は、オブジェクトの型を削除する既存の値をクリアするか、 `Release` `IDispatch*` 型および型のを呼び出し `IUnknown*` ます。 次に、オブジェクトに新しい値をコピーし `_variant_t` ます。 `_variant_t`、、およびの各引数に記載されている場合を除き、割り当てられた値と一致するように型を変更し **`short`** **`long`** **`double`** ます。 値型は直接コピーされます。 `VARIANT`または `_variant_t` ポインターまたは参照引数によって、割り当てられたオブジェクトのコンテンツと型がコピーされます。 その他のポインターまたは参照型の引数は、割り当てられたオブジェクトのコピーを作成します。 代入演算子は `AddRef` `IDispatch*` 、引数と `IUnknown*` 引数を呼び出します。

`operator=`[`_com_raise_error`](../cpp/com-raise-error.md)エラーが発生した場合は、を呼び出します。

`operator=` 更新されたオブジェクトへの参照を返し `_variant_t` ます。

## <a name="see-also"></a>関連項目

[`_variant_t` クラス](../cpp/variant-t-class.md)
