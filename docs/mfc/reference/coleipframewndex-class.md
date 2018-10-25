---
title: COleIPFrameWndEx クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AddPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::AdjustDockingLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::DockPaneLeftOf
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableAutoHidePanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnableDocking
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::EnablePaneMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetActivePopup
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetContainerFrameWindow
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDefaultResId
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetDockingManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMainFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetMenuBar
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetTearOffBars
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::GetToolbarButtonToolTipText
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InsertPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsMenuBarAvailable
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::IsPointNearDockSite
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::LoadFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseDockingPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCloseMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnClosePopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnCmdMsg
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuImage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnDrawMenuLogo
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMenuButtonToolHitTest
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnMoveMiniFrame
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnSetPreviewMode
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowCustomizePane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPanes
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnShowPopupMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::OnTearOffMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PaneFromPoint
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::PreTranslateMessage
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RecalcLayout
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::RemovePaneFromDockManager
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetDockState
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::SetupToolbarMenu
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::ShowPane
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::WinHelpA
- AFXOLEIPFRAMEWNDEX/COleIPFrameWndEx::InitUserToobars
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWndEx [MFC], AddDockSite
- COleIPFrameWndEx [MFC], AddPane
- COleIPFrameWndEx [MFC], AdjustDockingLayout
- COleIPFrameWndEx [MFC], DockPane
- COleIPFrameWndEx [MFC], DockPaneLeftOf
- COleIPFrameWndEx [MFC], EnableAutoHidePanes
- COleIPFrameWndEx [MFC], EnableDocking
- COleIPFrameWndEx [MFC], EnablePaneMenu
- COleIPFrameWndEx [MFC], GetActivePopup
- COleIPFrameWndEx [MFC], GetContainerFrameWindow
- COleIPFrameWndEx [MFC], GetDefaultResId
- COleIPFrameWndEx [MFC], GetDockFrame
- COleIPFrameWndEx [MFC], GetDockingManager
- COleIPFrameWndEx [MFC], GetMainFrame
- COleIPFrameWndEx [MFC], GetMenuBar
- COleIPFrameWndEx [MFC], GetPane
- COleIPFrameWndEx [MFC], GetTearOffBars
- COleIPFrameWndEx [MFC], GetToolbarButtonToolTipText
- COleIPFrameWndEx [MFC], InsertPane
- COleIPFrameWndEx [MFC], IsMenuBarAvailable
- COleIPFrameWndEx [MFC], IsPointNearDockSite
- COleIPFrameWndEx [MFC], LoadFrame
- COleIPFrameWndEx [MFC], OnCloseDockingPane
- COleIPFrameWndEx [MFC], OnCloseMiniFrame
- COleIPFrameWndEx [MFC], OnClosePopupMenu
- COleIPFrameWndEx [MFC], OnCmdMsg
- COleIPFrameWndEx [MFC], OnDrawMenuImage
- COleIPFrameWndEx [MFC], OnDrawMenuLogo
- COleIPFrameWndEx [MFC], OnMenuButtonToolHitTest
- COleIPFrameWndEx [MFC], OnMoveMiniFrame
- COleIPFrameWndEx [MFC], OnSetPreviewMode
- COleIPFrameWndEx [MFC], OnShowCustomizePane
- COleIPFrameWndEx [MFC], OnShowPanes
- COleIPFrameWndEx [MFC], OnShowPopupMenu
- COleIPFrameWndEx [MFC], OnTearOffMenu
- COleIPFrameWndEx [MFC], PaneFromPoint
- COleIPFrameWndEx [MFC], PreTranslateMessage
- COleIPFrameWndEx [MFC], RecalcLayout
- COleIPFrameWndEx [MFC], RemovePaneFromDockManager
- COleIPFrameWndEx [MFC], SetDockState
- COleIPFrameWndEx [MFC], SetupToolbarMenu
- COleIPFrameWndEx [MFC], ShowPane
- COleIPFrameWndEx [MFC], WinHelpA
- COleIPFrameWndEx [MFC], InitUserToobars
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a9cef05463ddf691b1d3136bae9d55f08608d67
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071077"
---
# <a name="coleipframewndex-class"></a>COleIPFrameWndEx クラス

