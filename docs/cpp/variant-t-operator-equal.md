---
description: '詳細については、「_variant_t:: operator =」を参照してください。'
title: _variant_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator=
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
ms.openlocfilehash: a304f0904f697ade7d04c6d12f375571a156e989
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161469"
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

- **operator = (**  *varsrc*  **)** 既存のを `VARIANT` オブジェクトに割り当て `_variant_t` ます。

- **operator = (**  *pVarSrc*  **)** 既存のを `VARIANT` オブジェクトに割り当て `_variant_t` ます。

- **operator = (**  *var_t_Src*  **)** 既存 `_variant_t` のオブジェクトをオブジェクトに割り当て `_variant_t` ます。

- **operator = (***sSrc***)****`short`** オブジェクトに整数値を割り当て `_variant_t` ます。    

- **operator = (** `lSrc` **)** **`long`** オブジェクトに整数値を代入 `_variant_t` します。    

- **operator = (**  *fltsrc*  **)** 数値を **`float`** オブジェクトに割り当て `_variant_t` ます。

- **operator = (**  *dblsrc*  **)** 数値を **`double`** オブジェクトに割り当て `_variant_t` ます。

- **operator = (**  *cysrc*  **)** オブジェクトを `CY` オブジェクトに割り当て `_variant_t` ます。

- **operator = (**  *bstrsrc*  **)** オブジェクトを `BSTR` オブジェクトに割り当て `_variant_t` ます。

- **operator = (**  *wstrsrc*  **)** Unicode 文字列をオブジェクトに割り当て `_variant_t` ます。

- **operator = (** `strSrc` **)** オブジェクトにマルチバイト文字列を代入 `_variant_t` します。    

- **operator = (** `bSrc` **)** **`bool`** オブジェクトに値を代入 `_variant_t` します。  

- **operator = (**  *pdispsrc*  **)** オブジェクトを `VT_DISPATCH` オブジェクトに割り当て `_variant_t` ます。

- **operator = (**  *pIUnknownSrc*  **)** オブジェクトを `VT_UNKNOWN` オブジェクトに割り当て `_variant_t` ます。

- **operator = (***decsrc***)**`DECIMAL`オブジェクトに値を割り当て `_variant_t` ます。    

- **operator = (** `bSrc` **)** `BYTE` オブジェクトに値を代入 `_variant_t` します。  

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
