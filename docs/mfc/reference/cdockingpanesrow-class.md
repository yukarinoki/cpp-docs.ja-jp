---
title: クラスをドッキングします。
ms.date: 10/18/2018
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
ms.openlocfilehash: d7535ae6c5246a372fd1a48573716bb166991d4e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753316"
---
# <a name="cdockingpanesrow-class"></a>クラスをドッキングします。

ドッキング サイトの同じ水平または垂直の行 (列) に配置されるペインの一覧を管理します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CDockingPanesRow : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CDockingPanesRow::CDockingPanesRow`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDockingPanesRow::AddPane](#addpane)||
|[CDockingPanesRow::AddPaneFromRow](#addpanefromrow)||
|[チャッキングペインズロウ::整列ペイン](#arrangepanes)|指定された余白および間隔のパラメーターに基づいてウィンドウを並べて整列します。|
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

## <a name="remarks"></a>解説

`CDockingPanesRow` オブジェクトは、ドック サイト オブジェクトによって内部的に作成されます。

## <a name="example"></a>例

`CMFCAutoHideBar` オブジェクトから `CDockingPanesRow` オブジェクトを取得する方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cdockingpanesrow-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxDockingペインズロウ.h

## <a name="cdockingpanesrowaddpane"></a><a name="addpane"></a>CDockingPanesRow::ペインの追加

```
virtual void AddPane(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod,
    LPCRECT lpRect = NULL,
    BOOL bAddLast = FALSE);