`COleIPFrameWndEx` クラスは、MFC をサポートする OLE コンテナーを実装します。 アプリケーションの埋め込み先フレーム ウィンドウ クラスを、 `COleIPFrameWndEx` COleIPFrameWnd [クラスからではなく、](../../mfc/reference/coleipframewnd-class.md)クラスから派生させる必要があります
詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。

## <a name="syntax"></a>構文

```
class COleIPFrameWndEx : public COleIPFrameWnd
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleIPFrameWndEx::AddDockSite](#adddocksite)||
|[COleIPFrameWndEx::AddPane](#addpane)||
|[COleIPFrameWndEx::AdjustDockingLayout](#adjustdockinglayout)||
|[COleIPFrameWndEx::DockPane](#dockpane)||
|[COleIPFrameWndEx::DockPaneLeftOf](#dockpaneleftof)|ウィンドウを別のウィンドウの左側にドッキングします。|
|[COleIPFrameWndEx::EnableAutoHidePanes](#enableautohidepanes)||
|[COleIPFrameWndEx::EnableDocking](#enabledocking)||
|[COleIPFrameWndEx::EnablePaneMenu](#enablepanemenu)||
|[COleIPFrameWndEx::GetActivePopup](#getactivepopup)|現在表示されているポップアップ メニューへのポインターを返します。|
|[COleIPFrameWndEx::GetContainerFrameWindow](#getcontainerframewindow)||
|[COleIPFrameWndEx::GetDefaultResId](#getdefaultresid)|ウィンドウが読み込まれるときに指定した、フレーム ウィンドウのリソース ID を返します。|
|[COleIPFrameWndEx::GetDockFrame](#getdockframe)||
|[COleIPFrameWndEx::GetDockingManager](#getdockingmanager)||
|[COleIPFrameWndEx::GetMainFrame](#getmainframe)||
|[COleIPFrameWndEx::GetMenuBar](#getmenubar)|フレーム ウィンドウにアタッチされているメニュー バーのオブジェクトへのポインターを返します。|
|[COleIPFrameWndEx::GetPane](#getpane)||
|[COleIPFrameWndEx::GetTearOffBars](#gettearoffbars)|ティアオフ状態にあるウィンドウ オブジェクトの一覧を返します。|
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|ボタンのツールヒントが表示される前に、フレームワークによって呼び出されます。|
|[COleIPFrameWndEx::InsertPane](#insertpane)||
|[COleIPFrameWndEx::IsMenuBarAvailable](#ismenubaravailable)|メニュー バーのオブジェクトへのポインターが `NULL`ではないかどうかを判断します。|
|[COleIPFrameWndEx::IsPointNearDockSite](#ispointneardocksite)||
|[COleIPFrameWndEx::LoadFrame](#loadframe)|( `COleIPFrameWnd::LoadFrame`をオーバーライドします)。|
|[COleIPFrameWndEx::OnCloseDockingPane](#onclosedockingpane)||
|[COleIPFrameWndEx::OnCloseMiniFrame](#oncloseminiframe)||
|[COleIPFrameWndEx::OnClosePopupMenu](#onclosepopupmenu)|アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|
|[COleIPFrameWndEx::OnCmdMsg](#oncmdmsg)|( `CFrameWnd::OnCmdMsg`をオーバーライドします)。|
|[COleIPFrameWndEx::OnDrawMenuImage](#ondrawmenuimage)|メニュー項目に関連付けられているイメージが描画されるときに、フレームワークによって呼び出されます。|
|[COleIPFrameWndEx::OnDrawMenuLogo](#ondrawmenulogo)|[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトが WM_PAINT メッセージを処理するときに、フレームワークによって呼び出されます。|
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](#onmenubuttontoolhittest)|[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトが WM_NCHITTEST Microsoft を処理するときに、フレームワークによって呼び出されます。|
|[COleIPFrameWndEx::OnMoveMiniFrame](#onmoveminiframe)||
|[COleIPFrameWndEx::OnSetPreviewMode](#onsetpreviewmode)|印刷プレビュー モードの内外にアプリケーションのメイン フレーム ウィンドウを設定するには、このメンバー関数を呼び出します。 ( [CFrameWnd::OnSetPreviewMode](../../mfc/reference/cframewnd-class.md#onsetpreviewmode)をオーバーライドします)。|
|[COleIPFrameWndEx::OnShowCustomizePane](#onshowcustomizepane)||
|[COleIPFrameWndEx::OnShowPanes](#onshowpanes)||
|[COleIPFrameWndEx::OnShowPopupMenu](#onshowpopupmenu)|ポップアップ メニューがアクティブにされるときにフレームワークによって呼び出されます。|
|[COleIPFrameWndEx::OnTearOffMenu](#ontearoffmenu)|ティアオフ バーのあるメニューがアクティブ化されるときにフレームワークによって呼び出されます。|
|[COleIPFrameWndEx::PaneFromPoint](#panefrompoint)||
|[COleIPFrameWndEx::PreTranslateMessage](#pretranslatemessage)|( `COleIPFrameWnd::PreTranslateMessage`をオーバーライドします)。|
|[COleIPFrameWndEx::RecalcLayout](#recalclayout)|( `COleIPFrameWnd::RecalcLayout`をオーバーライドします)。|
|[COleIPFrameWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)||
|[COleIPFrameWndEx::SetDockState](#setdockstate)|フレーム ウィンドウに属しているウィンドウに、指定のドッキング状態を適用します。|
|[COleIPFrameWndEx::SetupToolbarMenu](#setuptoolbarmenu)|ダミーの項目を検索して、指定されたユーザー定義の項目で置き換えることで、ツールバーのオブジェクトを変更します。|
|[COleIPFrameWndEx::ShowPane](#showpane)||
|[COleIPFrameWndEx::WinHelpA](#winhelpa)|WinHelp アプリケーションまたはコンテキスト ヘルプを起動するために、フレームワークによって呼び出されます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[COleIPFrameWndEx::InitUserToobars](#initusertoobars)|ユーザー定義のツールバーに割り当てられているコントロールの ID の範囲を初期化するようフレームワークに指示します。|

## <a name="example"></a>例

次の例は、 `COleIPFrameWndEx` クラスのインスタンスをサブクラス化して、メソッドをオーバーライドする方法を示しています。 `OnDestory` メソッド、 `RepositionFrame` メソッド、 `RecalcLayout` メソッド、および `CalcWindowRect` メソッドをオーバーライドする方法を例に示します。 このコード スニペットは、 [Word パッド サンプル](../../visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_WordPad#1](../../mfc/reference/codesnippet/cpp/coleipframewndex-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[クラスからではなく、](../../mfc/reference/coleipframewnd-class.md)

[COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxoleipframewndex.h

##  <a name="adddocksite"></a>  COleIPFrameWndEx::AddDockSite

```
void AddDockSite();
```

### <a name="remarks"></a>Remarks

##  <a name="addpane"></a>  COleIPFrameWndEx::AddPane

```
BOOL AddPane(
    CBasePane* pControlBar,
    BOOL bTail = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*pControlBar*<br/>
[in]*bTail*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="adjustdockinglayout"></a>  COleIPFrameWndEx::AdjustDockingLayout

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*hdwp*<br/>

### <a name="remarks"></a>Remarks

##  <a name="dockpane"></a>  COleIPFrameWndEx::DockPane

```
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*pBar*<br/>
[in]*辺*<br/>
[in]*lpRect*<br/>

### <a name="remarks"></a>Remarks

##  <a name="dockpaneleftof"></a>  COleIPFrameWndEx::DockPaneLeftOf

ウィンドウを別のウィンドウの左側にドッキングします。

```
BOOL DockPaneLeftOf(
    CPane* pBar,
    CPane* pLeftOf);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
[in]ドッキング ウィンドウへのポインター。

*pLeftOf*<br/>
[in]配信元として機能するウィンドウへのポインター。

### <a name="return-value"></a>戻り値

操作が成功した場合に TRUE を返します。 それ以外の場合、FALSE を返します。

### <a name="remarks"></a>Remarks

事前定義された順序でいくつかのウィンドウ オブジェクトをドッキングするには、このメソッドを呼び出します。 このメソッドで指定されたウィンドウのドッキング*pBar*で指定されたウィンドウの左側に*pLeftOf*します。

##  <a name="enableautohidepanes"></a>  COleIPFrameWndEx::EnableAutoHidePanes

```
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

[in]*dwDockStyle*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="enabledocking"></a>  COleIPFrameWndEx::EnableDocking

```
BOOL EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

[in]*dwDockStyle*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="enablepanemenu"></a>  COleIPFrameWndEx::EnablePaneMenu

```
void EnablePaneMenu(
    BOOL bEnable,
    UINT uiCustomizeCmd,
    const CString& strCustomizeLabel,
    UINT uiViewToolbarsMenuEntryID,
    BOOL bContextMenuShowsToolbarsOnly = FALSE,
    BOOL bViewMenuShowsToolbarsOnly = FALSE);
```

### <a name="parameters"></a>パラメーター

[in]*bEnable*<br/>
[in]*uiCustomizeCmd*<br/>
[in]*strCustomizeLabel*<br/>
[in]*uiViewToolbarsMenuEntryID*<br/>
[in]*bContextMenuShowsToolbarsOnly*<br/>
[in]*bViewMenuShowsToolbarsOnly*<br/>

### <a name="remarks"></a>Remarks

##  <a name="getactivepopup"></a>  COleIPFrameWndEx::GetActivePopup

現在表示されているポップアップ メニューへのポインターを返します。

```
CMFCPopupMenu* GetActivePopup() const;
```

### <a name="return-value"></a>戻り値

アクティブなポップアップ メニュー; へのポインターそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

ポインターを取得するには、このメソッドを使用して、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)現在表示されているオブジェクト。

