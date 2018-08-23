---
title: CMDIChildWndEx クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx
- AFXMDICHILDWNDEX/CMDIChildWndEx::ActivateTopLevelFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AddTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::AdjustDockingLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnMDITabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnTaskBarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::CanShowOnWindowsList
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::DockPaneLeftOf
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableAutoHidePanes
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableDocking
- AFXMDICHILDWNDEX/CMDIChildWndEx::EnableTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDockingManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetDocumentName
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameIcon
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetFrameText
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTabProxyWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarPreviewWnd
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::GetToolbarButtonToolTipText
- AFXMDICHILDWNDEX/CMDIChildWndEx::InsertPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::InvalidateIconicBitmaps
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsPointNearDockSite
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsReadOnly
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsRegisteredWithTaskbarTabs
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTabbedPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarTabsSupportEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled
- AFXMDICHILDWNDEX/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicLivePreviewBitmap
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnGetIconicThumbnail
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnMoveMiniFrame
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnSetPreviewMode
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnTaskbarTabThumbnailStretch
- AFXMDICHILDWNDEX/CMDIChildWndEx::OnUpdateFrameTitle
- AFXMDICHILDWNDEX/CMDIChildWndEx::PaneFromPoint
- AFXMDICHILDWNDEX/CMDIChildWndEx::RecalcLayout
- AFXMDICHILDWNDEX/CMDIChildWndEx::RegisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::RemovePaneFromDockManager
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetRelatedTabGroup
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabActive
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabOrder
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarTabProperties
- AFXMDICHILDWNDEX/CMDIChildWndEx::SetTaskbarThumbnailClipRect
- AFXMDICHILDWNDEX/CMDIChildWndEx::ShowPane
- AFXMDICHILDWNDEX/CMDIChildWndEx::UnregisterTaskbarTab
- AFXMDICHILDWNDEX/CMDIChildWndEx::UpdateTaskbarTabIcon
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWndEx [MFC], ActivateTopLevelFrame
- CMDIChildWndEx [MFC], AddPane
- CMDIChildWndEx [MFC], AddTabbedPane
- CMDIChildWndEx [MFC], AdjustDockingLayout
- CMDIChildWndEx [MFC], CanShowOnMDITabs
- CMDIChildWndEx [MFC], CanShowOnTaskBarTabs
- CMDIChildWndEx [MFC], CanShowOnWindowsList
- CMDIChildWndEx [MFC], DockPane
- CMDIChildWndEx [MFC], DockPaneLeftOf
- CMDIChildWndEx [MFC], EnableAutoHidePanes
- CMDIChildWndEx [MFC], EnableDocking
- CMDIChildWndEx [MFC], EnableTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetDockingManager
- CMDIChildWndEx [MFC], GetDocumentName
- CMDIChildWndEx [MFC], GetFrameIcon
- CMDIChildWndEx [MFC], GetFrameText
- CMDIChildWndEx [MFC], GetPane
- CMDIChildWndEx [MFC], GetRelatedTabGroup
- CMDIChildWndEx [MFC], GetTabbedPane
- CMDIChildWndEx [MFC], GetTabProxyWnd
- CMDIChildWndEx [MFC], GetTaskbarPreviewWnd
- CMDIChildWndEx [MFC], GetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], GetToolbarButtonToolTipText
- CMDIChildWndEx [MFC], InsertPane
- CMDIChildWndEx [MFC], InvalidateIconicBitmaps
- CMDIChildWndEx [MFC], IsPointNearDockSite
- CMDIChildWndEx [MFC], IsReadOnly
- CMDIChildWndEx [MFC], IsRegisteredWithTaskbarTabs
- CMDIChildWndEx [MFC], IsTabbedPane
- CMDIChildWndEx [MFC], IsTaskbarTabsSupportEnabled
- CMDIChildWndEx [MFC], IsTaskbarThumbnailClipRectEnabled
- CMDIChildWndEx [MFC], m_dwDefaultTaskbarTabPropertyFlags
- CMDIChildWndEx [MFC], OnGetIconicLivePreviewBitmap
- CMDIChildWndEx [MFC], OnGetIconicThumbnail
- CMDIChildWndEx [MFC], OnMoveMiniFrame
- CMDIChildWndEx [MFC], OnPressTaskbarThmbnailCloseButton
- CMDIChildWndEx [MFC], OnSetPreviewMode
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailMouseActivate
- CMDIChildWndEx [MFC], OnTaskbarTabThumbnailStretch
- CMDIChildWndEx [MFC], OnUpdateFrameTitle
- CMDIChildWndEx [MFC], PaneFromPoint
- CMDIChildWndEx [MFC], RecalcLayout
- CMDIChildWndEx [MFC], RegisterTaskbarTab
- CMDIChildWndEx [MFC], RemovePaneFromDockManager
- CMDIChildWndEx [MFC], SetRelatedTabGroup
- CMDIChildWndEx [MFC], SetTaskbarTabActive
- CMDIChildWndEx [MFC], SetTaskbarTabOrder
- CMDIChildWndEx [MFC], SetTaskbarTabProperties
- CMDIChildWndEx [MFC], SetTaskbarThumbnailClipRect
- CMDIChildWndEx [MFC], ShowPane
- CMDIChildWndEx [MFC], UnregisterTaskbarTab
- CMDIChildWndEx [MFC], UpdateTaskbarTabIcon
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 091c201b3b0b67879178d32f495410a1bbe22a53
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2018
ms.locfileid: "42541461"
---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx クラス
`CMDIChildWndEx`マルチ ドキュメント インターフェイス (MDI) 子ウィンドウに、Windows の機能を提供するクラス。 機能を拡張[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)します。 ある特定の MFC クラスを MDI アプリケーションで使用するときは、フレームワークにこのクラスが必要です。  
 
 詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。  

  
