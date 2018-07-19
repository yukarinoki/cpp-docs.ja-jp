---
title: CMFCDragFrameImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDragFrameImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 458288ecff0b457205ba1735494ad8106c3feae7
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040949"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpl クラス
`CMFCDragFrameImpl`クラスは、ユーザーが標準ドッキング モードのペインをドラッグしたときに表示されるドラッグ四角形を描画します。  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
   
## <a name="syntax"></a>構文  
  
```  
class CMFCDragFrameImpl  
```  
  
## <a name="remarks"></a>Remarks  
 このクラスのオブジェクトがそれぞれに埋め込まれた[CPane クラス](../../mfc/reference/cpane-class.md)オブジェクト。 したがって、されるそれぞれのウィンドウを使用して、`CanFloat`メソッドが、ユーザーがドラッグしたときに、ドラッグ四角形を表示します。  
  
 使用してドラッグ四角形の幅を制御できます[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat)と[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdragframeimpl.h  
  
##  <a name="enddrawdragframe"></a>  CMFCDragFrameImpl::EndDrawDragFrame  

  
```  
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bClearInternalRects*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="init"></a>  CMFCDragFrameImpl::Init  

  
```  
void Init(CWnd* pDraggedWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDraggedWnd*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="movedragframe"></a>  CMFCDragFrameImpl::MoveDragFrame  

  
```  
void MoveDragFrame(BOOL bForceMove = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bForceMove*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="placetabpredocking"></a>  CMFCDragFrameImpl::PlaceTabPreDocking  

  
```  
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,  
    BOOL bFirstTime);  
  
void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pTabbedBar*  
 [in]*bFirstTime*  
 [in]*pCBarToPlaceOn*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="removetabpredocking"></a>  CMFCDragFrameImpl::RemoveTabPreDocking  

  
```  
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pOldTargetBar*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="resetstate"></a>  CMFCDragFrameImpl::ResetState  

  
```  
void ResetState();
```  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane クラス](../../mfc/reference/cpane-class.md)