##  <a name="getcontainerframewindow"></a>  COleIPFrameWndEx::GetContainerFrameWindow

```
COleCntrFrameWndEx* GetContainerFrameWindow();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getdefaultresid"></a>  COleIPFrameWndEx::GetDefaultResId

メニュー リソース ID を指定のフレーム ウィンドウで、メニューが読み込まれるときに返します。

```
UINT GetDefaultResId() const;
```

### <a name="return-value"></a>戻り値

フレーム ウィンドウのメニュー バーにない場合は、メニューのまたは 0 のリソース ID を返します。

### <a name="remarks"></a>Remarks

リソース ID を取得するには、この関数は、フレーム ウィンドウによって呼び出すことでメニュー リソースが読み込まれるときに指定された呼び出し`COleIPFrameWndEx::LoadFrame`します。

##  <a name="getdockframe"></a>  COleIPFrameWndEx::GetDockFrame

```
CFrameWnd* GetDockFrame();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getdockingmanager"></a>  COleIPFrameWndEx::GetDockingManager

```
CDockingManager* GetDockingManager();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getmainframe"></a>  COleIPFrameWndEx::GetMainFrame

```
CFrameWnd* GetMainFrame();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="getmenubar"></a>  COleIPFrameWndEx::GetMenuBar

フレーム ウィンドウにアタッチされているメニュー バーのオブジェクトへのポインターを返します。

