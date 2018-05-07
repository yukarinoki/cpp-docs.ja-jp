---
title: CD2DPointU クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91496e96763ab8c79ae1c71d68b9ae8f8db15e50
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dpointu-class"></a>CD2DPointU クラス
`D2D1_POINT_2U`のラッパー。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DPointU : public D2D1_POINT_2U;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPointU::CD2DPointU](#cd2dpointu)|オーバーロードされます。 構築、`CD2DPointU`オブジェクトから`D2D1_POINT_2U`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DPointU::operator CPoint](#operator_cpoint)|変換`CD2DPointU`に`CPoint`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `D2D1_POINT_2U`  
  
 `CD2DPointU`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU  
 CPoint オブジェクトから CD2DPointU オブジェクトを構築します。  
  
```  
CD2DPointU(const CPoint& pt);  
CD2DPointU(const D2D1_POINT_2U& pt);  
  CD2DPointU(const D2D1_POINT_2U* pt);  
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 ソース ポイント  
  
 `uX`  
 ソース X  
  
 `uY`  
 ソース Y  
  
##  <a name="operator_cpoint"></a>  CD2DPointU::operator CPoint  
 CD2DPointU を CPoint オブジェクトに変換します。  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>戻り値  
 D2D ポイントの現在の値。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
