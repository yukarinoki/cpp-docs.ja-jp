---
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: fff116ef04967a1887eaa075d92d3ea0283d5427
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187532"
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
新しい `_variant_t` オブジェクトにコピーされる `VARIANT` オブジェクトへのポインター。

*var_t_Src*<br/>
新しい `_variant_t` オブジェクトにコピーされる `_variant_t` オブジェクト。

*fCopy*<br/>
**False**の場合、指定された `VARIANT` オブジェクトは、`VariantCopy`によって新しいコピーを作成せずに、新しい `_variant_t` オブジェクトにアタッチされます。

*ISrc、sSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる整数値。

*vtSrc*<br/>
新しい `_variant_t` オブジェクトの `VARTYPE`。

*fltSrc、dblSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる数値。

*cySrc*<br/>
新しい `CY` オブジェクトにコピーされる `_variant_t` オブジェクト。

*bstrSrc*<br/>
新しい `_bstr_t` オブジェクトにコピーされる `_variant_t` オブジェクト。

*strSrc、wstrSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる文字列。

*bSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる**ブール**値。

*pIUknownSrc*<br/>
新しい `_variant_t` オブジェクトにカプセル化される VT_UNKNOWN オブジェクトへの COM インターフェイスポインター。

*pDispSrc*<br/>
新しい `_variant_t` オブジェクトにカプセル化される VT_DISPATCH オブジェクトへの COM インターフェイスポインター。

*decSrc*<br/>
新しい `DECIMAL` オブジェクトにコピーされる `_variant_t` 値。

*bSrc*<br/>
新しい `BYTE` オブジェクトにコピーされる `_variant_t` 値。

*cSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる**char**値。

*usSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる**符号なし short**値。

*ulSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる**符号なし long**値。

*iSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる**int**値。

*uiSrc*<br/>
新しい `_variant_t` オブジェクトにコピーされる**符号なし整数**値。

*i8Src*<br/>
新しい `_variant_t` オブジェクトにコピーされる **__int64**値。

*ui8Src*<br/>
新しい `_variant_t` オブジェクトにコピーされる**符号なし __int64**値。

## <a name="remarks"></a>解説

- **_variant_t ()** 空の `_variant_t` オブジェクト、`VT_EMPTY`を構築します。

- **_variant_t (variant &** *varsrc* **)** `VARIANT` オブジェクトのコピーから `_variant_t` オブジェクトを構築します。 バリアント型は保持されます。

- **_variant_t (バリアント**<strong>\*</strong> *pVarSrc* **)** `VARIANT` オブジェクトのコピーから `_variant_t` オブジェクトを構築します。 バリアント型は保持されます。

- **_variant_t (_variant_t &** *var_t_Src* **)** 別の `_variant_t` オブジェクトから `_variant_t` オブジェクトを構築します。 バリアント型は保持されます。

- **_variant_t (variant &** *varsrc* **、bool**`fCopy` **)** 既存の `VARIANT` オブジェクトから `_variant_t` オブジェクトを構築します。 *Fcopy*が**false**の場合、 **VARIANT**オブジェクトはコピーを作成せずに新しいオブジェクトにアタッチされます。

- **_variant_t (short***sSrc* **、VARTYPE**`vtSrc` **= VT_I2)** VT_I2 型の `_variant_t` オブジェクト、または**short**整数値から VT_BOOL を構築します。 その他の `VARTYPE` は、E_INVALIDARG エラーになります。

- **_variant_t (long**`lSrc` **、VARTYPE**`vtSrc` **= VT_I4)** **長**整数値から VT_I4、VT_BOOL、または VT_ERROR 型の `_variant_t` オブジェクトを構築します。 その他の `VARTYPE` は、E_INVALIDARG エラーになります。

- **_variant_t (float**`fltSrc` **)** **Float**数値から VT_R4 型の `_variant_t` オブジェクトを構築します。

- **_variant_t (二重**`dblSrc` **、VARTYPE**`vtSrc` **= VT_R8)** VT_R8 型の `_variant_t` オブジェクト、または**2**つの数値から VT_DATE を構築します。 その他の `VARTYPE` は、E_INVALIDARG エラーになります。

- **_variant_t (CY &** `cySrc` **)** `CY` オブジェクトから VT_CY 型の `_variant_t` オブジェクトを構築します。

- **_variant_t (_bstr_t &** `bstrSrc` **)** `_bstr_t` オブジェクトから VT_BSTR 型の `_variant_t` オブジェクトを構築します。 新しい `BSTR` を割り当てます。

- **_variant_t (wchar_t** <strong>\*</strong> *wstrsrc*  **)** Unicode 文字列から VT_BSTR 型の `_variant_t` オブジェクトを構築します。 新しい `BSTR` を割り当てます。

- **_variant_t (char** <strong>\*</strong>`strSrc` **)** 文字列から VT_BSTR 型の `_variant_t` オブジェクトを構築します。 新しい `BSTR` を割り当てます。

- **_variant_t (bool**`bSrc` **)** **ブール**値から VT_BOOL 型の `_variant_t` オブジェクトを構築します。

- **_variant_t (IUnknown** <strong>\*</strong>`pIUknownSrc` **、bool**`fAddRef` **= true)** COM インターフェイスポインターから VT_UNKNOWN 型の `_variant_t` オブジェクトを構築します。 `fAddRef` が**true**の場合、指定されたインターフェイスポインターで `AddRef` が呼び出され、`_variant_t` オブジェクトが破棄されるときに発生する `Release` への呼び出しに一致します。 指定されたインターフェイスポインターで `Release` を呼び出すことができます。 `fAddRef` が**false**の場合、このコンストラクターは、指定されたインターフェイスポインターの所有権を取得します。指定されたインターフェイスポインターで `Release` を呼び出さないでください。

- **_variant_t (IDispatch** <strong>\*</strong>`pDispSrc` **、bool**`fAddRef` **= true)** COM インターフェイスポインターから VT_DISPATCH 型の `_variant_t` オブジェクトを構築します。 `fAddRef` が**true**の場合、指定されたインターフェイスポインターで `AddRef` が呼び出され、`_variant_t` オブジェクトが破棄されるときに発生する `Release` への呼び出しに一致します。 指定されたインターフェイスポインターで `Release` を呼び出すことができます。 `fAddRef` が**false**の場合、このコンストラクターは、指定されたインターフェイスポインターの所有権を取得します。指定されたインターフェイスポインターで `Release` を呼び出さないでください。

- **_variant_t (DECIMAL &** `decSrc` **)** `DECIMAL` 値から VT_DECIMAL 型の `_variant_t` オブジェクトを構築します。

- **_variant_t (バイト**`bSrc` **)** `BYTE` 値から `VT_UI1` 型の `_variant_t` オブジェクトを構築します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_variant_t クラス](../cpp/variant-t-class.md)
