---
title: _variant_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator=
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
ms.openlocfilehash: 402251592a87b723d75fd1b2cd0786be7b17dbfc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187623"
---
# <a name="_variant_toperator-"></a>_variant_t::operator =

**Microsoft 固有の仕様**

## <a name="syntax"></a>構文

```
_variant_t& operator=(
   const VARIANT& varSrc
);

_variant_t& operator=(
   const VARIANT* pVarSrc
);

_variant_t& operator=(
   const _variant_t& var_t_Src
);

_variant_t& operator=(
   short sSrc
);

_variant_t& operator=(
   long lSrc
);

_variant_t& operator=(
   float fltSrc
);

_variant_t& operator=(
   double dblSrc
);

_variant_t& operator=(
   const CY& cySrc
);

_variant_t& operator=(
   const _bstr_t& bstrSrc
);

_variant_t& operator=(
   const wchar_t* wstrSrc
);

_variant_t& operator=(
   const char* strSrc
);

_variant_t& operator=(
   IDispatch* pDispSrc
);

_variant_t& operator=(
   bool bSrc
);

_variant_t& operator=(
   IUnknown* pSrc
);

_variant_t& operator=(
   const DECIMAL& decSrc
);

_variant_t& operator=(
   BYTE bSrc
);

_variant_t& operator=(
   char cSrc
);

_variant_t& operator=(
   unsigned short usSrc
);

_variant_t& operator=(
   unsigned long ulSrc
);

_variant_t& operator=(
   int iSrc
);

_variant_t& operator=(
   unsigned int uiSrc
);

_variant_t& operator=(
   __int64 i8Src
);

_variant_t& operator=(
   unsigned __int64 ui8Src
);
```

## <a name="remarks"></a>解説

この演算子は、`_variant_t` オブジェクトに新しい値を代入します。

- **operator = (**  *varsrc*  **)** 既存の `VARIANT` を `_variant_t` オブジェクトに割り当てます。

- **operator = (**  *pVarSrc*  **)** 既存の `VARIANT` を `_variant_t` オブジェクトに割り当てます。

- **operator = (**  *var_t_Src*  **)** 既存の `_variant_t` オブジェクトを `_variant_t` オブジェクトに割り当てます。

- **operator = (** *sSrc* **)** `_variant_t` オブジェクトに**short**整数値を代入します。

- **operator = (** `lSrc` **)** `_variant_t` オブジェクトに**長**整数値を割り当てます。

- **operator = (** *fltsrc* **)** `_variant_t` オブジェクトに**float**数値を代入します。

- **operator = (** *dblsrc* **)** `_variant_t` オブジェクトに**2**つの数値を代入します。

- **operator = (** *cysrc* **)** `CY` オブジェクトを `_variant_t` オブジェクトに割り当てます。

- **operator = (** *bstrsrc* **)** `BSTR` オブジェクトを `_variant_t` オブジェクトに割り当てます。

- **operator = (** *wstrsrc* **)** `_variant_t` オブジェクトに Unicode 文字列を割り当てます。

- **operator = (** `strSrc` **)** マルチバイト文字列を `_variant_t` オブジェクトに割り当てます。

- **operator = (** `bSrc` **)** `_variant_t` オブジェクトに**ブール**値を割り当てます。

- **operator = (** *pdispsrc* **)** `VT_DISPATCH` オブジェクトを `_variant_t` オブジェクトに割り当てます。

- **operator = (** *pIUnknownSrc* **)** `VT_UNKNOWN` オブジェクトを `_variant_t` オブジェクトに割り当てます。

- **operator = (** *decsrc* **)** `DECIMAL` 値を `_variant_t` オブジェクトに割り当てます。

- **operator = (** `bSrc` **)** `BYTE` 値を `_variant_t` オブジェクトに割り当てます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_variant_t クラス](../cpp/variant-t-class.md)
