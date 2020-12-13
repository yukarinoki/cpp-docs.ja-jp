---
description: '詳細情報: CMFCAutoHideBar クラス'
title: CMFCAutoHideBar クラス
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
ms.openlocfilehash: d7cea85a71b8390520d1345e12000aa700026269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336597"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar クラス

`CMFCAutoHideBar` クラスは、自動非表示機能を実装している、特殊なツール バー クラスです。

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCAutoHideBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|( `CPane::AllowShowOnPaneMenu`をオーバーライドします)。|
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|( [Cbasepane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout)をオーバーライドします)。|
|[CMFCAutoHideBar::Create](#create)|コントロールバーを作成し、 [CPane](../../mfc/reference/cpane-class.md) オブジェクトにアタッチします。 ( [CPane:: Create](../../mfc/reference/cpane-class.md#create)をオーバーライドします)。|
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。 ( [CPane:: OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu)をオーバーライドします)。|
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|( [CPane:: SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup)をオーバーライドします)。|
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||
|[CMFCAutoHideBar::StretchPane](#stretchpane)|垂直または水平方向にウィンドウを拡大します。 ( [Cbasepane:: StretchPane](../../mfc/reference/cbasepane-class.md#stretchpane)をオーバーライドします)。|
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|ユーザーが [Cmfcautohidebutton クラス](../../mfc/reference/cmfcautohidebutton-class.md) の上にマウスカーソルを置いた時点から、フレームワークが関連ウィンドウを表示した時点までの時間間隔。|

## <a name="remarks"></a>解説

ユーザーがドック ウィンドウを自動非表示モードに切り替えると、フレームワークは自動的に `CMFCAutoHideBar` オブジェクトを作成します。 また、必要な [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) および [Cmfcautohidebutton](../../mfc/reference/cmfcautohidebutton-class.md) オブジェクトも作成します。 各 `CAutoHideDockSite` オブジェクトは、個別の `CMFCAutoHideButton` に関連付けられます。

`CMFCAutoHideBar` クラスは、ユーザーのマウスが `CMFCAutoHideButton` の上に移動したときの `CAutoHideDockSite` の表示を実装しています。 ツール バーが WM_MOUSEMOVE メッセージを受信すると、`CMFCAutoHideBar` がタイマーを開始します。 タイマーが終了したら、ツール バーに WM_TIMER イベント通知を送信します。 ツール バーは、タイマーが開始したときにマウス ポインターが位置していた自動非表示ボタン上にまだマウス ポインターがあるかどうかをチェックして、このイベントを処理します。 ある場合は、アタッチされている `CAutoHideDockSite` が表示されます。

タイマーの遅延の長さを制御するには、`m_nShowAHWndDelay` を設定します。 既定値は 400 ミリ秒です。

## <a name="example"></a>例

`CMFCAutoHideBar` オブジェクトを構築して、その `GetDockSiteRow` メソッドを使用する方法を、次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxautohidebar.h

## <a name="cmfcautohidebaraddautohidewindow"></a><a name="addautohidewindow"></a> CMFCAutoHideBar:: AddAutoHideWindow

自動的に隠す機能を `CDockablePane` ウィンドウに追加します。

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

*pAutoHideWnd*<br/>
から非表示にするウィンドウ。

*dwAlignment*<br/>
からアプリケーションウィンドウでの自動的に隠すボタンの配置を指定する値。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

*DwAlignment* パラメーターは、自動的に隠すボタンがアプリケーション内に存在する場所を示します。 このパラメーターは次のいずれかの値に設定できます。

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a> CMFCAutoHideBar:: AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCAutoHideBar:: CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

から *Bstretch*<br/>

から *bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarcmfcautohidebar"></a><a name="cmfcautohidebar"></a> CMFCAutoHideBar:: CMFCAutoHideBar

CMFCAutoHideBar オブジェクトを構築します。

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarcreate"></a><a name="create"></a> CMFCAutoHideBar:: 作成

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszClassName*<br/>

*dwStyle*<br/>

*rect*<br/>

*pParentWnd*<br/>

*nID*<br/>

*dwControlBarStyle*<br/>

*pContext*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebargetfirstahwindow"></a><a name="getfirstahwindow"></a> CMFCAutoHideBar:: Getファイヤの Hwindow

アプリケーションの最初の自動非表示ウィンドウへのポインターを返します。

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>戻り値

アプリケーションの最初の自動非表示ウィンドウ、または NULL (ウィンドウがない場合)。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebargetvisiblecount"></a><a name="getvisiblecount"></a> CMFCAutoHideBar:: GetVisibleCount

自動的に隠すボタンのうち、表示されているものの数を取得します。

```
int GetVisibleCount();
```

### <a name="return-value"></a>戻り値

自動的に隠すボタンのうち、表示されているものの数を返します。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarm_nshowahwnddelay"></a><a name="m_nshowahwnddelay"></a> CMFCAutoHideBar:: m_nShowAHWndDelay

ユーザーが [Cmfcautohidebutton クラス](../../mfc/reference/cmfcautohidebutton-class.md) の上にマウスカーソルを置いた時点から、フレームワークが関連ウィンドウを表示した時点までの時間間隔。

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>解説

ユーザーがマウスカーソルをの上に置くと `CMFCAutoHideButton` 、フレームワークが関連ウィンドウを表示する前にわずかな遅延が発生します。 このパラメーターは、ミリ秒単位の遅延の長さを決定します。

## <a name="cmfcautohidebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a> CMFCAutoHideBar:: OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>パラメーター

から *CPoint*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarremoveautohidewindow"></a><a name="removeautohidewindow"></a> CMFCAutoHideBar:: RemoveAutoHideWindow

自動的に隠すウィンドウを削除して破棄します。

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>パラメーター

CDockablePane * *pAutoHideWnd* 自動的に隠すウィンドウを削除します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarsetactiveingroup"></a><a name="setactiveingroup"></a> CMFCAutoHideBar:: SetActiveInGroup

自動的に隠すバーにアクティブというフラグを付けます。

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>パラメーター

からBOOL *bactive* TRUE に設定するとアクティブになります。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

「 [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup)」を参照してください。

## <a name="cmfcautohidebarsetrecentvisiblestate"></a><a name="setrecentvisiblestate"></a> CMFCAutoHideBar:: SetRecentVisibleState

```cpp
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>パラメーター

*bState*<br/>
から設定する状態。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarshowautohidewindow"></a><a name="showautohidewindow"></a> CMFCAutoHideBar:: ShowAutoHideWindow

自動的に隠すウィンドウを示します。

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

*pAutoHideWnd*<br/>
から表示するウィンドウ。

*bShow*<br/>
からウィンドウを表示する場合は TRUE。

*bDelay*<br/>
からこのパラメーターは無視されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarstretchpane"></a><a name="stretchpane"></a> CMFCAutoHideBar:: StretchPane

折りたたまれた状態の自動的に隠すバーを `CMFCAutoHideButton` オブジェクトに合わせてサイズ変更します。

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>パラメーター

*nLength*<br/>
からこの値は、基本実装では使用されません。 派生実装では、サイズを変更するウィンドウの長さを指定するためにこの値を使用します。

*bVert*<br/>
からこの値は、基本実装では使用されません。 派生実装では、自動的に隠すバーが垂直方向に折りたたまれている場合は TRUE を、自動非表示バーが水平方向に折りたたまれている場合は FALSE を使用して処理します。

### <a name="return-value"></a>戻り値

サイズを変更するウィンドウの結果のサイズ。

### <a name="remarks"></a>解説

派生クラスは、このメソッドをオーバーライドして動作をカスタマイズできます。

## <a name="cmfcautohidebarunsetautohidemode"></a><a name="unsetautohidemode"></a> CMFCAutoHideBar:: UnSetAutoHideMode

自動的に隠すバーのグループの自動非表示モードを無効にします。

```cpp
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>パラメーター

[in] pFirstBarInGroup グループ内の最初の自動非表示バーへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarupdatevisiblestate"></a><a name="updatevisiblestate"></a> CMFCAutoHideBar:: UpdateVisibleState

自動的に隠すバーを再描画する必要がある場合に、フレームワークによって呼び出されます。

```cpp
void UpdateVisibleState();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CPane クラス](../../mfc/reference/cpane-class.md)<br/>
[CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)<br/>
[CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)
