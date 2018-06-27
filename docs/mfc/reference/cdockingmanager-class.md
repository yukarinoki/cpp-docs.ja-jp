---
title: CDockingManager クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
dev_langs:
- C++
helpviewer_keywords:
- CDockingManager [MFC], AddDockSite
- CDockingManager [MFC], AddHiddenMDITabbedBar
- CDockingManager [MFC], AddMiniFrame
- CDockingManager [MFC], AddPane
- CDockingManager [MFC], AdjustDockingLayout
- CDockingManager [MFC], AdjustPaneFrames
- CDockingManager [MFC], AdjustRectToClientArea
- CDockingManager [MFC], AlignAutoHidePane
- CDockingManager [MFC], AutoHidePane
- CDockingManager [MFC], BringBarsToTop
- CDockingManager [MFC], BuildPanesMenu
- CDockingManager [MFC], CalcExpectedDockedRect
- CDockingManager [MFC], Create
- CDockingManager [MFC], DeterminePaneAndStatus
- CDockingManager [MFC], DisableRestoreDockState
- CDockingManager [MFC], DockPane
- CDockingManager [MFC], DockPaneLeftOf
- CDockingManager [MFC], EnableAutoHidePanes
- CDockingManager [MFC], EnableDocking
- CDockingManager [MFC], EnableDockSiteMenu
- CDockingManager [MFC], EnablePaneContextMenu
- CDockingManager [MFC], FindDockSite
- CDockingManager [MFC], FindDockSiteByPane
- CDockingManager [MFC], FindPaneByID
- CDockingManager [MFC], FixupVirtualRects
- CDockingManager [MFC], FrameFromPoint
- CDockingManager [MFC], GetClientAreaBounds
- CDockingManager [MFC], GetDockingMode
- CDockingManager [MFC], GetDockSiteFrameWnd
- CDockingManager [MFC], GetEnabledAutoHideAlignment
- CDockingManager [MFC], GetMiniFrames
- CDockingManager [MFC], GetOuterEdgeBounds
- CDockingManager [MFC], GetPaneList
- CDockingManager [MFC], GetSmartDockingManager
- CDockingManager [MFC], GetSmartDockingManagerPermanent
- CDockingManager [MFC], GetSmartDockingParams
- CDockingManager [MFC], GetSmartDockingTheme
- CDockingManager [MFC], HideAutoHidePanes
- CDockingManager [MFC], InsertDockSite
- CDockingManager [MFC], InsertPane
- CDockingManager [MFC], IsDockSiteMenu
- CDockingManager [MFC], IsInAdjustLayout
- CDockingManager [MFC], IsOLEContainerMode
- CDockingManager [MFC], IsPointNearDockSite
- CDockingManager [MFC], IsPrintPreviewValid
- CDockingManager [MFC], LoadState
- CDockingManager [MFC], LockUpdate
- CDockingManager [MFC], OnActivateFrame
- CDockingManager [MFC], OnClosePopupMenu
- CDockingManager [MFC], OnMoveMiniFrame
- CDockingManager [MFC], OnPaneContextMenu
- CDockingManager [MFC], PaneFromPoint
- CDockingManager [MFC], ProcessPaneContextMenuCommand
- CDockingManager [MFC], RecalcLayout
- CDockingManager [MFC], ReleaseEmptyPaneContainers
- CDockingManager [MFC], RemoveHiddenMDITabbedBar
- CDockingManager [MFC], RemoveMiniFrame
- CDockingManager [MFC], RemovePaneFromDockManager
- CDockingManager [MFC], ReplacePane
- CDockingManager [MFC], ResortMiniFramesForZOrder
- CDockingManager [MFC], SaveState
- CDockingManager [MFC], SendMessageToMiniFrames
- CDockingManager [MFC], Serialize
- CDockingManager [MFC], SetAutohideZOrder
- CDockingManager [MFC], SetDockingMode
- CDockingManager [MFC], SetDockState
- CDockingManager [MFC], SetPrintPreviewMode
- CDockingManager [MFC], SetSmartDockingParams
- CDockingManager [MFC], ShowDelayShowMiniFrames
- CDockingManager [MFC], ShowPanes
- CDockingManager [MFC], StartSDocking
- CDockingManager [MFC], StopSDocking
- CDockingManager [MFC], m_bHideDockingBarsInContainerMode
- CDockingManager [MFC], m_dockModeGlobal
- CDockingManager [MFC], m_nDockSensitivity
- CDockingManager [MFC], m_nTimeOutBeforeDockingBarDock
- CDockingManager [MFC], m_nTimeOutBeforeToolBarDock
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7e2fe05ba1bde0fc3d0de22d58a29f49f2130fc
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954079"
---
# <a name="cdockingmanager-class"></a>CDockingManager クラス
メイン フレーム ウィンドウのドッキング レイアウトを制御するコア機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDockingManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockingManager::AddDockSite](#adddocksite)|ドッキング ペインを作成し、コントロール バーのリストに追加します。|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|バーに、ハンドルを追加 ウィンドウを非表示の MDI タブ付きバー ペインの一覧にします。|  
|[CDockingManager::AddMiniFrame](#addminiframe)|ミニフレームの一覧に、フレームを追加します。|  
|[CDockingManager::AddPane](#addpane)|ペインをドッキング マネージャーに登録します。|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|再計算して、フレーム ウィンドウのすべてのウィンドウのレイアウトを調整します。|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|すべてのウィンドウに送信される WM_NCCALCSIZE メッセージと`CPaneFrameWnd`windows です。|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|四角形の配置を調整します。|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|全体の幅またはで囲まれた、フレームのクライアント領域の高さドッキング サイトになるため、自動非表示モードのドッキング ペインをサイズ変更します。|  
|[CDockingManager::AutoHidePane](#autohidepane)|自動的に隠すツールバーを作成します。|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|最上位に指定された配置を含むドッキング バーが表示されます。|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|メニューには、ドッキング ペインおよびツールバーの名前を追加します。|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|ドッキング ウィンドウの予想される四角形を計算します。|  
|[CDockingManager::Create](#create)|ドッキング マネージャーを作成します。|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|指定されたポイントとそのドッキング状態を含むウィンドウを決定します。|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|有効またはレジストリからドッキング レイアウトの読み込みを無効にします。|  
|[CDockingManager::DockPane](#dockpane)|別のウィンドウまたはフレーム ウィンドウには、ペインをドッキングします。|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|ペインを別のペインの左側にドッキングします。|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|メイン フレーム ウィンドウのドッキング、ドッキング ペインを作成でき、コントロール バーのリストに追加します。|  
|[CDockingManager::EnableDocking](#enabledocking)|ドッキング ペインを作成し、メイン フレーム ウィンドウのドッキングを有効にします。|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|すべてのドッキング ペインのキャプションにポップアップ メニューを開き、追加のボタンを表示します。|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|ユーザーがマウスの右ボタンをクリックするし、ライブラリ、WM_CONTEXTMENU メッセージの処理は、アプリケーションのツールバーとドッキング ウィンドウの一覧を持っている特殊なコンテキスト メニューを表示するライブラリを指示します。|  
|[CDockingManager::FindDockSite](#finddocksite)|バーを取得、指定した位置であるし、指定されたアラインメントを持つウィンドウです。|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|バーを返しますターゲット バー ペインの id を持つウィンドウです。|  
|[CDockingManager::FindPaneByID](#findpanebyid)|指定したコントロール ID によってペインを検索します。|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|ツールバーの現在位置の仮想四角形をコミットします。|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|指定したポイントを含むフレームを返します。|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|クライアント領域の境界を含む四角形を取得します。|  
|[CDockingManager::GetDockingMode](#getdockingmode)|現在のドッキング モードを返します。|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|親ウィンドウ フレームへのポインターを取得します。|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|ウィンドウの有効な配置を返します。|  
|[CDockingManager::GetMiniFrames](#getminiframes)|ミニフレームの一覧を取得します。|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|フレームの外側のエッジを含んだ四角形を取得します。|  
|[CDockingManager::GetPaneList](#getpanelist)|ドッキング マネージャーに属しているウィンドウの一覧を返します。 これには、すべてのフローティング ウィンドウが含まれます。|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|スマート ドッキング マネージャーへのポインターを取得します。|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|スマート ドッキング マネージャーへのポインターを取得します。|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|スマート ドッキングのパラメーターをドッキング マネージャーを返します。|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|スマート ドッキング マーカーの表示に使用されるテーマを返す静的メソッド。|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|自動非表示モードになっているウィンドウを非表示にします。|  
|[CDockingManager::InsertDockSite](#insertdocksite)|ドッキング ペインを作成し、コントロール バーのリストに挿入します。|  
|[CDockingManager::InsertPane](#insertpane)|コントロール ウィンドウをコントロール バーのリストに挿入します。|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|ポップアップ メニューがすべてのウィンドウのキャプションに表示されるかどうかを指定します。|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|すべてのウィンドウのレイアウトを調整するかどうかを判断します。|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|OLE コンテナー モードでは、ドッキング マネージャーかどうかを指定します。|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|指定したポイントがドッキング サイトの近くにいるかどうかを判断します。|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|印刷プレビュー モードが設定されているかどうかを判断します。|  
|[CDockingManager::LoadState](#loadstate)|レジストリからドッキング マネージャーの状態を読み込みます。|  
|[CDockingManager::LockUpdate](#lockupdate)|指定されたウィンドウをロックします。|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|フレーム ウィンドウがアクティブまたは非アクティブ化するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|ウィンドウのリストを持つメニューを作成するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|指定したポイントを含むウィンドウを返します。|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|選択または指定されたコマンドに対してチェック ボックスをオフにし、表示されるペインのレイアウトを再計算するため、フレームワークによって呼び出されます。|  
|[CDockingManager::RecalcLayout](#recalclayout)|コントロールのリストに存在するコントロールの内部レイアウトを再計算されます。|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|空のペインのコンテナーを解放します。|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|指定した非表示のウィンドウ バーを削除します。|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|ミニフレームの一覧から指定したフレームを削除します。|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|ペインの登録を解除し、ドッキング マネージャーの一覧から削除します。|  
|[CDockingManager::ReplacePane](#replacepane)|ペインを別のペインに置き換えます。|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|ミニフレームの一覧で、フレームを使用します。|  
|[CDockingManager::SaveState](#savestate)|レジストリには、ドッキング マネージャーの状態を保存します。|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|すべてのミニフレームに指定されたメッセージを送信します。|  
|[CDockingManager::Serialize](#serialize)|アーカイブは、ドッキング マネージャーに書き込みます。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|サイズ、幅、およびコントロール バーと、指定したウィンドウの高さを設定します。|  
|[CDockingManager::SetDockingMode](#setdockingmode)|ドッキングのモードを設定します。|  
|[CDockingManager::SetDockState](#setdockstate)|コントロール バー、ミニ フレーム、および自動的に隠すバーのドッキング状態を設定します。|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|印刷プレビューで表示されるバーの印刷プレビュー モードを設定します。|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|スマート ドッキングの動作を定義するパラメーターを設定します。|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|ミニフレーム ウィンドウの表示と非表示を切り替えます。|  
|[CDockingManager::ShowPanes](#showpanes)|コントロールと自動的に隠すバーのウィンドウの表示と非表示を切り替えます。|  
|[CDockingManager::StartSDocking](#startsdocking)|スマート ドッキング マネージャーの配置に応じて指定したウィンドウのスマート ドッキングを開始します。|  
|[CDockingManager::StopSDocking](#stopsdocking)|スマート ドッキングを停止します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|OLE コンテナー モードのペインがドッキング マネージャーに非表示にするかどうかを指定します。|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|グローバルのドッキング モードを指定します。|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|ドッキングと小文字の区別を指定します。|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|イミディ エイト モードでドッキング、ドッキング ウィンドウがドッキングされるまでは、時間 (ミリ秒単位) を指定します。|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|ツールバーがメイン フレーム ウィンドウにドッキングされる前に、時間 (ミリ秒単位) を指定します。|  
  
## <a name="remarks"></a>Remarks  
 メイン フレーム ウィンドウを作成し、このクラスを自動的に初期化します。  
  
 ドッキング マネージャー オブジェクトは、すべての一覧と、ドッキング レイアウト内にあるすべてのペインの一覧を保持して[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)メイン フレーム ウィンドウに属している windows です。  
  
 `CDockingManager`クラスは、ウィンドウの検索に使用できる一部のサービスを実装または`CPaneFrameWnd`ウィンドウです。 通常呼び出さないこれらのサービス直接メイン フレーム ウィンドウ オブジェクトにラップされるためです。 詳細については、次を参照してください。 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)です。  
  
## <a name="customization-tips"></a>カスタマイズのヒント  
 次のヒントを適用する`CDockingManager`オブジェクト。  
  
- [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)これらドッキングのモードをサポートしています。  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     これらのドッキングのモードがによって定義された[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)を呼び出して設定と[CDockingManager::SetDockingMode](#setdockingmode)です。  
  
-   サイズを変更できない、フローティング ウィンドウを作成する場合は、呼び出し、 [CDockingManager::AddPane](#addpane)メソッドです。 このメソッドは、これは、ウィンドウのレイアウトを担当する、ドッキング マネージャーに、ウィンドウを登録します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CDockingManager`を構成するクラス、`CDockingManager`オブジェクト。 例では、すべてのドッキング ペインのキャプションにポップアップ メニューを開き、追加のボタンを表示する方法と、オブジェクトのドッキング モードを設定する方法を示します。 このコード スニペットの一部である、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>  CDockingManager::AddDockSite  
 ドッキング ペインを作成し、コントロール バーのリストに追加します。  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*情報*  
 含む情報構造体への参照は、ペインの配置をドッキングします。  
  
 [out]*ppDockBar*  
 新しいドッキング ペインへのポインターへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング ウィンドウが正常に作成された場合`FALSE`それ以外の場合。  
  
##  <a name="addhiddenmditabbedbar"></a>  CDockingManager::AddHiddenMDITabbedBar  
 バーに、ハンドルを追加 ウィンドウを非表示の MDI タブ付きバー ペインの一覧にします。  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 バーへのポインター ウィンドウ  
  
##  <a name="addpane"></a>  CDockingManager::AddPane  
 ペインをドッキング マネージャーに登録します。  
  
```  
BOOL AddPane(
    CBasePane* pWnd,  
    BOOL bTail = TRUE,  
    BOOL bAutoHide = FALSE,  
    BOOL bInsertForOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力].*pWnd*  
 ドッキング マネージャーに追加するウィンドウを指定します。  
  
 [in]*bTail*  
 `TRUE` ペインの一覧の最後に、ドッキング マネージャー;、ウィンドウを追加するにはそれ以外の場合、`FALSE`です。  
  
 [in]*bAutoHide*  
 内部使用のみ。 常に既定値を使用して`FALSE`です。  
  
 [in]*bInsertForOuterEdge*  
 内部使用のみ。 常に既定値を使用して`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウは、ドッキング マネージャー; に正常に登録されましたそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出して、ドッキング マネージャーに、サイズを変更、フローティング ウィンドウを登録します。 ペインを登録しない場合は正しく表示されない、ドッキング マネージャーを配置するとき。  
  
##  <a name="adjustdockinglayout"></a>  CDockingManager::AdjustDockingLayout  
 再計算して、フレーム ウィンドウのすべてのウィンドウのレイアウトを調整します。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hdwp*  
 遅延ウィンドウ位置構造体を指定します。 詳細については、「 [Windows のデータ型](http://msdn.microsoft.com/library/windows/desktop/aa383751)」を参照してください。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="addminiframe"></a>  CDockingManager::AddMiniFrame  
 ミニフレームの一覧に、フレームを追加します。  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWnd*  
 フレームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` フレームがミニフレームの一覧ではなくを正常に追加された場合`FALSE`それ以外の場合。  
  
##  <a name="adjustpaneframes"></a>  CDockingManager::AdjustPaneFrames  
 により、`WM_NCCALCSIZE`すべてのウィンドウに送信されるメッセージと`CPaneFrameWnd`windows です。  
  
```  
virtual void AdjustPaneFrames();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="adjustrecttoclientarea"></a>  CDockingManager::AdjustRectToClientArea  
 四角形の配置を調整します。  
  
```  
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*rectResult*  
 参照、`CRect`オブジェクト  
  
 [in]*場合*  
 配置、`CRect`オブジェクト  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合の配置、`CRect`オブジェクトが調整されました。`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 *場合*パラメーターは、次の値のいずれかを持つことができます。  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>  CDockingManager::AlignAutoHidePane  
 全体の幅またはで囲まれた、フレームのクライアント領域の高さドッキング サイトになるため、自動非表示モードのドッキング ペインをサイズ変更します。  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDefaultSlider*  
 ドッキングのスライダー ペイン。  
  
 [in]*bIsVisible*  
 `TRUE` ドッキング ペインを表示する場合`FALSE`それ以外の場合。  
  
##  <a name="autohidepane"></a>  CDockingManager::AutoHidePane  
 自動的に隠すツールバーを作成します。  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 バーへのポインター ウィンドウです。  
  
 [in]*pCurrAutoHideToolBar*  
 自動へのポインターには、ツールバーが非表示にします。  
  
### <a name="return-value"></a>戻り値  
 `NULL` 場合は、自動非表示ツールバーは作成されませんでした。それ以外の場合、新しいツールバーへのポインター。  
  
##  <a name="bringbarstotop"></a>  CDockingManager::BringBarsToTop  
 最上位に指定された配置を含むドッキング バーが表示されます。  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*場合*  
 他のウィンドウの上部にドッキング バーの配置です。  
  
 [in]*bExcludeDockedBars*  
 `TRUE` 一番上にからドッキング バーを除外するにはそれ以外の場合`FALSE`です。  
  
##  <a name="buildpanesmenu"></a>  CDockingManager::BuildPanesMenu  
 メニューには、ドッキング ペインおよびツールバーの名前を追加します。  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*メニュー*  
 ドッキング ペインおよびツールバーの名前を追加するためのメニュー。  
  
 [in]*bToolbarsOnly*  
 `TRUE` ツールバー名のみをメニューに追加するには`FALSE`それ以外の場合。  
  
##  <a name="calcexpecteddockedrect"></a>  CDockingManager::CalcExpectedDockedRect  
 ドッキング ウィンドウの予想される四角形を計算します。  
  
```  
void CalcExpectedDockedRect(
    CWnd* pWnd,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWnd*  
 ドッキングするウィンドウへのポインター。  
  
 [in]*ptMouse*  
 マウスの位置。  
  
 [out]*rectResult*  
 計算される四角形。  
  
 [in]*bDrawTab*  
 `TRUE` タブを描画するにはそれ以外の場合`FALSE`です。  
  
 [out]*ppTargetBar*  
 ターゲット ウィンドウへのポインターへのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ウィンドウがユーザーによって指定されたポイントに、ウィンドウをドラッグする場合に使用する四角形を計算*ptMouse*し、そこにドッキングします。  
  
##  <a name="create"></a>  CDockingManager::Create  
 ドッキング マネージャーを作成します。  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pParentWnd*  
 ドッキング マネージャーの親フレームへのポインター。 この値にする必要がありますいない`NULL`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` いつも。  
  
##  <a name="determinepaneandstatus"></a>  CDockingManager::DeterminePaneAndStatus  
 指定されたポイントとそのドッキング状態を含むウィンドウを決定します。  
  
```  
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,  
    int nSensitivity,  
    DWORD dwEnabledAlignment,  
    CBasePane** ppTargetBar,  
    const CBasePane* pBarToIgnore,  
    const CBasePane* pBarToDock);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pt*  
 確認するウィンドウの場所です。  
  
 [in]*nSensitivity*  
 チェックする各ペインの ウィンドウ四角形を増加する値。 ペインは、指定された点がこの拡大された領域の場合、検索条件を満たします。  
  
 [in]*dwEnabledAlignment*  
 ドッキング ウィンドウの配置です。  
  
 [out]*ppTargetBar*  
 ターゲット ウィンドウへのポインターへのポインター。  
  
 [in]*pBarToIgnore*  
 メソッドが無視されるペイン。  
  
 [in]*pBarToDock*  
 ドッキングされているペインです。  
  
### <a name="return-value"></a>戻り値  
 ドッキング状態です。  
  
### <a name="remarks"></a>Remarks  
 ドッキング状態には、次の値のいずれかを指定できます。  
  
|AFX_CS_STATUS 値|説明|  
|---------------------------|-------------|  
|CS_NOTHING|ドッキング サイト上、ポインターはします。 そのため、ウィンドウがように浮動です。|  
|CS_DOCK_IMMEDIATELY|イミディ エイト モードでのドッキング サイト上にポインターが (DT_IMMEDIATE スタイルが有効になって) ため、すぐに、ウィンドウをドッキングする必要があります。|  
|CS_DELAY_DOCK|ドッキング サイトは、別のドッキング ペインまたはメイン フレームの境界を上にポインターがします。|  
|CS_DELAY_DOCK_TO_TAB|タブ付きウィンドウにドッキングするのには、ウィンドウの原因となるドッキング サイト上にポインターがします。 これは、別のドッキング ペインのキャプションまたはタブ付きウィンドウのタブ領域の上にマウスが発生します。|  
  
##  <a name="disablerestoredockstate"></a>  CDockingManager::DisableRestoreDockState  
 有効またはレジストリからドッキング レイアウトの読み込みを無効にします。  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bDisable*  
 `TRUE` レジストリからドッキング レイアウトの読み込みを無効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出すアプリケーションの状態を読み込むときに、ドッキング ペインおよびツールバーの現在のレイアウトを維持する必要があります。  
  
##  <a name="dockpane"></a>  CDockingManager::DockPane  
 別のウィンドウまたはフレーム ウィンドウには、ペインをドッキングします。  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 バーへのポインターにドッキングするウィンドウです。  
  
 [in]*辺*  
 ドッキングするのには、バーの id。  
  
 [in]*lpRect*  
 移行先の四角形。  
  
##  <a name="dockpaneleftof"></a>  CDockingManager::DockPaneLeftOf  
 ペインを別のペインの左側にドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBarToDock*  
 左側にドッキングするウィンドウへのポインター *pTargetBar*です。  
  
 [in]*pTargetBar*  
 ターゲット ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが正常にドッキング可能な場合それ以外の場合、`FALSE`です。  
  
##  <a name="enableautohidepanes"></a>  CDockingManager::EnableAutoHidePanes  
 メイン フレーム ウィンドウのドッキング、ドッキング ペインを作成でき、コントロール バーのリストに追加します。  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwStyle*  
 ドッキングの配置。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング ウィンドウが正常に作成された場合`FALSE`それ以外の場合。  
  
##  <a name="enabledocking"></a>  CDockingManager::EnableDocking  
 ドッキング ペインを作成し、メイン フレーム ウィンドウのドッキングを有効にします。  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwStyle*  
 ドッキングの配置。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング ウィンドウが正常に作成された場合`FALSE`それ以外の場合。  
  
##  <a name="enabledocksitemenu"></a>  CDockingManager::EnableDockSiteMenu  
 すべてのドッキング ペインのキャプションにポップアップ メニューを開き、追加のボタンを表示します。  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 `TRUE` ドッキング サイト メニュー; を有効にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 ドッキング サイト メニューには、ペインのドッキング状態を変更するため、次のオプションが表示されます。  
  
- `Floating` -ペインをフローティングします。  
  
- `Docking` -メイン フレームのウィンドウがドッキングされた最後の位置にあるペインをドッキングします。  
  
- `AutoHide` -、ペインを autohide モードに切り替わります  
  
- `Hide` ウィンドウを非表示になります  
  
 既定では、このメニューは表示されません。  
  
##  <a name="enablepanecontextmenu"></a>  CDockingManager::EnablePaneContextMenu  
 ユーザーがマウスの右ボタンをクリックするし、ライブラリ、WM_CONTEXTMENU メッセージの処理は、アプリケーションのツールバーとドッキング ウィンドウの一覧を持っている特殊なコンテキスト メニューを表示するライブラリを指示します。  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 場合`TRUE`場合、ライブラリが自動のコンテキスト メニューのサポートをオンに`FALSE`ライブラリが自動のコンテキスト メニューのサポートをオフにします。  
  
 [in]*uiCustomizeCmd*  
 コマンド id を**カスタマイズ**メニュー項目。  
  
 [in]*strCustomizeText*  
 テキスト、**カスタマイズ**項目。  
  
 [in]*bToolbarsOnly*  
 場合`TRUE`、メニューは、場合に、アプリケーション ツールバーの一覧のみを表示`FALSE`ライブラリでは、アプリケーションのドッキング ペインをこのリストに追加します。  
  
##  <a name="finddocksite"></a>  CDockingManager::FindDockSite  
 バーを取得、指定した位置であるし、指定されたアラインメントを持つウィンドウです。  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*場合*  
 バーの配置ウィンドウです。  
  
 [in]*bOuter*  
 場合`TRUE`、コントロール バーのリストの先頭にあるバーを取得します。 それ以外の場合、コントロール バーのリスト内の末尾位置にあるバーを取得します。  
  
### <a name="return-value"></a>戻り値  
 指定した位置が; ドッキング ペイン`NULL`それ以外の場合。  
  
##  <a name="findpanebyid"></a>  CDockingManager::FindPaneByID  
 指定したコントロール ID によってペインを検索します。  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uBarID*  
 検索するウィンドウのコントロール ID を指定します。  
  
 [in]*bSearchMiniFrames*  
 `TRUE` 検索に含めるすべてのフローティング ペイン、します。 `FALSE` 含めるドッキング ペインだけです。  
  
### <a name="return-value"></a>戻り値  
 [CBasePane](../../mfc/reference/cbasepane-class.md)を指定したコントロール ID を持つオブジェクトまたは`NULL`場合は、指定したウィンドウが見つかりません。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="finddocksitebypane"></a>  CDockingManager::FindDockSiteByPane  
 バーを返しますターゲット バー ペインの id を持つウィンドウです。  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pTargetBar*  
 対象のバー ペインへのポインター。  
  
### <a name="return-value"></a>戻り値  
 バーを対象のバー ペインの id を持つペイン`NULL`バー ウィンドウなどが存在しない場合。  
  
##  <a name="fixupvirtualrects"></a>  CDockingManager::FixupVirtualRects  
 ツールバーの現在位置の仮想四角形をコミットします。  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Remarks  
 ユーザーは、ツールバーのドラッグを起動するときにアプリケーションが記憶している元の位置で、*仮想の長方形*です。 ユーザーは、ツールバーをドッキング サイト間で移動、ときに、ツールバーには他のツールバーが変わることがあります。 他のツールバーの元の位置は、対応する仮想四角形に格納されます。  
  
##  <a name="framefrompoint"></a>  CDockingManager::FrameFromPoint  
 指定したポイントを含むフレームを返します。  
  
```  
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,  
    CPaneFrameWnd* pFrameToExclude,  
    BOOL bFloatMultiOnly) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pt*  
 確認の画面座標で、ポイントを指定します。  
  
 [in]*pFrameToExclude*  
 除外するフレームへのポインター。  
  
 [in]*bFloatMultiOnly*  
 `TRUE` インスタンスではないフレームを除外する`CMultiPaneFrameWnd`です。`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 指定したポイントを含むフレーム`NULL`それ以外の場合。  
  
##  <a name="getclientareabounds"></a>  CDockingManager::GetClientAreaBounds  
 クライアント領域の境界を含む四角形を取得します。  
  
```  
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [out]*rcClient*  
 クライアント領域の境界を含む四角形への参照。  
  
### <a name="return-value"></a>戻り値  
 クライアント領域の境界を含む四角形。  
  
##  <a name="getdockingmode"></a>  CDockingManager::GetDockingMode  
 現在のドッキング モードを返します。  
  
```  
static AFX_DOCK_TYPE GetDockingMode();
```  
  
### <a name="return-value"></a>戻り値  
 現在のドッキング モードを表す列挙値。 次の値のいずれかを指定できます。  
  
- `DT_STANDARD`  
  
- `DT_IMMEDIATE`  
  
- `DT_SMART`  
  
### <a name="remarks"></a>Remarks  
 ドッキングのモードを設定するには、呼び出す[CDockingManager::SetDockingMode](#setdockingmode)です。  
  
##  <a name="getdocksiteframewnd"></a>  CDockingManager::GetDockSiteFrameWnd  
 親ウィンドウ フレームへのポインターを取得します。  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親ウィンドウ フレームへのポインター。  
  
##  <a name="getenabledautohidealignment"></a>  CDockingManager::GetEnabledAutoHideAlignment  
 ウィンドウの有効な配置を返します。  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ビットごとの組み合わせ`CBRS_ALIGN_`フラグ、または自動的に隠すウィンドウが有効になっていない場合は 0 です。 詳細については、次を参照してください。 [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking)です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、自動非表示コントロール バーの有効な配置を返します。 自動的に隠すバーを有効にするを呼び出す[CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)です。  
  
##  <a name="getminiframes"></a>  CDockingManager::GetMiniFrames  
 ミニフレームの一覧を取得します。  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール バー、ドッキング マネージャーに属しているを含むミニフレームの一覧です。  
  
##  <a name="getouteredgebounds"></a>  CDockingManager::GetOuterEdgeBounds  
 フレームの外側のエッジを含んだ四角形を取得します。  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレームの外側のエッジを含む四角形。  
  
##  <a name="getpanelist"></a>  CDockingManager::GetPaneList  
 ドッキング マネージャーに属しているウィンドウの一覧を返します。 これには、すべてのフローティング ウィンドウが含まれます。  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力].*lstBars*  
 現在のドッキング マネージャーのすべてのペインが含まれています。  
  
 [in]*bIncludeAutohide*  
 `TRUE` 自動的に隠すモード; 内にあるペインを含めるそれ以外の場合、`FALSE`です。  
  
 [in]*pRTCFilter*  
 ない場合`NULL`、返された一覧にはペインのみ、指定したランタイム クラスが含まれています。  
  
 [in]*bIncludeTabs*  
 `TRUE` タブを含めるそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 ポインターを返します、ドッキング マネージャーに任意のタブ付きペインがある場合は、 [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)オブジェクトとする必要があります列挙タブ明示的にします。  
  
 使用して*pRTCFilter*ペインの特定のクラスを取得します。 たとえば、この値を適切に設定してツールバーのみを取得できます。  
  
##  <a name="getsmartdockingmanager"></a>  CDockingManager::GetSmartDockingManager  
 スマート ドッキング マネージャーへのポインターを取得します。  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、[スマート ドッキング マネージャー](http://msdn.microsoft.com/en-us/f537a1a6-fb9e-41d7-952f-0f25d5ee7534)です。  
  
##  <a name="getsmartdockingmanagerpermanent"></a>  CDockingManager::GetSmartDockingManagerPermanent  
 スマート ドッキング マネージャーへのポインターを取得します。  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スマート ドッキング マネージャーへのポインター。  
  
##  <a name="getsmartdockingparams"></a>  CDockingManager::GetSmartDockingParams  
 スマート ドッキングのパラメーターをドッキング マネージャーを返します。  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>戻り値  
 現在、ドッキング マネージャー スマート ドッキングのパラメーターを格納するクラス。 詳細については、次を参照してください。 [CSmartDockingInfo クラス](../../mfc/reference/csmartdockinginfo-class.md)です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="hideautohidepanes"></a>  CDockingManager::HideAutoHidePanes  
 自動非表示モードになっているウィンドウを非表示にします。  
  
```  
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,  
    BOOL bImmediately = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBarToExclude*  
 非表示から除外するバーへのポインター。  
  
 [in]*bImmediately*  
 `TRUE` すぐに、ウィンドウを非表示にするには`FALSE`効果が自動的に隠すウィンドウを非表示にします。  
  
##  <a name="insertdocksite"></a>  CDockingManager::InsertDockSite  
 ドッキング ペインを作成し、コントロール バーのリストに挿入します。  
  
```  
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,  
    DWORD dwAlignToInsertAfter,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*情報*  
 ドッキング ウィンドウの配置情報を含む構造体。  
  
 [in]*dwAlignToInsertAfter*  
 ドッキング ウィンドウの配置です。  
  
 [out]*ppDockBar*  
 ドッキング ペインへのポインターへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング ウィンドウが正常に作成された場合`FALSE`それ以外の場合。  
  
##  <a name="insertpane"></a>  CDockingManager::InsertPane  
 コントロール ウィンドウをコントロール バーのリストに挿入します。  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pControlBar*  
 コントロール ウィンドウへのポインター。  
  
 [in]*pTarget*  
 ターゲット ウィンドウへのポインター。  
  
 [in]*bAfter*  
 `TRUE` 対象のペインの位置の後に、ウィンドウを挿入するには`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` コントロールのウィンドウが正しく; のコントロール バーのリストに追加された場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 コントロール ウィンドウのコントロール バーのリストで既に場合、または対象のペインがコントロール バーのリストに存在しない場合、このメソッドは false を返します。  
  
##  <a name="isdocksitemenu"></a>  CDockingManager::IsDockSiteMenu  
 ポップアップ メニューがすべてのウィンドウのキャプションに表示されるかどうかを指定します。  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング サイト メニューがすべてのドッキング ペインのキャプションに表示されている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 呼び出して、ドック サイト メニューを有効にすることができます[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)です。  
  
##  <a name="isinadjustlayout"></a>  CDockingManager::IsInAdjustLayout  
 すべてのウィンドウのレイアウトを調整するかどうかを判断します。  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` すべてのウィンドウのレイアウトが調整されている場合`FALSE`それ以外の場合。  
  
##  <a name="isolecontainermode"></a>  CDockingManager::IsOLEContainerMode  
 OLE コンテナー モードでは、ドッキング マネージャーかどうかを指定します。  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` OLE コンテナー モードである場合は、ドッキング マネージャーそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 OLE コンテナー モードですべてのアプリケーションのツールバーとドッキング ペインは表示されません。 ペインも非表示にこのモードで設定した場合[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)に`TRUE`です。  
  
##  <a name="ispointneardocksite"></a>  CDockingManager::IsPointNearDockSite  
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
  
 [out]*dwBarAlignment*  
 点が近い端を指定します。 指定できる値は、`CBRS_ALIGN_LEFT`、`CBRS_ALIGN_RIGHT`、`CBRS_ALIGN_TOP`、および `CBRS_ALIGN_BOTTOM` です。  
  
 [out]*bOuterEdge*  
 `TRUE` ドッキング サイトの外側の境界線の近くのポイントがある場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング サイトの近くのポイントがある場合それ以外の場合`FALSE`です。  
  
##  <a name="isprintpreviewvalid"></a>  CDockingManager::IsPrintPreviewValid  
 印刷プレビュー モードが設定されているかどうかを判断します。  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 印刷プレビュー モードが設定されている場合`FALSE`それ以外の場合。  
  
##  <a name="loadstate"></a>  CDockingManager::LoadState  
 レジストリからドッキング マネージャーの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 プロファイルの名前。  
  
 [in]*uiID*  
 ドッキング マネージャーの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング マネージャーの状態が正常に読み込まれている場合それ以外の場合`FALSE`です。  
  
##  <a name="lockupdate"></a>  CDockingManager::LockUpdate  
 指定されたウィンドウをロックします。  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ブロック*  
 `TRUE` 場合は、ウィンドウがロックされています。`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 ウィンドウがロックされると、移動することはできませんし、再描画されることはできません。  
  
##  <a name="m_bhidedockingbarsincontainermode"></a>  CDockingManager::m_bHideDockingBarsInContainerMode  
 OLE コンテナー モードのペインがドッキング マネージャーに非表示にするかどうかを指定します。  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Remarks  
 この値を設定`FALSE`メイン フレームにドッキングされているすべてのペインを保持する場合と、アプリケーションが OLE コンテナー モード。 この値は、既定では、`TRUE`です。  
  
##  <a name="m_dockmodeglobal"></a>  CDockingManager::m_dockModeGlobal  
 グローバルのドッキング モードを指定します。  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Remarks  
 既定では、各ドッキング ペインは、このドッキングのモードを使用します。 このフィールドに設定できる値の詳細については、次を参照してください。 [cbasepane::getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode)です。  
  
##  <a name="m_ndocksensitivity"></a>  CDockingManager::m_nDockSensitivity  
 ドッキングと小文字の区別を指定します。  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Remarks  
 ドッキングの感度をどのくらい近づいて浮動定義ウィンドウから、フレームワークのドッキング状態を変更する前に、ドッキング ペイン、ドッキング サイト、または別のペインを得ることができます。  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>  CDockingManager::m_nTimeOutBeforeDockingBarDock  
 イミディ エイト モードでドッキング、ドッキング ウィンドウがドッキングされるまでは、時間 (ミリ秒単位) を指定します。  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Remarks  
 ペインをドッキングすると、前に、フレームワークは、一定の時間を待機します。 これは、ウィンドウが誤ったにドッキングされる場所、ユーザーがドラッグ中にすることを防ぎます。  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>  CDockingManager::m_nTimeOutBeforeToolBarDock  
 ツールバーがメイン フレーム ウィンドウにドッキングされる前に、時間 (ミリ秒単位) を指定します。  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Remarks  
 ツールバーをドッキングすると、前に、フレームワークは、一定の時間を待機します。 これは、ツールバーが誤ったにドッキングされる場所、ユーザーがドラッグ中にすることを防ぎます。  
  
##  <a name="onactivateframe"></a>  CDockingManager::OnActivateFrame  
 フレーム ウィンドウがアクティブまたは非アクティブ化するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bActivate*  
 場合`TRUE`、フレーム ウィンドウがアクティブになります以外の場合は`FALSE`、フレーム ウィンドウが非アクティブ化します。  
  
##  <a name="onclosepopupmenu"></a>  CDockingManager::OnClosePopupMenu  
 アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>Remarks  
 現在のメイン ウィンドウを閉じるしようとしているときに、フレームワークは WM_DESTROY メッセージを送信します。 通知を処理するには、このメソッドをオーバーライド`CMFCPopupMenu`フレーム ウィンドウに属するオブジェクトと、`CMFCPopupMenu`オブジェクトのプロセス、`WM_DESTROY`メッセージ。  
  
##  <a name="onmoveminiframe"></a>  CDockingManager::OnMoveMiniFrame  
 ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pFrame*  
 ミニフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
##  <a name="onpanecontextmenu"></a>  CDockingManager::OnPaneContextMenu  
 ウィンドウのリストを持つメニューを作成するときに、フレームワークによって呼び出されます。  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 メニューの場所を指定します。  
  
##  <a name="panefrompoint"></a>  CDockingManager::PaneFromPoint  
 指定したポイントを含むウィンドウを返します。  
  
```  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL,  
    BOOL bCheckVisibility = FALSE,  
    const CBasePane* pBarToIgnore = NULL) const;  
  
virtual CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    DWORD& dwAlignment,  
    CRuntimeClass* pRTCBarType = NULL,  
    const CBasePane* pBarToIgnore = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 確認の画面座標で、ポイントを指定します。  
  
 [in]*nSensitivity*  
 チェックする各ペインの ウィンドウ四角形を拡大するための値です。 ペインは、指定したポイントが高めのこの領域の場合、検索条件を満たします。  
  
 [in]*bExactBar*  
 `TRUE` 無視する、 *nSensitivity*パラメーターです。 それ以外の場合、`FALSE`です。  
  
 [in]*pRTCBarType*  
 ない場合`NULL`、指定した型のペインのみが検索されます。  
  
 [in]*bCheckVisibility*  
 `TRUE` 表示ペインにのみをチェックするにはそれ以外の場合、`FALSE`です。  
  
 [out]*場合*  
 指定した位置に、ウィンドウが見つかった場合、このパラメーターには、指定したポイントに最も近いしたペインの横が含まれています。 詳細については、「解説」を参照してください。  
  
 [in]*pBarToIgnore*  
 ない場合`NULL`メソッドは、このパラメーターで指定されたウィンドウを無視します。  
  
### <a name="return-value"></a>戻り値  
 [CBasePane](../../mfc/reference/cbasepane-class.md)-特定のポイントを格納しているオブジェクトを派生または`NULL`ウィンドウが見つからなかった場合です。  
  
### <a name="remarks"></a>Remarks  
 この関数を返し、ペインが見つかりましたが、*場合*指定した点の配置が含まれています。 たとえば、次の点が、ウィンドウの上部に最も近い*場合*に設定されている`CBRS_ALIGN_TOP`です。  
  
##  <a name="processpanecontextmenucommand"></a>  CDockingManager::ProcessPaneContextMenuCommand  
 選択または指定されたコマンドに対してチェック ボックスをオフにし、表示されるペインのレイアウトを再計算するため、フレームワークによって呼び出されます。  
  
```  
BOOL ProcessPaneContextMenuCommand(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nID*  
 メニュー コントロール バーの id。  
  
 [in]*nCode*  
 コマンド通知コード。  
  
 [in]*pExtra*  
 ポインターにキャストが無効にすることへのポインター`CCmdUI`場合*nCode* CN_UPDATE_COMMAND_UI がします。  
  
 [in]*pHandlerInfo*  
 情報構造体へのポインター。 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合*pEXtra*が NULL でないと*nCode* CN_UPDATE_COMMAND_UI、equals、指定したコントロール バーがある場合または*nID*です。  
  
##  <a name="recalclayout"></a>  CDockingManager::RecalcLayout  
 コントロールのリストに存在するコントロールの内部レイアウトを再計算されます。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bNotify*  
 このパラメーターは使用されません。  
  
##  <a name="releaseemptypanecontainers"></a>  CDockingManager::ReleaseEmptyPaneContainers  
 空のペインのコンテナーを解放します。  
  
```  
void ReleaseEmptyPaneContainers();
```  
  
##  <a name="removehiddenmditabbedbar"></a>  CDockingManager::RemoveHiddenMDITabbedBar  
 指定した非表示のウィンドウ バーを削除します。  
  
```  
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 バーへのポインターを削除するウィンドウです。  
  
##  <a name="removeminiframe"></a>  CDockingManager::RemoveMiniFrame  
 ミニフレームの一覧から指定したフレームを削除します。  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWnd*  
 削除するためのフレームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 指定したフレームが削除された場合`FALSE`それ以外の場合。  
  
##  <a name="removepanefromdockmanager"></a>  CDockingManager::RemovePaneFromDockManager  
 ペインの登録を解除し、ドッキング マネージャーの一覧から削除します。  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pWnd*  
 削除するウィンドウへのポインター。  
  
 [in]*bDestroy*  
 場合`TRUE`、削除されたウィンドウが破棄されます。  
  
 [in]*bAdjustLayout*  
 場合`TRUE`、すぐにドッキング レイアウトを調整します。  
  
 [in]*bAutoHide*  
 場合`TRUE`ペインが自動的に隠すバーのリストから削除します。 場合`FALSE`、標準のペインの一覧から、ウィンドウを削除します。  
  
 [in]*pBarReplacement*  
 削除されるペインに置き換えられるペインへのポインター。  
  
##  <a name="replacepane"></a>  CDockingManager::ReplacePane  
 ペインを別のペインに置き換えます。  
  
```  
BOOL ReplacePane(
    CDockablePane* pOriginalBar,  
    CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pOriginalBar*  
 元のウィンドウへのポインター。  
  
 [in]*pNewBar*  
 元のウィンドウを置換するウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウが正常に置換されます。`FALSE`それ以外の場合。  
  
##  <a name="resortminiframesforzorder"></a>  CDockingManager::ResortMiniFramesForZOrder  
 ミニフレームの一覧で、フレームを使用します。  
  
```  
void ResortMiniFramesForZOrder();
```  
  
##  <a name="savestate"></a>  CDockingManager::SaveState  
 レジストリには、ドッキング マネージャーの状態を保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 レジストリ キーへのパス。  
  
 [in]*uiID*  
 ドッキングのマネージャー id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 状態が正常に保存されている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 レジストリにドッキング マネージャーの状態の保存コントロール バーの状態、自動的に隠すバーの状態と、ドッキング マネージャーに存在ミニフレームの状態を保存する必要があります。  
  
##  <a name="sendmessagetominiframes"></a>  CDockingManager::SendMessageToMiniFrames  
 すべてのミニフレームに指定されたメッセージを送信します。  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uMessage*  
 送信するメッセージ。  
  
 [in]*wParam*  
 追加のメッセージの依存情報。  
  
 [in]*lParam*  
 追加のメッセージの依存情報。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` いつも。  
  
##  <a name="serialize"></a>  CDockingManager::Serialize  
 アーカイブは、ドッキング マネージャーに書き込みます。  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ar*  
 アーカイブ オブジェクトへの参照。  
  
### <a name="remarks"></a>Remarks  
 アーカイブ ファイルに、ドッキング マネージャーを書き込むには、ドッキング コントロール バーやスライダー、およびコントロール バー、ミニフレーム、自動的に隠すバー、および MDI タブ付きのバーのアーカイブへの書き込みの数の決定が含まれます。  
  
##  <a name="setautohidezorder"></a>  CDockingManager::SetAutohideZOrder  
 サイズ、幅、およびコントロール バーと、指定したウィンドウの高さを設定します。  
  
```  
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pAHDockingBar*  
 ドッキング可能ペインへのポインター。  
  
##  <a name="setdockingmode"></a>  CDockingManager::SetDockingMode  
 ドッキングのモードを設定します。  
  
```  
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,  
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```  
  
### <a name="parameters"></a>パラメーター  
 *dockMode*  
 新しいドッキング モードを指定します。 詳細については、「解説」を参照してください。  
  
 *テーマ*  
 スマート ドッキング マーカーに使用されるテーマを指定します。 次の列挙値のいずれかです: AFX_SDT_DEFAULT、AFX_SDT_VS2005、AFX_SDT_VS2008 です。  
  
### <a name="remarks"></a>Remarks  
 この静的メソッドを呼び出してドッキング モードを設定します。  
  
 *dockMode*次の値のいずれかになります。  
  
- `DT_STANDARD` 標準 Visual Studio .NET 2003 で実装されているモードをドッキングします。 ウィンドウは、ドラッグ コンテキストを使用せずにドラッグします。  
  
- `DT_IMMEDIATE` 即時のドッキング モードとしては、Microsoft Visio で実装されます。 ドラッグのコンテキストでウィンドウがドラッグが、マーカーは表示されません。  
  
- `DT_SMART` -Visual Studio 2005 で実装されるドッキング モードをスマートします。 ウィンドウがドラッグ コンテキストにドラッグし、スマート マーカーを表示するペインのドッキング位置を示すです。  
  
##  <a name="setdockstate"></a>  CDockingManager::SetDockState  
 コントロール バー、ミニ フレーム、および自動的に隠すバーのドッキング状態を設定します。  
  
```  
virtual void SetDockState();
```  
  
##  <a name="setprintpreviewmode"></a>  CDockingManager::SetPrintPreviewMode  
 印刷プレビューで表示されるバーの印刷プレビュー モードを設定します。  
  
```  
void SetPrintPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bPreview*  
 `TRUE` 印刷プレビュー モードが設定されている場合`FALSE`それ以外の場合。  
  
 [in]*pState*  
 プレビュー状態へのポインター。 このパラメーターは使用されません。  
  
##  <a name="setsmartdockingparams"></a>  CDockingManager::SetSmartDockingParams  
 スマート ドッキングの動作を定義するパラメーターを設定します。  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力].*params*  
 スマート ドッキングのパラメーターを定義します。  
  
### <a name="remarks"></a>Remarks  
 外観、色、またはスマート ドッキング マーカーの形状をカスタマイズする場合は、このメソッドを呼び出します。  
  
 スマート ドッキング マーカーの既定の表示形式を使用するには、インスタンスを初期化されていないを渡す[CSmartDockingInfo クラス](../../mfc/reference/csmartdockinginfo-class.md)に*params*です。  
  
##  <a name="showdelayshowminiframes"></a>  CDockingManager::ShowDelayShowMiniFrames  
 ミニフレーム ウィンドウの表示と非表示を切り替えます。  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bShow*  
 `TRUE` 表示されているフレームのウィンドウをアクティブ; にするには`FALSE`フレームのウィンドウを非表示にします。  
  
##  <a name="showpanes"></a>  CDockingManager::ShowPanes  
 コントロールと自動的に隠すバーのウィンドウの表示と非表示を切り替えます。  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bShow*  
 `TRUE` ウィンドウを表示するには`FALSE`ペインを非表示にします。  
  
### <a name="return-value"></a>戻り値  
 常に `FALSE`。  
  
##  <a name="startsdocking"></a>  CDockingManager::StartSDocking  
 スマート ドッキング マネージャーの配置に応じて指定したウィンドウのスマート ドッキングを開始します。  
  
```  
void StartSDocking(CWnd* pDockingWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDockingWnd*  
 ドッキングするウィンドウへのポインター。  
  
##  <a name="stopsdocking"></a>  CDockingManager::StopSDocking  
 スマート ドッキングを停止します。  
  
```  
void StopSDocking();
```  
  
##  <a name="getsmartdockingtheme"></a>  CDockingManager::GetSmartDockingTheme  
 スマート ドッキング マーカーの表示に使用されるテーマを返す静的メソッド。  
  
```  
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```  
  
### <a name="return-value"></a>戻り値  
 次の列挙値のいずれかを返します: AFX_SDT_DEFAULT、AFX_SDT_VS2005、AFX_SDT_VS2008 です。  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)