```
const CMFCMenuBar* GetMenuBar() const;
```

### <a name="return-value"></a>戻り値

メニュー バーのオブジェクトへのポインター。

### <a name="remarks"></a>Remarks

この関数が属するメニュー バーのオブジェクトへのポインターの取得を使用して、`COleIPFrameWndEx`オブジェクト。

##  <a name="getpane"></a>  COleIPFrameWndEx::GetPane

```
CBasePane* GetPane(UINT nID);
```

### <a name="parameters"></a>パラメーター

[in]*nID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="gettearoffbars"></a>  COleIPFrameWndEx::GetTearOffBars

ティアオフ状態にあるウィンドウ オブジェクトの一覧を返します。

```
const CObList& GetTearOffBars() const;
```

### <a name="return-value"></a>戻り値

参照を`CObList`へのポインターのコレクションを格納するオブジェクト、 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)の派生オブジェクト。

### <a name="remarks"></a>Remarks

`COleIPFrameWndEx`オブジェクトのリストとしてティアオフ メニューのコレクションを保持する[CBasePane クラス](../../mfc/reference/cbasepane-class.md)の派生オブジェクト。 この一覧への参照を取得するのにには、このメソッドを使用します。

##  <a name="gettoolbarbuttontooltiptext"></a>  COleIPFrameWndEx::GetToolbarButtonToolTipText

