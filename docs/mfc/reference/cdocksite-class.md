---
title: CDockSite Class
ms.date: 10/18/2018
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
ms.openlocfilehash: ccd1bc115f92e0c2605fe5f587a0567f672c6c09
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259803"
---
# <a name="cdocksite-class"></a>CDockSite Class

詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。

[CPane Class](../../mfc/reference/cpane-class.md) から派生したペインを一連の行に配置する機能を提供します。

## <a name="syntax"></a>構文

```
class CDockSite: public CBasePane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDockSite::AddRow](#addrow)||
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(上書き[cbasepane::adjustdockinglayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout))。|
|[CDockSite::AdjustLayout](#adjustlayout)|(上書き[cbasepane::adjustlayout](../../mfc/reference/cbasepane-class.md#adjustlayout))。|
|[CDockSite::AlignDockSite](#aligndocksite)||
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(上書き[cbasepane::calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout))。|
|[CDockSite::CanAcceptPane](#canacceptpane)|(上書き[cbasepane::canacceptpane](../../mfc/reference/cbasepane-class.md#canacceptpane))。|
|[CDockSite::CreateEx](#createex)|(上書き[cbasepane::createex](../../mfc/reference/cbasepane-class.md#createex))。|
|[CDockSite::CreateRow](#createrow)||
|[CDockSite::DockPane](#dockpane)|(上書き[cbasepane::dockpane](../../mfc/reference/cbasepane-class.md#dockpane))。|
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(上書き[cbasepane::doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore))。|
|[CDockSite::FindRowIndex](#findrowindex)||
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||
|[CDockSite::GetDockSiteID](#getdocksiteid)||
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|(`CBasePane::IsAccessibilityCompatible` をオーバーライドします)。|
|[CDockSite::IsDragMode](#isdragmode)||
|[CDockSite::IsLastRow](#islastrow)||
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||
|[CDockSite::IsResizable](#isresizable)|(上書き[cbasepane::isresizable](../../mfc/reference/cbasepane-class.md#isresizable))。|
|[CDockSite::MovePane](#movepane)||
|[CDockSite::OnInsertRow](#oninsertrow)||
|[CDockSite::OnRemoveRow](#onremoverow)||
|[CDockSite::OnResizeRow](#onresizerow)||
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||
|[CDockSite::OnShowRow](#onshowrow)||
|[CDockSite::OnSizeParent](#onsizeparent)||
|[CDockSite::PaneFromPoint](#panefrompoint)|パラメーターによって指定された点にあるドッキング サイトにドッキングされているペインを返します。|
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|ペインを別のペインの左側にドッキングします。|
|[CDockSite::FindPaneByID](#findpanebyid)|指定された ID によって識別されるペインを返します。|
|[CDockSite::GetPaneList](#getpanelist)|ドッキング サイトにドッキングされているペインの一覧を返します。|
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||
|[CDockSite::RemovePane](#removepane)||
|[CDockSite::RemoveRow](#removerow)||
|[CDockSite::ReplacePane](#replacepane)||
|[CDockSite::RepositionPanes](#repositionpanes)||
|[CDockSite::ResizeDockSite](#resizedocksite)||
|[CDockSite::ResizeRow](#resizerow)||
|[CDockSite::ShowPane](#showpane)|ペインを表示します。|
|[CDockSite::ShowRow](#showrow)||
|[CDockSite::SwapRows](#swaprows)||

## <a name="remarks"></a>Remarks

フレームワークは作成`CDockSite`を呼び出すときに自動的にオブジェクト[cframewndex::enabledocking](../../mfc/reference/cframewndex-class.md#enabledocking)します。 ドッキング サイト ウィンドウは、メイン フレーム ウィンドウ上のクライアント領域の端に配置されます。

通常はしなかったために、ドッキング サイトによって提供されるサービスを呼び出す[CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)これらのサービスを処理します。

## <a name="example"></a>例

次の例では、`CDockSite` クラスのオブジェクトを作成する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxDockSite.h

##  <a name="addrow"></a>  CDockSite::AddRow

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

[in]*pos*<br/>

[in] *nHeight*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="adjustdockinglayout"></a>  CDockSite::AdjustDockingLayout

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>Remarks

##  <a name="adjustlayout"></a>  CDockSite::AdjustLayout

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>Remarks

##  <a name="aligndocksite"></a>  CDockSite::AlignDockSite

```
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>パラメーター

