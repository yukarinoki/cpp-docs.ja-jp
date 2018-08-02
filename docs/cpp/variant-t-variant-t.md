---
title: _variant_t::_variant_t |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4ef7551047449167ff60372da146618fbdc4e564
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464163"
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t
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
 *varSrc*  
 新しい `VARIANT` オブジェクトにコピーされる `_variant_t` オブジェクト。  
  
 *pVarSrc*  
 ポインターを`VARIANT`新しいにコピーされるオブジェクト`_variant_t`オブジェクト。  
  
 *var_t_Src*  
 新しい `_variant_t` オブジェクトにコピーされる `_variant_t` オブジェクト。  
  
 *fCopy*  
 場合**false**、指定された`VARIANT`を新しいオブジェクトがアタッチされる`_variant_t`オブジェクトでの新しいコピーを作成せず`VariantCopy`します。  
  
 *ISrc、sSrc*  
 新しい `_variant_t` オブジェクトにコピーされる整数値。  
  
 *vtSrc*  
 `VARTYPE`新しい`_variant_t`オブジェクト。  
  
 *fltSrc、dblSrc*  
 新しい `_variant_t` オブジェクトにコピーされる数値。  
  
 *cySrc*  
 新しい `CY` オブジェクトにコピーされる `_variant_t` オブジェクト。  
  
 *bstrSrc*  
 新しい `_bstr_t` オブジェクトにコピーされる `_variant_t` オブジェクト。  
  
 *strSrc、wstrSrc*  
 新しい `_variant_t` オブジェクトにコピーされる文字列。  
  
 *bSrc*  
 A **bool**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *pIUknownSrc*  
 新しいにカプセル化 VT_UNKNOWN オブジェクトへの COM インターフェイス ポインター`_variant_t`オブジェクト。  
  
 *pDispSrc*  
 新しいにカプセル化 VT_DISPATCH オブジェクトへの COM インターフェイス ポインター`_variant_t`オブジェクト。  
  
 *decSrc*  
 新しい `DECIMAL` オブジェクトにコピーされる `_variant_t` 値。  
  
 *bSrc*  
 新しい `BYTE` オブジェクトにコピーされる `_variant_t` 値。  
  
 *cSrc*  
 A **char**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *usSrc*  
 A **unsigned short**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *ulSrc*  
 A **unsigned long**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *iSrc*  
 **Int**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *uiSrc*  
 **符号なし int**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *i8Src*  
 **_ _Int64**新しいにコピーされる値`_variant_t`オブジェクト。  
  
 *ui8Src*  
 **符号なし _ _int64**新しいにコピーされる値`_variant_t`オブジェクト。  
  
## <a name="remarks"></a>Remarks  
  
-   **_variant_t ()** 空を構築します`_variant_t`オブジェクト、`VT_EMPTY`します。  
  
-   **_variant_t (VARIANT &***varSrc***)** を構築、`_variant_t`オブジェクトのコピーから、`VARIANT`オブジェクト。     バリアント型は保持されます。  
  
-   **_variant_t (VARIANT\****pVarSrc***)** を構築、`_variant_t`オブジェクトのコピーから、`VARIANT`オブジェクト。     バリアント型は保持されます。  
  
-   **_variant_t( _variant_t&**  *var_t_Src*  **)** Constructs a `_variant_t` object from another `_variant_t` object. バリアント型は保持されます。  
  
-   **_variant_t (VARIANT &***varSrc* **、bool**`fCopy`**)** を構築、`_variant_t`既存のオブジェクト`VARIANT`オブジェクト。       場合*fCopy*は**false**、**バリアント**オブジェクトは、コピーを作成せず、新しいオブジェクトにアタッチされています。  
  
-   **_variant_t (short***sSrc* **、VARTYPE**`vtSrc`**= VT_I2)** を構築、 `_variant_t` からVT_I2またはVT_BOOLの型のオブジェクト**短い**整数値。       その他の`VARTYPE`E_INVALIDARG エラーが発生します。  
  
-   **_variant_t (long** `lSrc` **、VARTYPE**`vtSrc`**= VT_I4)** を構築、 `_variant_t` VT_I4、VT_BOOL、またはから VT_ERROR 型のオブジェクトを**長**整数値。       その他の`VARTYPE`E_INVALIDARG エラーが発生します。  
  
-   **_variant_t (float**`fltSrc`**)** を構築します、 `_variant_t` VT_R4 からの型のオブジェクトを**float**数値を指定します。      
  
-   **_variant_t (double** `dblSrc` **、VARTYPE**`vtSrc`**= VT_R8)** を構築、 `_variant_t` VT_R8 または VT_DATE から型のオブジェクトを**倍**数値を指定します。       その他の`VARTYPE`E_INVALIDARG エラーが発生します。  
  
-   **_variant_t (CY &**`cySrc`**)** を構築、 `_variant_t` VT_CY からの型のオブジェクトを`CY`オブジェクト。      
  
-   **_variant_t (_bstr_t &**`bstrSrc`**)** を構築、 `_variant_t` VT_BSTR からの型のオブジェクトを`_bstr_t`オブジェクト。     新しい `BSTR` を割り当てます。  
  
-   **_variant_t (wchar_t \***  *wstrSrc***)** を構築、`_variant_t`型 VT_BSTR Unicode 文字列からのオブジェクト。   新しい `BSTR` を割り当てます。  
  
-   **_variant_t (char\***`strSrc`**)** を構築、`_variant_t`型 VT_BSTR 文字列からのオブジェクト。     新しい `BSTR` を割り当てます。  
  
-   **_variant_t (bool**`bSrc`**)** を構築、 `_variant_t` VT_BOOL からの型のオブジェクトを**bool**値。      
  
-   **_variant_t (IUnknown\***  `pIUknownSrc` **、bool**`fAddRef`**= true)** を構築、 `_variant_t` VT_UNKNOWN の COM インターフェイス ポインターから型のオブジェクト.       場合`fAddRef`は**true**、し`AddRef`への呼び出しが一致するように指定されたインターフェイス ポインターで呼び出される`Release`が発生するときに、`_variant_t`オブジェクトは破棄されます。 呼び出すかどうかは`Release`で指定されたインターフェイス ポインター。 場合`fAddRef`は**false**、このコンス トラクターは、指定されたインターフェイス ポインターの所有権を受け取ります。 呼び出さない`Release`で指定されたインターフェイス ポインター。  
  
-   **_variant_t (IDispatch\***  `pDispSrc` **、bool**`fAddRef`**= true)** を構築、`_variant_t`型が VT_DISPATCH COM インターフェイスからのオブジェクトポインター。       場合`fAddRef`は**true**、し`AddRef`への呼び出しが一致するように指定されたインターフェイス ポインターで呼び出される`Release`が発生するときに、`_variant_t`オブジェクトは破棄されます。 呼び出すかどうかは`Release`で指定されたインターフェイス ポインター。 場合`fAddRef`は**false**、このコンス トラクターは、指定されたインターフェイス ポインターの所有権を受け取ります。 呼び出さない`Release`で指定されたインターフェイス ポインター。  
  
-   **_variant_t (10 進数 (& a)**`decSrc`**)** を構築、 `_variant_t` VT_DECIMAL からの型のオブジェクトを`DECIMAL`値。      
  
-   **_variant_t (バイト**`bSrc`**)** を構築、`_variant_t`型のオブジェクト`VT_UI1`から、`BYTE`値。      
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)