---
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: 50c10eb4ff617f4bcdc69d2e1781a9920b9eb0e5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233562"
---
# <a name="_variant_t_variant_t"></a>_variant_t::_variant_t

**Microsoft 固有の仕様**

`_variant_t` オブジェクトを構築します。

## <a name="syntax"></a>構文

```
_variant_t( ) throw( );

_variant_t(
   const VARIANT& varSrc
);

_variant_t(
   const VARIANT* pVarSrc
);

_variant_t(
   const _variant_t& var_t_Src
);

_variant_t(
   VARIANT& varSrc,
   bool fCopy
);

_variant_t(
   short sSrc,
   VARTYPE vtSrc = VT_I2
);

_variant_t(
   long lSrc,
   VARTYPE vtSrc = VT_I4
);

_variant_t(
   float fltSrc
) throw( );

_variant_t(
   double dblSrc,
   VARTYPE vtSrc = VT_R8
);

_variant_t(
   const CY& cySrc
) throw( );

_variant_t(
   const _bstr_t& bstrSrc
);

_variant_t(
   const wchar_t *wstrSrc
);

_variant_t(
   const char* strSrc
);

_variant_t(
   IDispatch* pDispSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   bool bSrc
) throw( );

_variant_t(
   IUnknown* pIUknownSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   const DECIMAL& decSrc
) throw( );

_variant_t(
   BYTE bSrc
) throw( );

variant_t(
   char cSrc
) throw();

_variant_t(
   unsigned short usSrc
) throw();

_variant_t(
   unsigned long ulSrc
) throw();

_variant_t(
   int iSrc
) throw();

_variant_t(
   unsigned int uiSrc
) throw();

_variant_t(
   __int64 i8Src
) throw();

_variant_t(
   unsigned __int64 ui8Src
) throw();
```

#### <a name="parameters"></a>パラメーター

*varSrc*<br/>
新しい `VARIANT` オブジェクトにコピーされる `_variant_t` オブジェクト。

*pVarSrc*<br/>
`VARIANT`新しいオブジェクトにコピーされるオブジェクトへのポインター `_variant_t` 。

*var_t_Src*<br/>
新しい `_variant_t` オブジェクトにコピーされる `_variant_t` オブジェクト。

*fCopy*<br/>
**`false`** の場合、指定された `VARIANT` オブジェクトは、 `_variant_t` によって新しいコピーが作成されることなく、新しいオブジェクトにアタッチされ `VariantCopy` ます。

*ISrc、sSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる整数値。

*vtSrc*<br/>
`VARTYPE`新しい `_variant_t` オブジェクトの。

*fltSrc、dblSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる数値。

*cySrc*<br/>
新しい `CY` オブジェクトにコピーされる `_variant_t` オブジェクト。

*bstrSrc*<br/>
新しい `_bstr_t` オブジェクトにコピーされる `_variant_t` オブジェクト。

*strSrc、wstrSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる文字列。

*bSrc*<br/>
**`bool`** 新しいオブジェクトにコピーされる値 `_variant_t` 。

*pIUknownSrc*<br/>
新しいオブジェクトにカプセル化される VT_UNKNOWN オブジェクトへの COM インターフェイスポインター `_variant_t` 。

*pDispSrc*<br/>
新しいオブジェクトにカプセル化される VT_DISPATCH オブジェクトへの COM インターフェイスポインター `_variant_t` 。

*decSrc*<br/>
新しい `DECIMAL` オブジェクトにコピーされる `_variant_t` 値。

*bSrc*<br/>
新しい `BYTE` オブジェクトにコピーされる `_variant_t` 値。

*cSrc*<br/>
**`char`** 新しいオブジェクトにコピーされる値 `_variant_t` 。

*usSrc*<br/>
**`unsigned short`** 新しいオブジェクトにコピーされる値 `_variant_t` 。

*ulSrc*<br/>
**`unsigned long`** 新しいオブジェクトにコピーされる値 `_variant_t` 。

*iSrc*<br/>
**`int`** 新しいオブジェクトにコピーされる値 `_variant_t` 。

*uiSrc*<br/>
**`unsigned int`** 新しいオブジェクトにコピーされる値 `_variant_t` 。

*i8Src*<br/>
**`__int64`** 新しいオブジェクトにコピーされる値 `_variant_t` 。

*ui8Src*<br/>
新しいオブジェクトにコピーされる**符号なし __int64**値 `_variant_t` 。

## <a name="remarks"></a>解説

- **_variant_t ()** 空 `_variant_t` のオブジェクトを構築 `VT_EMPTY` します。

- **_variant_t (variant&** *varsrc***)**`_variant_t`オブジェクトのコピーからオブジェクトを構築 `VARIANT` します。     バリアント型は保持されます。

