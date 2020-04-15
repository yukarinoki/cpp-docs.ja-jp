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
ms.openlocfilehash: a95ee024d9df835102eeffc8443ae6225775aff7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375539"
---
# <a name="cdocksite-class"></a>CDockSite Class

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

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
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(CBase ペインをオーバーライド[します::調整ドッキングレイアウト](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|
|[CDockSite::AdjustLayout](#adjustlayout)|[(CBasePane をオーバーライドします::レイアウトを調整](../../mfc/reference/cbasepane-class.md#adjustlayout)します。|
|[CDockSite::AlignDockSite](#aligndocksite)||
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(CBase ペインをオーバーライド[します::計算固定レイアウト](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CDockSite::CanAcceptPane](#canacceptpane)|(CBase ペインをオーバーライド[します。.](../../mfc/reference/cbasepane-class.md#canacceptpane)|
|[CDockSite::CreateEx](#createex)|(CBasePane をオーバーライド[します。::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|
|[CDockSite::CreateRow](#createrow)||
|[CDockSite::DockPane](#dockpane)|[(CBasePane::DockPane](../../mfc/reference/cbasepane-class.md#dockpane).をオーバーライドします。|
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|[(CBase ペインをオーバーライドします::DoesAllowDynInsert前に](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CDockSite::FindRowIndex](#findrowindex)||
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||
|[CDockSite::GetDockSiteID](#getdocksiteid)||
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|( `CBasePane::IsAccessibilityCompatible`をオーバーライドします)。|
|[CDockSite::IsDragMode](#isdragmode)||
|[CDockSite::IsLastRow](#islastrow)||
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||
|[CDockSite::IsResizable](#isresizable)|[(CBasePane をオーバーライドします::IsResable](../../mfc/reference/cbasepane-class.md#isresizable).)|
|[CDockSite::MovePane](#movepane)||
|[CDockSite::OnInsertRow](#oninsertrow)||
|[CDockSite::OnRemoveRow](#onremoverow)||
|[CDockSite::OnResizeRow](#onresizerow)||
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||
|[CDockSite::OnShowRow](#onshowrow)||
|[CDockSite::OnSizeParent](#onsizeparent)||
|[CDockSite::PaneFromPoint](#panefrompoint)|パラメーターによって指定された点にあるドッキング サイトにドッキングされているペインを返します。|
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|ペインを別のペインの左側にドッキングします。|
|[クドックサイト::ペインバイIDを検索します](#findpanebyid)|指定された ID によって識別されるペインを返します。|
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

## <a name="remarks"></a>解説

フレームワークは`CDockSite`[、CFrameWndEx::有効化ドッキング](../../mfc/reference/cframewndex-class.md#enabledocking)を呼び出すと、オブジェクトを自動的に作成します。 ドッキング サイト ウィンドウは、メイン フレーム ウィンドウ上のクライアント領域の端に配置されます。

[CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)はこれらのサービスを処理するため、通常は、ドッキング サイトによって提供されるサービスを呼び出す必要はありません。

## <a name="example"></a>例

次の例では、`CDockSite` クラスのオブジェクトを作成する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[Cobject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdターゲット](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxDockSite.h

## <a name="cdocksiteaddrow"></a><a name="addrow"></a>クドックサイト::追加行

```
CDockingPanesRow* AddRow(
    POSITION pos,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

[in]*ポス*<br/>

[in]*nHeight*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CDockSite::調整ドッキングレイアウト

```
virtual void AdjustDockingLayout();
```

### <a name="remarks"></a>解説

## <a name="cdocksiteadjustlayout"></a><a name="adjustlayout"></a>CDockSite::レイアウトを調整する

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>解説

## <a name="cdocksitealigndocksite"></a><a name="aligndocksite"></a>クドックサイト::整列ドックサイト

```
void AlignDockSite(
    const CRect& rectToAlignBy,
    CRect& rectResult,
    BOOL bMoveImmediately);
```

### <a name="parameters"></a>パラメーター

[in]*レクト・アライン・バイ*<br/>

[in]*レクト結果*<br/>

[in]*すぐに移動します。*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksitecalcfixedlayout"></a><a name="calcfixedlayout"></a>CDockSite::計算固定レイアウト

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

[in]*bストレッチ*<br/>

[in]*bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitecanacceptpane"></a><a name="canacceptpane"></a>クドックサイト::缶アクセプドペイン

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitecreateex"></a><a name="createex"></a>クドックサイト::作成Ex

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

[in]*ドウスタイルエックス*<br/>

[in]*ドウスタイル*<br/>

[in]*レクト*<br/>

[in]*親子*<br/>

[in]*コントロール バースタイル*<br/>

[in]*コンテキスト*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitecreaterow"></a><a name="createrow"></a>クドックサイト::作成行

```
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nRowHeight);
```

### <a name="parameters"></a>パラメーター

[in]*親のドックバー*<br/>

[in]*オフセット*<br/>

[in]*行の高さ*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitedockpane"></a><a name="dockpane"></a>クドックサイト::Dオックペイン

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*pWnd*<br/>

[in]*ドックメソッド*<br/>

[in]*lpRect*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksitedockpaneleftof"></a><a name="dockpaneleftof"></a>クドックサイト::Dオックペイン左

ペインを別のペインの左側にドッキングします。

```
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[イン、アウト]*pTargetBar*の左側にドッキングするペインへのポインター。

*をクリックします。*<br/>
[イン、アウト]ターゲット ペインへのポインター。

### <a name="return-value"></a>戻り値

ペインが正常にドッキングされた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cdocksitedoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>前に挿入:DoesAllowDyn

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitefindpanebyid"></a><a name="findpanebyid"></a>クドックサイト::ペインバイIDを検索します

指定された ID を持つペインを返します。

```
CPane* FindPaneByID(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]見つかるペインのコマンド ID。

### <a name="return-value"></a>戻り値

指定したコマンド ID を持つペインへのポインター。

### <a name="remarks"></a>解説

## <a name="cdocksitefindrowindex"></a><a name="findrowindex"></a>クドックサイト::検索行インデックス

```
int FindRowIndex(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitefixupvirtualrects"></a><a name="fixupvirtualrects"></a>クドックサイト::フィックスアップバーチャルレクト

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>解説

## <a name="cdocksitegetdocksiteid"></a><a name="getdocksiteid"></a>クドックサイト::ゲットドックサイトID

```
virtual UINT GetDockSiteID() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitegetdocksiterowslist"></a><a name="getdocksiterowslist"></a>クドックサイト::ゲットドックサイトロウリスト

```
const CObList& GetDockSiteRowsList() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitegetpanelist"></a><a name="getpanelist"></a>クドックサイト::ゲットペインリスト

ドッキング サイトにドッキングされているペインの一覧を返します。

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>戻り値

ドッキング バーに現在ドッキングされているペインの一覧への読み取り専用参照。

## <a name="cdocksiteisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>クドックサイト::Isアクセシビリティ互換

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteisdragmode"></a><a name="isdragmode"></a>クドックサイト::イズドラモード

```
virtual BOOL IsDragMode() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteislastrow"></a><a name="islastrow"></a>クドックサイト::イズラストロウ

```
bool IsLastRow(CDockingPanesRow* pRow) const;
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteisrectwithindocksite"></a><a name="isrectwithindocksite"></a>クドックサイト::イレクト内部ドックサイト

```
BOOL IsRectWithinDockSite(
    CRect rect,
    CPoint& ptDelta);
```

### <a name="parameters"></a>パラメーター

[in]*レクト*<br/>

[in]*ptデルタ*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteisresizable"></a><a name="isresizable"></a>クドックサイト::イズサイズ可能

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksitemovepane"></a><a name="movepane"></a>CDockSite::移動ペイン

```
virtual BOOL MovePane(
    CPane* pWnd,
    UINT nFlags,
    CPoint ptOffset);
```

### <a name="parameters"></a>パラメーター

[in]*pWnd*<br/>

[in]*nフラグ*<br/>

[in]*ptオフセット*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteoninsertrow"></a><a name="oninsertrow"></a>クドックサイト::挿入行

```
virtual void OnInsertRow(POSITION pos);
```

### <a name="parameters"></a>パラメーター

[in]*ポス*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksiteonremoverow"></a><a name="onremoverow"></a>クドックサイト::オン除去ロー

```
virtual void OnRemoveRow(
    POSITION pos,
    BOOL bByShow = FALSE);
```

### <a name="parameters"></a>パラメーター

[in]*ポス*<br/>

[in]*ビビショー*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksiteonresizerow"></a><a name="onresizerow"></a>クドックサイト::オンリサイズロウ

```
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,
    int nOffset);
```

### <a name="parameters"></a>パラメーター

[in]*サイズを変更します。*<br/>

[in]*オフセット*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteonsizeparent"></a><a name="onsizeparent"></a>クドックサイト::オンサイズ親

```
virtual void OnSizeParent(
    CRect& rectAvailable,
    UINT nSide,
    BOOL bExpand,
    int nOffset);
```

### <a name="parameters"></a>パラメーター

[in]*利用可能なレクト*<br/>

[in]*nサイド*<br/>

[in]*展開する*<br/>

[in]*オフセット*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksiteonsetwindowpos"></a><a name="onsetwindowpos"></a>クドックサイト::オンセットウィンドウポス

```
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,
    const CRect& rectWnd,
    UINT nFlags);
```

### <a name="parameters"></a>パラメーター

[in]*後に挿入します。*<br/>

[in]*直腸*<br/>

[in]*nフラグ*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteonshowrow"></a><a name="onshowrow"></a>クドックサイト::オンショーロウ

```
virtual void OnShowRow(
    POSITION pos,
    BOOL bShow);
```

### <a name="parameters"></a>パラメーター

[in]*ポス*<br/>

[in]*bショー*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksitepanefrompoint"></a><a name="panefrompoint"></a>クドックサイト::Pアンネフロトポイント

パラメーターによって指定された点にあるドッキング サイトにドッキングされているペインを返します。

```
virtual CPane* PaneFromPoint(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
[in]ペインが取得するポイント (画面座標)。

### <a name="return-value"></a>戻り値

指定したポイントにペインが存在しない場合は NULL を指定した位置にあるペインへのポインター。

### <a name="remarks"></a>解説

## <a name="cdocksiterectsidefrompoint"></a><a name="rectsidefrompoint"></a>ドックサイト::レクトサイドソースポイント

```
static int __stdcall RectSideFromPoint(
    const CRect& rect,
    const CPoint& point);
```

### <a name="parameters"></a>パラメーター

[in]*レクト*<br/>

[in]*ポイント*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteremovepane"></a><a name="removepane"></a>クドックサイト::ウィンドウの削除

```
virtual void RemovePane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>パラメーター

[in]*pWnd*<br/>

[in]*ドックメソッド*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksiteremoverow"></a><a name="removerow"></a>クドックサイト::除去行

```
void RemoveRow(CDockingPanesRow* pRow);
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksitereplacepane"></a><a name="replacepane"></a>クドックサイト::交換ペイン

```
BOOL ReplacePane(
    CPane* pOldBar,
    CPane* pNewBar);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

[in]*をクリックします。*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiterepositionpanes"></a><a name="repositionpanes"></a>CDockSite::ペインの位置変更

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>パラメーター

[in]*レクトニュークライアントエリア*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksiteresizedocksite"></a><a name="resizedocksite"></a>クドックサイト::リサイズドックサイト

```
void ResizeDockSite(
    int nNewWidth,
    int nNewHeight);
```

### <a name="parameters"></a>パラメーター

[in]*n新しい幅*<br/>

[in]*nNewHeight*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksiteresizerow"></a><a name="resizerow"></a>クドックサイト::リサイズ行

```
int ResizeRow(
    CDockingPanesRow* pRow,
    int nNewSize,
    BOOL bAdjustLayout = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

[in]*nNewサイズ*<br/>

[in]*レイアウトを調整する*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdocksiteshowpane"></a><a name="showpane"></a>クドックサイト::ショーペイン

ペインを表示します。

```
virtual BOOL ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[イン、アウト]表示または非表示にするペインへのポインター。

*bショー*<br/>
[in]ペインを表示するように指定する場合は TRUE。ペインを非表示にすることを指定する場合は FALSE。

*bディレイ*<br/>
[in]ペインのレイアウトを、ペインが表示されるまで遅延するように指定する場合は TRUE。それ以外の場合は FALSE。

*bアクティブ化*<br/>
[in]このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

ウィンドウが正常に表示または非表示にされた場合は TRUE。 指定されたペインがこのドッキング サイトに属していない場合は FALSE。

### <a name="remarks"></a>解説

ドッキングペインの表示と非表示を切り替えます。 通常は、親フレーム ウィンドウまたはベース`CDockSite::ShowPane`ペインから呼び出されるため、直接呼び出す必要はありません。

## <a name="cdocksiteshowrow"></a><a name="showrow"></a>クドックサイト::ショーロウ

```
void ShowRow(
    CDockingPanesRow* pRow,
    BOOL bShow,
    BOOL bAdjustLayout);
```

### <a name="parameters"></a>パラメーター

[in]*pRow*<br/>

[in]*bショー*<br/>

[in]*レイアウトを調整する*<br/>

### <a name="remarks"></a>解説

## <a name="cdocksiteswaprows"></a><a name="swaprows"></a>クドックサイト::スワップ行

```
void SwapRows(
    CDockingPanesRow* pFirstRow,
    CDockingPanesRow* pSecondRow);
```

### <a name="parameters"></a>パラメーター

[in]*pファーストロー*<br/>

[in]*pセカンドロー*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[Cベースウィンドウクラス](../../mfc/reference/cbasepane-class.md)
