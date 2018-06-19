---
title: COleIPFrameWndEx クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 71610035d029c4d8f5ca403c52d9eddd575e3a8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377572"
---
# <a name="coleipframewndex-class"></a>COleIPFrameWndEx クラス
`COleIPFrameWndEx` クラスは、MFC をサポートする OLE コンテナーを実装します。 アプリケーションの埋め込み先フレーム ウィンドウ クラスを、 `COleIPFrameWndEx` COleIPFrameWnd [クラスからではなく、](../../mfc/reference/coleipframewnd-class.md)クラスから派生させる必要があります 
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]   
  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxoleipframewndex.h  
  
##  <a name="adddocksite"></a>  COleIPFrameWndEx::AddDockSite  

  
```  
void AddDockSite();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addpane"></a>  COleIPFrameWndEx::AddPane  

  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 [入力] `bTail`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="adjustdockinglayout"></a>  COleIPFrameWndEx::AdjustDockingLayout  

  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hdwp`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dockpane"></a>  COleIPFrameWndEx::DockPane  

  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `nDockBarID`  
 [入力] `lpRect`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="dockpaneleftof"></a>  COleIPFrameWndEx::DockPaneLeftOf  
 ウィンドウを別のウィンドウの左側にドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ドッキング ウィンドウへのポインター。  
  
 [入力] `pLeftOf`  
 配信元として機能するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`操作が成功した場合。 それ以外の場合は、`FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 定義済みの順序で複数のペインのオブジェクトをドッキングするには、このメソッドを呼び出します。 このメソッドで指定されたウィンドウのドッキング`pBar`で指定されたウィンドウの左側に`pLeftOf`です。  
  
##  <a name="enableautohidepanes"></a>  COleIPFrameWndEx::EnableAutoHidePanes  

  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="enabledocking"></a>  COleIPFrameWndEx::EnableDocking  

  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwDockStyle`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
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
 [入力] `bEnable`  
 [入力] `uiCustomizeCmd`  
 [入力] `strCustomizeLabel`  
 [入力] `uiViewToolbarsMenuEntryID`  
 [入力] `bContextMenuShowsToolbarsOnly`  
 [入力] `bViewMenuShowsToolbarsOnly`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getactivepopup"></a>  COleIPFrameWndEx::GetActivePopup  
 現在表示されているポップアップ メニューへのポインターを返します。  
  
```  
CMFCPopupMenu* GetActivePopup() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アクティブなポップアップ メニューへのポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用してへのポインターを取得する、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)現在表示されているオブジェクト。  
  
##  <a name="getcontainerframewindow"></a>  COleIPFrameWndEx::GetContainerFrameWindow  

  
```  
COleCntrFrameWndEx* GetContainerFrameWindow();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdefaultresid"></a>  COleIPFrameWndEx::GetDefaultResId  
 メニュー リソース ID を指定、フレーム ウィンドウで、メニューが読み込まれるときに返します。  
  
```  
UINT GetDefaultResId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレーム ウィンドウには、メニュー バーがあるない場合は、メニューのまたは 0 のリソース ID を返します。  
  
### <a name="remarks"></a>コメント  
 リソース ID を取得するには、この関数は、フレーム ウィンドウによって呼び出すことでメニュー リソースが読み込まれるときに指定された呼び出し`COleIPFrameWndEx::LoadFrame`です。  
  
##  <a name="getdockframe"></a>  COleIPFrameWndEx::GetDockFrame  

  
```  
CFrameWnd* GetDockFrame();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getdockingmanager"></a>  COleIPFrameWndEx::GetDockingManager  

  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getmainframe"></a>  COleIPFrameWndEx::GetMainFrame  

  
```  
CFrameWnd* GetMainFrame();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getmenubar"></a>  COleIPFrameWndEx::GetMenuBar  
 フレーム ウィンドウにアタッチされているメニュー バーのオブジェクトへのポインターを返します。  
  
