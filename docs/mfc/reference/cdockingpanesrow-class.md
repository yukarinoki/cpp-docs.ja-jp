---
title: CDockingPanesRow クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPane
- AFXDOCKINGPANESROW/CDockingPanesRow::AddPaneFromRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ArrangePanes
- AFXDOCKINGPANESROW/CDockingPanesRow::CalcFixedLayout
- AFXDOCKINGPANESROW/CDockingPanesRow::Create
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::ExpandStretchedPanesRect
- AFXDOCKINGPANESROW/CDockingPanesRow::FixupVirtualRects
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableLength
- AFXDOCKINGPANESROW/CDockingPanesRow::GetAvailableSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetClientRect
- AFXDOCKINGPANESROW/CDockingPanesRow::GetDockSite
- AFXDOCKINGPANESROW/CDockingPanesRow::GetExtraSpace
- AFXDOCKINGPANESROW/CDockingPanesRow::GetGroupFromPane
- AFXDOCKINGPANESROW/CDockingPanesRow::GetID
- AFXDOCKINGPANESROW/CDockingPanesRow::GetMaxPaneSize
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetPaneList
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowAlignment
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowHeight
- AFXDOCKINGPANESROW/CDockingPanesRow::GetRowOffset
- AFXDOCKINGPANESROW/CDockingPanesRow::GetVisibleCount
- AFXDOCKINGPANESROW/CDockingPanesRow::GetWindowRect
- AFXDOCKINGPANESROW/CDockingPanesRow::HasPane
- AFXDOCKINGPANESROW/CDockingPanesRow::IsEmpty
- AFXDOCKINGPANESROW/CDockingPanesRow::IsExclusiveRow
- AFXDOCKINGPANESROW/CDockingPanesRow::IsHorizontal
- AFXDOCKINGPANESROW/CDockingPanesRow::IsVisible
- AFXDOCKINGPANESROW/CDockingPanesRow::Move
- AFXDOCKINGPANESROW/CDockingPanesRow::MovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::OnResizePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RedrawAll
- AFXDOCKINGPANESROW/CDockingPanesRow::RemovePane
- AFXDOCKINGPANESROW/CDockingPanesRow::ReplacePane
- AFXDOCKINGPANESROW/CDockingPanesRow::RepositionPanes
- AFXDOCKINGPANESROW/CDockingPanesRow::Resize
- AFXDOCKINGPANESROW/CDockingPanesRow::ResizeByPaneDivider
- AFXDOCKINGPANESROW/CDockingPanesRow::ScreenToClient
- AFXDOCKINGPANESROW/CDockingPanesRow::SetExtra
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowDockSiteRow
- AFXDOCKINGPANESROW/CDockingPanesRow::ShowPane
- AFXDOCKINGPANESROW/CDockingPanesRow::UpdateVisibleState
dev_langs:
- C++
helpviewer_keywords:
- CDockingPanesRow [MFC], AddPane
- CDockingPanesRow [MFC], AddPaneFromRow
- CDockingPanesRow [MFC], ArrangePanes
- CDockingPanesRow [MFC], CalcFixedLayout
- CDockingPanesRow [MFC], Create
- CDockingPanesRow [MFC], ExpandStretchedPanes
- CDockingPanesRow [MFC], ExpandStretchedPanesRect
- CDockingPanesRow [MFC], FixupVirtualRects
- CDockingPanesRow [MFC], GetAvailableLength
- CDockingPanesRow [MFC], GetAvailableSpace
- CDockingPanesRow [MFC], GetClientRect
- CDockingPanesRow [MFC], GetDockSite
- CDockingPanesRow [MFC], GetExtraSpace
- CDockingPanesRow [MFC], GetGroupFromPane
- CDockingPanesRow [MFC], GetID
- CDockingPanesRow [MFC], GetMaxPaneSize
- CDockingPanesRow [MFC], GetPaneCount
- CDockingPanesRow [MFC], GetPaneList
- CDockingPanesRow [MFC], GetRowAlignment
- CDockingPanesRow [MFC], GetRowHeight
- CDockingPanesRow [MFC], GetRowOffset
- CDockingPanesRow [MFC], GetVisibleCount
- CDockingPanesRow [MFC], GetWindowRect
- CDockingPanesRow [MFC], HasPane
- CDockingPanesRow [MFC], IsEmpty
- CDockingPanesRow [MFC], IsExclusiveRow
- CDockingPanesRow [MFC], IsHorizontal
- CDockingPanesRow [MFC], IsVisible
- CDockingPanesRow [MFC], Move
- CDockingPanesRow [MFC], MovePane
- CDockingPanesRow [MFC], OnResizePane
- CDockingPanesRow [MFC], RedrawAll
- CDockingPanesRow [MFC], RemovePane
- CDockingPanesRow [MFC], ReplacePane
- CDockingPanesRow [MFC], RepositionPanes
- CDockingPanesRow [MFC], Resize
- CDockingPanesRow [MFC], ResizeByPaneDivider
- CDockingPanesRow [MFC], ScreenToClient
- CDockingPanesRow [MFC], SetExtra
- CDockingPanesRow [MFC], ShowDockSiteRow
- CDockingPanesRow [MFC], ShowPane
- CDockingPanesRow [MFC], UpdateVisibleState
ms.assetid: e7a17832-0ebb-4bce-b799-cec9b60f76fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a06fafc1c2aee472b7a2fa4701802ee8a53956ca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446271"
---
# <a name="cdockingpanesrow-class"></a>CDockingPanesRow クラス

