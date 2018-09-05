---
title: CDockingManager Class |Microsoft Docs
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
ms.openlocfilehash: 08b8aa623f79c32303a0d5fb84c9b865bff918d9
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43683578"
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
|[CDockingManager::AddDockSite](#adddocksite)|ドッキング ペインを作成し、それをコントロール バーのリストに追加します。|  
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|バーに識別するハンドルを追加 ウィンドウを非表示の MDI タブ付きバー ペインの一覧にします。|  
|[CDockingManager::AddMiniFrame](#addminiframe)|ミニフレームの一覧には、フレームを追加します。|  
|[CDockingManager::AddPane](#addpane)|ペインをドッキング マネージャーに登録します。|  
|[CDockingManager::AdjustDockingLayout](#adjustdockinglayout)|再計算し、フレーム ウィンドウ内のすべてのウィンドウのレイアウトを調整します。|  
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|すべてのペインに送られる WM_NCCALCSIZE メッセージと`CPaneFrameWnd`windows。|  
|[CDockingManager::AdjustRectToClientArea](#adjustrecttoclientarea)|四角形の配置を調整します。|  
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|全体の幅またはで囲まれたフレームのクライアント領域の高さのドッキング サイトになるため、自動非表示モードでのドッキング ペインをサイズします。|  
|[CDockingManager::AutoHidePane](#autohidepane)|自動的に隠すツールバーを作成します。|  
|[CDockingManager::BringBarsToTop](#bringbarstotop)|先頭に指定された配置を持つドッキング バーが表示されます。|  
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|メニューには、ドッキング ペインおよびツールバーの名前を追加します。|  
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|ドッキング ウィンドウの予想される四角形を計算します。|  
|[CDockingManager::Create](#create)|ドッキング マネージャーを作成します。|  
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|特定のポイントとそのドッキング状態を含むウィンドウを決定します。|  
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|有効または、レジストリからのドッキング レイアウトの読み込みを無効にします。|  
|[CDockingManager::DockPane](#dockpane)|別のウィンドウまたはフレーム ウィンドウ ペインをドッキングします。|  
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|ペインを別のペインの左側にドッキングします。|  
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|メイン フレーム ウィンドウのドッキングを有効がドック ウィンドウを作成し、コントロール バーのリストに追加します。|  
|[CDockingManager::EnableDocking](#enabledocking)|ドッキング ペインを作成し、メイン フレーム ウィンドウのドッキングを有効にします。|  
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|すべてのドッキング ペインのキャプションにポップアップ メニューを開き、追加のボタンが表示されます。|  
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|ユーザーがマウスの右ボタンをクリックし、ライブラリ WM_CONTEXTMENU メッセージの処理はときに、アプリケーションのツールバーとドッキング ペインの一覧のある特別なコンテキスト メニューを表示するライブラリに指示します。|  
|[CDockingManager::FindDockSite](#finddocksite)|バーを取得します。 指定した位置にあると、指定された配置を持つウィンドウです。|  
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|バーを返しますターゲット バー ペインの id を持つウィンドウです。|  
|[CDockingManager::FindPaneByID](#findpanebyid)|指定したコントロール ID によってペインを検索します|  
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|ツールバーの現在位置の仮想四角形をコミットします。|  
|[CDockingManager::FrameFromPoint](#framefrompoint)|指定したポイントを含むフレームを返します。|  
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|クライアント領域の境界を含む四角形を取得します。|  
|[CDockingManager::GetDockingMode](#getdockingmode)|現在のドッキング モードを返します。|  
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|親ウィンドウのフレームへのポインターを取得します。|  
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|ウィンドウの有効な配置を返します。|  
|[CDockingManager::GetMiniFrames](#getminiframes)|ミニフレームの一覧を取得します。|  
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|フレームの外側のエッジを含む四角形を取得します。|  
|[CDockingManager::GetPaneList](#getpanelist)|ドッキング マネージャーに属しているウィンドウの一覧を返します。 これには、すべての浮動ペインが含まれます。|  
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|スマート ドッキング マネージャーへのポインターを取得します。|  
|[CDockingManager::GetSmartDockingManagerPermanent](#getsmartdockingmanagerpermanent)|スマート ドッキング マネージャーへのポインターを取得します。|  
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|ドッキング マネージャーのスマート ドッキングのパラメーターを返します。|  
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|スマート ドッキング マーカーの表示に使用されるテーマを返す静的メソッド。|  
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|自動非表示モードになっているウィンドウを非表示にします。|  
|[CDockingManager::InsertDockSite](#insertdocksite)|ドッキング ペインを作成し、コントロール バーのリストに挿入します。|  
|[CDockingManager::InsertPane](#insertpane)|コントロール バーのリストには、コントロールのウィンドウを挿入します。|  
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|すべてのペインのキャプションにポップアップ メニューが表示されるかどうかを指定します。|  
|[CDockingManager::IsInAdjustLayout](#isinadjustlayout)|すべてのペインのレイアウトを調整するかどうかを決定します。|  
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|OLE コンテナー モードで、ドッキング マネージャーであるかどうかを指定します。|  
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|指定したポイントがドッキング サイトに近いかどうかを判断します。|  
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|印刷プレビュー モードが設定されているかどうかを決定します。|  
|[CDockingManager::LoadState](#loadstate)|レジストリから、ドッキング マネージャーの状態を読み込みます。|  
|[CDockingManager::LockUpdate](#lockupdate)|指定されたウィンドウをロックします。|  
|[CDockingManager::OnActivateFrame](#onactivateframe)|フレーム ウィンドウがアクティブになりますかが非アクティブ化するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。|  
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|ペインの一覧のあるメニューを作成するときに、フレームワークによって呼び出されます。|  
|[CDockingManager::PaneFromPoint](#panefrompoint)|指定したポイントを含むペインを返します。|  
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|選択または指定されたコマンドのチェック ボックスをオフにし、表示されるペインのレイアウトを再計算するため、フレームワークによって呼び出されます。|  
|[CDockingManager::RecalcLayout](#recalclayout)|コントロールのリストに存在するコントロールの内部レイアウトを再計算します。|  
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|空のペインのコンテナーを解放します。|  
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|指定した非表示のウィンドウ バーを削除します。|  
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|ミニフレームの一覧から、指定したフレームを削除します。|  
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|ウィンドウの登録を解除し、ドッキング マネージャーの一覧から削除されます。|  
|[CDockingManager::ReplacePane](#replacepane)|ペインを別のペインに置き換えます。|  
|[CDockingManager::ResortMiniFramesForZOrder](#resortminiframesforzorder)|ミニフレームの一覧内のフレームを場合します。|  
|[CDockingManager::SaveState](#savestate)|レジストリには、ドッキング マネージャーの状態を保存します。|  
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|すべてのミニフレームを指定したメッセージを送信します。|  
|[CDockingManager::Serialize](#serialize)|アーカイブは、ドッキング マネージャーに書き込みます。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|  
|[CDockingManager::SetAutohideZOrder](#setautohidezorder)|サイズ、幅、およびコントロール バーと、指定したウィンドウの高さを設定します。|  
|[CDockingManager::SetDockingMode](#setdockingmode)|ドッキングのモードを設定します。|  
|[CDockingManager::SetDockState](#setdockstate)|コントロール バー、ミニ フレーム、および自動的に隠すバーのドッキング状態を設定します。|  
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|印刷プレビューで表示されるバーの印刷プレビュー モードを設定します。|  
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|スマート ドッキングの動作を定義するパラメーターを設定します。|  
|[CDockingManager::ShowDelayShowMiniFrames](#showdelayshowminiframes)|ミニフレーム ウィンドウの表示と非表示を切り替えます。|  
|[CDockingManager::ShowPanes](#showpanes)|コントロールと自動的に隠すバーのウィンドウの表示と非表示を切り替えます。|  
|[CDockingManager::StartSDocking](#startsdocking)|スマート ドッキング マネージャーの配置に従って指定したウィンドウのスマート ドッキングを開始します。|  
|[CDockingManager::StopSDocking](#stopsdocking)|スマート ドッキングを停止します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|OLE コンテナー モードのペインがドッキング マネージャーに非表示にするかどうかを指定します。|  
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|グローバルのドッキングのモードを指定します。|  
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|ドッキングの感度を指定します。|  
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|イミディ エイト モードでドッキング ドッキング ペインをドッキングする前に、(ミリ秒単位)、時間を指定します。|  
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|メイン フレーム ウィンドウにツールバーをドッキングする前に、(ミリ秒単位)、時間を指定します。|  
  
## <a name="remarks"></a>Remarks  
 メイン フレーム ウィンドウでは、作成して、自動的にこのクラスを初期化します。  
  
 ドッキング マネージャー オブジェクトのすべてのリストとドッキングのレイアウトに含まれるすべてのペインのリストを保持する[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)メイン フレーム ウィンドウに属している windows。  
  
 `CDockingManager`クラスは、ウィンドウの検索に使用できる一部のサービスを実装または`CPaneFrameWnd`ウィンドウ。 通常は呼び出すことはありませんこれらのサービス直接メイン フレーム ウィンドウのオブジェクトにラップされるためです。 詳細については、次を参照してください。 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)します。  
  
## <a name="customization-tips"></a>カスタマイズのヒント  
 次のヒントを適用`CDockingManager`オブジェクト。  
  
- [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)これらドッキングのモードをサポートします。  
  
    - `AFX_DOCK_TYPE::DT_IMMEDIATE`  
  
    - `AFX_DOCK_TYPE::DT_STANDARD`  
  
    - `AFX_DOCK_TYPE::DT_SMART`  
  
     これらのドッキングのモードが定めた[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)呼び出すことによって設定されます[CDockingManager::SetDockingMode](#setdockingmode)。  
  
-   サイズを変更できない、フローティング ウィンドウを作成する場合は、呼び出し、 [CDockingManager::AddPane](#addpane)メソッド。 このメソッドは、ウィンドウのレイアウトを担当する、ドッキング マネージャーのウィンドウを登録します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CDockingManager`を構成するクラス、`CDockingManager`オブジェクト。 例では、すべてのドッキング ペインのキャプションにポップアップ メニューを開くための追加 ボタンを表示する方法と、オブジェクトのドッキングのモードを設定する方法を示します。 このコード スニペットの一部、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDockingManager](../../mfc/reference/cdockingmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDockingManager.h  
  
##  <a name="adddocksite"></a>  CDockingManager::AddDockSite  
 ドッキング ペインを作成し、それをコントロール バーのリストに追加します。  
  
```  
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,  
    CDockSite** ppDockBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*情報*  
 含む情報構造体への参照はドッキング ペインの配置です。  
  
 [out]*ppDockBar*  
 新しいドッキング ペインへのポインターへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ドッキング ウィンドウが正常に作成された場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="addhiddenmditabbedbar"></a>  CDockingManager::AddHiddenMDITabbedBar  
 バーに識別するハンドルを追加 ウィンドウを非表示の MDI タブ付きバー ペインの一覧にします。  
  
```  
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 バーへのポインターのウィンドウ  
  
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
 [入力、出力]*我が物*  
 ドッキング マネージャーに追加するウィンドウを指定します。  
  
 [in]*bTail*  
 ペインの一覧の末尾に、ドッキング マネージャーに、ウィンドウを追加する場合は TRUEそれ以外の場合、FALSE です。  
  
 [in]*bAutoHide*  
 内部使用のみ。 常に既定値 FALSE を使用します。  
  
 [in]*bInsertForOuterEdge*  
 内部使用のみ。 常に既定値 FALSE を使用します。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、ウィンドウはドッキング マネージャーに正常に登録されましたそれ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 サイズを変更できない、フローティング ウィンドウをドッキング マネージャーに登録するには、このメソッドを呼び出します。 ウィンドウを登録していない場合が正しく表示されない、ドッキング マネージャーがレイアウトされるとき。  
  
##  <a name="adjustdockinglayout"></a>  CDockingManager::AdjustDockingLayout  
 再計算し、フレーム ウィンドウ内のすべてのウィンドウのレイアウトを調整します。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hdwp*  
 遅延のウィンドウの位置の構造体を指定します。 詳細については、次を参照してください。[データ型の Windows](/windows/desktop/WinProg/windows-data-types)します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="addminiframe"></a>  CDockingManager::AddMiniFrame  
 ミニフレームの一覧には、フレームを追加します。  
  
```  
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*我が物*  
 フレームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 フレームがミニフレームの一覧にないし、正常に追加された場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="adjustpaneframes"></a>  CDockingManager::AdjustPaneFrames  
 すべてのペインに送られる WM_NCCALCSIZE メッセージと`CPaneFrameWnd`windows。  
  
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
 参照を`CRect`オブジェクト  
  
 [in]*場合*  
 配置、`CRect`オブジェクト  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合の配置、`CRect`オブジェクトが調整されました。FALSE それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 *場合*パラメーターには、次の値の 1 つには。  
  
-   CBRS_ALIGN_TOP  
  
-   CBRS_ALIGN_BOTTOM  
  
-   CBRS_ALIGN_LEFT  
  
-   CBRS_ALIGN_RIGHT  
  
##  <a name="alignautohidepane"></a>  CDockingManager::AlignAutoHidePane  
 全体の幅またはで囲まれたフレームのクライアント領域の高さのドッキング サイトになるため、自動非表示モードでのドッキング ペインをサイズします。  
  
```  
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,  
    BOOL bIsVisible = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDefaultSlider*  
 ドッキングのスライダー ペイン。  
  
 [in]*bIsVisible*  
 ドッキング ペインを表示する場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="autohidepane"></a>  CDockingManager::AutoHidePane  
 自動的に隠すツールバーを作成します。  
  
```  
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,  
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 バーへのポインターのウィンドウ。  
  
 [in]*pCurrAutoHideToolBar*  
 自動へのポインターには、ツールバーが非表示にします。  
  
### <a name="return-value"></a>戻り値  
 自動ツールバーを非表示にする場合は NULL は作成されませんでした。それ以外の場合、新しいツールバーへのポインター。  
  
##  <a name="bringbarstotop"></a>  CDockingManager::BringBarsToTop  
 先頭に指定された配置を持つドッキング バーが表示されます。  
  
```  
void BringBarsToTop(
    DWORD dwAlignment = 0,  
    BOOL bExcludeDockedBars = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*場合*  
 他のウィンドウの一番上に置かれるドッキング バーの配置です。  
  
 [in]*bExcludeDockedBars*  
 一番上にからドッキング バーを除外する場合は TRUEそれ以外の場合は FALSE です。  
  
##  <a name="buildpanesmenu"></a>  CDockingManager::BuildPanesMenu  
 メニューには、ドッキング ペインおよびツールバーの名前を追加します。  
  
```  
void BuildPanesMenu(
    CMenu& menu,  
    BOOL bToolbarsOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*メニュー*  
 ドッキング ペインおよびツールバーの名前を追加するメニュー。  
  
 [in]*bToolbarsOnly*  
 メニューにのみツールバー名を追加する場合は TRUEFALSE それ以外の場合。  
  
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
 [in]*我が物*  
 ドッキングするウィンドウへのポインター。  
  
 [in]*ptMouse*  
 マウスの位置。  
  
 [out]*rectResult*  
 計算される四角形。  
  
 [in]*bDrawTab*  
 タブを描画する場合は Trueそれ以外の場合は FALSE です。  
  
 [out]*ppTargetBar*  
 [ターゲット] ウィンドウへのポインターへのポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ウィンドウがユーザーによって指定されたポイントに、ウィンドウをドラッグした場合に使用される四角形を計算*ptMouse*し、そこにドッキングします。  
  
##  <a name="create"></a>  CDockingManager::Create  
 ドッキング マネージャーを作成します。  
  
```  
BOOL Create(CFrameWnd* pParentWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pParentWnd*  
 ドッキングのマネージャーの親フレームへのポインター。 この値は、NULL は指定できません。  
  
### <a name="return-value"></a>戻り値  
 常に true を設定します。  
  
##  <a name="determinepaneandstatus"></a>  CDockingManager::DeterminePaneAndStatus  
 特定のポイントとそのドッキング状態を含むウィンドウを決定します。  
  
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
 確認するウィンドウの場所。  
  
 [in]*nSensitivity*  
 チェックされている各ウィンドウのウィンドウの四角形を増加する値。 ペインは、この増加のリージョンでの指定したポイントがある場合に、検索条件を満たします。  
  
 [in]*dwEnabledAlignment*  
 ドッキング ウィンドウの配置です。  
  
 [out]*ppTargetBar*  
 [ターゲット] ウィンドウへのポインターへのポインター。  
  
 [in]*pBarToIgnore*  
 このウィンドウは、メソッドは無視します。  
  
 [in]*pBarToDock*  
 このウィンドウがドッキングされています。  
  
### <a name="return-value"></a>戻り値  
 ドッキング状態です。  
  
### <a name="remarks"></a>Remarks  
 ドッキング状態には、次の値のいずれかを指定できます。  
  
|AFX_CS_STATUS 値|説明|  
|---------------------------|-------------|  
|CS_NOTHING|ドッキング サイト上のポインターが。 そのため、ウィンドウがようにフローティングします。|  
|CS_DOCK_IMMEDIATELY|イミディ エイト モードでのドッキング サイト上にポインターが (DT_IMMEDIATE スタイルが有効になって) ため、すぐに、ウィンドウをドッキングする必要があります。|  
|CS_DELAY_DOCK|別のドッキング ペインまたはメイン フレームの端は、ドッキング サイト上にポインターが。|  
|CS_DELAY_DOCK_TO_TAB|タブ付きウィンドウにドッキングするウィンドウをドッキング サイト上にポインターが。 これには、別のドッキング ペインのキャプションまたはタブ付きウィンドウのタブ領域の上にマウスがときに発生します。|  
  
##  <a name="disablerestoredockstate"></a>  CDockingManager::DisableRestoreDockState  
 有効または、レジストリからのドッキング レイアウトの読み込みを無効にします。  
  
```  
void DisableRestoreDockState(BOOL bDisable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bDisable*  
 レジストリからのドッキング レイアウトの読み込みを無効にする場合は Trueそれ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出すアプリケーションの状態の読み込み時に、ドッキング ペインおよびツールバーの現在のレイアウトを維持する必要があります。  
  
##  <a name="dockpane"></a>  CDockingManager::DockPane  
 別のウィンドウまたはフレーム ウィンドウ ペインをドッキングします。  
  
```  
void DockPane(
    CBasePane* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBar*  
 バーへのポインターにドッキングするウィンドウ。  
  
 [in]*辺*  
 ドッキングするのには、バーの id。  
  
 [in]*lpRect*  
 先の四角形。  
  
##  <a name="dockpaneleftof"></a>  CDockingManager::DockPaneLeftOf  
 ペインを別のペインの左側にドッキングします。  
  
```  
BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pBarToDock*  
 左側にドッキングするウィンドウへのポインター *pTargetBar*します。  
  
 [in]*pTargetBar*  
 [ターゲット] ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが正常にドッキングされている場合は TRUE。それ以外の場合、FALSE です。  
  
##  <a name="enableautohidepanes"></a>  CDockingManager::EnableAutoHidePanes  
 メイン フレーム ウィンドウのドッキングを有効がドック ウィンドウを作成し、コントロール バーのリストに追加します。  
  
```  
BOOL EnableAutoHidePanes(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwStyle*  
 ドッキングの配置。  
  
### <a name="return-value"></a>戻り値  
 ドッキング ウィンドウが正常に作成された場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="enabledocking"></a>  CDockingManager::EnableDocking  
 ドッキング ペインを作成し、メイン フレーム ウィンドウのドッキングを有効にします。  
  
```  
BOOL EnableDocking(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*dwStyle*  
 ドッキングの配置。  
  
### <a name="return-value"></a>戻り値  
 ドッキング ウィンドウが正常に作成された場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="enabledocksitemenu"></a>  CDockingManager::EnableDockSiteMenu  
 すべてのドッキング ペインのキャプションにポップアップ メニューを開き、追加のボタンが表示されます。  
  
```  
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 ドッキング サイトのメニューを有効にする場合は TRUEそれ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ドッキング サイトのメニューには、ウィンドウのドッキング状態を変更するために、次のオプションが表示されます。  
  
- `Floating` -ペインをフローティングします。  
  
- `Docking` -で、ウィンドウがドッキングされた最後の位置にあるメイン フレーム ウィンドウをドッキングします。  
  
- `AutoHide` -ペインを autohide モードに切り替わります  
  
- `Hide` -ペインを非表示になります  
  
 既定では、このメニューは表示されません。  
  
##  <a name="enablepanecontextmenu"></a>  CDockingManager::EnablePaneContextMenu  
 ユーザーがマウスの右ボタンをクリックし、ライブラリ WM_CONTEXTMENU メッセージの処理はときに、アプリケーションのツールバーとドッキング ペインの一覧のある特別なコンテキスト メニューを表示するライブラリに指示します。  
  
```  
void EnablePaneContextMenu(
    BOOL bEnable,  
    UINT uiCustomizeCmd,  
    const CString& strCustomizeText,  
    BOOL bToolbarsOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bEnable*  
 ライブラリは、自動のコンテキスト メニューのサポートをオンに TRUE の場合、FALSE の場合、ライブラリは、自動のコンテキスト メニューのサポートをオフにします。  
  
 [in]*uiCustomizeCmd*  
 コマンド id を**カスタマイズ**メニュー項目。  
  
 [in]*strCustomizeText*  
 テキスト、**カスタマイズ**項目。  
  
 [in]*bToolbarsOnly*  
 TRUE の場合、メニューがアプリケーション ツールバーの一覧のみを表示しますFALSE の場合、ライブラリは、アプリケーションのドッキング ペインをこの一覧に追加します。  
  
##  <a name="finddocksite"></a>  CDockingManager::FindDockSite  
 バーを取得します。 指定した位置にあると、指定された配置を持つウィンドウです。  
  
```  
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,  
    BOOL bOuter);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*場合*  
 バーの配置ウィンドウ。  
  
 [in]*bOuter*  
 TRUE の場合は、コントロール バーの一覧で、ヘッドの位置にあるバーを取得します。 それ以外の場合、コントロール バーのリストの末尾位置にあるバーを取得します。  
  
### <a name="return-value"></a>戻り値  
 指定した位置が; ドッキング ペインそれ以外の場合は NULL です。  
  
##  <a name="findpanebyid"></a>  CDockingManager::FindPaneByID  
 指定したコントロール ID によってペインを検索します  
  
```  
virtual CBasePane* FindPaneByID(
    UINT uBarID,  
    BOOL bSearchMiniFrames = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uBarID*  
 検索する、ウィンドウのコントロール ID を指定します。  
  
 [in]*bSearchMiniFrames*  
 すべての浮動ペインを検索に含めるには TRUE です。 ドッキング ペインのみを含める場合は FALSE。  
  
### <a name="return-value"></a>戻り値  
 [CBasePane](../../mfc/reference/cbasepane-class.md)を指定したウィンドウが見つからない場合は、指定したコントロール ID、または NULL を持つオブジェクト。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="finddocksitebypane"></a>  CDockingManager::FindDockSiteByPane  
 バーを返しますターゲット バー ペインの id を持つウィンドウです。  
  
```  
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pTargetBar*  
 バーの [ターゲット] ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 バー ターゲット バー ペインの id を持つウィンドウバー ウィンドウなどが存在しない場合は NULL です。  
  
##  <a name="fixupvirtualrects"></a>  CDockingManager::FixupVirtualRects  
 ツールバーの現在位置の仮想四角形をコミットします。  
  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>Remarks  
 ユーザーは、ツールバーのドラッグを起動すると、アプリケーションはの元の位置を記憶、*仮想の長方形*します。 ユーザーは、ツールバーをドッキング サイト間で移動したとき、ツールバーが他のツールバーに移動します。 他のツールバーの元の位置は、対応する仮想四角形に格納されます。  
  
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
 インスタンスではないするフレームを除外する場合は True `CMultiPaneFrameWnd`;FALSE それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 特定のポイントでは; を含むフレームそれ以外の場合は NULL です。  
  
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
  
- DT_STANDARD  
  
- DT_IMMEDIATE  
  
- DT_SMART  
  
### <a name="remarks"></a>Remarks  
 ドッキングのモードを設定するには、呼び出す[CDockingManager::SetDockingMode](#setdockingmode)します。  
  
##  <a name="getdocksiteframewnd"></a>  CDockingManager::GetDockSiteFrameWnd  
 親ウィンドウのフレームへのポインターを取得します。  
  
```  
CFrameWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親ウィンドウのフレームへのポインター。  
  
##  <a name="getenabledautohidealignment"></a>  CDockingManager::GetEnabledAutoHideAlignment  
 ウィンドウの有効な配置を返します。  
  
```  
DWORD GetEnabledAutoHideAlignment() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Cbrs_align _ フラグ、または自動的に隠すウィンドウが有効になっていない場合は 0 のビットごとの組み合わせ。 詳細については、次を参照してください。 [CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking)します。  
  
### <a name="remarks"></a>Remarks  
 メソッドは、自動的に隠す のコントロール バーに対して有効な配置を返します。 自動的に隠すバーを有効にするには、呼び出す[CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)します。  
  
##  <a name="getminiframes"></a>  CDockingManager::GetMiniFrames  
 ミニフレームの一覧を取得します。  
  
```  
const CObList& GetMiniFrames() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール バー、ドッキング マネージャーに属しているを含むミニフレームの一覧。  
  
##  <a name="getouteredgebounds"></a>  CDockingManager::GetOuterEdgeBounds  
 フレームの外側のエッジを含む四角形を取得します。  
  
```  
CRect GetOuterEdgeBounds() const;  
```  
  
### <a name="return-value"></a>戻り値  
 フレームの外側のエッジを含む四角形。  
  
##  <a name="getpanelist"></a>  CDockingManager::GetPaneList  
 ドッキング マネージャーに属しているウィンドウの一覧を返します。 これには、すべての浮動ペインが含まれます。  
  
```  
void GetPaneList(
    CObList& lstBars,  
    BOOL bIncludeAutohide = FALSE,  
    CRuntimeClass* pRTCFilter = NULL,  
    BOOL bIncludeTabs = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力]*lstBars*  
 現在、ドッキング マネージャーのすべてのペインが含まれています。  
  
 [in]*bIncludeAutohide*  
 自動的に隠すモードであるペインを含める場合は TRUE。それ以外の場合、FALSE です。  
  
 [in]*pRTCFilter*  
 NULL 以外の場合、返された一覧には、指定されたランタイム クラスのみのペインが含まれています。  
  
 [in]*bIncludeTabs*  
 True に設定する; タブそれ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 ポインターを返します、ドッキング マネージャーに任意のタブ付きペインがある場合は、 [CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)オブジェクトとする必要があります列挙タブ明示的にします。  
  
 使用*pRTCFilter*ペインの特定のクラスを取得します。 たとえば、この値を適切に設定してツールバーだけを取得できます。  
  
##  <a name="getsmartdockingmanager"></a>  CDockingManager::GetSmartDockingManager  
 スマート ドッキング マネージャーへのポインターを取得します。  
  
```  
CSmartDockingManager* GetSmartDockingManager();
```  
  
### <a name="return-value"></a>戻り値  
 スマート ドッキング マネージャーへのポインター。  
  
##  <a name="getsmartdockingmanagerpermanent"></a>  CDockingManager::GetSmartDockingManagerPermanent  
 スマート ドッキング マネージャーへのポインターを取得します。  
  
```  
CSmartDockingManager* GetSmartDockingManagerPermanent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 スマート ドッキング マネージャーへのポインター。  
  
##  <a name="getsmartdockingparams"></a>  CDockingManager::GetSmartDockingParams  
 ドッキング マネージャーのスマート ドッキングのパラメーターを返します。  
  
```  
static CSmartDockingInfo& GetSmartDockingParams();
```  
  
### <a name="return-value"></a>戻り値  
 このクラスは、現在、ドッキング マネージャーのスマート ドッキングのパラメーターが含まれています。 詳細については、次を参照してください。 [CSmartDockingInfo クラス](../../mfc/reference/csmartdockinginfo-class.md)します。  
  
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
 隠ぺいから除外するバーへのポインター。  
  
 [in]*bImmediately*  
 すぐに、ウィンドウを非表示にする場合は TRUE自動非表示効果にウィンドウを非表示にする場合は FALSE。  
  
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
 ドッキング ウィンドウが正常に作成された場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="insertpane"></a>  CDockingManager::InsertPane  
 コントロール バーのリストには、コントロールのウィンドウを挿入します。  
  
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
 [ターゲット] ウィンドウへのポインター。  
  
 [in]*bAfter*  
 ウィンドウの [ターゲット] ウィンドウで; の位置より後に挿入する場合は TRUEFALSE それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 コントロールのウィンドウが正常にコントロール バーのリストに追加する場合は TRUE。FALSE それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 コントロール ウィンドウのコントロール バーのリストが既にいる場合、または [ターゲット] ウィンドウがコントロール バーのリストに存在しない場合、このメソッドは false を返します。  
  
##  <a name="isdocksitemenu"></a>  CDockingManager::IsDockSiteMenu  
 すべてのペインのキャプションにポップアップ メニューが表示されるかどうかを指定します。  
  
```  
static BOOL IsDockSiteMenu();
```  
  
### <a name="return-value"></a>戻り値  
 すべてのドッキング ペインのキャプションにドッキング サイトのメニューが表示されている場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 呼び出して、ドック サイト メニューを有効にできる[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)します。  
  
##  <a name="isinadjustlayout"></a>  CDockingManager::IsInAdjustLayout  
 すべてのペインのレイアウトを調整するかどうかを決定します。  
  
```  
BOOL IsInAdjustLayout() const;  
```  
  
### <a name="return-value"></a>戻り値  
 すべてのペインのレイアウトが調整されている場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="isolecontainermode"></a>  CDockingManager::IsOLEContainerMode  
 OLE コンテナー モードで、ドッキング マネージャーであるかどうかを指定します。  
  
```  
BOOL IsOLEContainerMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドッキング マネージャーが OLE コンテナー モードでは、TRUE を返します。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 OLE コンテナーのモードですべてのドッキング ペインとアプリケーションのツールバーが表示されません。 設定した場合に、ペインはこのモードで非表示も[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)を TRUE にします。  
  
##  <a name="ispointneardocksite"></a>  CDockingManager::IsPointNearDockSite  
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
  
 [out]*dwBarAlignment*  
 どちらの端点が近いを指定します。 使用可能な値は、CBRS_ALIGN_LEFT、CBRS_ALIGN_RIGHT、CBRS_ALIGN_TOP、CBRS_ALIGN_BOTTOM です。  
  
 [out]*bOuterEdge*  
 ポイントが、ドッキング サイトの外側の境界線の近くにある場合は TRUE。FALSE それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 点がドッキング サイトに近い場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="isprintpreviewvalid"></a>  CDockingManager::IsPrintPreviewValid  
 印刷プレビュー モードが設定されているかどうかを決定します。  
  
```  
BOOL IsPrintPreviewValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 印刷プレビュー モードが設定されている場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="loadstate"></a>  CDockingManager::LoadState  
 レジストリから、ドッキング マネージャーの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 プロファイルの名前。  
  
 [in]*uiID*  
 ドッキングのマネージャーの id。  
  
### <a name="return-value"></a>戻り値  
 ドッキング マネージャーの状態が正常に読み込まれている場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="lockupdate"></a>  CDockingManager::LockUpdate  
 指定されたウィンドウをロックします。  
  
```  
void LockUpdate(BOOL bLock);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ブロック*  
 TRUE の場合は、ウィンドウがロックされています。FALSE それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 ウィンドウがロックされると、移動することはできず、それを再描画することはできません。  
  
##  <a name="m_bhidedockingbarsincontainermode"></a>  CDockingManager::m_bHideDockingBarsInContainerMode  
 OLE コンテナー モードのペインがドッキング マネージャーに非表示にするかどうかを指定します。  
  
```  
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;  
```  
  
### <a name="remarks"></a>Remarks  
 アプリケーションが OLE コンテナー モードの場合は、メイン フレームにドッキングされているすべてのペインを保持したい場合は、この値を FALSE に設定します。 既定ではこの値は TRUE です。  
  
##  <a name="m_dockmodeglobal"></a>  CDockingManager::m_dockModeGlobal  
 グローバルのドッキングのモードを指定します。  
  
```  
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;  
```  
  
### <a name="remarks"></a>Remarks  
 既定では、各ドッキング ペインは、このドッキングのモードを使用します。 このフィールドに設定できる値の詳細については、次を参照してください。 [cbasepane::getdockingmode](../../mfc/reference/cbasepane-class.md#getdockingmode)します。  
  
##  <a name="m_ndocksensitivity"></a>  CDockingManager::m_nDockSensitivity  
 ドッキングの感度を指定します。  
  
```  
AFX_IMPORT_DATA static int m_nDockSensitivity;  
```  
  
### <a name="remarks"></a>Remarks  
 ドッキングと小文字の区別を定義、閉じる方法の浮動ペインはドッキング ペイン、ドッキング サイト、または別のペイン、フレームワークは、ドッキング状態を変更する前に、アプローチことができます。  
  
##  <a name="m_ntimeoutbeforedockingbardock"></a>  CDockingManager::m_nTimeOutBeforeDockingBarDock  
 イミディ エイト モードでドッキング ドッキング ペインをドッキングする前に、(ミリ秒単位)、時間を指定します。  
  
```  
static UINT m_nTimeOutBeforeDockingBarDock;  
```  
  
### <a name="remarks"></a>Remarks  
 ペインをドッキングすると、前に、フレームワークは、指定した長さの時間を待機します。 これは、ウィンドウがユーザーがドラッグしても、誤っての場所にドッキングすることを防ぎます。  
  
##  <a name="m_ntimeoutbeforetoolbardock"></a>  CDockingManager::m_nTimeOutBeforeToolBarDock  
 メイン フレーム ウィンドウにツールバーをドッキングする前に、(ミリ秒単位)、時間を指定します。  
  
```  
static UINT m_nTimeOutBeforeToolBarDock;  
```  
  
### <a name="remarks"></a>Remarks  
 ツールバーをドッキングすると、前に、フレームワークは、指定した長さの時間を待機します。 これにより、ツールバーは、ユーザーがドラッグしても中に、場所にドッキングされている誤ってできなくなります。  
  
##  <a name="onactivateframe"></a>  CDockingManager::OnActivateFrame  
 フレーム ウィンドウがアクティブになりますかが非アクティブ化するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateFrame(BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bActivate*  
 TRUE の場合、フレーム ウィンドウがアクティブになります。FALSE の場合、フレーム ウィンドウが非アクティブ化します。  
  
##  <a name="onclosepopupmenu"></a>  CDockingManager::OnClosePopupMenu  
 アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。  
  
```  
void OnClosePopupMenu();
```  
  
### <a name="remarks"></a>Remarks  
 現在のメイン ウィンドウを閉じるしようとしているときに、フレームワークは WM_DESTROY メッセージを送信します。 通知を処理するには、このメソッドをオーバーライド`CMFCPopupMenu`フレーム ウィンドウに属するオブジェクトと、 `CMFCPopupMenu` WM_DESTROY メッセージを処理するオブジェクト。  
  
##  <a name="onmoveminiframe"></a>  CDockingManager::OnMoveMiniFrame  
 ミニフレーム ウィンドウを移動するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pFrame*  
 ミニフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE。それ以外の場合は FALSE です。  
  
##  <a name="onpanecontextmenu"></a>  CDockingManager::OnPaneContextMenu  
 ペインの一覧のあるメニューを作成するときに、フレームワークによって呼び出されます。  
  
```  
void OnPaneContextMenu(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 メニューの場所を指定します。  
  
##  <a name="panefrompoint"></a>  CDockingManager::PaneFromPoint  
 指定したポイントを含むペインを返します。  
  
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
 チェックされている各ウィンドウのウィンドウの四角形を拡大するための値。 ペインは、指定したポイントが高めのこの領域の場合、検索条件を満たします。  
  
 [in]*bExactBar*  
 無視する場合は TRUE、 *nSensitivity*パラメーター場合は FALSE。  
  
 [in]*pRTCBarType*  
 NULL 以外の場合、メソッドは、指定した型のウィンドウだけを検索します。  
  
 [in]*bCheckVisibility*  
 表示ペインにのみを確認する場合は TRUEそれ以外の場合、FALSE です。  
  
 [out]*場合*  
 指定した時点で、ウィンドウが見つかった場合、このパラメーターには、指定したポイントに最も近いいたペインの横にはが含まれています。 詳細については、「解説」を参照してください。  
  
 [in]*pBarToIgnore*  
 NULL 以外の場合、メソッドは、このパラメーターで指定されたウィンドウを無視します。  
  
### <a name="return-value"></a>戻り値  
 [CBasePane](../../mfc/reference/cbasepane-class.md)-ウィンドウが見つからなかった場合は、特定のポイント、または NULL を含む派生オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 関数に戻り、ペインが検出されましたが、*場合*指定した点の配置が含まれています。 たとえば、次の点が、ウィンドウの上部に最も近い*場合*CBRS_ALIGN_TOP に設定されます。  
  
##  <a name="processpanecontextmenucommand"></a>  CDockingManager::ProcessPaneContextMenuCommand  
 選択または指定されたコマンドのチェック ボックスをオフにし、表示されるペインのレイアウトを再計算するため、フレームワークによって呼び出されます。  
  
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
 Void をへのポインターがへのポインターにキャストされる`CCmdUI`場合*nCode* CN_UPDATE_COMMAND_UI が。  
  
 [in]*pHandlerInfo*  
 情報構造体へのポインター。 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合*pEXtra*が NULL でないと*nCode* CN_UPDATE_COMMAND_UI、等しい、指定したコントロール バーがある場合、または*nID*。  
  
##  <a name="recalclayout"></a>  CDockingManager::RecalcLayout  
 コントロールのリストに存在するコントロールの内部レイアウトを再計算します。  
  
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
 バーへのポインターを削除するウィンドウ。  
  
##  <a name="removeminiframe"></a>  CDockingManager::RemoveMiniFrame  
 ミニフレームの一覧から、指定したフレームを削除します。  
  
```  
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*我が物*  
 削除するためのフレームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定したフレームが削除された場合は TRUE。FALSE それ以外の場合。  
  
##  <a name="removepanefromdockmanager"></a>  CDockingManager::RemovePaneFromDockManager  
 ウィンドウの登録を解除し、ドッキング マネージャーの一覧から削除されます。  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pWnd,  
    BOOL bDestroy,  
    BOOL bAdjustLayout,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*我が物*  
 削除する ウィンドウへのポインター。  
  
 [in]*bDestroy*  
 TRUE の場合、削除されたウィンドウが破棄されます。  
  
 [in]*bAdjustLayout*  
 TRUE の場合は、すぐにドッキング レイアウトを調整します。  
  
 [in]*bAutoHide*  
 TRUE の場合、ウィンドウが自動的に隠すバーのリストから削除されます。 FALSE の場合、ウィンドウは、一定のペインの一覧から削除されます。  
  
 [in]*pBarReplacement*  
 削除されたウィンドウを置換するウィンドウへのポインター。  
  
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
 TRUE の場合、ウィンドウは正常に置き換えられました。FALSE それ以外の場合。  
  
##  <a name="resortminiframesforzorder"></a>  CDockingManager::ResortMiniFramesForZOrder  
 ミニフレームの一覧内のフレームを場合します。  
  
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
 ドッキング マネージャー id。  
  
### <a name="return-value"></a>戻り値  
 状態が正常に保存されている場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 レジストリに、ドッキング マネージャーの状態の保存、コントロール バーの状態、状態は、自動的に隠すバー、および、ドッキング マネージャーに存在するミニフレームの状態を保存する必要があります。  
  
##  <a name="sendmessagetominiframes"></a>  CDockingManager::SendMessageToMiniFrames  
 すべてのミニフレームを指定したメッセージを送信します。  
  
```  
BOOL SendMessageToMiniFrames(
    UINT uMessage,  
    WPARAM wParam = 0,  
    LPARAM lParam = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uMessage*  
 送信されるメッセージ。  
  
 [in]*wParam*  
 追加のメッセージの依存情報です。  
  
 [in]*lParam*  
 追加のメッセージの依存情報です。  
  
### <a name="return-value"></a>戻り値  
 常に true を設定します。  
  
##  <a name="serialize"></a>  CDockingManager::Serialize  
 アーカイブは、ドッキング マネージャーに書き込みます。  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ar*  
 アーカイブ オブジェクトへの参照。  
  
### <a name="remarks"></a>Remarks  
 アーカイブ ファイルに、ドッキング マネージャーを書き込むには、ドッキング コントロール バーやスライダー、およびアーカイブへのコントロール バー、ミニ フレーム、自動的に隠すバー、および MDI タブ付きの横棒の書き込みの数を決定する必要があります。  
  
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
 スマート ドッキング マーカーに使用されるテーマを指定します。 次の列挙値のいずれか: AFX_SDT_DEFAULT、AFX_SDT_VS2005、AFX_SDT_VS2008 します。  
  
### <a name="remarks"></a>Remarks  
 ドッキングのモードを設定するこの静的メソッドを呼び出します。  
  
 *dockMode*次の値のいずれかを指定できます。  
  
- DT_STANDARD - として Visual Studio .NET 2003 で実装された標準ドッキング モード。 ウィンドウは、ドラッグのコンテキストを使用せずにドラッグします。  
  
- DT_IMMEDIATE - イミディ エイトのドッキング モードとして Microsoft Visio に実装されています。 ドラッグのコンテキストでウィンドウがドラッグが、マーカーは表示されません。  
  
- DT_SMART - Visual Studio 2005 の実装としてスマート ドッキングのモード。 ドラッグのコンテキストでウィンドウをドラッグし、スマート マーカーが表示されます、ウィンドウのドッキング先を表示します。  
  
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
 印刷プレビュー モードが設定されている場合は TRUE。FALSE それ以外の場合。  
  
 [in]*pState*  
 プレビュー状態へのポインター。 このパラメーターは使用されません。  
  
##  <a name="setsmartdockingparams"></a>  CDockingManager::SetSmartDockingParams  
 スマート ドッキングの動作を定義するパラメーターを設定します。  
  
```  
static void SetSmartDockingParams(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力]*params*  
 スマート ドッキングのパラメーターを定義します。  
  
### <a name="remarks"></a>Remarks  
 外観、色、またはスマート ドッキング マーカーの図形をカスタマイズする場合は、このメソッドを呼び出します。  
  
 スマート ドッキング マーカーの外観は、既定を使用するには、初期化されていないインスタンスを渡す[CSmartDockingInfo クラス](../../mfc/reference/csmartdockinginfo-class.md)に*params*します。  
  
##  <a name="showdelayshowminiframes"></a>  CDockingManager::ShowDelayShowMiniFrames  
 ミニフレーム ウィンドウの表示と非表示を切り替えます。  
  
```  
void ShowDelayShowMiniFrames(BOOL bshow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bShow*  
 表示されるフレームのウィンドウをアクティブな場合は TRUEフレームのウィンドウを非表示にする場合は FALSE。  
  
##  <a name="showpanes"></a>  CDockingManager::ShowPanes  
 コントロールと自動的に隠すバーのウィンドウの表示と非表示を切り替えます。  
  
```  
virtual BOOL ShowPanes(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bShow*  
 ウィンドウを表示する場合は TRUE。ウィンドウを非表示にする場合は FALSE。  
  
### <a name="return-value"></a>戻り値  
 常に FALSE です。  
  
##  <a name="startsdocking"></a>  CDockingManager::StartSDocking  
 スマート ドッキング マネージャーの配置に従って指定したウィンドウのスマート ドッキングを開始します。  
  
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
 次の列挙値のいずれかを返します: AFX_SDT_DEFAULT、AFX_SDT_VS2005、AFX_SDT_VS2008 します。  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [CFrameWndEx クラス](../../mfc/reference/cframewndex-class.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)