ボタンのツールヒントが表示される前に、フレームワークによって呼び出されます。

```
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,
    CString& strTTText);
```

### <a name="parameters"></a>パラメーター

*pButton*<br/>
[in]ボタンへのポインター。

*strTTText*<br/>
[in]ツールヒントのテキストへのポインター。

### <a name="return-value"></a>戻り値

既定の実装では、0 を返します。

### <a name="remarks"></a>Remarks

ツールバーのボタンのツールヒントの表示をカスタマイズするには、この関数をオーバーライドします。

##  <a name="initusertoobars"></a>  COleIPFrameWndEx::InitUserToobars

コントロール、フレームワークは、ユーザー定義のツールバーに割り当てる Id 範囲を指定します。

```
void InitUserToolbars(
    LPCTSTR lpszRegEntry,
    UINT uiUserToolbarFirst,
    UINT uiUserToolbarLast)
```

### <a name="parameters"></a>パラメーター

*lpszRegEntry*<br/>
[in]レジストリ エントリは、ライブラリがユーザーのツールバーの設定を格納する場所です。

*uiUserToolbarFirst*<br/>
[in]最初のユーザー定義のツールバーに割り当てられているコントロール ID。

*uiUserToolbarLast*<br/>
[in]最後のユーザー定義のツールバーに割り当てられているコントロール ID。

### <a name="remarks"></a>Remarks

この関数を使用して、ユーザーを動的に定義するツールバーへの割り当てのコントロール Id の範囲を初期化します。 パラメーター *uiUserToolbarFirst*と*uiUserToolbarLast*許可されているツールバーのコントロール Id の範囲を定義します。 ユーザー定義のツールバーの作成を無効にするには設定*uiUserToolbarFirst*または*uiUserToolbarLast*を-1 にします。

##  <a name="insertpane"></a>  COleIPFrameWndEx::InsertPane

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*pControlBar*<br/>
[in]*pTarget*<br/>
[in]*bAfter*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="ismenubaravailable"></a>  COleIPFrameWndEx::IsMenuBarAvailable

メニュー バーのオブジェクトへのポインターが NULL でないかどうかを決定します。

```
BOOL IsMenuBarAvailable() const;
```

### <a name="return-value"></a>戻り値

フレーム ウィンドウ、メニュー バーがある場合は、値を返します、0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

フレーム ウィンドウが、メニュー バーのオブジェクトへの NULL 以外のポインターを保持するかどうかを判断するには、このメソッドを呼び出します。

##  <a name="ispointneardocksite"></a>  COleIPFrameWndEx::IsPointNearDockSite

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>パラメーター

[in]*ポイント*<br/>
[in]*dwBarAlignment*<br/>
[in]*bOuterEdge*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="loadframe"></a>  COleIPFrameWndEx::LoadFrame

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

[in]*可能*<br/>
[in]*dwDefaultStyle*<br/>
[in]*pParentWnd*<br/>
[in]*pContext*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onclosedockingpane"></a>  COleIPFrameWndEx::OnCloseDockingPane

```
virtual BOOL OnCloseDockingPane(CDockablePane*);
```

### <a name="parameters"></a>パラメーター

[in]*CDockablePane&#42;*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="oncloseminiframe"></a>  COleIPFrameWndEx::OnCloseMiniFrame

```
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```

### <a name="parameters"></a>パラメーター

[in]*CPaneFrameWnd&#42;*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onclosepopupmenu"></a>  COleIPFrameWndEx::OnClosePopupMenu

アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。

```
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```

### <a name="parameters"></a>パラメーター

*pMenuPopup*<br/>
[in]ポップアップ メニュー オブジェクトへのポインター。

### <a name="remarks"></a>Remarks

通知を受信するには、このメソッドをオーバーライド`CMFCPopupMenu`WM_DESTROY メッセージの処理時にオブジェクトします。

##  <a name="oncmdmsg"></a>  COleIPFrameWndEx::OnCmdMsg

