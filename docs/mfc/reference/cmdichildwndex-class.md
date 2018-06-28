---
title: CMDIChildWndEx クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 906e956bae9bce14c83d938218f51dfea9288b96
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041891"
---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx クラス
`CMDIChildWndEx`マルチ ドキュメント インターフェイス (MDI) 子ウィンドウに、Windows の機能を提供するクラス。 機能を拡張[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)です。 ある特定の MFC クラスを MDI アプリケーションで使用するときは、フレームワークにこのクラスが必要です。  
 
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  

  
## <a name="syntax"></a>構文  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](#activatetoplevelframe)|タスク バー タブから、アプリケーションをアクティブ化する場合は、トップ レベルのフレームをアクティブ化するためにフレームワークによって内部的に呼び出されます。|  
|`CMDIChildWndEx::AddDockSite`|このメソッドは、使用または実装されていません。|  
|[CMDIChildWndEx::AddPane](#addpane)|ペインを追加します。|  
|[CMDIChildWndEx::AddTabbedPane](#addtabbedpane)|タブ付きペインを追加します。|  
|[CMDIChildWndEx::AdjustDockingLayout](#adjustdockinglayout)|ドッキング レイアウトを調整します。|  
|[CMDIChildWndEx::CanShowOnMDITabs](#canshowonmditabs)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](#canshowontaskbartabs)|この MDI 子フォームを Windows 7 のタスクバー タブに表示されるかどうかをフレームワークに指示します。|  
|[CMDIChildWndEx::CanShowOnWindowsList](#canshowonwindowslist)|返します`TRUE`に MDI 子ウィンドウの名前を表示できるかどうか、 [CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) ダイアログ ボックス。 それ以外の場合は、`FALSE` を返します。|  
|`CMDIChildWndEx::CreateObject`|このクラス型の動的インスタンスを作成するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::DockPane](#dockpane)|ペインをドッキングします。|  
|[CMDIChildWndEx::DockPaneLeftOf](#dockpaneleftof)|ウィンドウを別のウィンドウの左側にドッキングします。|  
|[CMDIChildWndEx::EnableAutoHidePanes](#enableautohidepanes)|有効に自動的に隠すウィンドウのモード ウィンドウの指定した辺にドッキングされている場合。|  
|[CMDIChildWndEx::EnableDocking](#enabledocking)|メイン フレームに子ウィンドウのドッキングを有効にします。|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](#enabletaskbarthumbnailcliprect)|有効またはウィンドウのクライアント領域の一部の自動選択を無効にします。|  
|[CMDIChildWndEx::GetDockingManager](#getdockingmanager)||  
|[CMDIChildWndEx::GetDocumentName](#getdocumentname)|MDI 子ウィンドウに表示されるドキュメントの名前を返します。|  
|[CMDIChildWndEx::GetFrameIcon](#getframeicon)|MDI 子ウィンドウのアイコンを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetFrameText](#getframetext)|MDI 子ウィンドウのテキストを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetPane](#getpane)|指定したコントロール ID によってペインを検索します。|  
|[CMDIChildWndEx::GetRelatedTabGroup](#getrelatedtabgroup)||  
|[CMDIChildWndEx::GetTabbedPane](#gettabbedpane)|タブ付きドキュメントに変換された埋め込みドッキング ペインへのポインターを返します。|  
|[CMDIChildWndEx::GetTabProxyWnd](#gettabproxywnd)|Windows 7 のタスクバー タブに実際に登録されているプロキシ ウィンドウ タブを返します。|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](#gettaskbarpreviewwnd)|Windows 7 のタスクバー タブのサムネイルに表示する子ウィンドウ (通常はビューまたは分割ウィンドウ) を取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](#gettaskbarthumbnailcliprect)|ウィンドウのクライアント領域の一部を選択する必要があるときに、フレームワークによって呼び出されます。|  
|`CMDIChildWndEx::GetThisClass`|ポインターを取得するためにフレームワークによって呼び出される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](#gettoolbarbuttontooltiptext)|ツール バー ボタンのツールヒントを取得するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::InsertPane](#insertpane)|指定したウィンドウをドッキング マネージャーに登録します。|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](#invalidateiconicbitmaps)|MDI 子フォームのアイコン ビットマップ形式を無効にします。|  
|[CMDIChildWndEx::IsPointNearDockSite](#ispointneardocksite)|指定したポイントがドッキング サイトの近くにいるかどうかを判断します。|  
|[CMDIChildWndEx::IsReadOnly](#isreadonly)|返します`TRUE`場合は、子ウィンドウに表示されるドキュメントは読み取り専用です。 それ以外の場合は、`FALSE` を返します。|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](#isregisteredwithtaskbartabs)|MDI 子フォームが Windows 7 のタスクバー タブに正常に登録されている場合は、TRUE を返します。|  
|[CMDIChildWndEx::IsTabbedPane](#istabbedpane)|返します`TRUE`MDI 子ウィンドウには、ドッキング ペインが含まれている場合。 それ以外の場合は、`FALSE` を返します。|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](#istaskbartabssupportenabled)|Windows 7 のタスクバー タブに、MDI 子ウィンドウを表示できるかどうかを指示します。|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](#istaskbarthumbnailcliprectenabled)|ウィンドウのクライアント領域の一部の自動選択が有効か無効かどうかを示します。|  
|[CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|フレームワークによって SetTaskbarTabProperties メソッドはとタブ (MDI 子)、に渡されるフラグの組み合わせは、Windows 7 のタスクバー タブに登録しています。 既定値の組み合わせが STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE です。|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](#ongeticoniclivepreviewbitmap)|MDI 子ウィンドウのライブのプレビューのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnGetIconicThumbnail](#ongeticonicthumbnail)|MDI 子フォームのアイコンのサムネイルのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnMoveMiniFrame](#onmoveminiframe)|ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](#onpresstaskbarthmbnailclosebutton)|ユーザーがタスク バーのタブのサムネイルの閉じるボタンを押したときに、フレームワークによって呼び出されます.|  
|[CMDIChildWndEx::OnSetPreviewMode](#onsetpreviewmode)|入力するか、印刷プレビュー モードを終了するためにフレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](#ontaskbartabthumbnailactivate)|タスク バーのタブのサムネイルは WM_ACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](#ontaskbartabthumbnailmouseactivate)|タスク バーのタブのサムネイルは WM_MOUSEACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](#ontaskbartabthumbnailstretch)|MDI 子ウィンドウの Windows 7 タスク バー タブの縮小表示プレビューのビットマップを拡大する必要があるときに、フレームワークによって呼び出されます。|  
|[CMDIChildWndEx::OnUpdateFrameTitle](#onupdateframetitle)|フレームのタイトルを更新するためにフレームワークによって呼び出されます。 (`CMDIChildWnd::OnUpdateFrameTitle` をオーバーライドします)。|  
|[CMDIChildWndEx::PaneFromPoint](#panefrompoint)|指定したポイントを含むウィンドウを返します。|  
|`CMDIChildWndEx::PreTranslateMessage`|[TranslateMessage](../../mfc/reference/cwinapp-class.md) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) の各 Windows 関数にディスパッチされる前に、ウィンドウ メッセージを変換するためにクラス [CWinApp](http://msdn.microsoft.com/library/windows/desktop/ms644934) で使用されます。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|  
|[CMDIChildWndEx::RecalcLayout](#recalclayout)|ウィンドウのレイアウトを再計算されます。|  
|[CMDIChildWndEx::RegisterTaskbarTab](#registertaskbartab)|Windows 7 のタスクバー タブに、MDI 子フォームを登録します。|  
|[CMDIChildWndEx::RemovePaneFromDockManager](#removepanefromdockmanager)|ドッキング マネージャーから、ウィンドウを削除します。|  
|[CMDIChildWndEx::SetRelatedTabGroup](#setrelatedtabgroup)||  
|[CMDIChildWndEx::SetTaskbarTabActive](#settaskbartabactive)|対応する Windows 7 のタスクバー タブをアクティブにします。|  
|[CMDIChildWndEx::SetTaskbarTabOrder](#settaskbartaborder)|Windows 7 のタスクバー タブで指定された期間の前に MDI 子フォームを挿入します。|  
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Windows 7 のタスクバー タブのプロパティを設定します。|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](#settaskbarthumbnailcliprect)|ウィンドウのクライアント領域の一部を選択するクリッピング四角形を設定するためにフレームワークによって内部的に呼び出されます。|  
|[CMDIChildWndEx::ShowPane](#showpane)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](#unregistertaskbartab)|Windows 7 のタスクバー タブから、MDI 子フォームを削除します。|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](#updatetaskbartabicon)|Windows 7 のタスクバー タブのアイコンを更新します。|  
  
## <a name="remarks"></a>Remarks  
 MDI アプリケーションでドッキングの拡張機能を利用する、アプリケーションからの MDI 子ウィンドウのクラスを派生`CMDIChildWndEx`の代わりに[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)です。  
  
## <a name="example"></a>例  
 次の例からクラスを派生する`CMDIChildWndEx`です。 このコード スニペットを起源、 [VisualStudioDemo サンプル: Visual Studio の MFC アプリケーション](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## <a name="requirements"></a>必要条件  
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
 `TRUE` ペインの一覧の最後に、ドッキング マネージャー;、ウィンドウを追加するにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウは、ドッキング マネージャー; に正常に登録されましたそれ以外の場合、`FALSE`です。  
  
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
 遅延ウィンドウ位置構造体へのハンドルします。  
  
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
 `TRUE` ウィンドウを表示できる場合、 **Windows**  ダイアログ ボックス、それ以外の`FALSE`します。  
  
### <a name="remarks"></a>Remarks  
 派生クラスでは、このメソッドをオーバーライドし、返す`FALSE`ウィンドウに表示しない場合、 **Windows**  ダイアログ ボックス。 この関数から`CMFCWindowsManagerDialog`です。  
  
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
 ドッキングするのには、ウィンドウへのポインター。  
  
 *pLeftOf*  
 参照のポイントとして機能するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 成功した場合、`FALSE`エラー発生時にします。  
  
### <a name="remarks"></a>Remarks  
 このメソッドで指定されたウィンドウ*pBar*で指定されたウィンドウの左側にドッキングして*pLeftOf*です。  
  
 事前定義された順序でいくつかのペインをドッキングするときに、このメソッドを呼び出します。  
  
##  <a name="enableautohidepanes"></a>  CMDIChildWndEx::EnableAutoHidePanes  
 有効に自動的に隠すウィンドウのモード ウィンドウの指定した辺にドッキングされている場合。  
  
```  
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwDockStyle*  
 有効になっているメイン フレーム ウィンドウの辺を指定します。 次のフラグの 1 つ以上を使用します。  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
##  <a name="enabledocking"></a>  CMDIChildWndEx::EnableDocking  
 メイン フレームに子ウィンドウのドッキングを有効にします。  
  
```  
BOOL EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwDockStyle*  
 ドッキングの配置を有効にするを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
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
 ドキュメントの名前を表す文字列へのポインター。  
  
### <a name="remarks"></a>Remarks  
 ドキュメントは、MDI 子ウィンドウが表示されます。 一般に、ウィンドウから読み込まれた、またはファイルに保存されるデータを表示します。 したがって、ドキュメントの名前は、ファイルの名前です。 既定の実装`GetDocumentName`から取得した文字列を返します`CDocument::GetPathName`です。  
  
 ウィンドウには、ファイルから読み込まれていないドキュメントが表示されている場合は、派生クラスでは、このメソッドをオーバーライドし、一意のドキュメント識別子を返します。  
  
 `GetDocumentName` すべての開いているドキュメントの状態を保存するときに、フレームワークによって呼び出されます。 返される文字列は、レジストリに書き込まれます。  
  
 ドキュメント名がレジストリから読み取られに渡されるフレームワークでは、後で状態を復元は、 [CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow)です。 このメソッドをオーバーライドする[CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-派生クラスを作成またはこの名前を持つドキュメントを開くし、この名前を持つファイルの読み取り。 ドキュメントがないファイルに基づく場合は、ドキュメント識別子自体に基づくドキュメントを作成します。 保存し、ドキュメントを復元する場合にのみ、上記の操作を行う必要があります。  
  
### <a name="example"></a>例  
 `GetDocumentName` メソッドの使用例を次に示します。 このコード スニペットを起源、 [VisualStudioDemo サンプル: Visual Studio の MFC アプリケーション](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#17](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]  
  
##  <a name="getframeicon"></a>  CMDIChildWndEx::GetFrameIcon  
 MDI 子ウィンドウのアイコンを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual HICON GetFrameIcon() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ アイコンへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、MDI 子フレーム ウィンドウを含む MDI タブ上に表示するには、どのようなアイコンを決定するためにフレームワークによって呼び出されます。  
  
 既定では、このメソッドは、ウィンドウのアイコンを返します。 オーバーライド`GetFrameIcon`で、 `CMDIChildWndEx`-この動作をカスタマイズするクラスを派生します。  
  
##  <a name="getframetext"></a>  CMDIChildWndEx::GetFrameText  
 MDI 子ウィンドウのテキストを取得するためにフレームワークによって呼び出されます。  
  
```  
virtual CString GetFrameText() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレーム ウィンドウのテキストを含む文字列です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、MDI 子フレーム ウィンドウを含む MDI タブに表示するには、どのようなテキストを調べるためにフレームワークによって呼び出されます。  
  
 既定では、このメソッドは、ウィンドウのテキストを返します。 オーバーライド`GetFrameText`で、 `CMDIChildWndEx`-この動作をカスタマイズするクラスを派生します。  
  
##  <a name="getpane"></a>  CMDIChildWndEx::GetPane  
 指定したコントロール ID によってペインを検索します。  
  
```  
CBasePane* GetPane(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nID*  
 検索するウィンドウのコントロール ID。  
  
### <a name="return-value"></a>戻り値  
 ペインへのポインター場合が見つかると、それ以外の場合`NULL`です。  
  
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
 `TRUE` 場合は、ツールヒントが表示されています。 既定の実装では、`FALSE` が返されます。  
  
### <a name="remarks"></a>Remarks  
 ツール バー ボタンのカスタム ツールヒントを表示する場合は、このメソッドをオーバーライドします。  
  
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
 隣のウィンドウへのポインター。  
  
 [in]*bAfter*  
 場合`TRUE`、 *pControlBar*の後に挿入*pTarget*です。 場合`FALSE`、 *pControlBar*前に、挿入は*pTarget*です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功すると、`FALSE`それ以外の場合。  
  
##  <a name="ispointneardocksite"></a>  CMDIChildWndEx::IsPointNearDockSite  
 指定したポイントがドッキング サイトの近くにいるかどうかを判断します。  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 指定された点です。  
  
 [in]*dwBarAlignment*  
 点が近い端を指定します。 指定できる値は`CBRS_ALIGN_LEFT`、 `CBRS_ALIGN_RIGHT`、 `CBRS_ALIGN_TOP`、および `CBRS_ALIGN_BOTTOM`  
  
 [in]*bOuterEdge*  
 `TRUE` ドッキング サイトの外側の境界線の近くのポイントがある場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング サイトの近くのポイントがある場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 点は、ドッキング マネージャーで設定された感度内にある場合、ドッキング サイトに近いです。 既定値と小文字の区別は、15 ピクセルです。  
  
##  <a name="isreadonly"></a>  CMDIChildWndEx::IsReadOnly  
 子ウィンドウに表示されるドキュメントは読み取り専用であるかどうかを指定します。  
  
```  
virtual BOOL IsReadOnly();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ドキュメントが読み取り専用です。それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 この関数を防ぐために使用される読み取り専用の文書を保存します。  
  
### <a name="example"></a>例  
 次の例では、オーバーライドを示しています、`IsReadOnly`メソッドです。 このコード スニペットを起源、 [VisualStudioDemo サンプル: Visual Studio の MFC アプリケーション](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#2](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]  
  
##  <a name="istabbedpane"></a>  CMDIChildWndEx::IsTabbedPane  
 MDI 子ウィンドウがドッキング ペインを含むかどうかを指定します。  
  
```  
BOOL IsTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` MDI 子ウィンドウには、タブ付きドキュメントに変換されたドッキング ウィンドウが含まれている場合それ以外の場合`FALSE`です。  
  
##  <a name="onmoveminiframe"></a>  CMDIChildWndEx::OnMoveMiniFrame  
 ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pFrame*  
 ミニフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合、それ以外の場合`FALSE`です。  
  
##  <a name="onsetpreviewmode"></a>  CMDIChildWndEx::OnSetPreviewMode  
 入力するか、印刷プレビュー モードを終了するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bPreview*  
 場合`TRUE`、印刷プレビュー モードを入力します。 場合`FALSE`、印刷プレビュー モードを終了します。  
  
 [in]*pState*  
 印刷プレビューの状態の構造体へのポインター。  
  
##  <a name="onupdateframetitle"></a>  CMDIChildWndEx::OnUpdateFrameTitle  
 フレームのタイトルを更新するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bAddToTitle*  
 場合`TRUE`タイトルには、ドキュメント名を追加します。  
  
##  <a name="panefrompoint"></a>  CMDIChildWndEx::PaneFromPoint  
 指定したポイントを含むウィンドウを返します。  
  
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
 この量によって、検索の領域を増やします。 ペインは、指定したポイントが拡大された領域内になった場合に、検索条件を満たします。  
  
 [in]*bExactBar*  
 `TRUE` 無視する、 *nSensitivity*パラメーターです。 それ以外の場合、`FALSE`です。  
  
 [in]*pRTCBarType*  
 ない場合`NULL`、指定した型のペインのみが検索されます。  
  
 [in]*場合*  
 指定した位置に、ウィンドウが見つかった場合、このパラメーターには、指定したポイントに最も近いしたペインの横が含まれています。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `CBasePane`-特定のポイントを格納しているオブジェクトを派生または`NULL`ウィンドウが見つからなかった場合です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドでは、ランタイム クラスと可視性などの指定した条件に従って、指定したポイントがペインに含まれるかどうかを決定します。  
  
 この関数を返し、ペインが見つかりましたが、*場合*指定した点の配置が含まれています。 たとえば、次の点が、ウィンドウの上部に最も近い*場合*に設定されている`CBRS_ALIGN_TOP`です。  
  
##  <a name="recalclayout"></a>  CMDIChildWndEx::RecalcLayout  
 ウィンドウのレイアウトを再計算されます。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bNotify*  
 場合`TRUE`ウィンドウのアクティブなインプレースで項目がレイアウトの変更の通知を受信します。  
  
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
 場合`TRUE`、削除されたウィンドウが破棄されます。  
  
 [in]*bAdjustLayout*  
 場合`TRUE`、すぐにドッキング レイアウトを調整します。  
  
 [in]*bAutoHide*  
 場合`TRUE`、ドッキング レイアウトは自動的に隠すバーのリストに関連します。 場合`FALSE`、ドッキング レイアウトは標準のペインの一覧に関連します。  
  
 [in]*pBarReplacement*  
 削除されるペインに置き換えられるペインへのポインター。  
  
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
 Windows 7 のタスクバー タブのアイコンを更新します。  
  
```  
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 *hIcon*  
 Windows 7 のタスクバー タブに表示するアイコンのハンドル。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="unregistertaskbartab"></a>  CMDIChildWndEx::UnregisterTaskbarTab  
 Windows 7 のタスクバー タブから、MDI 子ウィンドウを削除します。  
  
```  
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bCheckRegisteredMDIChildCount*  
 この関数を MDI タブに登録されている MDI 子の数を確認する必要があるかどうかを指定します。 この数が 0 の場合、この関数は、アプリケーションのタスク バーのサムネイルからクリッピング四角形を削除し、します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbarthumbnailcliprect"></a>  CMDIChildWndEx::SetTaskbarThumbnailClipRect  
 ウィンドウのクライアント領域の一部を選択するクリッピング四角形を設定するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 新しいクリッピング四角形を指定します。 四角形が空または null の場合は、領域は削除されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE`。それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbartabproperties"></a>  CMDIChildWndEx::SetTaskbarTabProperties  
 Windows 7 のタスクバー タブのプロパティを設定します。  
  
```  
void SetTaskbarTabProperties(DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwFlags*  
 STPFLAG の値の組み合わせ。 詳細については、次を参照してください。 [itaskbarlist 4::settabproperties](http://msdn.microsoft.com/library/dd562049\(vs.85\).aspx)です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbartaborder"></a>  CMDIChildWndEx::SetTaskbarTabOrder  
 Windows 7 のタスクバー タブで指定された期間の前に、MDI 子を挿入します。  
  
```  
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndBefore*  
 サムネイルの左側に挿入が MDI 子ウィンドウへのポインター。 このウィンドウはによって既に登録される必要があります`RegisterTaskbarTab`です。 この値が場合`NULL`、新しいサムネイルがリストの末尾に追加します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbartabactive"></a>  CMDIChildWndEx::SetTaskbarTabActive  
 対応する Windows 7 のタスクバー タブをアクティブにします。  
  
```  
void SetTaskbarTabActive();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="registertaskbartab"></a>  CMDIChildWndEx::RegisterTaskbarTab  
 Windows 7 のタスクバー タブに、MDI 子を登録します。  
  
```  
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndBefore*  
 サムネイルの左側に挿入が MDI 子ウィンドウへのポインター。 このウィンドウはによって既に登録される必要があります`RegisterTaskbarTab`です。 この値が場合`NULL`、新しいサムネイルがリストの末尾に追加します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ontaskbartabthumbnailstretch"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailStretch  
 MDI 子ウィンドウの Windows 7 タスク バー タブ縮小表示プレビューのビットマップを拡大する必要があるときに、フレームワークによって呼び出されます。  
  
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
 元のビットマップへのハンドル。  
  
 *rectSrc*  
 元の四角形を指定します。  
  
### <a name="remarks"></a>Remarks  
 Requirementher または彼彼彼彼彼彼彼 **:** afxmdichildwndex.h  
  
##  <a name="ontaskbartabthumbnailmouseactivate"></a>  CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate  
 タスク バーのタブのサムネイルは WM_MOUSEACTIVATE メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,  
    UINT nHitTest,  
    UINT message);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDesktopWnd*  
 アクティブ化されているウィンドウの最上位の親ウィンドウへのポインターを指定します。 ポインターは、一時的な場合があり、保存されません。  
  
 *nHitTest*  
 ヒット テストの市外局番を指定します。 ヒット テストは、カーソルの位置を決定するテストです。  
  
 *message*  
 マウスのメッセージ番号を指定します。  
  
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
 *%n 状態*  
 指定するかどうか、`CWnd`がアクティブまたは非アクティブ化します。  
  
 *pWndOther*  
 ポインター、`CWnd`アクティブまたは非アクティブ化します。 マウス ポインターを指定できます`NULL`、一時的な可能性があるとします。  
  
 *bMinimized*  
 最小化された状態を指定します、`CWnd`アクティブまたは非アクティブ化します。 値`TRUE`ウィンドウが最小化することを示します。  
  
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
 MDI 子ウィンドウのライブのプレビューのビットマップを取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,  
    CPoint& ptLocation);
```  
  
### <a name="parameters"></a>パラメーター  
 *bIsMDIChildActive*  
 このパラメーターは`TRUE`MDI 子ウィンドウのビットマップが要求された場合は、現在アクティブとのメイン ウィンドウが最小化されていません。 既定の処理をここでは、メイン ウィンドウのスナップショットを取得します。  
  
 *ptLocation*  
 メイン (最上位)、ビットマップの場所を指定するウィンドウのクライアント座標。 このポイントは、呼び出し先によって提供される必要があります。  
  
### <a name="return-value"></a>戻り値  
 処理がある場合のハンドルを返します有効 32 bpp のビットマップでは、それ以外の場合`NULL`です。  
  
### <a name="remarks"></a>Remarks  
 派生クラスでは、このメソッドをオーバーライドし、MDI 子ウィンドウのライブのプレビューの有効 32 bpp のビットマップを返します。 MDI 子ウィンドウは、Windows 7 のタスクバー タブに表示される場合にのみ、このメソッドが呼び出されます。 返す場合`NULL`、MFC の既定のハンドラーを呼び出すし、ビットマップを使用して取得`PrintClient`または`PrintWindow`です。  
  
##  <a name="m_dwdefaulttaskbartabpropertyflags"></a>  CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags  
 フレームワークによって渡されるフラグの組み合わせ、`SetTaskbarTabProperties`メソッドは、Windows 7 のタスクバー タブに、タブ (MDI 子) を登録するとします。  
  
```  
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;  
```  
  
### <a name="remarks"></a>Remarks  
 既定値の組み合わせが STPF_USEAPPTHUMBNAILWHENACTIVE &#124; STPF_USEAPPPEEKWHENACTIVE です。  
  
##  <a name="istaskbarthumbnailcliprectenabled"></a>  CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled  
 ウィンドウのクライアント領域の一部の自動選択が有効か無効かどうかを示します。  
  
```  
BOOL IsTaskbarThumbnailClipRectEnabled() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`を表示するウィンドウのクライアント領域の一部の自動選択は、それ以外の有効なかどうかは`FALSE`します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="istaskbartabssupportenabled"></a>  CMDIChildWndEx::IsTaskbarTabsSupportEnabled  
 Windows 7 のタスクバー タブに、MDI 子ウィンドウを表示できるかどうかを指示します。  
  
```  
BOOL IsTaskbarTabsSupportEnabled();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` MDI 子ウィンドウは、Windows 7 のタスクバー タブ; に表示できる場合`FALSE`場合は、MDI 子が Windows 7 のタスクバー タブに表示されないことができます。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isregisteredwithtaskbartabs"></a>  CMDIChildWndEx::IsRegisteredWithTaskbarTabs  
 返します`TRUE`場合は、MDI 子は、Windows 7 のタスクバー タブに正常に登録されました。  
  
```  
BOOL IsRegisteredWithTaskbarTabs();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` MDI 子ウィンドウが Windows 7 のタスクバー タブ; に登録されている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="invalidateiconicbitmaps"></a>  CMDIChildWndEx::InvalidateIconicBitmaps  
 MDI 子ウィンドウのアイコン ビットマップ表示を無効にします。  
  
```  
BOOL InvalidateIconicBitmaps();
```  
  
### <a name="return-value"></a>戻り値  
 返します`FALSE`Windows 7 タスク バーのサポートが無効にするか、MDI 子は、Windows 7 のタスクバー タブ; に登録されていない場合それを返します`TRUE`です。  
  
### <a name="remarks"></a>Remarks  
 ライブ コンテンツまたは MDI 子ウィンドウのサイズが変更されたときに呼び出す必要があります。  
  
##  <a name="gettaskbarthumbnailcliprect"></a>  CMDIChildWndEx::GetTaskbarThumbnailClipRect  
 ウィンドウのクライアント領域の一部を選択する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual CRect GetTaskbarThumbnailClipRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Windows の座標で四角形。 この四角形は、最上位のフレームのクライアント領域にマップされます。 四角形は、クリッピング四角形をオフにする場合は空にする必要があります。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gettaskbarpreviewwnd"></a>  CMDIChildWndEx::GetTaskbarPreviewWnd  
 Windows 7 のタスクバー タブのサムネイルに表示する子ウィンドウ (通常はビューまたは分割ウィンドウ) を取得する必要があるときに、フレームワークによって呼び出されます。  
  
```  
virtual CWnd* GetTaskbarPreviewWnd();
```  
  
### <a name="return-value"></a>戻り値  
 有効なポインターを返す必要があります、`CWnd`この MDI の子に関連するオブジェクト、Windows 7 のタスクバー タブ上のプレビューを表示する必要があります。 既定の実装が AFX_IDW_PANE_FIRST コントロール ID の場合は、この MDI 子の子ウィンドウを返します (これは、通常、 `CView`-派生クラス)。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="gettabproxywnd"></a>  CMDIChildWndEx::GetTabProxyWnd  
 Windows 7 のタスクバー タブに登録されているタブ プロキシ ウィンドウを返します。  
  
```  
CMDITabProxyWnd* GetTabProxyWnd();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMDITabProxyWnd`オブジェクトで、Windows 7 のタスクバー タブに登録されています。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="enabletaskbarthumbnailcliprect"></a>  CMDIChildWndEx::EnableTaskbarThumbnailClipRect  
 有効またはウィンドウのクライアント領域の一部の自動選択を無効にします。  
  
```  
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnable*  
 有効にするかどうかを指定します ( `TRUE`)、または無効にする ( `FALSE`) を表示するウィンドウのクライアント領域の一部の自動選択します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="canshowontaskbartabs"></a>  CMDIChildWndEx::CanShowOnTaskBarTabs  
 この MDI 子フォームを Windows 7 のタスクバー タブに表示されるかどうかをフレームワークに指示します。  
  
```  
virtual BOOL CanShowOnTaskBarTabs();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` MDI 子ウィンドウの内容は、Windows 7 のタスクバーの縮小表示で表示できます。 場合、  
  
### <a name="remarks"></a>Remarks  
 派生クラスでは、このメソッドをオーバーライドし、返す`FALSE`この MDI 子フォームの Windows 7 のタスクバー タブの外観を無効にします。  
  
##  <a name="activatetoplevelframe"></a>  CMDIChildWndEx::ActivateTopLevelFrame  
 タスク バー タブから、アプリケーションがアクティブになったときに、最上位のフレームをアクティブ化するためにフレームワークによって呼び出されます。  
  
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
