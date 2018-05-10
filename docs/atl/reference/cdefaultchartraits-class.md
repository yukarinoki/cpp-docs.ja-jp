---
title: CDefaultCharTraits クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24aa01ec29f063c1fa65ebe24c707deb1ea58556
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits クラス
このクラスは、大文字と小文字を変換するための 2 つの静的関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CDefaultCharTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDefaultCharTraits::CharToLower](#chartolower)|(静的)文字を大文字に変換するには、この関数を呼び出します。|  
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(静的)文字を小文字に変換するには、この関数を呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスには、クラスによって使用される関数[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="chartolower"></a>  CDefaultCharTraits::CharToLower  
 文字を小文字に変換するには、この関数を呼び出します。  
  
```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 小文字に変換する文字。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]  
  
##  <a name="chartoupper"></a>  CDefaultCharTraits::CharToUpper  
 文字を大文字に変換するには、この関数を呼び出します。  
  
```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 大文字に変換する文字。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