- **_variant_t (variant** <strong>\*</strong> *pVarSrc***)** `_variant_t` オブジェクトのコピーからオブジェクトを構築 `VARIANT` します。     バリアント型は保持されます。

- **_variant_t (_variant_t&** *var_t_Src***)** 別の `_variant_t` オブジェクトからオブジェクトを構築 `_variant_t` します。     バリアント型は保持されます。

- **_variant_t (variant&** *varsrc* **, bool** `fCopy` **)** は、 `_variant_t` 既存のオブジェクトからオブジェクトを構築 `VARIANT` します。       *Fcopy*がの場合は **`false`** 、コピーを作成せずに、**バリアント**オブジェクトが新しいオブジェクトにアタッチされます。

- **_variant_t (short***sSrc* **, VARTYPE** `vtSrc` **= VT_I2)** は、 `_variant_t` 整数値から VT_I2 または VT_BOOL 型のオブジェクトを構築 **`short`** します。       それ以外の場合 `VARTYPE` は、E_INVALIDARG エラーになります。

- **_variant_t (long** `lSrc` **、VARTYPE** `vtSrc` **= VT_I4)** は、 `_variant_t` 整数値から型 VT_I4、VT_BOOL、または VT_ERROR のオブジェクトを構築 **`long`** します。       それ以外の場合 `VARTYPE` は、E_INVALIDARG エラーになります。

- **_variant_t (float** `fltSrc` **)** は、 `_variant_t` 数値から VT_R4 型のオブジェクトを構築 **`float`** します。    

- **_variant_t (double** `dblSrc` **、VARTYPE** `vtSrc` **= VT_R8)** は、 `_variant_t` 型 VT_R8 のオブジェクト、または数値からの VT_DATE を構築 **`double`** します。       それ以外の場合 `VARTYPE` は、E_INVALIDARG エラーになります。

- **_variant_t (CY&** `cySrc` **)** `_variant_t` は、オブジェクトから VT_CY 型のオブジェクトを構築 `CY` します。    

- **_variant_t (_bstr_t&** `bstrSrc` **)** は、 `_variant_t` オブジェクトから VT_BSTR 型のオブジェクトを構築 `_bstr_t` します。     新しい `BSTR` を割り当てます。

- **_variant_t (wchar_t** <strong>\*</strong> *wstrsrc*  **)** は、 `_variant_t` Unicode 文字列から VT_BSTR 型のオブジェクトを構築します。 新しい `BSTR` を割り当てます。

- **_variant_t (char** <strong>\*</strong> `strSrc`**)** `_variant_t` 文字列から VT_BSTR 型のオブジェクトを構築します。     新しい `BSTR` を割り当てます。

- **_variant_t (bool** `bSrc` **)** は、 `_variant_t` 値から VT_BOOL 型のオブジェクトを構築 **`bool`** します。    

- **_variant_t (IUnknown** <strong>\*</strong> `pIUknownSrc`**、bool** `fAddRef`**= true)**`_variant_t`COM インターフェイスポインターから VT_UNKNOWN 型のオブジェクトを構築します。       `fAddRef`がの場合は **`true`** 、指定された `AddRef` インターフェイスポインターでが呼び出され、 `Release` オブジェクトが破棄されるときに発生するへの呼び出しに一致し `_variant_t` ます。 指定されたインターフェイスポインターに対してを呼び出すことができ `Release` ます。 がの場合 `fAddRef` **`false`** 、このコンストラクターは指定されたインターフェイスポインターの所有権を取得します。指定された `Release` インターフェイスポインターでを呼び出さないでください。

- **_variant_t (IDispatch** <strong>\*</strong> `pDispSrc`**、bool** `fAddRef`**= true)**`_variant_t`COM インターフェイスポインターから VT_DISPATCH 型のオブジェクトを構築します。       `fAddRef`がの場合は **`true`** 、指定された `AddRef` インターフェイスポインターでが呼び出され、 `Release` オブジェクトが破棄されるときに発生するへの呼び出しに一致し `_variant_t` ます。 指定されたインターフェイスポインターに対してを呼び出すことができ `Release` ます。 がの場合 `fAddRef` **`false`** 、このコンストラクターは指定されたインターフェイスポインターの所有権を取得します。指定された `Release` インターフェイスポインターでを呼び出さないでください。

- **_variant_t (DECIMAL&** `decSrc` **)** `_variant_t` は、値から VT_DECIMAL 型のオブジェクトを構築 `DECIMAL` します。    

- **_variant_t (BYTE** `bSrc` **)** `_variant_t` は、値から型のオブジェクトを構築 `VT_UI1` `BYTE` します。    

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