```
virtual BOOL OnCmdMsg(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>パラメーター

[in]*nID*<br/>
[in]*nCode*<br/>
[in]*pExtra*<br/>
[in]*pHandlerInfo*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="ondrawmenuimage"></a>  COleIPFrameWndEx::OnDrawMenuImage

メニュー項目に関連付けられているイメージが描画されるときに、フレームワークによって呼び出されます。

```
virtual BOOL OnDrawMenuImage(
    CDC* pDC,
    const CMFCToolBarMenuButton* pMenuButton,
    const CRect& rectImage);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*pMenuButton*<br/>
[in]メニュー ボタンへのポインター。

*rectImage*<br/>
[in]メニュー項目に関連付けられたイメージ。

### <a name="return-value"></a>戻り値

既定の実装では、何も実行し、0 を返します。

### <a name="remarks"></a>Remarks

このメソッドをオーバーライドして、によって所有されている、メニュー バーに属しているメニュー項目のイメージの描画をカスタマイズする場合、 `COleIPFrameWndEx`-派生オブジェクト。

##  <a name="ondrawmenulogo"></a>  COleIPFrameWndEx::OnDrawMenuLogo

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトが WM_PAINT メッセージを処理するときに、フレームワークによって呼び出されます。

```
virtual void OnDrawMenuLogo(
    CDC* pDC,
    CMFCPopupMenu* pMenu,
    const CRect& rectLogo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*pMenu*<br/>
[in]ポップアップ メニュー オブジェクトへのポインター。

*rectLogo*<br/>
[in]表示するロゴへのポインター。

### <a name="remarks"></a>Remarks

によって所有されている、メニュー バーに関連付けられたポップアップ メニューにロゴを表示するには、このメソッドをオーバーライド、 `COleIPFrameWndEx`-派生オブジェクト。 既定の実装では、何も行われません。

##  <a name="onmenubuttontoolhittest"></a>  COleIPFrameWndEx::OnMenuButtonToolHitTest

フレームワークによって呼び出されるときに、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトが WM_NCHITTEST メッセージを処理します。

```
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,
    TOOLINFO* pTI);
```

### <a name="parameters"></a>パラメーター

[in] メニュー ボタンにポインターを pButton します。

[out] pTI ポインターを`TOOLINFO`構造体。

### <a name="return-value"></a>戻り値

既定の実装では、何も実行し、0 を返します。 空き領域がなくなる場合は、実装が 0 以外の値を返す必要があります、 *pTI*パラメーター。

### <a name="remarks"></a>Remarks

特定のメニュー項目のツールヒント情報を提供するには、このメソッドをオーバーライドします。

##  <a name="onmoveminiframe"></a>  COleIPFrameWndEx::OnMoveMiniFrame

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>パラメーター

[in]*pFrame*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onsetpreviewmode"></a>  COleIPFrameWndEx::OnSetPreviewMode

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>パラメーター

[in]*bPreview*<br/>
[in]*pState*<br/>

### <a name="remarks"></a>Remarks

##  <a name="onshowcustomizepane"></a>  COleIPFrameWndEx::OnShowCustomizePane

```
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,
    UINT uiToolbarID);