## <a name="syntax"></a>構文  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|タスク バー タブから、アプリケーションをアクティブ化するときに、トップ レベルのフレームをアクティブ化するためにフレームワークによって内部的に呼び出されます。|  
|`CMDIChildWndEx::AddDockSite`|このメソッドを実装または使用されていません。|  
|[CMDIChildWndEx::AddPane](#addpane)|ペインを追加します。|  
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|タブ付きペインを追加します。|  
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|ドッキング レイアウトを調整します。|  
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|Windows 7 タスク バーのタブでこの MDI 子フォームを表示できるかどうかをフレームワークに指示します。|  
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|MDI 子ウィンドウの名前で表示できる場合は TRUE を返します、 [CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) ダイアログ ボックス。 それ以外の場合、FALSE を返します。|  
|`CMDIChildWndEx::CreateObject`|このクラス型の動的インスタンスを作成するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::DockPane](#dockpane)|ペインをドッキングします。|  
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|ウィンドウを別のウィンドウの左側にドッキングします。|  
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|により自動的に隠すウィンドウ モード、ウィンドウの指定した辺にドッキングされている場合。|  
|[CMDIChildWndEx::EnableDocking](#enabledocking)|メイン フレームに子ウィンドウのドッキングを有効にします。|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|有効またはウィンドウのクライアント領域の一部の自動選択を無効にします。|  
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||  
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|MDI 子ウィンドウに表示されるドキュメントの名前を返します。|  
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|MDI 子ウィンドウのアイコンを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetFrameText](#getframetext)|MDI 子ウィンドウのテキストを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetPane](#getpane)|指定したコントロール ID によってペインを検索します|  
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||  
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|タブ付きドキュメントに変換された埋め込みのドッキング ペインへのポインターを返します。|  
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|タブの Windows 7 タスク バーのタブに実際に登録されているプロキシ ウィンドウを返します。|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Windows 7 タスク バーのタブのサムネイルに表示する子ウィンドウ (通常はビューまたは分割ウィンドウ) を取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|ウィンドウのクライアント領域の一部を選択する必要があるときに、フレームワークによって呼び出されます。|  
|`CMDIChildWndEx::GetThisClass`|ポインターを取得するためにフレームワークによって呼び出される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|ツール バー ボタンのツールヒントを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::InsertPane](#insertpane)|指定したウィンドウをドッキング マネージャーに登録します。|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|MDI 子フォームのアイコンのビットマップ表現を無効にします。|  
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|指定したポイントがドッキング サイトに近いかどうかを判断します。|  
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|子ウィンドウに表示されているドキュメントが読み取り専用の場合は、TRUE を返します。 それ以外の場合、FALSE を返します。|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|MDI 子ウィンドウに Windows 7 タスク バーのタブが正常に登録されている場合は、TRUE を返します。|  
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|MDI 子ウィンドウには、ドッキング ペインが含まれている場合は、TRUE を返します。 それ以外の場合、FALSE を返します。|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|Windows 7 タスク バーのタブに、MDI 子フォームを表示できるかどうかを指示します。|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|ウィンドウのクライアント領域の一部の自動選択が有効になっているかどうかを指示します。|  
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|フレームワークによって、SetTaskbarTabProperties メソッドは、タブ (MDI 子) に渡されるフラグの組み合わせは、Windows 7 タスク バーのタブに登録しています。 既定の組み合わせが STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE します。|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|MDI 子フォームのライブ プレビューのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|MDI 子フォームのアイコンのサムネイルのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|ユーザーがタスク バーのタブのサムネイルの閉じるボタンを押したときに、フレームワークによって呼び出されます.|  
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|入力するか、印刷プレビュー モードを終了するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|タスク バーのタブのサムネイルは WM_ACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|タスク バーのタブのサムネイルが WM_MOUSEACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|MDI 子フォームの Windows 7 タスク バー タブの縮小表示プレビューのビットマップを拡大する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|フレームのタイトルを更新するためにフレームワークによって呼び出されます。 (`CMDIChildWnd::OnUpdateFrameTitle` をオーバーライドします)。|  
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|指定したポイントを含むペインを返します。|  
|`CMDIChildWndEx::PreTranslateMessage`|[TranslateMessage](../../mfc/reference/cwinapp-class.md) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) の各 Windows 関数にディスパッチされる前に、ウィンドウ メッセージを変換するためにクラス [CWinApp](http://msdn.microsoft.com/library/windows/desktop/ms644934) で使用されます。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|  
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|ウィンドウのレイアウトを再計算します。|  
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Windows 7 タスク バーのタブ付き MDI 子フォームを登録します。|  
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|ドッキング マネージャーから、ウィンドウを削除します。|  
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||  
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|対応する Windows 7 タスク バーのタブがアクティブにします。|  
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Windows 7 タスク バーのタブで指定されたウィンドウの前に MDI 子フォームを挿入します。|  
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Windows 7 のタスクバー タブのプロパティを設定します。|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|ウィンドウのクライアント領域の一部を選択するクリッピング四角形を設定するためにフレームワークによって内部的に呼び出されます。|  
|[CMDIChildWndEx::ShowPane](#showpane)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Windows 7 タスク バーのタブからは、MDI 子フォームを削除します。|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Windows 7 タスク バーのタブのアイコンを更新します。|  
  
## <a name="remarks"></a>Remarks  
 MDI アプリケーションでドッキングの拡張機能を利用するアプリケーションの MDI 子ウィンドウ クラスを派生`CMDIChildWndEx`の代わりに[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、派生クラスから`CMDIChildWndEx`します。 このコード スニペットに由来、 [VisualStudioDemo サンプル: Visual Studio アプリケーションを MFC](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxMDIChildWndEx.h  
  
##  <a name="addpane"></a>  CMDIChildWndEx::AddPane  
 ペインを追加します。  
  
```  
BOOL AddPane(
    CBasePane* pControlBar,  
    BOOL bTail = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pControlBar*  
 ペインへのポインター。  
  
 [in]*bTail*  
 ペインの一覧の末尾に、ドッキング マネージャーに、ウィンドウを追加する場合は TRUEそれ以外の場合、FALSE です。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、ウィンドウはドッキング マネージャーに正常に登録されましたそれ以外の場合、FALSE です。  
  
##  <a name="addtabbedpane"></a>  CMDIChildWndEx::AddTabbedPane  
 タブ付きペインを追加します。  
  
```  
void AddTabbedPane(CDockablePane* pControlBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pControlBar*  
 ペインへのポインター。  
  
##  <a name="adjustdockinglayout"></a>  CMDIChildWndEx::AdjustDockingLayout  
 ドッキング レイアウトを調整します。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hdwp*  
 遅延のウィンドウの位置の構造体へのハンドルします。  
  
##  <a name="canshowonmditabs"></a>  CMDIChildWndEx::CanShowOnMDITabs  

  
```  
virtual BOOL CanShowOnMDITabs();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="canshowonwindowslist"></a>  CMDIChildWndEx::CanShowOnWindowsList  
 MDI 子ウィンドウの名前を表示できるかどうかを指定します、 [CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) ダイアログ ボックス。  
  
```  
virtual BOOL CanShowOnWindowsList();
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウを表示できる場合は TRUE、 **Windows**  ダイアログ ボックス場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 派生クラスでは、このメソッドをオーバーライドしで、ウィンドウを表示するかしない場合は FALSE を返します、 **Windows**  ダイアログ ボックス。 この関数から`CMFCWindowsManagerDialog`します。  
  
##  <a name="dockpane"></a>  CMDIChildWndEx::DockPane  
 ペインをドッキングします。  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 ペインへのポインター。  
  
 [in]*辺*  
 ペインの ID。  
  
 [in]*lpRect*  
 四角形へのポインター。  
  
### <a name="remarks"></a>Remarks  
 *LpRect*パラメーターは使用されません。  
  
##  <a name="dockpaneleftof"></a>  CMDIChildWndEx::DockPaneLeftOf  
 ウィンドウを別のウィンドウの左側にドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBar,  
    CPane* pLeftOf);
```  
  
### <a name="parameters"></a>パラメーター  
 *pBar*  
 ドッキング ウィンドウへのポインター。  
  
 *pLeftOf*  
 参照のポイントとして機能するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、失敗した場合にします。  
  
### <a name="remarks"></a>Remarks  
 このメソッドで指定されたウィンドウは、 *pBar*で指定されたウィンドウの左側にドッキングと*pLeftOf*します。  
  
 事前定義された順序でいくつかのペインをドッキングする場合に、このメソッドを呼び出します。  
  
##  <a name="enableautohidepanes"></a>  CMDIChildWndEx::EnableAutoHidePanes  
 により自動的に隠すウィンドウ モード、ウィンドウの指定した辺にドッキングされている場合。  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwDockStyle*  
 有効になっているメイン フレーム ウィンドウの辺を指定します。 次のフラグの 1 つ以上を使用します。  
  
- CBRS_ALIGN_LEFT  
  
- CBRS_ALIGN_RIGHT  
  
- CBRS_ALIGN_TOP  
  
- CBRS_ALIGN_BOTTOM  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="enabledocking"></a>  CMDIChildWndEx::EnableDocking  
 メイン フレームに子ウィンドウのドッキングを有効にします。  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwDockStyle*  
 有効にするドッキングの配置を指定します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 メイン フレームにドッキングの配置を有効にするには、このメソッドを呼び出します。 Cbrs_align _ フラグの組み合わせを渡すことができます (詳細については、次を参照してください。 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking))。  
  
##  <a name="getdockingmanager"></a>  CMDIChildWndEx::GetDockingManager  

  
```  
CDockingManager* GetDockingManager();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getdocumentname"></a>  CMDIChildWndEx::GetDocumentName  
 MDI 子ウィンドウに表示されるドキュメントの名前を返します。  
  
```  
virtual LPCTSTR GetDocumentName(CObject** pObj);
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントの名前を含む文字列へのポインター。  
  
### <a name="remarks"></a>Remarks  
 ドキュメントは、MDI 子ウィンドウが表示されます。 一般に、ウィンドウから読み込まれた、またはファイルに保存されるデータが表示されます。 そのため、ドキュメントの名前は、ファイルの名前です。 既定の実装`GetDocumentName`から取得した文字列を返します`CDocument::GetPathName`します。  
  
 ウィンドウには、ファイルから読み込まれていないドキュメントが表示されている場合は、派生クラスでこのメソッドをオーバーライドし、ドキュメントの一意の識別子を返します。  
  
 `GetDocumentName` すべての開いているドキュメントの状態を保存するときに、フレームワークによって呼び出されます。 返される文字列は、レジストリに書き込まれます。  
  
 ドキュメント名がレジストリから読み取るしに渡されるフレームワークでは、後で状態を復元は、 [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow)します。 このメソッドをオーバーライドする[CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-派生クラスと作成またはこの名前を持つドキュメントを開き、この名前を持つファイルの読み取り。 ドキュメントがファイルに基づいていない場合、は、ドキュメント識別子自体に基づくドキュメントを作成します。 保存し、ドキュメントを復元する場合にのみ、上記の操作を行う必要があります。  
  
### <a name="example"></a>例  
 `GetDocumentName` メソッドの使用例を次に示します。 このコード スニペットに由来、 [VisualStudioDemo サンプル: Visual Studio アプリケーションを MFC](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#17](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]  
  
##  <a name="getframeicon"></a>  CMDIChildWndEx::GetFrameIcon  
 MDI 子ウィンドウのアイコンを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual HICON GetFrameIcon() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ アイコンへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、MDI 子フレーム ウィンドウを含む MDI タブに表示するには、どのようなアイコンを決定するためにフレームワークによって呼び出されます。  
  
 既定では、このメソッドは、ウィンドウのアイコンを返します。 オーバーライド`GetFrameIcon`で、 `CMDIChildWndEx`-この動作をカスタマイズするクラスを派生します。  
  
##  <a name="getframetext"></a>  CMDIChildWndEx::GetFrameText  
 MDI 子ウィンドウのテキストを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual CString GetFrameText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレーム ウィンドウのテキストを含む文字列。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、MDI 子フレーム ウィンドウを含む MDI タブに表示するには、どのようなテキストを決定するためにフレームワークによって呼び出されます。  
  
 既定では、このメソッドは、ウィンドウのテキストを返します。 オーバーライド`GetFrameText`で、 `CMDIChildWndEx`-この動作をカスタマイズするクラスを派生します。  
  
##  <a name="getpane"></a>  CMDIChildWndEx::GetPane  
 指定したコントロール ID によってペインを検索します  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nID*  
 検索する、ウィンドウのコントロール ID。  
  
### <a name="return-value"></a>戻り値  
 見つかった場合 NULL それ以外の場合、ウィンドウへのポインター。  
  
##  <a name="getrelatedtabgroup"></a>  CMDIChildWndEx::GetRelatedTabGroup  

  
```  
CMFCTabCtrl* GetRelatedTabGroup();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gettabbedpane"></a>  CMDIChildWndEx::GetTabbedPane  
 タブ付きドキュメントの MDI のグループの一部であるドッキング ペインへのポインターを返します。  
  
```  
CDockablePane* GetTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ付きドキュメントの MDI のグループの一部であるドッキング ペインへのポインター。  
  
##  <a name="gettoolbarbuttontooltiptext"></a>  CMDIChildWndEx::GetToolbarButtonToolTipText  
 ツール バー ボタンのツールヒントを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*, 
    CString&);
```  
  
### <a name="return-value"></a>戻り値  
 ツールヒントが表示されている場合は TRUE。 既定の実装では、FALSE を返します。  
  
### <a name="remarks"></a>Remarks  
 ツール バー ボタンのカスタム ツール ヒントを表示したい場合は、このメソッドをオーバーライドします。  
  
##  <a name="insertpane"></a>  CMDIChildWndEx::InsertPane  
 指定したウィンドウをドッキング マネージャーに登録します。  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pControlBar*  
 挿入するウィンドウへのポインター。  
  
 [in]*pTarget*  
 隣接するウィンドウへのポインター。  
  
 [in]*bAfter*  
 TRUE の場合、 *pControlBar*後に挿入されます*pTarget*します。 FALSE の場合、 *pControlBar*前に挿入されます*pTarget*します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合、FALSE それ以外の場合は TRUE。  
  
##  <a name="ispointneardocksite"></a>  CMDIChildWndEx::IsPointNearDockSite  
 指定したポイントがドッキング サイトに近いかどうかを判断します。  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 指定した点。  
  
 [in]*dwBarAlignment*  
 どちらの端点が近いを指定します。 指定できる値は CBRS_ALIGN_LEFT、CBRS_ALIGN_RIGHT、CBRS_ALIGN_TOP、および CBRS_ALIGN_BOTTOM です。  
  
 [in]*bOuterEdge*  
 ポイントが、ドッキング サイトの外側の境界線の近くにある場合は TRUE。FALSE それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 点がドッキング サイトに近い場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ポイントは、ドッキング マネージャーで設定された感度内にある場合に、ドッキング サイトに近いです。 既定の感度は、15 ピクセルです。  
  
##  <a name="isreadonly"></a>  CMDIChildWndEx::IsReadOnly  
 子ウィンドウに表示されているドキュメントが読み取り専用かどうかを指定します。  
  
```  
virtual BOOL IsReadOnly();
```  
  
### <a name="return-value"></a>戻り値  
 ドキュメントが読み取り専用である場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 この関数の使用を防ぐために読み取り専用の文書を保存します。  
  
### <a name="example"></a>例  
 次の例は、オーバーライド、`IsReadOnly`メソッド。 このコード スニペットに由来、 [VisualStudioDemo サンプル: Visual Studio アプリケーションを MFC](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#2](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]  
  
##  <a name="istabbedpane"></a>  CMDIChildWndEx::IsTabbedPane  
 MDI 子ウィンドウがドッキング ペインを含むかどうかを指定します。  
  
```  
BOOL IsTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 MDI 子ウィンドウには、タブ付きドキュメントに変換されたドッキング ペインが含まれている場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="onmoveminiframe"></a>  CMDIChildWndEx::OnMoveMiniFrame  
 ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pFrame*  
 ミニフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、メソッドが成功した場合は FALSE。  
  
##  <a name="onsetpreviewmode"></a>  CMDIChildWndEx::OnSetPreviewMode  
 入力するか、印刷プレビュー モードを終了するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bPreview*  
 TRUE の場合は、印刷プレビュー モードを入力します。 FALSE の場合、終了印刷プレビュー モードです。  
  
 [in]*pState*  
 印刷プレビュー状態の構造体へのポインター。  
  
##  <a name="onupdateframetitle"></a>  CMDIChildWndEx::OnUpdateFrameTitle  
 フレームのタイトルを更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bAddToTitle*  
 TRUE の場合は、タイトルにドキュメント名を追加します。  
  
##  <a name="panefrompoint"></a>  CMDIChildWndEx::PaneFromPoint  
 指定したポイントを含むペインを返します。  
  
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
 [in]*ポイント*  
 確認の画面座標で、ポイントを指定します。  
  
 [in]*nSensitivity*  
 この金額には、検索領域を増やします。 ペインは、指定したポイントが拡大された領域内にある場合に、検索条件を満たします。  
  
 [in]*bExactBar*  
 無視する場合は TRUE、 *nSensitivity*パラメーター場合は FALSE。  
  
 [in]*pRTCBarType*  
 NULL 以外の場合、メソッドは、指定した型のウィンドウだけを検索します。  
  
 [in]*場合*  
 指定した時点で、ウィンドウが見つかった場合、このパラメーターには、指定したポイントに最も近いいたペインの横にはが含まれています。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `CBasePane`-ウィンドウが見つからなかった場合は、特定のポイント、または NULL を含む派生オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 ランタイム クラスと可視性など、指定した条件に従って、指定したポイントがウィンドウに含まれるかどうかを確認するには、このメソッドを呼び出します。  
  
 関数に戻り、ペインが検出されましたが、*場合*指定した点の配置が含まれています。 たとえば、次の点が、ウィンドウの上部に最も近い*場合*CBRS_ALIGN_TOP に設定されます。  
  
##  <a name="recalclayout"></a>  CMDIChildWndEx::RecalcLayout  
 ウィンドウのレイアウトを再計算します。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bNotify*  
 TRUE の場合、ウィンドウのアクティブなインプレース項目は、レイアウトの変更の通知を受け取ります。  
  
##  <a name="removepanefromdockmanager"></a>  CMDIChildWndEx::RemovePaneFromDockManager  
 ドッキング マネージャーから、ウィンドウを削除します。  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pControlBar,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide,  
    CBasePane* pBarReplacement);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pControlBar*  
 削除するウィンドウへのポインター。  
  
 [in]*bDestroy*  
 TRUE の場合、削除されたウィンドウが破棄されます。  
  
 [in]*bAdjustLayout*  
 TRUE の場合は、すぐにドッキング レイアウトを調整します。  
  
 [in]*bAutoHide*  
 TRUE の場合、ドッキング レイアウトは自動的に隠すバーのリストに関連します。 FALSE の場合、ドッキング レイアウトに関連する標準のペインの一覧。  
  
 [in]*pBarReplacement*  
 削除されたウィンドウを置換するウィンドウへのポインター。  
  
##  <a name="setrelatedtabgroup"></a>  CMDIChildWndEx::SetRelatedTabGroup  

  
```  
void SetRelatedTabGroup(CMFCTabCtrl* p);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*p*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="showpane"></a>  CMDIChildWndEx::ShowPane  

  
```  
void ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 [in]*bShow*  
 [in]*bDelay*  
 [in]*bActivate*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="updatetaskbartabicon"></a>  CMDIChildWndEx::UpdateTaskbarTabIcon  
 Windows 7 タスク バーのタブのアイコンを更新します。  
  
```  
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 *hIcon*  
 Windows 7 タスク バーのタブに表示するアイコンへのハンドル。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="unregistertaskbartab"></a>  CMDIChildWndEx::UnregisterTaskbarTab  
 Windows 7 タスク バーのタブから、MDI 子フォームを削除します。  
  
```  
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bCheckRegisteredMDIChildCount*  
 この関数が MDI 子フォーム MDI タブに登録されている数を確認する必要があるかどうかを指定します。 この番号が 0 の場合、この関数は、アプリケーションのタスク バーのサムネイルからクリッピング四角形を削除します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbarthumbnailcliprect"></a>  CMDIChildWndEx::SetTaskbarThumbnailClipRect  
 ウィンドウのクライアント領域の一部を選択するクリッピング四角形を設定するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 新しいクリッピング四角形を指定します。 四角形が空または null の場合は、クリッピングは削除されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は TRUE、それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbartabproperties"></a>  CMDIChildWndEx::SetTaskbarTabProperties  
 Windows 7 のタスクバー タブのプロパティを設定します。  
  
```  
void SetTaskbarTabProperties(DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 STPFLAG の値の組み合わせ。 詳細については、次を参照してください。 [itaskbarlist 4::settabproperties](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-itaskbarlist4-settabproperties)します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbartaborder"></a>  CMDIChildWndEx::SetTaskbarTabOrder  
 Windows 7 タスク バーのタブで指定したウィンドウの前に、MDI 子フォームを挿入します。  
  
```  
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndBefore*  
 左側にあるサムネイルを挿入する MDI 子ウィンドウへのポインター。 このウィンドウを登録する必要が既に`RegisterTaskbarTab`します。 この値が NULL の場合は、新しいサムネイルがリストの末尾に追加されます。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbartabactive"></a>  CMDIChildWndEx::SetTaskbarTabActive  
 対応する Windows 7 タスク バーのタブがアクティブにします。  
  
```  
void SetTaskbarTabActive();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="registertaskbartab"></a>  CMDIChildWndEx::RegisterTaskbarTab  
 Windows 7 タスク バーのタブ付き MDI 子ウィンドウを登録します。  
  
```  
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndBefore*  
 左側にあるサムネイルを挿入する MDI 子ウィンドウへのポインター。 このウィンドウを登録する必要が既に`RegisterTaskbarTab`します。 この値が NULL の場合は、新しいサムネイルがリストの末尾に追加されます。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ontaskbartabthumbnailstretch"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailStretch  
 MDI 子ウィンドウの Windows 7 タスクバー タブ縮小表示プレビューのビットマップを拡大する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,  
    const CRect& rectDst,  
    HBITMAP hBmpSrc,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *hBmpDst*  
 コピー先ビットマップへのハンドル。  
  
 *rectDst*  
 先の四角形を指定します。  
  
 *hBmpSrc*  
 ソース ビットマップへのハンドル。  
  
 *rectSrc*  
 元の四角形を指定します。  
  
### <a name="remarks"></a>Remarks  
 要件: afxmdichildwndex.h  
  
##  <a name="ontaskbartabthumbnailmouseactivate"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate  
 タスク バーのタブのサムネイルが WM_MOUSEACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDesktopWnd*  
 アクティブ化されているウィンドウの最上位の親ウィンドウへのポインターを指定します。 ポインターは、一時的な場合があり、保存してはなりません。  
  
 *nHitTest*  
 ヒット テスト領域のコードを指定します。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 *message*  
 マウス メッセージの数を指定します。  
  
### <a name="remarks"></a>Remarks  
 既定の実装には、関連する MDI 子フレームがアクティブにします。  
  
##  <a name="ontaskbartabthumbnailactivate"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailActivate  
 タスク バーのタブのサムネイルは WM_ACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,  
    CWnd* pWndOther,  
    BOOL bMinimized);
```  
  
### <a name="parameters"></a>パラメーター  
 *状態*  
 指定するかどうか、`CWnd`がアクティブまたは非アクティブ化します。  
  
 *pWndOther*  
 ポインター、`CWnd`アクティブまたは非アクティブ化します。 ポインターが NULL にできるし、は一時的なものです。  
  
 *bMinimized*  
 最小化された状態を指定します、`CWnd`アクティブまたは非アクティブ化します。 TRUE の値は、ウィンドウが最小化を示します。  
  
### <a name="remarks"></a>Remarks  
 既定の実装には、関連する MDI 子フレームがアクティブにします。  
  
##  <a name="onpresstaskbarthmbnailclosebutton"></a>  CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton  
 ユーザーがタスク バーのタブのサムネイルの閉じるボタンを押したときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnPressTaskbarThmbnailCloseButton();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ongeticonicthumbnail"></a>  CMDIChildWndEx::OnGetIconicThumbnail  
 MDI 子ウィンドウのアイコンのサムネイルのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>パラメーター  
 *nWidth*  
 必要なビットマップの幅を指定します。  
  
 *パラメーター nHeight*  
 必要なビットマップの高さを指定します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ongeticoniclivepreviewbitmap"></a>  CMDIChildWndEx::OnGetIconicLivePreviewBitmap  
 MDI 子ウィンドウのライブ プレビューのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,  
    CPoint& ptLocation);
```  
  
### <a name="parameters"></a>パラメーター  
 *bIsMDIChildActive*  
 現在アクティブな MDI 子のビットマップが要求され、メイン ウィンドウが最小化されていない場合、このパラメーターは TRUE です。 既定の処理をここでは、メイン ウィンドウのスナップショットを取得します。  
  
 *ptLocation*  
 ビットマップの場所を指定して、メインの (最上位レベル) ウィンドウのクライアント座標。 呼び出し先によっては、このポイントを指定する必要があります。  
  
### <a name="return-value"></a>戻り値  
 処理がある場合、有効な 32 bpp のビットマップへのハンドルを返すそれ以外の場合 NULL です。  
  
### <a name="remarks"></a>Remarks  
 派生クラスでは、このメソッドをオーバーライドし、MDI 子フォームのライブ プレビューの有効な 32 bpp のビットマップを返します。 MDI 子ウィンドウは、Windows 7 タスク バーのタブに表示される場合にのみ、このメソッドが呼び出されます。 MFC が既定のハンドラーを呼び出すし、ビットマップを使用してを取得します。 NULL を返す場合`PrintClient`または`PrintWindow`します。  
  
##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>  CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags  
 フレームワークによって渡されるフラグの組み合わせ、`SetTaskbarTabProperties`メソッドは、タブ (MDI 子フォームでは、Windows 7 タスク バーのタブに登録しています。  
  
```  
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;  
```  
  
### <a name="remarks"></a>Remarks  
 既定の組み合わせが STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE します。  
  
##  <a name="istaskbarthumbnailcliprectenabled"></a>  CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled  
 ウィンドウのクライアント領域の一部の自動選択が有効になっているかどうかを指示します。  
  
```  
BOOL IsTaskbarThumbnailClipRectEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 表示するウィンドウのクライアント領域の一部を返します。 TRUE の場合、自動選択を有効にすると;それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="istaskbartabssupportenabled"></a>  CMDIChildWndEx::IsTaskbarTabsSupportEnabled  
 Windows 7 タスク バーのタブに、MDI 子フォームを表示できるかどうかを指示します。  
  
```  
BOOL IsTaskbarTabsSupportEnabled();
```  
  
### <a name="return-value"></a>戻り値  
 Windows 7 タスク バーのタブ; に MDI 子ウィンドウが表示できる場合は TRUE。MDI 子ウィンドウは Windows 7 タスク バーのタブに表示されない場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isregisteredwithtaskbartabs"></a>  CMDIChildWndEx::IsRegisteredWithTaskbarTabs  
 MDI 子ウィンドウに Windows 7 タスク バーのタブが正常に登録されている場合は、TRUE を返します。  
  
```  
BOOL IsRegisteredWithTaskbarTabs();
```  
  
### <a name="return-value"></a>戻り値  
 MDI 子ウィンドウが Windows 7 タスク バーのタブ; に登録されている場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="invalidateiconicbitmaps"></a>  CMDIChildWndEx::InvalidateIconicBitmaps  
 MDI 子ウィンドウのアイコン ビットマップ表示を無効にします。  
  
```  
BOOL InvalidateIconicBitmaps();
```  
  
### <a name="return-value"></a>戻り値  
 MDI 子や Windows 7 タスク バーのサポートが無効になっている場合は FALSE を返しますが、Windows 7 タスク バーのタブ; に登録されていませんそれ以外の場合は TRUE を返します。  
  
### <a name="remarks"></a>Remarks  
 ライブ コンテンツまたは MDI 子ウィンドウのサイズが変更されたときに呼び出されます。  
  
##  <a name="gettaskbarthumbnailcliprect"></a>  CMDIChildWndEx::GetTaskbarThumbnailClipRect  
 ウィンドウのクライアント領域の一部を選択する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual CRect GetTaskbarThumbnailClipRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows の座標で四角形。 この四角形は、最上位レベルのフレームのクライアント領域にマップされます。 四角形は、クリッピング四角形をオフにする場合は空にする必要があります。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gettaskbarpreviewwnd"></a>  CMDIChildWndEx::GetTaskbarPreviewWnd  
 Windows 7 タスク バーのタブのサムネイルに表示する子ウィンドウ (通常はビューまたは分割ウィンドウ) を取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual CWnd* GetTaskbarPreviewWnd();
```  
  
### <a name="return-value"></a>戻り値  
 有効なポインターを返す必要があります、`CWnd`プレビューは、Windows 7 タスク バーのタブに表示するか、オブジェクトに関連するこの MDI 子フォーム。 既定の実装は、この MDI 子フォーム AFX_IDW_PANE_FIRST コントロール id の子ウィンドウを返します (これは通常、 `CView`-派生クラス)。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gettabproxywnd"></a>  CMDIChildWndEx::GetTabProxyWnd  
 Windows 7 タスク バーのタブに登録されているタブ プロキシ ウィンドウを返します。  
  
```  
CMDITabProxyWnd* GetTabProxyWnd();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `CMDITabProxyWnd` Windows 7 タスク バーのタブに登録されているオブジェクト。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="enabletaskbarthumbnailcliprect"></a>  CMDIChildWndEx::EnableTaskbarThumbnailClipRect  
 有効またはウィンドウのクライアント領域の一部の自動選択を無効にします。  
  
```  
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnable*  
 表示するウィンドウのクライアント領域の一部の自動選択を無効にする (FALSE) か (TRUE) を有効にするかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="canshowontaskbartabs"></a>  CMDIChildWndEx::CanShowOnTaskBarTabs  
 Windows 7 タスク バーのタブでこの MDI 子フォームを表示できるかどうかをフレームワークに指示します。  
  
```  
virtual BOOL CanShowOnTaskBarTabs();
```  
  
### <a name="return-value"></a>戻り値  
 MDI 子ウィンドウのコンテンツは、Windows 7 タスク バー サムネイルに表示できる場合は TRUE。  
  
### <a name="remarks"></a>Remarks  
 派生クラスでは、このメソッドをオーバーライドし、Windows 7 タスク バーのタブでこの MDI 子フォームの外観を無効にする場合は FALSE を返します。  
  
##  <a name="activatetoplevelframe"></a>  CMDIChildWndEx::ActivateTopLevelFrame  
 タスク バー タブから、アプリケーションがアクティブにすると、最上位レベルのフレームをアクティブ化するためにフレームワークによって呼び出されます。  
  
```  
virtual void ActivateTopLevelFrame();
```  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)   
 [CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)
