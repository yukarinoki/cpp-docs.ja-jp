---
description: '詳細情報: CGlobalUtils クラス'
title: CGlobalUtils クラス
ms.date: 10/18/2018
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
ms.openlocfilehash: d1e2f096825d34a907afbcdb022c550b94476906
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184102"
---
# <a name="cglobalutils-class"></a>CGlobalUtils クラス

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

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

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

[CGlobalUtils](../../mfc/reference/cglobalutils-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxglobalutils

## <a name="cglobalutilsadjustrecttoworkarea"></a><a name="adjustrecttoworkarea"></a> CGlobalUtils:: AdjustRectToWorkArea

```cpp
void AdjustRectToworkArea(
    CRect& rect,
    CRect* pRectDelta = NULL);
```

### <a name="parameters"></a>パラメーター

[入力、出力] *rect*<br/>
から *Prectdelta*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilscalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a> CGlobalUtils:: CalcExpectedDockedRect

```cpp
void CalcExpectedDockedRect(
    CPaneContainerManager& barContainerManager,
    CWnd* pWndTodock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>パラメーター

から *barContainerManager*<br/>

から *pWndTodock*<br/>

から *Ptmouse*<br/>

入出力 *rectResult*<br/>

入出力 *[Bdrawtab タブ*<br/>

入出力 *Pptargetbar*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilscanbeattached"></a><a name="canbeattached"></a> CGlobalUtils:: CanBeAttached

```
BOOL CanBeAttached(CWnd* pWnd) const;
```

### <a name="parameters"></a>パラメーター

から *pWnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilscanpanebeinfloatingmultipaneframewnd"></a><a name="canpanebeinfloatingmultipaneframewnd"></a> CGlobalUtils:: CanPaneBeInFloatingMultiPaneFrameWnd

```
BOOL CanPaneBeInFloatingMultiPaneFrameWnd(CWnd* pWnd) const;
```

### <a name="parameters"></a>パラメーター

から *pWnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilscheckalignment"></a><a name="checkalignment"></a> CGlobalUtils:: CheckAlignment

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

から *ポイント*<br/>

から *Pbar*<br/>

から *Nsensitivity*<br/>

から *pDockManager*<br/>

から *Bouteredge*<br/>

入出力 *dwAlignment*<br/>

から *dwEnabledDockBars*<br/>

から *lpRectBounds*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilscyfromstring"></a><a name="cyfromstring"></a> CGlobalUtils:: CyFromString

```
BOOL CyFromString(
    CY& cy,
    LPCTSTR psz);
```

### <a name="parameters"></a>パラメーター

入出力 *cy*<br/>

から *psz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsdecimalfromstring"></a><a name="decimalfromstring"></a> CGlobalUtils::D ecimalFromString

```
BOOL DecimalFromString(
    DECIMAL& decimal,
    LPCTSTR psz);
```

### <a name="parameters"></a>パラメーター

入出力 *10 進数*<br/>

から *psz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsfliprect"></a><a name="fliprect"></a> CGlobalUtils:: FlipRect

```cpp
void FlipRect(
    CRect& rect,
    int nDegrees);
```

### <a name="parameters"></a>パラメーター

[入力、出力] *rect*<br/>
から *Ndegrees*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilsforceadjustlayout"></a><a name="forceadjustlayout"></a> CGlobalUtils:: ForceAdjustLayout

```cpp
void ForceAdjustLayout(
    CDockingManager* pDockManager,
    BOOL bForce = FALSE,
    BOOL bForceInvisible = FALSE);
```

### <a name="parameters"></a>パラメーター

[入力、出力] *pDockManager*<br/>

から *Bforce*<br/>

から *Bforceinvisible*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilsgetdockingmanager"></a><a name="getdockingmanager"></a> CGlobalUtils:: Getdoc王国マネージャー

```
CDockingManager* GetDockingManager(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

から *pWnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsgetoppositealignment"></a><a name="getoppositealignment"></a> CGlobalUtils:: GetOppositeAlignment

```
DWORD GetOppositeAlignment(DWORD dwAlign);
```

### <a name="parameters"></a>パラメーター

から *Dwalign*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsgetpaneandalignfrompoint"></a><a name="getpaneandalignfrompoint"></a> CGlobalUtils:: GetPaneAndAlignFromPoint

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

から *barContainerManager*<br/>

から *pt*<br/>

入出力 *ppTargetControlBar*<br/>

入出力 *dwAlignment*<br/>

入出力 *Btabarea*<br/>

入出力 *Bcaption*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsgetwndicon"></a><a name="getwndicon"></a> CGlobalUtils:: GetWndIcon

```
HICON GetWndIcon(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

から *pWnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilssetnewparent"></a><a name="setnewparent"></a> CGlobalUtils:: SetNewParent

```cpp
void SetNewParent(
    CObList& lstControlBars,
    CWnd* pNewParent,
    BOOL bCheckVisibility = TRUE);
```

### <a name="parameters"></a>パラメーター

から *lstControlBars*<br/>

から *Pnewparent*<br/>

から *Bcheckvisibility*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilsstringfromcy"></a><a name="stringfromcy"></a> CGlobalUtils:: StringFromCy

```
BOOL StringFromCy(
    CString& str,
    CY& cy);
```

### <a name="parameters"></a>パラメーター

入出力 *str*<br/>

から *cy*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsstringfromdecimal"></a><a name="stringfromdecimal"></a> CGlobalUtils:: StringFromDecimal

```
BOOL StringFromDecimal(
    CString& str,
    DECIMAL& decimal);
```

### <a name="parameters"></a>パラメーター

入出力 *str*<br/>

から *10 進数*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