```

### <a name="parameters"></a>パラメーター

[in]*pMenuPane*<br/>
[in]*uiToolbarID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onshowpanes"></a>  COleIPFrameWndEx::OnShowPanes

```
virtual BOOL OnShowPanes(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

[in]*bShow*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="onshowpopupmenu"></a>  COleIPFrameWndEx::OnShowPopupMenu

ポップアップ メニューが表示される場合に、フレームワークによって呼び出されます。

```
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenuPopup);
```

### <a name="parameters"></a>パラメーター

*pMenuPopup*<br/>
[in]表示されるポップアップ メニューへのポインター。

### <a name="return-value"></a>戻り値

既定の実装では、何も実行し、0 以外の値を返します。 ポップアップ メニューを表示できない場合、実装は FALSE を返す必要があります。

### <a name="remarks"></a>Remarks

ポップアップ メニューの表示をカスタマイズするには、このメソッドをオーバーライドします。 たとえば、メニュー ボタンをメニュー ボタンの色を変更したり、ティアオフ バーを初期化します。

##  <a name="ontearoffmenu"></a>  COleIPFrameWndEx::OnTearOffMenu

ティアオフ バーのあるメニューを選択すると、フレームワークによって呼び出されます。

```
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,
    CPane* pBar);
```

### <a name="parameters"></a>パラメーター

*pMenuPopup*<br/>
[in]ユーザーが選択されているポップアップ メニューへのポインター。

*pBar*<br/>
[in]メニューをホストするウィンドウへのポインター。

### <a name="return-value"></a>戻り値

ポップアップ メニューをアクティブにする場合は TRUE。それ以外の場合は FALSE です。 既定値は TRUE です。

### <a name="remarks"></a>Remarks

ティアオフ バーの設定をカスタマイズする場合は、この関数をオーバーライドします。

##  <a name="panefrompoint"></a>  COleIPFrameWndEx::PaneFromPoint

```
CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar,
    CRuntimeClass* pRTCBarType) const;

CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    DWORD& dwAlignment,
    CRuntimeClass* pRTCBarType) const;
```

### <a name="parameters"></a>パラメーター

[in]*ポイント*<br/>
[in]*nSensitivity*<br/>
[in]*bExactBar*<br/>
[in]*pRTCBarType*<br/>
[in]*場合*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="pretranslatemessage"></a>  COleIPFrameWndEx::PreTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

[in]*pMsg*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="recalclayout"></a>  COleIPFrameWndEx::RecalcLayout

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*bNotify*<br/>

### <a name="remarks"></a>Remarks

##  <a name="removepanefromdockmanager"></a>  COleIPFrameWndEx::RemovePaneFromDockManager

```
void RemovePaneFromDockManager(
    CBasePane* pControlBar,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide,
    CBasePane* pBarReplacement);
```

### <a name="parameters"></a>パラメーター

[in]*pControlBar*<br/>
[in]*bDestroy*<br/>
[in]*bAdjustLayout*<br/>
[in]*bAutoHide*<br/>
[in]*pBarReplacement*<br/>

### <a name="remarks"></a>Remarks

##  <a name="setdockstate"></a>  COleIPFrameWndEx::SetDockState

フレーム ウィンドウに属しているウィンドウには、指定したドッキング状態を適用します。

```
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>パラメーター

*state*<br/>
[in]ドッキング状態を指定します。

### <a name="remarks"></a>Remarks

この関数に属しているウィンドウの新しいドッキング状態の指定を使用して、`COleIPFrameWndEx`オブジェクト。

##  <a name="setuptoolbarmenu"></a>  COleIPFrameWndEx::SetupToolbarMenu

ダミーの項目を検索して、指定されたユーザー定義の項目で置き換えることで、ツールバーのオブジェクトを変更します。

```
void SetupToolbarMenu(
    CMenu& menu,
    const UINT uiViewUserToolbarCmdFirst,
    const UINT uiViewUserToolbarCmdLast);
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
[in]参照を[CMenu](../../mfc/reference/cmenu-class.md)オブジェクトを変更します。

*uiViewUserToolbarCmdFirst*<br/>
[in]ユーザー定義の最初のコマンドを指定します。

*uiViewUserToolbarCmdLast*<br/>
[in]ユーザー定義の最後のコマンドを指定します。

### <a name="remarks"></a>Remarks

##  <a name="showpane"></a>  COleIPFrameWndEx::ShowPane

```
void ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

[in]*pBar*<br/>
[in]*bShow*<br/>
[in]*bDelay*<br/>
[in]*bActivate*<br/>

### <a name="remarks"></a>Remarks

##  <a name="winhelpa"></a>  COleIPFrameWndEx::WinHelpA

WinHelp アプリケーションまたはコンテキスト ヘルプを起動するために、フレームワークによって呼び出されます。

```
virtual void WinHelp(
    DWORD dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>パラメーター

[入力] dwdata で指定されたヘルプの種類の必要に応じて指定データ*nCmd*します。

*nCmd*<br/>
[in]要求されたヘルプの種類を指定します。 使用可能な値、および影響についての一覧については、*指定*パラメーターを参照してください、 [WinHelp 関数](/windows/desktop/api/winuser/nf-winuser-winhelpa)Windows SDK にします。

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)<br/>
[CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)
