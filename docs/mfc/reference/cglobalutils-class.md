---
title: CGlobalUtils クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils::AdjustRectToWorkArea
- AFXGLOBALUTILS/CGlobalUtils::CalcExpectedDockedRect
- AFXGLOBALUTILS/CGlobalUtils::CanBeAttached
- AFXGLOBALUTILS/CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd
- AFXGLOBALUTILS/CGlobalUtils::CheckAlignment
- AFXGLOBALUTILS/CGlobalUtils::CyFromString
- AFXGLOBALUTILS/CGlobalUtils::DecimalFromString
- AFXGLOBALUTILS/CGlobalUtils::FlipRect
- AFXGLOBALUTILS/CGlobalUtils::ForceAdjustLayout
- AFXGLOBALUTILS/CGlobalUtils::GetDockingManager
- AFXGLOBALUTILS/CGlobalUtils::GetOppositeAlignment
- AFXGLOBALUTILS/CGlobalUtils::GetPaneAndAlignFromPoint
- AFXGLOBALUTILS/CGlobalUtils::GetWndIcon
- AFXGLOBALUTILS/CGlobalUtils::SetNewParent
- AFXGLOBALUTILS/CGlobalUtils::StringFromCy
- AFXGLOBALUTILS/CGlobalUtils::StringFromDecimal
dev_langs:
- C++
helpviewer_keywords:
- CGlobalUtils [MFC], AdjustRectToWorkArea
- CGlobalUtils [MFC], CalcExpectedDockedRect
- CGlobalUtils [MFC], CanBeAttached
- CGlobalUtils [MFC], CanPaneBeInFloatingMultiPaneFrameWnd
- CGlobalUtils [MFC], CheckAlignment
- CGlobalUtils [MFC], CyFromString
- CGlobalUtils [MFC], DecimalFromString
- CGlobalUtils [MFC], FlipRect
- CGlobalUtils [MFC], ForceAdjustLayout
- CGlobalUtils [MFC], GetDockingManager
- CGlobalUtils [MFC], GetOppositeAlignment
- CGlobalUtils [MFC], GetPaneAndAlignFromPoint
- CGlobalUtils [MFC], GetWndIcon
- CGlobalUtils [MFC], SetNewParent
- CGlobalUtils [MFC], StringFromCy
- CGlobalUtils [MFC], StringFromDecimal
ms.assetid: 2c5bd1a6-f80c-4e79-a476-b4ceebabfb2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50d5e2c1938a975da956502f3b071c8c51c6ad48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367478"
---
# <a name="cglobalutils-class"></a>CGlobalUtils クラス
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>構文  
  