```  
const CMFCMenuBar* GetMenuBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メニュー バーのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数に属しているメニュー バーのオブジェクトへのポインターの取得を使用して、`COleIPFrameWndEx`オブジェクト。  
  
##  <a name="getpane"></a>  COleIPFrameWndEx::GetPane  

  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettearoffbars"></a>  COleIPFrameWndEx::GetTearOffBars  
 ティアオフ状態にあるウィンドウ オブジェクトの一覧を返します。  
  
```  
const CObList& GetTearOffBars() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照、`CObList`へのポインターのコレクションを格納するオブジェクト、 [CBasePane クラス](../../mfc/reference/cbasepane-class.md)-派生オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `COleIPFrameWndEx`オブジェクトの一覧としてティアオフ メニューのコレクションを保持する[CBasePane クラス](../../mfc/reference/cbasepane-class.md)-派生オブジェクト。 このメソッドを使用すると、この一覧への参照を取得できます。  
  
##  <a name="gettoolbarbuttontooltiptext"></a>  COleIPFrameWndEx::GetToolbarButtonToolTipText  
 ボタンのツールヒントが表示される前に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton* pButton,  
    CString& strTTText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 ボタンへのポインター。  
  
 [入力] `strTTText`  
 ツールヒントのテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、0 を返します。  
  
### <a name="remarks"></a>コメント  
 ツール バー ボタンのツールヒントの表示をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="initusertoobars"></a>  COleIPFrameWndEx::InitUserToobars  
 ユーザー定義のツールバーに、フレームワークを割り当てましているコントロールの Id 範囲を指定します。  
  
```  
void InitUserToolbars(
    LPCTSTR lpszRegEntry,   
    UINT uiUserToolbarFirst,   
    UINT uiUserToolbarLast)  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszRegEntry`  
 レジストリ エントリは、ライブラリがユーザーのツールバーの設定を格納する場所です。  
  
 [入力] `uiUserToolbarFirst`  
 最初のユーザー定義のツールバーに割り当てられているコントロールの ID。  
  
 [入力] `uiUserToolbarLast`  
 最後のユーザー定義のツールバーに割り当てられているコントロールの ID。  
  
### <a name="remarks"></a>コメント  
 この関数を使用して、ユーザーが動的に定義するツールバーへの割り当てにコントロール Id の範囲を初期化します。 パラメーター`uiUserToolbarFirst`と`uiUserToolbarLast`許可されているツール バー コントロール Id の範囲を定義します。 ユーザー定義のツールバーの作成を無効にする設定`uiUserToolbarFirst`または`uiUserToolbarLast`-1 です。  
  
##  <a name="insertpane"></a>  COleIPFrameWndEx::InsertPane  

  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 [入力] `pTarget`  
 [入力] `bAfter`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ismenubaravailable"></a>  COleIPFrameWndEx::IsMenuBarAvailable  
 メニュー バーのオブジェクトへのポインターが `NULL`  
  
```  
BOOL IsMenuBarAvailable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレーム ウィンドウは、メニュー バーがある場合は 0 以外を返します値。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 かどうか、フレーム ウィンドウは、以外を決定するには、このメソッドを呼び出す`NULL`メニュー バーのオブジェクトへのポインター。  
  
##  <a name="ispointneardocksite"></a>  COleIPFrameWndEx::IsPointNearDockSite  

  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 [入力] `dwBarAlignment`  
 [入力] `bOuterEdge`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="loadframe"></a>  COleIPFrameWndEx::LoadFrame  

  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIDResource`  
 [入力] `dwDefaultStyle`  
 [入力] `pParentWnd`  
 [入力] `pContext`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onclosedockingpane"></a>  COleIPFrameWndEx::OnCloseDockingPane  

  
