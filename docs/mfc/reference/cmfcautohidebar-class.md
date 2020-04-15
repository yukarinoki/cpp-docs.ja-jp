---
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
ms.openlocfilehash: 62750f4fb1261f4f30286297c3a240ab67e6df1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369897"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar クラス

`CMFCAutoHideBar` クラスは、自動非表示機能を実装している、特殊なツール バー クラスです。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

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
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(CBase ペインをオーバーライド[します::計算固定レイアウト](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCAutoHideBar::Create](#create)|コントロール バーを作成し[、CPane](../../mfc/reference/cpane-class.md)オブジェクトにアタッチします。 (CPane をオーバーライド[::作成](../../mfc/reference/cpane-class.md#create).)|
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|特殊ウィンドウ メニューが表示されるときにフレームワークによって呼び出されます。 (CPane をオーバーライド[します::オンショーコントロールバーメニュー](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(CPane をオーバーライド[します。::セットアクティブイングループ](../../mfc/reference/cpane-class.md#setactiveingroup).)|
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||
|[CMFCAutoHideBar::StretchPane](#stretchpane)|垂直または水平方向にウィンドウを拡大します。 [(CBasePane をオーバーライドします::ストレッチペイン](../../mfc/reference/cbasepane-class.md#stretchpane).)|
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|ユーザーが[CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)の上にマウス カーソルを置く瞬間と、フレームワークが関連付けられたウィンドウを表示する瞬間の間の時間の遅延。|

## <a name="remarks"></a>解説

ユーザーがドック ウィンドウを自動非表示モードに切り替えると、フレームワークは自動的に `CMFCAutoHideBar` オブジェクトを作成します。 また、必要な[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)オブジェクトと[CMFC 自動非表示ボタン](../../mfc/reference/cmfcautohidebutton-class.md)オブジェクトも作成されます。 各 `CAutoHideDockSite` オブジェクトは、個別の `CMFCAutoHideButton` に関連付けられます。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** afxautohidebar.h

## <a name="cmfcautohidebaraddautohidewindow"></a><a name="addautohidewindow"></a>CMFC 自動ハイドバー::自動非表示ウィンドウの追加

自動的に隠す機能を `CDockablePane` ウィンドウに追加します。

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

*を自動非表示にする*<br/>
[in]非表示にするウィンドウ。

*dw配置*<br/>
[in]アプリケーション ウィンドウと自動非表示ボタンの配置を指定する値。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

*dwAlignment*パラメーターは、アプリケーション内の自動非表示ボタンの位置を示します。 このパラメーターは次のいずれかの値に設定できます。

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="cmfcautohidebarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFC 自動ハイドバー::ウィンドウオンペインを表示するメニュー

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFC 自動ハイドバー::計算レイアウト

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

## <a name="cmfcautohidebarcmfcautohidebar"></a><a name="cmfcautohidebar"></a>CMFC 自動ハイドバー::CMFC 自動ハイドバー

CMFCAutoHideBar オブジェクトを構築します。

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarcreate"></a><a name="create"></a>CMFC オートハイダバー::作成

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

*クラス名*<br/>

*Dwstyle*<br/>

*Rect*<br/>

*pParentWnd*<br/>

*nID*<br/>

*コントロール バースタイル*<br/>

*pContext*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebargetfirstahwindow"></a><a name="getfirstahwindow"></a>CMFC オートハイダーバー::最初のウィンドウを取得します。

アプリケーションの最初の自動非表示ウィンドウへのポインターを返します。

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>戻り値

アプリケーションの最初の自動非表示ウィンドウ、または NULL (ウィンドウがない場合)。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebargetvisiblecount"></a><a name="getvisiblecount"></a>CMFC 自動隠しグループ::取得Visibleカウント

自動的に隠すボタンのうち、表示されているものの数を取得します。

```
int GetVisibleCount();
```

### <a name="return-value"></a>戻り値

自動的に隠すボタンのうち、表示されているものの数を返します。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarm_nshowahwnddelay"></a><a name="m_nshowahwnddelay"></a>CMFC オートハイダバー::m_nShowAHWndDelay

ユーザーが[CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)の上にマウス カーソルを置く瞬間と、フレームワークが関連付けられたウィンドウを表示する瞬間の間の時間の遅延。

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>解説

ユーザーがマウス カーソルを`CMFCAutoHideButton`上に置くと、フレームワークが関連するウィンドウを表示するまでに若干の遅延が発生します。 このパラメーターは、その遅延の長さをミリ秒単位で決定します。

## <a name="cmfcautohidebaronshowcontrolbarmenu"></a><a name="onshowcontrolbarmenu"></a>コントロール バー メニューを表示します。

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>パラメーター

[in]*CPoint*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarremoveautohidewindow"></a><a name="removeautohidewindow"></a>CMFC 自動ハイダバー::削除自動ハイドウィンドウ

自動的に隠すウィンドウを削除して破棄します。

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>パラメーター

CDockablePane* *pAutoHideWnd*削除する自動非表示ウィンドウ。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarsetactiveingroup"></a><a name="setactiveingroup"></a>CMFC オートハイダバー::セットアクティブイングループ

自動的に隠すバーにアクティブというフラグを付けます。

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>パラメーター

[in]ブール*値をアクティブ*に設定する場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

「 [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup)」を参照してください。

## <a name="cmfcautohidebarsetrecentvisiblestate"></a><a name="setrecentvisiblestate"></a>状態を設定します。

```
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>パラメーター

*bState*<br/>
[in]設定する状態。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarshowautohidewindow"></a><a name="showautohidewindow"></a>CMFC 自動ハイダバー::自動隠しウィンドウを表示します。

自動的に隠すウィンドウを示します。

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

*を自動非表示にする*<br/>
[in]表示するウィンドウ。

*bショー*<br/>
[in]ウィンドウを表示する場合は TRUE。

*bディレイ*<br/>
[in]このパラメーターは無視されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarstretchpane"></a><a name="stretchpane"></a>CMFC 自動ハイドバー::ストレッチペイン

折りたたまれた状態の自動的に隠すバーを `CMFCAutoHideButton` オブジェクトに合わせてサイズ変更します。

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>パラメーター

*nレングス*<br/>
[in]この値は基本実装では使用されません。 派生実装では、サイズを変更するウィンドウの長さを指定するためにこの値を使用します。

*bVert*<br/>
[in]この値は基本実装では使用されません。 派生実装では、自動非表示バーが垂直に折りたたまれている場合を処理するには TRUE を使用し、自動非表示バーが水平方向に折りたたまれている場合は FALSE を使用します。

### <a name="return-value"></a>戻り値

サイズを変更するウィンドウの結果のサイズ。

### <a name="remarks"></a>解説

派生クラスは、このメソッドをオーバーライドして動作をカスタマイズできます。

## <a name="cmfcautohidebarunsetautohidemode"></a><a name="unsetautohidemode"></a>CMFC 自動ハイダバー::自動隠しモードを設定解除

自動的に隠すバーのグループの自動非表示モードを無効にします。

```
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>パラメーター

[in] pFirstBarInGroup グループ内の最初の自動非表示バーへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcautohidebarupdatevisiblestate"></a><a name="updatevisiblestate"></a>CMFC 自動隠しバー::更新Visible状態

自動的に隠すバーを再描画する必要がある場合に、フレームワークによって呼び出されます。

```
void UpdateVisibleState();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)<br/>
[クラスを自動非表示にする](../../mfc/reference/cautohidedocksite-class.md)<br/>
[CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)