[in] *rectToAlignBy*<br/>

[in]*rectResult*<br/>

[in]*bMoveImmediately*<br/>

### <a name="remarks"></a>Remarks

##  <a name="calcfixedlayout"></a>  CDockSite::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

[in]*bStretch*<br/>

[in] *bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="canacceptpane"></a>  CDockSite::CanAcceptPane

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>パラメーター

[in]*pBar*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="createex"></a>  CDockSite::CreateEx

```
virtual BOOL CreateEx(
    DWORD dwStyleEx,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    DWORD dwControlBarStyle,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*dwStyleEx*<br/>

[in] *dwStyle*<br/>

[in]*rect*<br/>

[in] *pParentWnd*<br/>

[in] *dwControlBarStyle*<br/>

[in]*pContext*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="createrow"></a>  CDockSite::CreateRow

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>パラメーター

[in] *pParentDockBar*<br/>

[in]*nOffset*<br/>

[in] *nRowHeight*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="dockpane"></a>  CDockSite::DockPane

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*我が物*<br/>

[in]*dockMethod*<br/>

[in]*lpRect*<br/>

### <a name="remarks"></a>Remarks

##  <a name="dockpaneleftof"></a>  CDockSite::DockPaneLeftOf

ペインを別のペインの左側にドッキングします。

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>パラメーター

*pBarToDock*<br/>
[入力、出力]左側にドッキングするウィンドウへのポインター *pTargetBar*します。

*pTargetBar*<br/>
[入力、出力][ターゲット] ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

ウィンドウが正常にドッキングされている場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="doesallowdyninsertbefore"></a>  CDockSite::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="findpanebyid"></a>  CDockSite::FindPaneByID

その ID を持つペインを返します

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]検索する、ウィンドウのコマンド ID。

### <a name="return-value"></a>戻り値

指定したコマンド ID、または、ウィンドウが見つからない場合は NULL で、ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

##  <a name="findrowindex"></a>  CDockSite::FindRowIndex

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="fixupvirtualrects"></a>  CDockSite::FixupVirtualRects

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Remarks

##  <a name="getdocksiteid"></a>  CDockSite::GetDockSiteID

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getdocksiterowslist"></a>  CDockSite::GetDockSiteRowsList

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getpanelist"></a>  CDockSite::GetPaneList

ドッキング サイトにドッキングされているペインの一覧を返します。

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>戻り値

現在、ドッキング バーにドッキングされているペインの一覧への読み取り専用の参照。

##  <a name="isaccessibilitycompatible"></a>  CDockSite::IsAccessibilityCompatible

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="isdragmode"></a>  CDockSite::IsDragMode

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="islastrow"></a>  CDockSite::IsLastRow

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="isrectwithindocksite"></a>  CDockSite::IsRectWithinDockSite

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>パラメーター

[in]*rect*<br/>

[in]*ptDelta*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="isresizable"></a>  CDockSite::IsResizable

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="movepane"></a>  CDockSite::MovePane

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>パラメーター

[in]*我が物*<br/>

[in]*nFlags*<br/>

[in]*ptOffset*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="oninsertrow"></a>  CDockSite::OnInsertRow

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>パラメーター

[in]*pos*<br/>

### <a name="remarks"></a>Remarks

##  <a name="onremoverow"></a>  CDockSite::OnRemoveRow

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>パラメーター

[in]*pos*<br/>

[in] *bByShow*<br/>

### <a name="remarks"></a>Remarks

##  <a name="onresizerow"></a>  CDockSite::OnResizeRow

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>パラメーター

[in]*pRowToResize*<br/>

[in]*nOffset*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onsizeparent"></a>  CDockSite::OnSizeParent

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>パラメーター

[in] *rectAvailable*<br/>

[in]*nSide*<br/>

[in]*bExpand*<br/>

[in]*nOffset*<br/>

### <a name="remarks"></a>Remarks

##  <a name="onsetwindowpos"></a>  CDockSite::OnSetWindowPos

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

[in]*pWndInsertAfter*<br/>

[in]*rectWnd*<br/>

[in]*nFlags*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onshowrow"></a>  CDockSite::OnShowRow

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>パラメーター

[in]*pos*<br/>

[in]*bShow*<br/>

### <a name="remarks"></a>Remarks

##  <a name="panefrompoint"></a>  CDockSite::PaneFromPoint

パラメーターによって指定された点にあるドッキング サイトにドッキングされているペインを返します。

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
[in]取得するウィンドウの画面座標にポイントします。

### <a name="return-value"></a>戻り値

指定したポイントに存在するウィンドウがない場合は、指定した点または NULL にあるウィンドウへのポインター。

### <a name="remarks"></a>Remarks

##  <a name="rectsidefrompoint"></a>  CDockSite::RectSideFromPoint

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>パラメーター

[in]*rect*<br/>

[in]*ポイント*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="removepane"></a>  CDockSite::RemovePane

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>パラメーター

[in]*我が物*<br/>

[in]*dockMethod*<br/>

### <a name="remarks"></a>Remarks

##  <a name="removerow"></a>  CDockSite::RemoveRow

```
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