```  
virtual BOOL OnCloseDockingPane(CDockablePane*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CDockablePane*`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oncloseminiframe"></a>  COleIPFrameWndEx::OnCloseMiniFrame  

  
```  
virtual BOOL OnCloseMiniFrame(CPaneFrameWnd*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CPaneFrameWnd*`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onclosepopupmenu"></a>  COleIPFrameWndEx::OnClosePopupMenu  
 アクティブなポップアップ メニューを処理するときに、フレームワークによって呼び出されます、`WM_DESTROY`メッセージ。  
  
```  
virtual void OnClosePopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPopup`  
 ポップアップ メニュー オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 通知を受信するには、このメソッドをオーバーライド`CMFCPopupMenu`オブジェクトを処理するときに`WM_DESTROY`メッセージ。  
  
##  <a name="oncmdmsg"></a>  COleIPFrameWndEx::OnCmdMsg  

  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 [入力] `nCode`  
 [入力] `pExtra`  
 [入力] `pHandlerInfo`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawmenuimage"></a>  COleIPFrameWndEx::OnDrawMenuImage  
 メニュー項目に関連付けられているイメージが描画されるときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrawMenuImage(
    CDC* pDC,  
    const CMFCToolBarMenuButton* pMenuButton,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `pMenuButton`  
 メニュー ボタンへのポインター。  
  
 [入力] `rectImage`  
 メニュー項目に関連付けられているイメージ。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、何も実行し、0 を返します。  
  
### <a name="remarks"></a>コメント  
 所有するメニュー バーに属しているメニュー項目のイメージの描画をカスタマイズする場合は、このメソッドをオーバーライド、 `COleIPFrameWndEx`-派生オブジェクト。  
  
##  <a name="ondrawmenulogo"></a>  COleIPFrameWndEx::OnDrawMenuLogo  
 フレームワークによって呼び出されますときに、 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトのプロセス、`WM_PAINT`メッセージ。  
  
```  
virtual void OnDrawMenuLogo(
    CDC* pDC,  
    CMFCPopupMenu* pMenu,  
    const CRect& rectLogo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `pMenu`  
 ポップアップ メニュー オブジェクトへのポインター。  
  
 [入力] `rectLogo`  
 表示するロゴへのポインター。  
  
### <a name="remarks"></a>コメント  
 所有するメニュー バーに関連付けられたポップアップ メニューにロゴを表示するには、このメソッドをオーバーライドして、 `COleIPFrameWndEx`-派生オブジェクト。 既定の実装では、何も行われません。  
  
##  <a name="onmenubuttontoolhittest"></a>  COleIPFrameWndEx::OnMenuButtonToolHitTest  
 フレームワークによって呼び出されますときに、 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)オブジェクトのプロセス、`WM_NCHITTEST`メッセージ。  
  
```  
virtual BOOL OnMenuButtonToolHitTest(
    CMFCToolBarButton* pButton,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>パラメーター  
 [in] pButton  
 メニュー ボタンへのポインター。  
  
 [out] pTI  
 `TOOLINFO` 構造体へのポインター。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、何も実行し、0 を返します。 空き領域がなくなる場合、実装には 0 以外の値を返す必要があります、`pTI`パラメーター。  
  
### <a name="remarks"></a>コメント  
 特定のメニュー項目のツールヒント情報を提供するには、このメソッドをオーバーライドします。  
  
##  <a name="onmoveminiframe"></a>  COleIPFrameWndEx::OnMoveMiniFrame  

  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pFrame`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onsetpreviewmode"></a>  COleIPFrameWndEx::OnSetPreviewMode  

  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bPreview`  
 [入力] `pState`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowcustomizepane"></a>  COleIPFrameWndEx::OnShowCustomizePane  

  
```  
virtual BOOL OnShowCustomizePane(
    CMFCPopupMenu* pMenuPane,  
    UINT uiToolbarID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPane`  
 [入力] `uiToolbarID`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowpanes"></a>  COleIPFrameWndEx::OnShowPanes  

  
```  
virtual BOOL OnShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onshowpopupmenu"></a>  COleIPFrameWndEx::OnShowPopupMenu  
 ポップアップ メニューが表示されたときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnShowPopupMenu(CMFCPopupMenu* pMenuPopup);
```  
  
### <a name="parameters"></a>パラメーター  
 `[in] pMenuPopup`  
 表示されるポップアップ メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 既定の実装では、何も実行し、0 以外の値を返します。 実装を返す必要があります`FALSE`ポップアップ メニューを表示できない場合。  
  
### <a name="remarks"></a>コメント  
 ポップアップ メニューの表示をカスタマイズするには、このメソッドをオーバーライドします。 たとえば、色のメニュー項目にメニュー ボタンを変更またはティアオフ バーを初期化することができます。  
  
##  <a name="ontearoffmenu"></a>  COleIPFrameWndEx::OnTearOffMenu  
 ティアオフ バーのあるメニューを選択すると、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnTearOffMenu(
    CMFCPopupMenu* pMenuPopup,  
    CPane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMenuPopup`  
 ユーザーが選択されているポップアップ メニューへのポインター。  
  
 [入力] `pBar`  
 メニューをホストするウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ポップアップ メニューをアクティブにする場合それ以外の場合`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
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
 [入力] `point`  
 [入力] `nSensitivity`  
 [入力] `bExactBar`  
 [入力] `pRTCBarType`  
 [入力] `dwAlignment`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="pretranslatemessage"></a>  COleIPFrameWndEx::PreTranslateMessage  

  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMsg`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="recalclayout"></a>  COleIPFrameWndEx::RecalcLayout  

  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNotify`  
  
### <a name="remarks"></a>コメント  
  
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
 [入力] `pControlBar`  
 [入力] `bDestroy`  
 [入力] `bAdjustLayout`  
 [入力] `bAutoHide`  
 [入力] `pBarReplacement`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setdockstate"></a>  COleIPFrameWndEx::SetDockState  
 フレーム ウィンドウに属しているウィンドウを指定されたドッキング状態を適用します。  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `state`  
 ドッキング状態を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数に属しているウィンドウの新しいドッキング状態を指定を使用して、`COleIPFrameWndEx`オブジェクト。  
  
##  <a name="setuptoolbarmenu"></a>  COleIPFrameWndEx::SetupToolbarMenu  
 ダミーの項目を検索して、指定されたユーザー定義の項目で置き換えることで、ツールバーのオブジェクトを変更します。  
  
```  
void SetupToolbarMenu(
    CMenu& menu,  
    const UINT uiViewUserToolbarCmdFirst,  
    const UINT uiViewUserToolbarCmdLast);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `menu`  
 参照、 [CMenu](../../mfc/reference/cmenu-class.md)オブジェクトを変更できます。  
  
 [入力] `uiViewUserToolbarCmdFirst`  
 ユーザー定義の最初のコマンドを指定します。  
  
 [入力] `uiViewUserToolbarCmdLast`  
 ユーザー定義の最後のコマンドを指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="showpane"></a>  COleIPFrameWndEx::ShowPane  

  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 [入力] `bShow`  
 [入力] `bDelay`  
 [入力] `bActivate`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="winhelpa"></a>  COleIPFrameWndEx::WinHelpA  
 WinHelp アプリケーションまたはコンテキスト ヘルプを起動するために、フレームワークによって呼び出されます。  
  
```  
virtual void WinHelp(
    DWORD dwData,  
    UINT nCmd = HELP_CONTEXT);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] dwData  
 `nCmd`で指定されたヘルプの種類に必要とされるデータを指定します。  
  
 [入力] `nCmd`  
 要求されるヘルプの種類を指定します。 有効な値の一覧と `dwData` パラメーターに与える影響については、Windows SDK の「 [WinHelp 関数](http://msdn.microsoft.com/library/windows/desktop/bb762267) 」を参照してください。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)
