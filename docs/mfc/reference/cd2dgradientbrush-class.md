---
title: CD2DGradientBrush クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
dev_langs:
- C++
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e479c156967addc7add8f048d2ef1c3abab0dd8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956234"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush クラス
CD2DLinearGradientBrush および CD2DRadialGradientBrush クラスの基底クラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|CD2DGradientBrush オブジェクトを構築します。|  
|[CD2DGradientBrush:: ~ CD2DGradientBrush](#cd2dgradientbrush__~cd2dgradientbrush)|デストラクターです。 D2D グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGradientBrush::Destroy](#destroy)|CD2DGradientBrush オブジェクトを破棄します。 (上書き[CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy))。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP 構造体の配列。|  
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|グラデーション境界間の補間を実行する色で領域です。|  
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|[0, 1] の正規化された範囲外のグラデーションの動作です。|  
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|D2D1_GRADIENT_STOP 構造体の配列へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DGradientBrush`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgradientbrush"></a>  CD2DGradientBrush:: ~ CD2DGradientBrush  
 デストラクターです。 D2D グラデーション ブラシ オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DGradientBrush();
```  
  
##  <a name="cd2dgradientbrush"></a>  CD2DGradientBrush::CD2DGradientBrush  
 CD2DGradientBrush オブジェクトを構築します。  
  
```  
CD2DGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,  
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentTarget*  
 レンダー ターゲットへのポインター。  
  
 *gradientStops*  
 D2D1_GRADIENT_STOP 構造体の配列へのポインター。  
  
 *gradientStopsCount*  
 大きいか gradientStops 配列でグラデーション境界の数を示す 1 に等しい値です。  
  
 *colorInterpolationGamma*  
 グラデーション境界間の補間を実行する色で領域です。  
  
 *オン*  
 [0, 1] の正規化された範囲外のグラデーションの動作です。  
  
 *pBrushProperties*  
 不透明度およびブラシの変換へのポインター。  
  
 *bAutoDestroy*  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="destroy"></a>  CD2DGradientBrush::Destroy  
 CD2DGradientBrush オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="m_argradientstops"></a>  CD2DGradientBrush::m_arGradientStops  
 D2D1_GRADIENT_STOP 構造体の配列。  
  
```  
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;  
```  
  
##  <a name="m_colorinterpolationgamma"></a>  CD2DGradientBrush::m_colorInterpolationGamma  
 グラデーション境界間の補間を実行する色で領域です。  
  
```  
D2D1_GAMMA m_colorInterpolationGamma;  
```  
  
##  <a name="m_extendmode"></a>  CD2DGradientBrush::m_extendMode  
 [0, 1] の正規化された範囲外のグラデーションの動作です。  
  
```  
D2D1_EXTEND_MODE m_extendMode;  
```  
  
##  <a name="m_pgradientstops"></a>  CD2DGradientBrush::m_pGradientStops  
 D2D1_GRADIENT_STOP 構造体の配列へのポインター。  
  
```  
ID2D1GradientStopCollection* m_pGradientStops;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