```  
class CGlobalUtils  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CGlobalUtils::AdjustRectToWorkArea](#adjustrecttoworkarea)||  
|[CGlobalUtils::CalcExpectedDockedRect](#calcexpecteddockedrect)||  
|[CGlobalUtils::CanBeAttached](#canbeattached)||  
|[CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd](#canpanebeinfloatingmultipaneframewnd)||  
|[CGlobalUtils::CheckAlignment](#checkalignment)||  
|[CGlobalUtils::CyFromString](#cyfromstring)||  
|[CGlobalUtils::DecimalFromString](#decimalfromstring)||  
|[CGlobalUtils::FlipRect](#fliprect)||  
|[CGlobalUtils::ForceAdjustLayout](#forceadjustlayout)||  
|[CGlobalUtils::GetDockingManager](#getdockingmanager)||  
|[CGlobalUtils::GetOppositeAlignment](#getoppositealignment)||  
|[CGlobalUtils::GetPaneAndAlignFromPoint](#getpaneandalignfrompoint)||  
|[CGlobalUtils::GetWndIcon](#getwndicon)||  
|[CGlobalUtils::SetNewParent](#setnewparent)||  
|[CGlobalUtils::StringFromCy](#stringfromcy)||  
|[CGlobalUtils::StringFromDecimal](#stringfromdecimal)||  
  
## <a name="remarks"></a>コメント  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CGlobalUtils](../../mfc/reference/cglobalutils-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxglobalutils.h  
  
##  <a name="adjustrecttoworkarea"></a>  CGlobalUtils::AdjustRectToWorkArea  
  
```  
void AdjustRectToworkArea(
    CRect& rect,  
    CRect* pRectDelta = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `rect`  
 [入力] `pRectDelta`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="calcexpecteddockedrect"></a>  CGlobalUtils::CalcExpectedDockedRect  

  
```  
void CalcExpectedDockedRect(
    CPaneContainerManager& barContainerManager,  
    CWnd* pWndTodock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `barContainerManager`  
 [入力] `pWndTodock`  
 [入力] `ptMouse`  
 [出力] `rectResult`  
 [出力] `bDrawTab`  
 [出力] `ppTargetBar`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="canbeattached"></a>  CGlobalUtils::CanBeAttached  

  
```  
BOOL CanBeAttached(CWnd* pWnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="canpanebeinfloatingmultipaneframewnd"></a>  CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd  

  
```  
BOOL CanPaneBeInFloatingMultiPaneFrameWnd(CWnd* pWnd) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="checkalignment"></a>  CGlobalUtils::CheckAlignment  

  
```  
BOOL CheckAlignment(
    CPoint point,  
    CBasePane* pBar,  
    int nSensitivity,  
    const CDockingManager* pDockManager,  
    BOOL bOuterEdge,  
    DWORD& dwAlignment,  
    DWORD dwEnabledDockBars = CBRS_ALIGN_ANY,  
    LPCRECT lpRectBounds = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 [入力] `pBar`  
 [入力] `nSensitivity`  
 [入力] `pDockManager`  
 [入力] `bOuterEdge`  
 [出力] `dwAlignment`  
 [入力] `dwEnabledDockBars`  
 [入力] `lpRectBounds`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cyfromstring"></a>  CGlobalUtils::CyFromString  

  
```  
BOOL CyFromString(
    CY& cy,  
    LPCTSTR psz);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `cy`  
 [入力] `psz`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="decimalfromstring"></a>  CGlobalUtils::DecimalFromString  

  
```  
BOOL DecimalFromString(
    DECIMAL& decimal,  
    LPCTSTR psz);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `decimal`  
 [入力] `psz`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="fliprect"></a>  CGlobalUtils::FlipRect  

  
```  
void FlipRect(
    CRect& rect,  
    int nDegrees);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `rect`  
 [入力] `nDegrees`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="forceadjustlayout"></a>  CGlobalUtils::ForceAdjustLayout  

  
```  
void ForceAdjustLayout(
    CDockingManager* pDockManager,  
    BOOL bForce = FALSE,  
    BOOL bForceInvisible = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pDockManager`  
 [入力] `bForce`  
 [入力] `bForceInvisible`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdockingmanager"></a>  CGlobalUtils::GetDockingManager  

  
```  
CDockingManager* GetDockingManager(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getoppositealignment"></a>  CGlobalUtils::GetOppositeAlignment  

  
```  
DWORD GetOppositeAlignment(DWORD dwAlign);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlign`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getpaneandalignfrompoint"></a>  CGlobalUtils::GetPaneAndAlignFromPoint  

  
```  
BOOL GetPaneAndAlignFromPoint(
    CPaneContainerManager& barContainerManager,  
    CPoint pt,  
    CDockablePane** ppTargetControlBar,  
    DWORD& dwAlignment,  
    BOOL& bTabArea,  
    BOOL& bCaption);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `barContainerManager`  
 [入力] `pt`  
 [出力] `ppTargetControlBar`  
 [出力] `dwAlignment`  
 [出力] `bTabArea`  
 [出力] `bCaption`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getwndicon"></a>  CGlobalUtils::GetWndIcon  

  
```  
HICON GetWndIcon(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setnewparent"></a>  CGlobalUtils::SetNewParent  

  
```  
void SetNewParent(
    CObList& lstControlBars,  
    CWnd* pNewParent,  
    BOOL bCheckVisibility = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lstControlBars`  
 [入力] `pNewParent`  
 [入力] `bCheckVisibility`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="stringfromcy"></a>  CGlobalUtils::StringFromCy  

  
```  
BOOL StringFromCy(
    CString& str,  
    CY& cy);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `str`  
 [入力] `cy`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="stringfromdecimal"></a>  CGlobalUtils::StringFromDecimal  

  
```  
BOOL StringFromDecimal(
    CString& str,  
    DECIMAL& decimal);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `str`  
 [入力] `decimal`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
