---
title: ピクセル HIMETRIC 変換のグローバル関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92d84204bdf02e75f1baf64bd52d96eab0b3d271
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359427"
---
# <a name="pixelhimetric-conversion-global-functions"></a>ピクセル/HIMETRIC 変換のグローバル関数
これらの関数は、ピクセルと HIMETRIC 単位に変換するためのサポートを提供します。  
  
> [!IMPORTANT]
>  次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC 単位 (各単位は 0.01 ミリメートル) をピクセル単位に変換します。|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|HIMETRIC 単位 (ピクセル) に変換します (各単位は 0.01 ミリメートル)。|  
  
##  <a name="atlhimetrictopixel"></a>  AtlHiMetricToPixel  
 HIMETRIC 単位 (各単位は 0.01 mm) のオブジェクトのサイズを画面デバイス上のピクセル単位のサイズに変換します。  
  
 
```
extern void AtlHiMetricToPixel(
  const SIZEL* lpSizeInHiMetric, 
  LPSIZEL lpSizeInPix);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSizeInHiMetric`  
 [in]HIMETRIC 単位内のオブジェクトのサイズへのポインター。  
  
 `lpSizeInPix`  
 [out]オブジェクトのサイズ (ピクセル単位) が返されるへのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="atlpixeltohimetric"></a>  AtlPixelToHiMetric  
 画面デバイス上のピクセル単位のオブジェクトのサイズを HIMETRIC 単位 (各単位は 0.01 mm) のサイズに変換します。  
  
```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix, 
    LPSIZEL lpSizeInHiMetric);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSizeInPix`  
 [in]オブジェクトのサイズ (ピクセル単位) へのポインター。  
  
 `lpSizeInHiMetric`  
 [out]オブジェクトのサイズを HIMETRIC 単位が返されるへのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