ドッキング サイトの同じ水平または垂直の行 (列) に配置されるペインの一覧を管理します。

詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。

## <a name="syntax"></a>構文

```
class CDockingPanesRow : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CDockingPanesRow::CDockingPanesRow`|既定のコンストラクター|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDockingPanesRow::AddPane](#addpane)||
|[CDockingPanesRow::AddPaneFromRow](#addpanefromrow)||
|[CDockingPanesRow::ArrangePanes](#arrangepanes)|指定された余白および間隔のパラメーターに基づいてウィンドウを並べて整列します。|
|[CDockingPanesRow::CalcFixedLayout](#calcfixedlayout)||
|[CDockingPanesRow::Create](#create)||
|[CDockingPanesRow::ExpandStretchedPanes](#expandstretchedpanes)||
|[CDockingPanesRow::ExpandStretchedPanesRect](#expandstretchedpanesrect)||
|[CDockingPanesRow::FixupVirtualRects](#fixupvirtualrects)||
|[CDockingPanesRow::GetAvailableLength](#getavailablelength)||
|[CDockingPanesRow::GetAvailableSpace](#getavailablespace)||
|[CDockingPanesRow::GetClientRect](#getclientrect)||
|[CDockingPanesRow::GetDockSite](#getdocksite)||
|[CDockingPanesRow::GetExtraSpace](#getextraspace)||
|[CDockingPanesRow::GetGroupFromPane](#getgroupfrompane)||
|[CDockingPanesRow::GetID](#getid)||
|[CDockingPanesRow::GetMaxPaneSize](#getmaxpanesize)||
|[CDockingPanesRow::GetPaneCount](#getpanecount)||
|[CDockingPanesRow::GetPaneList](#getpanelist)||
|[CDockingPanesRow::GetRowAlignment](#getrowalignment)||
|[CDockingPanesRow::GetRowHeight](#getrowheight)||
|[CDockingPanesRow::GetRowOffset](#getrowoffset)||
|[CDockingPanesRow::GetVisibleCount](#getvisiblecount)||
|[CDockingPanesRow::GetWindowRect](#getwindowrect)||
|[CDockingPanesRow::HasPane](#haspane)||
|[CDockingPanesRow::IsEmpty](#isempty)||
|[CDockingPanesRow::IsExclusiveRow](#isexclusiverow)||
|[CDockingPanesRow::IsHorizontal](#ishorizontal)||
|[CDockingPanesRow::IsVisible](#isvisible)||
|[CDockingPanesRow::Move](#move)||
|[CDockingPanesRow::MovePane](#movepane)||
|[CDockingPanesRow::OnResizePane](#onresizepane)||
|[CDockingPanesRow::RedrawAll](#redrawall)||
|[CDockingPanesRow::RemovePane](#removepane)||
|[CDockingPanesRow::ReplacePane](#replacepane)||
|[CDockingPanesRow::RepositionPanes](#repositionpanes)||
|[CDockingPanesRow::Resize](#resize)||
|[CDockingPanesRow::ResizeByPaneDivider](#resizebypanedivider)||
|[CDockingPanesRow::ScreenToClient](#screentoclient)||
|[CDockingPanesRow::SetExtra](#setextra)||
|[CDockingPanesRow::ShowDockSiteRow](#showdocksiterow)||
|[CDockingPanesRow::ShowPane](#showpane)||
|[CDockingPanesRow::UpdateVisibleState](#updatevisiblestate)||

## <a name="remarks"></a>Remarks

`CDockingPanesRow` オブジェクトは、ドック サイト オブジェクトによって内部的に作成されます。

## <a name="example"></a>例

`CMFCAutoHideBar` オブジェクトから `CDockingPanesRow` オブジェクトを取得する方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cdockingpanesrow-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxDockingPanesRow.h

##  <a name="addpane"></a>  CDockingPanesRow::AddPane


```
virtual void AddPane(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL,
    BOOL bAddLast = FALSE);
```

### <a name="parameters"></a>パラメーター

*pControlBar*<br/>
[in][in]*dockMethod*
*lpRect*<br/>
[in][in]*bAddLast*

### <a name="remarks"></a>Remarks

##  <a name="addpanefromrow"></a>  CDockingPanesRow::AddPaneFromRow


```
virtual void AddPaneFromRow(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>パラメーター

*pControlBar*<br/>
[in][in]*dockMethod*

### <a name="remarks"></a>Remarks

##  <a name="arrangepanes"></a>  CDockingPanesRow::ArrangePanes

指定された余白に従って行でウィンドウのドッキングと間隔パラメーターを配置します。

```
virtual void ArrangePanes(
    int nMargin,
    int nSpacing);
```

### <a name="parameters"></a>パラメーター

*nMargin*<br/>
[in]行の左上隅から最初のウィンドウのピクセル単位のオフセットを指定します。

*nSpacing*<br/>
[in]ウィンドウのピクセル単位で間隔を指定します。

### <a name="remarks"></a>Remarks

行が、ドッキング ウィンドウを整列するには、このメソッドを呼び出します。 このメソッドを呼び出した後に呼び出す必要がある`CDockingPanesRow::FixupVirtualRects(FALSE, NULL)`します。

##  <a name="calcfixedlayout"></a>  CDockingPanesRow::CalcFixedLayout


```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*bStretch*<br/>
[in][in]*bHorz*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="cdockingpanesrow"></a>  CDockingPanesRow::CDockingPanesRow


```
CDockingPanesRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*pParentDockBar*<br/>
[in][in]*nOffset* [in]*パラメーター nHeight*

### <a name="remarks"></a>Remarks

##  <a name="create"></a>  CDockingPanesRow::Create


```
virtual BOOL Create();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="expandstretchedpanes"></a>  CDockingPanesRow::ExpandStretchedPanes


```
void ExpandStretchedPanes();
```

### <a name="remarks"></a>Remarks

##  <a name="expandstretchedpanesrect"></a>  CDockingPanesRow::ExpandStretchedPanesRect


```
void ExpandStretchedPanesRect();
```

### <a name="remarks"></a>Remarks

##  <a name="fixupvirtualrects"></a>  CDockingPanesRow::FixupVirtualRects


```
void FixupVirtualRects(
    bool bMoveBackToVirtualRect,
    CPane* pBarToExclude = NULL);
```

### <a name="parameters"></a>パラメーター

*bMoveBackToVirtualRect*<br/>
[in][in]*pBarToExclude*

### <a name="remarks"></a>Remarks

##  <a name="getavailablelength"></a>  CDockingPanesRow::GetAvailableLength


```
virtual int GetAvailableLength(BOOL bUseVirtualRect = FALSE) const;
```

### <a name="parameters"></a>パラメーター

[in]*bUseVirtualRect*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getavailablespace"></a>  CDockingPanesRow::GetAvailableSpace


```
virtual void GetAvailableSpace(CRect& rect);
```

### <a name="parameters"></a>パラメーター

[in]*rect*

### <a name="remarks"></a>Remarks

##  <a name="getclientrect"></a>  CDockingPanesRow::GetClientRect


```
void GetClientRect(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

[in]*rect*

### <a name="remarks"></a>Remarks

##  <a name="getdocksite"></a>  CDockingPanesRow::GetDockSite


```
CDockSite* GetDockSite() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getextraspace"></a>  CDockingPanesRow::GetExtraSpace


```
int GetExtraSpace() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getgroupfrompane"></a>  CDockingPanesRow::GetGroupFromPane


```
void GetGroupFromPane(
    CPane* pBar,
    CObList& lst);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
[in][in]*lst*

### <a name="remarks"></a>Remarks

##  <a name="getid"></a>  CDockingPanesRow::GetID


```
int GetID() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getmaxpanesize"></a>  CDockingPanesRow::GetMaxPaneSize


```
int GetMaxPaneSize(BOOL bSkipHiddenBars = TRUE) const;
```

### <a name="parameters"></a>パラメーター

[in]*bSkipHiddenBars*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getpanecount"></a>  CDockingPanesRow::GetPaneCount


```
int GetPaneCount() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getpanelist"></a>  CDockingPanesRow::GetPaneList


```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getrowalignment"></a>  CDockingPanesRow::GetRowAlignment


```
DWORD GetRowAlignment() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getrowheight"></a>  CDockingPanesRow::GetRowHeight


```
int GetRowHeight() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getrowoffset"></a>  CDockingPanesRow::GetRowOffset


```
int GetRowOffset() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getvisiblecount"></a>  CDockingPanesRow::GetVisibleCount


```
virtual int GetVisibleCount();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getwindowrect"></a>  CDockingPanesRow::GetWindowRect


```
void GetWindowRect(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

[in]*rect*

### <a name="remarks"></a>Remarks

##  <a name="haspane"></a>  CDockingPanesRow::HasPane


```
BOOL HasPane(CBasePane* pControlBar);
```

### <a name="parameters"></a>パラメーター

[in]*pControlBar*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="isempty"></a>  CDockingPanesRow::IsEmpty


```
virtual BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="isexclusiverow"></a>  CDockingPanesRow::IsExclusiveRow


```
virtual BOOL IsExclusiveRow() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="ishorizontal"></a>  CDockingPanesRow::IsHorizontal


```
bool IsHorizontal() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="isvisible"></a>  CDockingPanesRow::IsVisible


```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="move"></a>  CDockingPanesRow::Move


```
virtual void Move(int nOffset);
```

### <a name="parameters"></a>パラメーター

[in]*nOffset*

### <a name="remarks"></a>Remarks

##  <a name="movepane"></a>  CDockingPanesRow::MovePane


```
void MovePane(
    CPane* pControlBar,
    CPoint ptOffset,
    BOOL bSwapControlBars,
    HDWP& hdwp);


void MovePane(
    CPane* pControlBar,
    CRect rectTarget,
    HDWP& hdwp);


void MovePane(
    CPane* pControlBar,
    int nOffset,
    bool bForward,
    HDWP& hdwp);


void MovePane(
    CPane* pControlBar,
    int nAbsolutOffset,
    HDWP& hdwp);
```

### <a name="parameters"></a>パラメーター

*pControlBar*<br/>
[in][in]*ptOffset*
*bSwapControlBars*<br/>
[in][in]*hdwp*
*rectTarget*<br/>
[in][in]*nOffset*
*bForward*<br/>
[in][in]*nAbsolutOffset*

### <a name="remarks"></a>Remarks

##  <a name="onresizepane"></a>  CDockingPanesRow::OnResizePane


```
virtual void OnResizePane(CBasePane* pControlBar);
```

### <a name="parameters"></a>パラメーター

[in]*pControlBar*

### <a name="remarks"></a>Remarks

##  <a name="redrawall"></a>  CDockingPanesRow::RedrawAll


```
void RedrawAll();
```

### <a name="remarks"></a>Remarks

##  <a name="removepane"></a>  CDockingPanesRow::RemovePane


```
virtual void RemovePane(CPane* pControlBar);
```

### <a name="parameters"></a>パラメーター

[in]*pControlBar*

### <a name="remarks"></a>Remarks

##  <a name="replacepane"></a>  CDockingPanesRow::ReplacePane


```
virtual BOOL ReplacePane(
    CPane* pBarOld,
    CPane* pBarNew);
```

### <a name="parameters"></a>パラメーター

*pBarOld*<br/>
[in][in]*pBarNew*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="repositionpanes"></a>  CDockingPanesRow::RepositionPanes


```
virtual void RepositionPanes(
    CRect& rectNewParentBarArea,
    UINT nSide = (UINT)-1,
    BOOL bExpand = FALSE,
    int nOffset = 0);
```

### <a name="parameters"></a>パラメーター

*rectNewParentBarArea*<br/>
[in][in]*nSide*
*bExpand*<br/>
[in][in]*nOffset*

### <a name="remarks"></a>Remarks

##  <a name="resize"></a>  CDockingPanesRow::Resize


```
virtual int Resize(int nOffset);
```

### <a name="parameters"></a>パラメーター

[in]*nOffset*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="resizebypanedivider"></a>  CDockingPanesRow::ResizeByPaneDivider


```
virtual int ResizeByPaneDivider(int);
```

### <a name="parameters"></a>パラメーター

[in]*int*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="screentoclient"></a>  CDockingPanesRow::ScreenToClient


```
void ScreenToClient(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

[in]*rect*

### <a name="remarks"></a>Remarks

##  <a name="setextra"></a>  CDockingPanesRow::SetExtra


```
void SetExtra(
    int nExtraSpace,
    AFX_ROW_ALIGNMENT rowExtraAlign);
```

### <a name="parameters"></a>パラメーター

*nExtraSpace*<br/>
[in][in]*rowExtraAlign*

### <a name="remarks"></a>Remarks

##  <a name="showdocksiterow"></a>  CDockingPanesRow::ShowDockSiteRow


```
virtual void ShowDockSiteRow(
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
[in][in]*bDelay*

### <a name="remarks"></a>Remarks

##  <a name="showpane"></a>  CDockingPanesRow::ShowPane


```
virtual BOOL ShowPane(
    CPane* pControlBar,
    BOOL bShow,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>パラメーター

*pControlBar*<br/>
[in][in]*bShow* [in] *bDelay*

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="updatevisiblestate"></a>  CDockingPanesRow::UpdateVisibleState


```
virtual void UpdateVisibleState(BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

[in]*bDelay*

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[CDockSite クラス](../../mfc/reference/cdocksite-class.md)<br/>
[CPane クラス](../../mfc/reference/cpane-class.md)