### <a name="remarks"></a>Remarks

##  <a name="replacepane"></a>  CDockSite::ReplacePane

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>パラメーター

[in] *pOldBar*<br/>

[in] *pNewBar*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="repositionpanes"></a>  CDockSite::RepositionPanes

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>パラメーター

[in] *rectNewClientArea*<br/>

### <a name="remarks"></a>Remarks

##  <a name="resizedocksite"></a>  CDockSite::ResizeDockSite

```
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>パラメーター

[in] *nNewWidth*<br/>

[in] *nNewHeight*<br/>

### <a name="remarks"></a>Remarks

##  <a name="resizerow"></a>  CDockSite::ResizeRow

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

[in] *nNewSize*<br/>

[in]*bAdjustLayout*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="showpane"></a>  CDockSite::ShowPane

ペインを表示します。

```
virtual BOOL ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
[入力、出力]表示/非表示するウィンドウへのポインター。

*bShow*<br/>
[in]ウィンドウを表示することを指定する場合は TRUEウィンドウを非表示にすることを指定する場合は FALSE。

*bDelay*<br/>
[in]ウィンドウが表示されます。 後に、ウィンドウのレイアウトがまで延期されることを指定する場合は TRUEそれ以外の場合、FALSE です。

*bActivate*<br/>
[in]このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

TRUE の場合は、ウィンドウが表示または非表示に正常にします。 指定したウィンドウがこのドッキング サイトに属していない場合は FALSE です。

### <a name="remarks"></a>Remarks

ドッキング ペインを非表示には、このメソッドを呼び出します。 通常、必要はありませんを呼び出す`CDockSite::ShowPane`直接、親フレーム ウィンドウまたは基本ウィンドウによって呼び出されるためです。

##  <a name="showrow"></a>  CDockSite::ShowRow

```
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

[in]*bShow*<br/>

[in]*bAdjustLayout*<br/>

### <a name="remarks"></a>Remarks

##  <a name="swaprows"></a>  CDockSite::SwapRows

```
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>パラメーター

[in] *pFirstRow*<br/>

[in] *pSecondRow*<br/>

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CBasePane クラス](../../mfc/reference/cbasepane-class.md)