```

### <a name="parameters"></a>パラメーター

[in]*コントロールバー*<br/>

[in]*ドックメソッド*<br/>

[in]*lpRect*<br/>

[in]*ラストを追加する*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowaddpanefromrow"></a><a name="addpanefromrow"></a>CDockingPanesRow::ペインの一行を追加します

```
virtual void AddPaneFromRow(
    CPane* pControlBar,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>パラメーター

[in]*コントロールバー*<br/>

[in]*ドックメソッド*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowarrangepanes"></a><a name="arrangepanes"></a>チャッキングペインズロウ::整列ペイン

指定した余白と間隔のパラメータに従って、ドッキング ペインを行に配置します。

```
virtual void ArrangePanes(
    int nMargin,
    int nSpacing);
```

### <a name="parameters"></a>パラメーター

*nマージン*<br/>
[in]行の左上隅からの最初のペインのオフセットをピクセル単位で指定します。

*n間隔*<br/>
[in]ペイン間の間隔をピクセル単位で指定します。

### <a name="remarks"></a>解説

ドッキングする行のペインを配置します。 このメソッドを呼び出した後`CDockingPanesRow::FixupVirtualRects(FALSE, NULL)`、 を呼び出す必要があります。

## <a name="cdockingpanesrowcalcfixedlayout"></a><a name="calcfixedlayout"></a>チャッキングペインズロウ::計算式レイアウト

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

## <a name="cdockingpanesrowcdockingpanesrow"></a><a name="cdockingpanesrow"></a>クッキングペインズロウ::Cドッキングペインズロウ

```
CDockingPanesRow(
    CDockSite* pParentDockBar,
    int nOffset,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

[in]*親のドックバー*<br/>

[in]*オフセット*<br/>

[in]*nHeight*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowcreate"></a><a name="create"></a>チャッキングペインズロウ::作成

```
virtual BOOL Create();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowexpandstretchedpanes"></a><a name="expandstretchedpanes"></a>CDockingPanesRow::拡張ストレッチペイン

```cpp
void ExpandStretchedPanes();
```

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowexpandstretchedpanesrect"></a><a name="expandstretchedpanesrect"></a>CDockingPanesRow::拡張ストレッチペインズレクト

```cpp
void ExpandStretchedPanesRect();
```

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowfixupvirtualrects"></a><a name="fixupvirtualrects"></a>クドックペインズロウ::フィクスアップバーチャルレクト

```cpp
void FixupVirtualRects(
    bool bMoveBackToVirtualRect,
    CPane* pBarToExclude = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*仮想レクトに戻る*<br/>

[in]*を除外します。*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetavailablelength"></a><a name="getavailablelength"></a>クドックペインズロウ::取得利用可能な長さ

```
virtual int GetAvailableLength(BOOL bUseVirtualRect = FALSE) const;
```

### <a name="parameters"></a>パラメーター

[in]*バーチャルレクトを使用します。*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetavailablespace"></a><a name="getavailablespace"></a>クドックペインズロウ::ゲット利用可能なスペース

```
virtual void GetAvailableSpace(CRect& rect);
```

### <a name="parameters"></a>パラメーター

[in]*レクト*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetclientrect"></a><a name="getclientrect"></a>クドックペインズロウ::Getクライアントレクト

```cpp
void GetClientRect(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

[in]*レクト*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetdocksite"></a><a name="getdocksite"></a>クドックペインズロウ::ゲットドックサイト

```
CDockSite* GetDockSite() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetextraspace"></a><a name="getextraspace"></a>クドックペインズロウ::ゲットエクストラスペース

```
int GetExtraSpace() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetgroupfrompane"></a><a name="getgroupfrompane"></a>クドックペインズロウ::ゲットグループフロインペイン

```cpp
void GetGroupFromPane(
    CPane* pBar,
    CObList& lst);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

[in]*lst*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetid"></a><a name="getid"></a>クッキングペインズロウ::ゲットID

```
int GetID() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetmaxpanesize"></a><a name="getmaxpanesize"></a>クッキングペインズロウ::ゲットマックスペインサイズ

```
int GetMaxPaneSize(BOOL bSkipHiddenBars = TRUE) const;
```

### <a name="parameters"></a>パラメーター

[in]*バー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetpanecount"></a><a name="getpanecount"></a>クッキングペインズロウ::GetPaneCount

```
int GetPaneCount() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetpanelist"></a><a name="getpanelist"></a>クドックペインズロウ::GetPaneリスト

```
const CObList& GetPaneList() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetrowalignment"></a><a name="getrowalignment"></a>クッキングペインズロウ::ゲットローアライメント

```
DWORD GetRowAlignment() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetrowheight"></a><a name="getrowheight"></a>チャッキングペインズロウ::ゲットローハイト

```
int GetRowHeight() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetrowoffset"></a><a name="getrowoffset"></a>クッキングペインズロウ::ゲットローオフセット

```
int GetRowOffset() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetvisiblecount"></a><a name="getvisiblecount"></a>ウィンドウズペインズロウ::取得VisibleCount

```
virtual int GetVisibleCount();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowgetwindowrect"></a><a name="getwindowrect"></a>クッキングペインズロウ::GetWindowRect

```cpp
void GetWindowRect(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

[in]*レクト*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowhaspane"></a><a name="haspane"></a>チャッキングペインズロウ::ハズペイン

```
BOOL HasPane(CBasePane* pControlBar);
```

### <a name="parameters"></a>パラメーター

[in]*コントロールバー*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowisempty"></a><a name="isempty"></a>チャッキングペインズロウ::IsEmpty

```
virtual BOOL IsEmpty() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowisexclusiverow"></a><a name="isexclusiverow"></a>チャッキングペインズロウ::イエクスクルーシブロウ

```
virtual BOOL IsExclusiveRow() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowishorizontal"></a><a name="ishorizontal"></a>チャッキングペインズロウ::イス水平

```
bool IsHorizontal() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowisvisible"></a><a name="isvisible"></a>チャッキングペインズロウ::イズビジブル

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowmove"></a><a name="move"></a>チャッキングペインズロウ::移動

```
virtual void Move(int nOffset);
```

### <a name="parameters"></a>パラメーター

[in]*オフセット*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowmovepane"></a><a name="movepane"></a>チャッキングペインズロウ::移動ペイン

```cpp
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

[in]*コントロールバー*<br/>

[in]*ptオフセット*<br/>

[in]*コントロールバーを切り替える*<br/>

[in]*hdwp*<br/>

[in]*レクトターゲット*<br/>

[in]*オフセット*<br/>

[in]*bフォワード*<br/>

[in]*アブソルトオフセット*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowonresizepane"></a><a name="onresizepane"></a>CDockingPanesRow::オンリサイズペイン

```
virtual void OnResizePane(CBasePane* pControlBar);
```

### <a name="parameters"></a>パラメーター

[in]*コントロールバー*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowredrawall"></a><a name="redrawall"></a>チャッキングペインズロウ::再描画

```cpp
void RedrawAll();
```

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowremovepane"></a><a name="removepane"></a>CDockingPanesRow::ウィンドウの削除

```
virtual void RemovePane(CPane* pControlBar);
```

### <a name="parameters"></a>パラメーター

[in]*コントロールバー*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowreplacepane"></a><a name="replacepane"></a>CDockingPanesRow::置換ペイン

```
virtual BOOL ReplacePane(
    CPane* pBarOld,
    CPane* pBarNew);
```

### <a name="parameters"></a>パラメーター

[in]*をクリックします。*<br/>

[in]*新しい*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowrepositionpanes"></a><a name="repositionpanes"></a>CDockingPanesRow::再配置ペイン

```
virtual void RepositionPanes(
    CRect& rectNewParentBarArea,
    UINT nSide = (UINT)-1,
    BOOL bExpand = FALSE,
    int nOffset = 0);
```

### <a name="parameters"></a>パラメーター

[in]*レクトニューペアレントバーエリア*<br/>

[in]*nサイド*<br/>

[in]*展開する*<br/>

[in]*オフセット*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowresize"></a><a name="resize"></a>CDockingPanesRow::サイズ変更

```
virtual int Resize(int nOffset);
```

### <a name="parameters"></a>パラメーター

[in]*オフセット*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowresizebypanedivider"></a><a name="resizebypanedivider"></a>クドックペインズロウ::サイズ変更バイペインディバイダー

```
virtual int ResizeByPaneDivider(int /*ignored*/);
```

### <a name="parameters"></a>パラメーター

[in]*無視される*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowscreentoclient"></a><a name="screentoclient"></a>クドックペインズロウ::スクリーントクライアント

```cpp
void ScreenToClient(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

[in]*レクト*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowsetextra"></a><a name="setextra"></a>チャッキングペインズロウ::セットエクストラ

```cpp
void SetExtra(
    int nExtraSpace,
    AFX_ROW_ALIGNMENT rowExtraAlign);
```

### <a name="parameters"></a>パラメーター

[in]*nエクストラスペース*<br/>

[in]*行エクストラ整列*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowshowdocksiterow"></a><a name="showdocksiterow"></a>チャッキングペインズロウ::ショードックサイトロウ

```
virtual void ShowDockSiteRow(
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

[in]*bショー*<br/>

[in]*bディレイ*<br/>

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowshowpane"></a><a name="showpane"></a>チャッキングペインズロウ::ショーペイン

```
virtual BOOL ShowPane(
    CPane* pControlBar,
    BOOL bShow,
    BOOL bDelay = FALSE);
```

### <a name="parameters"></a>パラメーター

[in]*コントロールバー*<br/>

[in]*bショー*<br/>

[in]*bディレイ*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockingpanesrowupdatevisiblestate"></a><a name="updatevisiblestate"></a>ウィンドウズペインズロウ::更新VisibleState

```
virtual void UpdateVisibleState(BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

[in]*bディレイ*<br/>

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[CDockSite クラス](../../mfc/reference/cdocksite-class.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)
