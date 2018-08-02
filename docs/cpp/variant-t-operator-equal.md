---
title: _variant_t::operator = |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d757c645ae131b88ffb99e571d1e08214eda8129
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462866"
---
# <a name="varianttoperator-"></a>_variant_t::operator =
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
  
## <a name="remarks"></a>Remarks  
 この演算子は、`_variant_t` オブジェクトに新しい値を代入します。  
  
-   **operator = (***varSrc***)** に既存`VARIANT`を`_variant_t`オブジェクト。  
  
-   **operator = (***pVarSrc***)** に既存`VARIANT`を`_variant_t`オブジェクト。  
  
-   **operator = (***var_t_Src***)** 既存`_variant_t`オブジェクトを`_variant_t`オブジェクト。      
  
-   **演算子 = (***sSrc***)** 割り当てます、**短い**整数値を`_variant_t`オブジェクト。  
  
-   **演算子 = (**`lSrc`**)** 割り当てます、**長い**整数値を`_variant_t`オブジェクト。  
  
-   **演算子 = (***fltSrc***)** 割り当てます、 **float**数値を`_variant_t`オブジェクト。  
  
-   **演算子 = (***dblSrc***)** 割り当てます、**二重**数値を`_variant_t`オブジェクト。  
  
-   **operator = (***cySrc***)** 割り当てます、`CY`オブジェクトを`_variant_t`オブジェクト。  
  
-   **operator = (***bstrSrc***)** 割り当てます、`BSTR`オブジェクトを`_variant_t`オブジェクト。  
  
-   **operator = (***wstrSrc***)** に Unicode 文字列を代入、`_variant_t`オブジェクト。  
  
-   **operator = (**`strSrc`**)** にマルチバイト文字列を代入、`_variant_t`オブジェクト。  
  
-   **operator = (** `bSrc` **)** 割り当てます、 **bool**値を`_variant_t`オブジェクト。  
  
-   **operator = (***pDispSrc***)** 割り当てます、`VT_DISPATCH`オブジェクトを`_variant_t`オブジェクト。  
  
-   **operator = (***pIUnknownSrc***)** 割り当てます、`VT_UNKNOWN`オブジェクトを`_variant_t`オブジェクト。  
  
-   **operator = (***decSrc***)** 割り当てます、`DECIMAL`値を`_variant_t`オブジェクト。  
  
-   **operator = (** `bSrc` **)** 割り当てます、`BYTE`値を`_variant_t`オブジェクト。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)