---
title: CDockingManager クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 339e5d5e464aacb51d1c4ab8fe3c2957a3afbd4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375580"
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
|[クマッキングマネージャー::追加ドックサイト](#adddocksite)|ドッキング ペインを作成し、コントロール バーの一覧に追加します。|
|[チャッキングマネージャー::アドヒデンムディタブードバー](#addhiddenmditabbedbar)|非表示の MDI タブ付きバー ペインのリストにバー ペインへのハンドルを追加します。|
|[CDockingマネージャー::追加ミニフレーム](#addminiframe)|ミニ フレームのリストにフレームを追加します。|
|[CDockingマネージャー::ペインの追加](#addpane)|ドッキング マネージャーにペインを登録します。|
|[チャッキングマネージャー::調整ドッキングレイアウト](#adjustdockinglayout)|フレーム ウィンドウ内のすべてのペインのレイアウトを再計算および調整します。|
|[ウィンドウディングマネージャー::ペインフレームの調整](#adjustpaneframes)|WM_NCCALCSIZEメッセージをすべてのウィンドウ枠に`CPaneFrameWnd`送信します。|
|[クライアント領域を調整します。](#adjustrecttoclientarea)|四角形の配置を調整します。|
|[CDockingマネージャー::整列自動非表示ペイン](#alignautohidepane)|ドッキング ペインのサイズを自動非表示モードで変更し、ドッキング サイトで囲まれたフレームのクライアント領域の幅または高さを取得します。|
|[CDockingマネージャー::自動非表示ペイン](#autohidepane)|自動非表示ツール バーを作成します。|
|[チャッキングマネージャー::ブリングバーズトップ](#bringbarstotop)|指定した配置を持つドッキングされた棒を上端に移動します。|
|[メニューメニュー](#buildpanesmenu)|ドッキング ペインとツール バーの名前をメニューに追加します。|
|[クッキングマネージャー::カルク予期しないドッキングレクト](#calcexpecteddockedrect)|ドッキングウィンドウの予想される四角形を計算します。|
|[クッキングマネージャー::作成](#create)|ドッキング マネージャーを作成します。|
|[チャッキングマネージャー::Dエターミンペインとステータス](#determinepaneandstatus)|指定したポイントとそのドッキング状態を含むペインを決定します。|
|[:D可能な復元ドック状態](#disablerestoredockstate)|レジストリからのドッキング レイアウトの読み込みを有効または無効にします。|
|[クッキングマネージャー::Dロックペイン](#dockpane)|ペインを別のペインまたはフレーム ウィンドウにドッキングします。|
|[オ :Dックペイン左](#dockpaneleftof)|ペインを別のペインの左側にドッキングします。|
|[CDockingマネージャー::自動隠しペインを有効にします](#enableautohidepanes)|ペインをメイン フレームにドッキングし、ドッキング ペインを作成し、コントロール バーの一覧に追加します。|
|[CDockingマネージャー::ドッキングを有効にする](#enabledocking)|ドッキング ペインを作成し、ペインをメイン フレームにドッキングできるようにします。|
|[をクリックします。](#enabledocksitemenu)|すべてのドッキング ペインのキャプションにポップアップ メニューを開く追加ボタンを表示します。|
|[ウィンドウディングマネージャー::ウィンドウコンテキストメニューを有効にします。](#enablepanecontextmenu)|ユーザーがマウスの右ボタンをクリックし、ライブラリがWM_CONTEXTMENU メッセージを処理しているときに、アプリケーション のツール バーとドッキング ペインの一覧を含む特別なコンテキスト メニューを表示するようにライブラリに指示します。|
|[クッキングマネージャー::検索ドックサイト](#finddocksite)|指定した位置にあり、指定した配置を持つバー ペインを取得します。|
|[クッキングマネージャー::検索ドッキングサイトバイペイン](#finddocksitebypane)|ターゲット バー ペインの ID を持つバー ペインを返します。|
|[クッキングマネージャー::ペインバイIDを検索します](#findpanebyid)|指定したコントロール ID でペインを検索します。|
|[クッキングマネージャー::フィックスアップバーチャルレクト](#fixupvirtualrects)|現在のすべてのツール バーの位置を仮想四角形にコミットします。|
|[チャッキングマネージャー::フレームフロインポイント](#framefrompoint)|指定したポイントを含むフレームを返します。|
|[クライアントエリアの境界](#getclientareabounds)|クライアント領域の境界を含む四角形を取得します。|
|[クリッピングマネージャー::取得ドッキングモード](#getdockingmode)|現在のドッキング モードを返します。|
|[クッキングマネージャー::ゲットドックサイトフレームウンド](#getdocksiteframewnd)|親ウィンドウ フレームへのポインターを取得します。|
|[クリッピングマネージャー::取得有効化オートハイドアライメント](#getenabledautohidealignment)|ペインの有効な配置を返します。|
|[クッキングマネージャー::ゲットミニフレーム](#getminiframes)|ミニフレームの一覧を取得します。|
|[クリッピングマネージャー::ゲットアウターエッジバウンド](#getouteredgebounds)|フレームの外縁を含む四角形を取得します。|
|[クッキングマネージャー::取得ペインリスト](#getpanelist)|ドッキング マネージャーに属するペインの一覧を返します。 これには、すべてのフローティング ペインが含まれます。|
|[クリッピングマネージャー::ゲットスマートドッキングマネージャー](#getsmartdockingmanager)|スマート ドッキング マネージャーへのポインターを取得します。|
|[チャッキングマネージャー::ゲットスマートドッキングマネージャーパーマネント](#getsmartdockingmanagerpermanent)|スマート ドッキング マネージャーへのポインターを取得します。|
|[チャッキングマネージャー::ゲットスマートドッキングパラム](#getsmartdockingparams)|ドッキング マネージャーのスマート ドッキング パラメーターを返します。|
|[チャッキングマネージャー::ゲットスマートドッキングテーマ](#getsmartdockingtheme)|スマート ドッキング マーカーの表示に使用するテーマを返す静的メソッド。|
|[CDockingマネージャー::隠し自動隠しペイン](#hideautohidepanes)|自動非表示モードのペインを非表示にします。|
|[クッキングマネージャー::挿入ドックサイト](#insertdocksite)|ドッキング ペインを作成し、コントロール バーのリストに挿入します。|
|[ウィンドウディングマネージャー::挿入ペイン](#insertpane)|コントロール バーの一覧にコントロール ペインを挿入します。|
|[クッキングマネージャー::イズドックサイトメニュー](#isdocksitemenu)|すべてのペインのキャプションにポップアップ メニューを表示するかどうかを指定します。|
|[チャッキングマネージャー::IsInAdjustレイアウト](#isinadjustlayout)|すべてのペインのレイアウトを調整するかどうかを決定します。|
|[をクリックします。](#isolecontainermode)|ドッキング マネージャーが OLE コンテナー モードであるかどうかを指定します。|
|[チャッキングマネージャー::イスポイントニアドックサイト](#ispointneardocksite)|指定したポイントがドッキング サイトの近くにあるかどうかを判断します。|
|[クッキングマネージャー::イズプリントプレビュー有効](#isprintpreviewvalid)|印刷プレビュー モードを設定するかどうかを決定します。|
|[クッキングマネージャー::ロードステート](#loadstate)|レジストリからドッキング マネージャーの状態を読み込みます。|
|[クッキングマネージャー::ロックアップデート](#lockupdate)|指定されたウィンドウをロックします。|
|[チャッキングマネージャー::オンアクティブフレーム](#onactivateframe)|フレーム ウィンドウがアクティブになったり非アクティブになったりしたときに、フレームワークによって呼び出されます。|
|[メニューメニューを閉じる](#onclosepopupmenu)|アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。|
|[チャッキングマネージャー::オンムーブミニフレーム](#onmoveminiframe)|ミニフレーム ウィンドウを移動するために、フレームワークによって呼び出されます。|
|[ウィンドウディングマネージャー::オンペインコンテキストメニュー](#onpanecontextmenu)|ペインの一覧を含むメニューを構築するときに、フレームワークによって呼び出されます。|
|[:Pアネア](#panefrompoint)|指定したポイントを含むペインを返します。|
|[:Pロセスペインコンテキストメニューコマンド](#processpanecontextmenucommand)|指定したコマンドのチェック ボックスをオンまたはオフにして、表示されたペインのレイアウトを再計算するために、フレームワークによって呼び出されます。|
|[キャッキングマネージャー::再計算レイアウト](#recalclayout)|コントロールの一覧に表示されているコントロールの内部レイアウトを再計算します。|
|[::リリース空のペインコンテナ](#releaseemptypanecontainers)|空のペイン コンテナを解放します。|
|[チャッキングマネージャー::削除隠しタブベッドバー](#removehiddenmditabbedbar)|指定した非表示バー ペインを削除します。|
|[チャッキングマネージャー::ミニフレームの削除](#removeminiframe)|ミニ フレームのリストから指定したフレームを削除します。|
|[次の操作を行います。](#removepanefromdockmanager)|ペインの登録を解除し、ドッキング マネージャーのリストから削除します。|
|[ウィンドウを置き換えるマネージャー:ペインを置き換える](#replacepane)|ペインを別のペインに置き換えます。|
|[チャッキングマネージャー::リゾートミニフレームフォーズオーダー](#resortminiframesforzorder)|ミニ フレームのリスト内のフレームをリゾートします。|
|[チャッキングマネージャー::セーブステート](#savestate)|ドッキング マネージャーの状態をレジストリに保存します。|
|[ウィンドウディングマネージャー::メッセージを送信ミニフレーム](#sendmessagetominiframes)|指定されたメッセージをすべてのミニフレームに送信します。|
|[CDockingマネージャー::シリアライズ](#serialize)|ドッキング マネージャーをアーカイブに書き込みます。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|
|[クリッピングマネージャー::自動ハイドZOrderを設定します](#setautohidezorder)|コントロール バーと指定したペインのサイズ、幅、および高さを設定します。|
|[クッキングマネージャー::セットドッキングモード](#setdockingmode)|ドッキング モードを設定します。|
|[クッキングマネージャー::セットドックステート](#setdockstate)|コントロール バー、ミニ フレーム、および自動非表示バーのドッキング状態を設定します。|
|[をクリックします。](#setprintpreviewmode)|印刷プレビューに表示されるバーの印刷プレビュー モードを設定します。|
|[チャッキングマネージャー::セットスマートドッキングパラム](#setsmartdockingparams)|スマート ドッキングの動作を定義するパラメーターを設定します。|
|[チャッキングマネージャー::ショーディレイショーミニフレーム](#showdelayshowminiframes)|ミニ フレームのウィンドウを表示または非表示にします。|
|[チャッキングマネージャー::ショーペイン](#showpanes)|コントロールバーおよび自動非表示バーのペインを表示または非表示にします。|
|[チャッキングマネージャー::スタートスドッキング](#startsdocking)|スマート ドッキング マネージャーの配置に従って、指定したウィンドウのスマート ドッキングを開始します。|
|[チャッキングマネージャー::ストップスドッキング](#stopsdocking)|スマート ドッキングを停止します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[チャッキングマネージャー::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|ドッキング マネージャーが OLE コンテナー モードでペインを非表示にするかどうかを指定します。|
|[クッキングマネージャー::m_dockModeGlobal](#m_dockmodeglobal)|グローバル ドッキング モードを指定します。|
|[チャッキングマネージャー::m_nDockSensitivity](#m_ndocksensitivity)|ドッキングの感度を指定します。|
|[チャッキングマネージャー::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|ドッキング ペインが即時ドッキング モードでドッキングされるまでの時間をミリ秒単位で指定します。|
|[クリッピングマネージャー::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|ツール バーがメイン フレーム ウィンドウにドッキングされるまでの時間をミリ秒単位で指定します。|

## <a name="remarks"></a>解説

メイン フレーム ウィンドウでは、このクラスが自動的に作成および初期化されます。

ドッキング マネージャー オブジェクトには、ドッキング レイアウト内のすべてのペインの一覧と、メイン フレーム ウィンドウに属するすべての[CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)ウィンドウの一覧が含まれます。

この`CDockingManager`クラスは、ペインまたはウィンドウを検索するために使用できるいくつかのサービスを`CPaneFrameWnd`実装します。 通常、これらのサービスはメイン フレーム ウィンドウ オブジェクトにラップされているため、直接呼び出しません。 詳細については[、「CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)」を参照してください。

## <a name="customization-tips"></a>カスタマイズのヒント

オブジェクトには、次の`CDockingManager`ヒントが適用されます。

- [CDockingManager クラスは](../../mfc/reference/cdockingmanager-class.md)、次のドッキングモードをサポートしています。

  - `AFX_DOCK_TYPE::DT_IMMEDIATE`

  - `AFX_DOCK_TYPE::DT_STANDARD`

  - `AFX_DOCK_TYPE::DT_SMART`

  これらのドッキング モードは[、CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)によって定義され[、CDockingManager::SetDockingMode](#setdockingmode)を呼び出すことによって設定されます。

- 浮動型、サイズ変更できないペインを作成する場合は[、CDockingManager::AddPane](#addpane)メソッドを呼び出します。 このメソッドは、ペインのレイアウトを担当するドッキング マネージャーにペインを登録します。

## <a name="example"></a>例

クラスのさまざまなメソッドを使用してオブジェクトを構成する方法を`CDockingManager`次の例に`CDockingManager`示します。 この例では、すべてのドッキング ペインのキャプションにポップアップ メニューを開く追加ボタンを表示する方法と、オブジェクトのドッキング モードを設定する方法を示します。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CDockingManager](../../mfc/reference/cdockingmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxDockingManager.h

## <a name="cdockingmanageradddocksite"></a><a name="adddocksite"></a>クマッキングマネージャー::追加ドックサイト

ドッキング ペインを作成し、コントロール バーの一覧に追加します。

```
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>パラメーター

*info*<br/>
[in]ドッキング ペインの配置を含む情報構造への参照。

*をクリックします。*<br/>
[アウト]新しいドッキング ペインへのポインターへのポインター。

### <a name="return-value"></a>戻り値

ドッキング ペインが正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanageraddhiddenmditabbedbar"></a><a name="addhiddenmditabbedbar"></a>チャッキングマネージャー::アドヒデンムディタブードバー

非表示の MDI タブ付きバー ペインのリストにバー ペインへのハンドルを追加します。

```
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]バー ペインへのポインター

## <a name="cdockingmanageraddpane"></a><a name="addpane"></a>CDockingマネージャー::ペインの追加

ドッキング マネージャーにペインを登録します。

```
BOOL AddPane(
    CBasePane* pWnd,
    BOOL bTail = TRUE,
    BOOL bAutoHide = FALSE,
    BOOL bInsertForOuterEdge = FALSE);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[イン、アウト]ドッキング マネージャーに追加するペインを指定します。

*bTail*<br/>
[in]ドッキング マネージャーのペインの一覧の末尾にペインを追加する場合は TRUE。それ以外の場合は FALSE。

*b 自動非表示*<br/>
[in]内部使用のみ。 常にデフォルト値 FALSE を使用します。

*アウターエッジを挿入*<br/>
[in]内部使用のみ。 常にデフォルト値 FALSE を使用します。

### <a name="return-value"></a>戻り値

ペインがドッキング マネージャーに正常に登録された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ドッキング マネージャーに、非浮動、サイズ変更できないペインを登録します。 ペインを登録しないと、ドッキング マネージャーのレイアウト時に正しく表示されません。

## <a name="cdockingmanageradjustdockinglayout"></a><a name="adjustdockinglayout"></a>チャッキングマネージャー::調整ドッキングレイアウト

フレーム ウィンドウ内のすべてのペインのレイアウトを再計算および調整します。

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>パラメーター

*hdwp*<br/>
[in]遅延ウィンドウ位置構造体を指定します。 詳細については、「 [Windows のデータ型](/windows/win32/WinProg/windows-data-types)」を参照してください。

### <a name="remarks"></a>解説

## <a name="cdockingmanageraddminiframe"></a><a name="addminiframe"></a>CDockingマネージャー::追加ミニフレーム

ミニ フレームのリストにフレームを追加します。

```
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]フレームへのポインター。

### <a name="return-value"></a>戻り値

フレームがミニ フレームの一覧に含まれ、正常に追加された場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanageradjustpaneframes"></a><a name="adjustpaneframes"></a>ウィンドウディングマネージャー::ペインフレームの調整

WM_NCCALCSIZEメッセージをすべてのウィンドウ枠に`CPaneFrameWnd`送信します。

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>解説

## <a name="cdockingmanageradjustrecttoclientarea"></a><a name="adjustrecttoclientarea"></a>クライアント領域を調整します。

四角形の配置を調整します。

```
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,
    DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

*レクト結果*<br/>
[in]`CRect`オブジェクトへの参照

*dw配置*<br/>
[in]`CRect`オブジェクトの配置

### <a name="return-value"></a>戻り値

オブジェクトの配置が`CRect`調整された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*dwAlignment*パラメーターには、次のいずれかの値を指定できます。

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

## <a name="cdockingmanageralignautohidepane"></a><a name="alignautohidepane"></a>CDockingマネージャー::整列自動非表示ペイン

ドッキング ペインのサイズを自動非表示モードで変更し、ドッキング サイトで囲まれたフレームのクライアント領域の幅または高さを取得します。

```
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,
    BOOL bIsVisible = TRUE);
```

### <a name="parameters"></a>パラメーター

*の初期設定*<br/>
[in]ドッキング スライダー ウィンドウ。

*ビズブル*<br/>
[in]ドッキング ペインが表示されている場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerautohidepane"></a><a name="autohidepane"></a>CDockingマネージャー::自動非表示ペイン

自動非表示ツール バーを作成します。

```
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]バー ペインへのポインター。

*ツール バー*<br/>
[in]自動非表示ツール バーへのポインター。

### <a name="return-value"></a>戻り値

自動非表示ツール バーが作成されなかった場合は NULL。それ以外の場合は、新しいツール バーへのポインター。

## <a name="cdockingmanagerbringbarstotop"></a><a name="bringbarstotop"></a>チャッキングマネージャー::ブリングバーズトップ

指定した配置を持つドッキングされた棒を上端に移動します。

```
void BringBarsToTop(
    DWORD dwAlignment = 0,
    BOOL bExcludeDockedBars = TRUE);
```

### <a name="parameters"></a>パラメーター

*dw配置*<br/>
[in]他のウィンドウの上部に表示されるドッキング バーの配置。

*ブロックドドッキングバー*<br/>
[in]ドッキング バーが上にあるのを除外する場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerbuildpanesmenu"></a><a name="buildpanesmenu"></a>メニューメニュー

ドッキング ペインとツール バーの名前をメニューに追加します。

```
void BuildPanesMenu(
    CMenu& menu,
    BOOL bToolbarsOnly);
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
[in]ドッキング ペインとツール バーの名前を追加するメニュー。

*bツールバーのみ*<br/>
[in]メニューにツールバー名のみを追加する場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>クッキングマネージャー::カルク予期しないドッキングレクト

ドッキングウィンドウの予想される四角形を計算します。

```
void CalcExpectedDockedRect(
    CWnd* pWnd,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]ドッキングするウィンドウへのポインター。

*ptマウス*<br/>
[in]マウスの位置。

*レクト結果*<br/>
[アウト]計算される四角形。

*タブを描く*<br/>
[in]タブを描画する場合は TRUE。それ以外の場合は FALSE。

*ターゲットバー*<br/>
[アウト]ターゲット ペインへのポインターへのポインター。

### <a name="remarks"></a>解説

このメソッドは、ユーザーが *、ptMouse*で指定されたポイントにウィンドウをドラッグして、そこにドッキングした場合に、ウィンドウが占有する四角形を計算します。

## <a name="cdockingmanagercreate"></a><a name="create"></a>クッキングマネージャー::作成

ドッキング マネージャーを作成します。

```
BOOL Create(CFrameWnd* pParentWnd);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
[in]ドッキング マネージャーの親フレームへのポインター。 この値は NULL にできません。

### <a name="return-value"></a>戻り値

常に TRUE。

## <a name="cdockingmanagerdeterminepaneandstatus"></a><a name="determinepaneandstatus"></a>チャッキングマネージャー::Dエターミンペインとステータス

指定したポイントとそのドッキング状態を含むペインを決定します。

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

*Pt*<br/>
[in]確認するペインの場所。

*n感度*<br/>
[in]各チェック ボックスをオンにしたペインのウィンドウ四角形を増やす値。 指定したポイントがこの増加した領域にある場合、ペインは検索条件を満たします。

*整列*<br/>
[in]ドッキング ペインの配置。

*ターゲットバー*<br/>
[アウト]ターゲット ペインへのポインターへのポインター。

*無視する*<br/>
[in]メソッドが無視するペイン。

*をクリックします。*<br/>
[in]ドッキングされているペイン。

### <a name="return-value"></a>戻り値

ドッキングの状態。

### <a name="remarks"></a>解説

ドッキングステータスは、次のいずれかの値になります。

|AFX_CS_STATUS値|意味|
|---------------------------|-------------|
|CS_NOTHING|ポインターがドッキング サイト上にありません。 したがって、ペインをフローティング状態に保ちます。|
|CS_DOCK_IMMEDIATELY|ポインターは、即時モード (DT_IMMEDIATEスタイルが有効) でドッキング サイト上にあるため、ペインを直ちにドッキングする必要があります。|
|CS_DELAY_DOCK|ポインターが、別のドッキング ペインまたはメイン フレームの端であるドッキング サイト上にあります。|
|CS_DELAY_DOCK_TO_TAB|ポインターがドッキング サイト上にあり、そのペインがタブ付きウィンドウにドッキングされます。 これは、マウスが別のドッキング ペインのキャプションの上にある場合、またはタブ付きペインのタブ領域上に移動した場合に発生します。|

## <a name="cdockingmanagerdisablerestoredockstate"></a><a name="disablerestoredockstate"></a>:D可能な復元ドック状態

レジストリからのドッキング レイアウトの読み込みを有効または無効にします。

```
void DisableRestoreDockState(BOOL bDisable = TRUE);
```

### <a name="parameters"></a>パラメーター

*無効にする*<br/>
[in]レジストリからのドッキング レイアウトの読み込みを無効にする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アプリケーションの状態が読み込み中にドッキング ペインとツール バーの現在のレイアウトを保持する必要がある場合は、このメソッドを呼び出します。

## <a name="cdockingmanagerdockpane"></a><a name="dockpane"></a>クッキングマネージャー::Dロックペイン

ペインを別のペインまたはフレーム ウィンドウにドッキングします。

```
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]ドッキングするバー ペインへのポインター。

*nドックバーID*<br/>
[in]ドッキングするバーの ID。

*Lprect*<br/>
[in]コピー先の四角形。

## <a name="cdockingmanagerdockpaneleftof"></a><a name="dockpaneleftof"></a>オ :Dックペイン左

ペインを別のペインの左側にドッキングします。

```
BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]*pTargetBar*の左側にドッキングするペインへのポインター。

*をクリックします。*<br/>
[in]ターゲット ペインへのポインター。

### <a name="return-value"></a>戻り値

ペインが正常にドッキングされた場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerenableautohidepanes"></a><a name="enableautohidepanes"></a>CDockingマネージャー::自動隠しペインを有効にします

ペインをメイン フレームにドッキングし、ドッキング ペインを作成し、コントロール バーの一覧に追加します。

```
BOOL EnableAutoHidePanes(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
[in]ドッキングの配置。

### <a name="return-value"></a>戻り値

ドッキング ペインが正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerenabledocking"></a><a name="enabledocking"></a>CDockingマネージャー::ドッキングを有効にする

ドッキング ペインを作成し、ペインをメイン フレームにドッキングできるようにします。

```
BOOL EnableDocking(DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
[in]ドッキングの配置。

### <a name="return-value"></a>戻り値

ドッキング ペインが正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerenabledocksitemenu"></a><a name="enabledocksitemenu"></a>をクリックします。

すべてのドッキング ペインのキャプションにポップアップ メニューを開く追加ボタンを表示します。

```
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]ドッキング サイト メニューを有効にする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ドッキング サイト メニューには、ペインのドッキング状態を変更するための次のオプションが表示されます。

- `Floating`- ペインをフロートします

- `Docking`- ペインが最後にドッキングされた場所に、メイン フレームにペインをドッキングします。

- `AutoHide`- ペインを自動非表示モードに切り替えます

- `Hide`- ペインを非表示にする

既定では、このメニューは表示されません。

## <a name="cdockingmanagerenablepanecontextmenu"></a><a name="enablepanecontextmenu"></a>ウィンドウディングマネージャー::ウィンドウコンテキストメニューを有効にします。

ユーザーがマウスの右ボタンをクリックし、ライブラリがWM_CONTEXTMENU メッセージを処理しているときに、アプリケーション のツール バーとドッキング ペインの一覧を含む特別なコンテキスト メニューを表示するようにライブラリに指示します。

```
void EnablePaneContextMenu(
    BOOL bEnable,
    UINT uiCustomizeCmd,
    const CString& strCustomizeText,
    BOOL bToolbarsOnly = FALSE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]TRUE の場合、ライブラリは自動コンテキスト メニューのサポートをオンにします。FALSE の場合、ライブラリは自動コンテキスト メニューのサポートをオフにします。

*ui カスタマイズCmd*<br/>
[in]メニューの **[カスタマイズ**] 項目のコマンド ID。

*テキストをカスタマイズします。*<br/>
[in]**カスタマイズ**項目のテキスト。

*bツールバーのみ*<br/>
[in]TRUE の場合、メニューにはアプリケーション ツールバーの一覧のみが表示されます。FALSE の場合、ライブラリはアプリケーションのドッキング ペインをこのリストに追加します。

## <a name="cdockingmanagerfinddocksite"></a><a name="finddocksite"></a>クッキングマネージャー::検索ドックサイト

指定した位置にあり、指定した配置を持つバー ペインを取得します。

```
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,
    BOOL bOuter);
```

### <a name="parameters"></a>パラメーター

*dw配置*<br/>
[in]バー ペインの配置。

*ボター*<br/>
[in]TRUE の場合は、コントロール バーのリストの先頭位置にあるバーを取得します。 それ以外の場合は、コントロール バーのリストの末尾の位置にあるバーを取得します。

### <a name="return-value"></a>戻り値

指定された配置を持つドッキング ペイン。それ以外の場合は NULL。

## <a name="cdockingmanagerfindpanebyid"></a><a name="findpanebyid"></a>クッキングマネージャー::ペインバイIDを検索します

指定したコントロール ID でペインを検索します。

```
virtual CBasePane* FindPaneByID(
    UINT uBarID,
    BOOL bSearchMiniFrames = FALSE);
```

### <a name="parameters"></a>パラメーター

*ユーバーID*<br/>
[in]検索するペインのコントロール ID を指定します。

*ビクサー・ミニフレーム*<br/>
[in]検索にフローティング ペインをすべて含める場合は TRUE。 ドッキングされたペインのみを含める場合は FALSE。

### <a name="return-value"></a>戻り値

指定したコントロール ID を持つ[CBasePane](../../mfc/reference/cbasepane-class.md)オブジェクト。または指定されたペインが見つからない場合は NULL。

### <a name="remarks"></a>解説

## <a name="cdockingmanagerfinddocksitebypane"></a><a name="finddocksitebypane"></a>クッキングマネージャー::検索ドッキングサイトバイペイン

ターゲット バー ペインの ID を持つバー ペインを返します。

```
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ターゲット バー ペインへのポインター。

### <a name="return-value"></a>戻り値

ターゲット バー ペインの ID を持つバー ペイン。そのようなバー ペインが存在しない場合は NULL。

## <a name="cdockingmanagerfixupvirtualrects"></a><a name="fixupvirtualrects"></a>クッキングマネージャー::フィックスアップバーチャルレクト

現在のすべてのツール バーの位置を仮想四角形にコミットします。

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>解説

ユーザーがツール バーをドラッグし始めると、アプリケーションは*仮想四角形*内の元の位置を記憶します。 ユーザーがドッキング サイトを横切ってツール バーを移動すると、ツール バーが他のツール バーを移動することがあります。 他のツールバーの元の位置は、対応する仮想四角形に格納されます。

## <a name="cdockingmanagerframefrompoint"></a><a name="framefrompoint"></a>チャッキングマネージャー::フレームフロインポイント

指定したポイントを含むフレームを返します。

```
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,
    CPaneFrameWnd* pFrameToExclude,
    BOOL bFloatMultiOnly) const;
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
[in]チェックする点を画面座標で指定します。

*を除外します。*<br/>
[in]除外するフレームへのポインター。

*をクリックする*<br/>
[in]インスタンスではないフレームを除外する場合は`CMultiPaneFrameWnd`TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

指定したポイントを含むフレーム。それ以外の場合は NULL。

## <a name="cdockingmanagergetclientareabounds"></a><a name="getclientareabounds"></a>クライアントエリアの境界

クライアント領域の境界を含む四角形を取得します。

```
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```

### <a name="parameters"></a>パラメーター

*rcクライアント*<br/>
[アウト]クライアント領域の境界を含む四角形への参照。

### <a name="return-value"></a>戻り値

クライアント領域の境界を含む四角形。

## <a name="cdockingmanagergetdockingmode"></a><a name="getdockingmode"></a>クリッピングマネージャー::取得ドッキングモード

現在のドッキング モードを返します。

```
static AFX_DOCK_TYPE GetDockingMode();
```

### <a name="return-value"></a>戻り値

現在のドッキング モードを表す列挙子の値。 次のいずれかの値を指定できます。

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

### <a name="remarks"></a>解説

ドッキング モードを設定するには[、CDockingManager::SetDockingMode](#setdockingmode)を呼び出します。

## <a name="cdockingmanagergetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>クッキングマネージャー::ゲットドックサイトフレームウンド

親ウィンドウ フレームへのポインターを取得します。

```
CFrameWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>戻り値

親ウィンドウ フレームへのポインター。

## <a name="cdockingmanagergetenabledautohidealignment"></a><a name="getenabledautohidealignment"></a>クリッピングマネージャー::取得有効化オートハイドアライメント

ペインの有効な配置を返します。

```
DWORD GetEnabledAutoHideAlignment() const;
```

### <a name="return-value"></a>戻り値

CBRS_ALIGN_ フラグのビットごとの組み合わせ、または自動非表示ペインが有効になっていない場合は 0。 詳細については[、「CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking)」を参照してください。

### <a name="remarks"></a>解説

このメソッドは、自動非表示コントロール バーの有効な配置を返します。 バーの自動非表示を有効にするには[、CFrameWndEx::自動ハイドペインを有効にします](../../mfc/reference/cframewndex-class.md#enableautohidepanes)。

## <a name="cdockingmanagergetminiframes"></a><a name="getminiframes"></a>クッキングマネージャー::ゲットミニフレーム

ミニフレームの一覧を取得します。

```
const CObList& GetMiniFrames() const;
```

### <a name="return-value"></a>戻り値

ドッキング マネージャーに属するコントロール バーを含むミニフレームの一覧。

## <a name="cdockingmanagergetouteredgebounds"></a><a name="getouteredgebounds"></a>クリッピングマネージャー::ゲットアウターエッジバウンド

フレームの外縁を含む四角形を取得します。

```
CRect GetOuterEdgeBounds() const;
```

### <a name="return-value"></a>戻り値

フレームの外縁を含む四角形。

## <a name="cdockingmanagergetpanelist"></a><a name="getpanelist"></a>クッキングマネージャー::取得ペインリスト

ドッキング マネージャーに属するペインの一覧を返します。 これには、すべてのフローティング ペインが含まれます。

```
void GetPaneList(
    CObList& lstBars,
    BOOL bIncludeAutohide = FALSE,
    CRuntimeClass* pRTCFilter = NULL,
    BOOL bIncludeTabs = FALSE);
```

### <a name="parameters"></a>パラメーター

*lstバー*<br/>
[イン、アウト]現在のドッキング マネージャーのすべてのペインが含まれています。

*b 自動非表示を含める*<br/>
[in]自動非表示モードのペインを含める場合は TRUE。それ以外の場合は FALSE。

*フィルター*<br/>
[in]NULL でない場合、返されるリストには、指定されたランタイム クラスのペインのみが含まれます。

*bタブを含める*<br/>
[in]タブを含める場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ドッキング マネージャーにタブ付きペインがある場合、メソッドは[CBaseTabbedPane クラス](../../mfc/reference/cbasetabbedpane-class.md)オブジェクトへのポインターを返し、タブを明示的に列挙する必要があります。

*pRTCFilter を*使用して、特定のクラスのペインを取得します。 たとえば、この値を適切に設定すると、ツール バーのみを取得できます。

## <a name="cdockingmanagergetsmartdockingmanager"></a><a name="getsmartdockingmanager"></a>クリッピングマネージャー::ゲットスマートドッキングマネージャー

スマート ドッキング マネージャーへのポインターを取得します。

```
CSmartDockingManager* GetSmartDockingManager();
```

### <a name="return-value"></a>戻り値

スマート ドッキング マネージャーへのポインター。

## <a name="cdockingmanagergetsmartdockingmanagerpermanent"></a><a name="getsmartdockingmanagerpermanent"></a>チャッキングマネージャー::ゲットスマートドッキングマネージャーパーマネント

スマート ドッキング マネージャーへのポインターを取得します。

```
CSmartDockingManager* GetSmartDockingManagerPermanent() const;
```

### <a name="return-value"></a>戻り値

スマート ドッキング マネージャーへのポインター。

## <a name="cdockingmanagergetsmartdockingparams"></a><a name="getsmartdockingparams"></a>チャッキングマネージャー::ゲットスマートドッキングパラム

ドッキング マネージャーのスマート ドッキング パラメーターを返します。

```
static CSmartDockingInfo& GetSmartDockingParams();
```

### <a name="return-value"></a>戻り値

現在のドッキング マネージャーのスマート ドッキング パラメーターを格納しているクラス。 詳細については[、「CSmartDockingInfo クラス](../../mfc/reference/csmartdockinginfo-class.md)」を参照してください。

### <a name="remarks"></a>解説

## <a name="cdockingmanagerhideautohidepanes"></a><a name="hideautohidepanes"></a>CDockingマネージャー::隠し自動隠しペイン

自動非表示モードのペインを非表示にします。

```
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,
    BOOL bImmediately = FALSE);
```

### <a name="parameters"></a>パラメーター

*を除外します。*<br/>
[in]非表示から除外するバーへのポインター。

*bすぐに*<br/>
[in]ペインをすぐに非表示にするには TRUE。自動非表示効果を使用してペインを非表示にする場合は FALSE。

## <a name="cdockingmanagerinsertdocksite"></a><a name="insertdocksite"></a>クッキングマネージャー::挿入ドックサイト

ドッキング ペインを作成し、コントロール バーのリストに挿入します。

```
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,
    DWORD dwAlignToInsertAfter,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>パラメーター

*info*<br/>
[in]ドッキング ペインの配置情報を格納する構造体。

*後に挿入する*<br/>
[in]ドッキング ペインの配置。

*をクリックします。*<br/>
[アウト]ドッキング ペインへのポインターへのポインター。

### <a name="return-value"></a>戻り値

ドッキング ペインが正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerinsertpane"></a><a name="insertpane"></a>ウィンドウディングマネージャー::挿入ペイン

コントロール バーの一覧にコントロール ペインを挿入します。

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>パラメーター

*コントロールバー*<br/>
[in]コントロール ペインへのポインター。

*pターゲット*<br/>
[in]ターゲット ペインへのポインター。

*bアフター*<br/>
[in]ターゲット ペインの位置の後にペインを挿入する場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

コントロール ペインがコントロール バーの一覧に正常に追加された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

コントロール ペインがコントロール バーのリストに既に表示されている場合、またはターゲット ペインがコントロール バーの一覧に存在しない場合は、このメソッドは false を返します。

## <a name="cdockingmanagerisdocksitemenu"></a><a name="isdocksitemenu"></a>クッキングマネージャー::イズドックサイトメニュー

すべてのペインのキャプションにポップアップ メニューを表示するかどうかを指定します。

```
static BOOL IsDockSiteMenu();
```

### <a name="return-value"></a>戻り値

すべてのドッキング ペインのキャプションにドッキング サイト メニューが表示される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ドッキング サイト メニューを有効にするには[、CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)を呼び出します。

## <a name="cdockingmanagerisinadjustlayout"></a><a name="isinadjustlayout"></a>チャッキングマネージャー::IsInAdjustレイアウト

すべてのペインのレイアウトを調整するかどうかを決定します。

```
BOOL IsInAdjustLayout() const;
```

### <a name="return-value"></a>戻り値

すべてのペインのレイアウトが調整されている場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerisolecontainermode"></a><a name="isolecontainermode"></a>をクリックします。

ドッキング マネージャーが OLE コンテナー モードであるかどうかを指定します。

```
BOOL IsOLEContainerMode() const;
```

### <a name="return-value"></a>戻り値

ドッキング マネージャーが OLE コンテナー モードの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

OLE コンテナ モードでは、すべてのドッキング ペインとアプリケーション ツール バーが非表示になります。 [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)を TRUE に設定している場合、ペインもこのモードでは非表示になります。

## <a name="cdockingmanagerispointneardocksite"></a><a name="ispointneardocksite"></a>チャッキングマネージャー::イスポイントニアドックサイト

指定したポイントがドッキング サイトの近くにあるかどうかを判断します。

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]指定したポイント。

*整列*<br/>
[アウト]ポイントの近くにあるエッジを指定します。 使用できる値は、CBRS_ALIGN_LEFT、CBRS_ALIGN_RIGHT、CBRS_ALIGN_TOP、およびCBRS_ALIGN_BOTTOMです。

*ボターエッジ*<br/>
[アウト]ポイントがドッキング サイトの外側の境界付近にある場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ポイントがドッキング サイトの近くにある場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerisprintpreviewvalid"></a><a name="isprintpreviewvalid"></a>クッキングマネージャー::イズプリントプレビュー有効

印刷プレビュー モードを設定するかどうかを決定します。

```
BOOL IsPrintPreviewValid() const;
```

### <a name="return-value"></a>戻り値

印刷プレビュー モードが設定されている場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerloadstate"></a><a name="loadstate"></a>クッキングマネージャー::ロードステート

レジストリからドッキング マネージャーの状態を読み込みます。

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]プロファイル名。

*Uiid*<br/>
[in]ドッキング マネージャーの ID。

### <a name="return-value"></a>戻り値

ドッキング マネージャーの状態が正常に読み込まれた場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerlockupdate"></a><a name="lockupdate"></a>クッキングマネージャー::ロックアップデート

指定されたウィンドウをロックします。

```
void LockUpdate(BOOL bLock);
```

### <a name="parameters"></a>パラメーター

*ブロック*<br/>
[in]ウィンドウがロックされている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ウィンドウがロックされていると、移動できず、再描画もできません。

## <a name="cdockingmanagerm_bhidedockingbarsincontainermode"></a><a name="m_bhidedockingbarsincontainermode"></a>チャッキングマネージャー::m_bHideDockingBarsInContainerMode

ドッキング マネージャーが OLE コンテナー モードでペインを非表示にするかどうかを指定します。

```
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;
```

### <a name="remarks"></a>解説

アプリケーションが OLE コンテナ モードのときに、すべてのペインをメイン フレームにドッキングしたままにする場合は、この値を FALSE に設定します。 既定では、この値は TRUE です。

## <a name="cdockingmanagerm_dockmodeglobal"></a><a name="m_dockmodeglobal"></a>クッキングマネージャー::m_dockModeGlobal

グローバル ドッキング モードを指定します。

```
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;
```

### <a name="remarks"></a>解説

既定では、各ドッキング ペインは、このドッキング モードを使用します。 このフィールドに設定できる値の詳細については[、「CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)」を参照してください。

## <a name="cdockingmanagerm_ndocksensitivity"></a><a name="m_ndocksensitivity"></a>チャッキングマネージャー::m_nDockSensitivity

ドッキングの感度を指定します。

```
AFX_IMPORT_DATA static int m_nDockSensitivity;
```

### <a name="remarks"></a>解説

ドッキングの感度は、フレームワークがドッキング状態を変更する前に、フローティング ペインがドッキング ペイン、ドッキング サイト、または別のペインにどの程度近づくかを定義します。

## <a name="cdockingmanagerm_ntimeoutbeforedockingbardock"></a><a name="m_ntimeoutbeforedockingbardock"></a>チャッキングマネージャー::m_nTimeOutBeforeDockingBarDock

ドッキング ペインが即時ドッキング モードでドッキングされるまでの時間をミリ秒単位で指定します。

```
static UINT m_nTimeOutBeforeDockingBarDock;
```

### <a name="remarks"></a>解説

ペインがドッキングされる前に、フレームワークは指定された時間待機します。 これにより、ユーザーがドラッグしている間に、ペインが誤って場所にドッキングされるのを防ぐことができます。

## <a name="cdockingmanagerm_ntimeoutbeforetoolbardock"></a><a name="m_ntimeoutbeforetoolbardock"></a>クリッピングマネージャー::m_nTimeOutBeforeToolBarDock

ツール バーがメイン フレーム ウィンドウにドッキングされるまでの時間をミリ秒単位で指定します。

```
static UINT m_nTimeOutBeforeToolBarDock;
```

### <a name="remarks"></a>解説

ツールバーがドッキングされる前に、フレームワークは指定された時間を待機します。 これにより、ユーザーがドラッグしている間に、ツール バーが誤って位置にドッキングされるのを防ぐことができます。

## <a name="cdockingmanageronactivateframe"></a><a name="onactivateframe"></a>チャッキングマネージャー::オンアクティブフレーム

フレーム ウィンドウがアクティブになったり非アクティブになったりしたときに、フレームワークによって呼び出されます。

```
virtual void OnActivateFrame(BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*bアクティブ化*<br/>
[in]TRUE の場合、フレーム ウィンドウはアクティブになります。FALSE の場合、フレーム ウィンドウは非アクティブになります。

## <a name="cdockingmanageronclosepopupmenu"></a><a name="onclosepopupmenu"></a>メニューメニューを閉じる

アクティブなポップアップ メニューが WM_DESTROY メッセージを処理するときに、フレームワークによって呼び出されます。

```
void OnClosePopupMenu();
```

### <a name="remarks"></a>解説

フレームワークは、現在のメイン ウィンドウを閉じるときにWM_DESTROY メッセージを送信します。 このメソッドをオーバーライドすると、オブジェクト`CMFCPopupMenu`がWM_DESTROY メッセージを処理するときに、フレーム`CMFCPopupMenu`ウィンドウに属するオブジェクトからの通知を処理できます。

## <a name="cdockingmanageronmoveminiframe"></a><a name="onmoveminiframe"></a>チャッキングマネージャー::オンムーブミニフレーム

ミニフレーム ウィンドウを移動するために、フレームワークによって呼び出されます。

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
[in]ミニフレーム ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanageronpanecontextmenu"></a><a name="onpanecontextmenu"></a>ウィンドウディングマネージャー::オンペインコンテキストメニュー

ペインの一覧を含むメニューを構築するときに、フレームワークによって呼び出されます。

```
void OnPaneContextMenu(CPoint point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]メニューの場所を指定します。

## <a name="cdockingmanagerpanefrompoint"></a><a name="panefrompoint"></a>:Pアネア

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

*ポイント*<br/>
[in]チェックする点を画面座標で指定します。

*n感度*<br/>
[in]各チェック ボックスのウィンドウ枠のウィンドウ四角形を拡大する値。 指定したポイントがこの膨張領域にある場合、ペインは検索条件を満たします。

*をクリックします。*<br/>
[in]n感度パラメータを無視する*場合は*TRUE。それ以外の場合は FALSE。

*タイプを変更します。*<br/>
[in]NULL でない場合、メソッドは指定された型のペインのみを検索します。

*可視性を確認する*<br/>
[in]表示されているペインのみをチェックする場合は TRUE。それ以外の場合は FALSE。

*dw配置*<br/>
[アウト]指定したポイントにペインが見つかった場合、このパラメーターには、指定したポイントに最も近いペインの辺が含まれます。 詳細については、「解説」を参照してください。

*無視する*<br/>
[in]NULL でない場合、メソッドはこのパラメーターで指定されたペインを無視します。

### <a name="return-value"></a>戻り値

指定したポイントを含む[CBasePane](../../mfc/reference/cbasepane-class.md)派生オブジェクト。

### <a name="remarks"></a>解説

関数が返り、ペインが見つかった場合 *、dwAlignment*には指定した点の配置が含まれます。 たとえば、ポイントがペインの最上部に最も近い場合は *、dwAlignment*がCBRS_ALIGN_TOPに設定されます。

## <a name="cdockingmanagerprocesspanecontextmenucommand"></a><a name="processpanecontextmenucommand"></a>:Pロセスペインコンテキストメニューコマンド

指定したコマンドのチェック ボックスをオンまたはオフにして、表示されたペインのレイアウトを再計算するために、フレームワークによって呼び出されます。

```
BOOL ProcessPaneContextMenuCommand(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]メニューのコントロール バーの ID。

*nコード*<br/>
[in]コマンド通知コード。

*pエクストラ*<br/>
[in]*nCode*がCN_UPDATE_COMMAND_UIかどうかを指すポインターにキャストされる`CCmdUI`void へのポインター。

*をクリックします。*<br/>
[in]情報構造体へのポインター。 このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

*pEXtra*が NULL で *、nCode*がCN_UPDATE_COMMAND_UIに等しい場合、または指定された*nID*のコントロール バーがある場合は TRUE。

## <a name="cdockingmanagerrecalclayout"></a><a name="recalclayout"></a>キャッキングマネージャー::再計算レイアウト

コントロールの一覧に表示されているコントロールの内部レイアウトを再計算します。

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*通知する*<br/>
[in]このパラメーターは使用されません。

## <a name="cdockingmanagerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>::リリース空のペインコンテナ

空のペイン コンテナを解放します。

```
void ReleaseEmptyPaneContainers();
```

## <a name="cdockingmanagerremovehiddenmditabbedbar"></a><a name="removehiddenmditabbedbar"></a>チャッキングマネージャー::削除隠しタブベッドバー

指定した非表示バー ペインを削除します。

```
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]削除するバー ペインへのポインター。

## <a name="cdockingmanagerremoveminiframe"></a><a name="removeminiframe"></a>チャッキングマネージャー::ミニフレームの削除

ミニ フレームのリストから指定したフレームを削除します。

```
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]削除するフレームへのポインター。

### <a name="return-value"></a>戻り値

指定されたフレームが削除された場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>次の操作を行います。

ペインの登録を解除し、ドッキング マネージャーのリストから削除します。

```
void RemovePaneFromDockManager(
    CBasePane* pWnd,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]削除するペインへのポインター。

*bデストロイ*<br/>
[in]TRUE の場合、削除されたペインは破棄されます。

*レイアウトを調整する*<br/>
[in]TRUE の場合は、ドッキング レイアウトをすぐに調整します。

*b 自動非表示*<br/>
[in]TRUE の場合、ペインは自動非表示バーのリストから削除されます。 FALSE の場合、通常のペインの一覧からペインが削除されます。

*交換用*<br/>
[in]削除されたペインを置き換えるペインへのポインター。

## <a name="cdockingmanagerreplacepane"></a><a name="replacepane"></a>ウィンドウを置き換えるマネージャー:ペインを置き換える

ペインを別のペインに置き換えます。

```
BOOL ReplacePane(
    CDockablePane* pOriginalBar,
    CDockablePane* pNewBar);
```

### <a name="parameters"></a>パラメーター

*の使用*<br/>
[in]元のペインへのポインター。

*をクリックします。*<br/>
[in]元のペインを置き換えるペインへのポインター。

### <a name="return-value"></a>戻り値

ペインが正常に置き換えられた場合は TRUE。それ以外の場合は FALSE。

## <a name="cdockingmanagerresortminiframesforzorder"></a><a name="resortminiframesforzorder"></a>チャッキングマネージャー::リゾートミニフレームフォーズオーダー

ミニ フレームのリスト内のフレームをリゾートします。

```
void ResortMiniFramesForZOrder();
```

## <a name="cdockingmanagersavestate"></a><a name="savestate"></a>チャッキングマネージャー::セーブステート

ドッキング マネージャーの状態をレジストリに保存します。

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]レジストリ キーへのパス。

*Uiid*<br/>
[in]ドッキング マネージャー ID。

### <a name="return-value"></a>戻り値

状態が正常に保存された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ドッキング マネージャーの状態をレジストリに保存するには、コントロール バーの状態、自動非表示バーの状態、およびドッキング マネージャーに存在するミニ フレームの状態を保存する必要があります。

## <a name="cdockingmanagersendmessagetominiframes"></a><a name="sendmessagetominiframes"></a>ウィンドウディングマネージャー::メッセージを送信ミニフレーム

指定されたメッセージをすべてのミニフレームに送信します。

```
BOOL SendMessageToMiniFrames(
    UINT uMessage,
    WPARAM wParam = 0,
    LPARAM lParam = 0);
```

### <a name="parameters"></a>パラメーター

*メッセージ*<br/>
[in]送信されるメッセージ。

*wParam*<br/>
[in]追加のメッセージ依存情報。

*lParam*<br/>
[in]追加のメッセージ依存情報。

### <a name="return-value"></a>戻り値

常に TRUE。

## <a name="cdockingmanagerserialize"></a><a name="serialize"></a>CDockingマネージャー::シリアライズ

ドッキング マネージャーをアーカイブに書き込みます。

```
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
[in]アーカイブ オブジェクトへの参照。

### <a name="remarks"></a>解説

ドッキング マネージャーをアーカイブに書き込むには、ドッキング コントロール バーとスライダーの数を決定し、コントロール バー、ミニ フレーム、自動非表示バー、および MDI タブ付きバーをアーカイブに書き込みます。

## <a name="cdockingmanagersetautohidezorder"></a><a name="setautohidezorder"></a>クリッピングマネージャー::自動ハイドZOrderを設定します

コントロール バーと指定したペインのサイズ、幅、および高さを設定します。

```
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```

### <a name="parameters"></a>パラメーター

*pAHドッキングバー*<br/>
[in]ドッキング可能なペインへのポインター。

## <a name="cdockingmanagersetdockingmode"></a><a name="setdockingmode"></a>クッキングマネージャー::セットドッキングモード

ドッキング モードを設定します。

```
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```

### <a name="parameters"></a>パラメーター

*ドックモード*<br/>
新しいドッキング モードを指定します。 詳細については、「解説」を参照してください。

*テーマ*<br/>
スマート ドッキング マーカーに使用するテーマを指定します。 列挙値は、AFX_SDT_DEFAULT、AFX_SDT_VS2005、AFX_SDT_VS2008のいずれかです。

### <a name="remarks"></a>解説

ドッキング モードを設定するには、この静的メソッドを呼び出します。

*ドックモードは*、次のいずれかの値を指定できます。

- DT_STANDARD - Visual Studio .NET 2003 で実装されている標準のドッキング モード。 ペインは、コンテキストをドラッグせずにドラッグされます。

- DT_IMMEDIATE - Microsoft Visio で実装されている即時ドッキング モード。 ペインはドラッグコンテキストでドラッグされますが、マーカーは表示されません。

- DT_SMART - Visual Studio 2005 で実装されているスマート ドッキング モード。 ペインはドラッグコンテキストでドラッグされ、スマート マーカーが表示され、ペインをドッキングできる場所が表示されます。

## <a name="cdockingmanagersetdockstate"></a><a name="setdockstate"></a>クッキングマネージャー::セットドックステート

コントロール バー、ミニ フレーム、および自動非表示バーのドッキング状態を設定します。

```
virtual void SetDockState();
```

## <a name="cdockingmanagersetprintpreviewmode"></a><a name="setprintpreviewmode"></a>をクリックします。

印刷プレビューに表示されるバーの印刷プレビュー モードを設定します。

```
void SetPrintPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>パラメーター

*bプレビュー*<br/>
[in]印刷プレビュー モードが設定されている場合は TRUE。それ以外の場合は FALSE。

*pステート*<br/>
[in]プレビュー状態へのポインター。 このパラメーターは使用されません。

## <a name="cdockingmanagersetsmartdockingparams"></a><a name="setsmartdockingparams"></a>チャッキングマネージャー::セットスマートドッキングパラム

スマート ドッキングの動作を定義するパラメーターを設定します。

```
static void SetSmartDockingParams(CSmartDockingInfo& params);
```

### <a name="parameters"></a>パラメーター

*params*<br/>
[イン、アウト]スマート ドッキングのパラメーターを定義します。

### <a name="remarks"></a>解説

スマート ドッキング マーカーの外観、色、または形状をカスタマイズする場合は、このメソッドを呼び出します。

スマート ドッキング マーカーの既定の外観を使用するには[、cSmartDockingInfo クラス](../../mfc/reference/csmartdockinginfo-class.md)の初期化されていないインスタンスを*params*に渡します。

## <a name="cdockingmanagershowdelayshowminiframes"></a><a name="showdelayshowminiframes"></a>チャッキングマネージャー::ショーディレイショーミニフレーム

ミニ フレームのウィンドウを表示または非表示にします。

```
void ShowDelayShowMiniFrames(BOOL bshow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]表示されたフレームのウィンドウをアクティブにするには TRUE。FALSE を指定すると、フレームのウィンドウが非表示になります。

## <a name="cdockingmanagershowpanes"></a><a name="showpanes"></a>チャッキングマネージャー::ショーペイン

コントロールバーおよび自動非表示バーのペインを表示または非表示にします。

```
virtual BOOL ShowPanes(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]ペインを表示する場合は TRUE。FALSE を指定すると、ペインが非表示になります。

### <a name="return-value"></a>戻り値

常に FALSE です。

## <a name="cdockingmanagerstartsdocking"></a><a name="startsdocking"></a>チャッキングマネージャー::スタートスドッキング

スマート ドッキング マネージャーの配置に従って、指定したウィンドウのスマート ドッキングを開始します。

```
void StartSDocking(CWnd* pDockingWnd);
```

### <a name="parameters"></a>パラメーター

*pドッキングウンド*<br/>
[in]ドッキングするウィンドウへのポインター。

## <a name="cdockingmanagerstopsdocking"></a><a name="stopsdocking"></a>チャッキングマネージャー::ストップスドッキング

スマート ドッキングを停止します。

```
void StopSDocking();
```

## <a name="cdockingmanagergetsmartdockingtheme"></a><a name="getsmartdockingtheme"></a>チャッキングマネージャー::ゲットスマートドッキングテーマ

スマート ドッキング マーカーの表示に使用するテーマを返す静的メソッド。

```
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```

### <a name="return-value"></a>戻り値

AFX_SDT_DEFAULT、AFX_SDT_VS2005、AFX_SDT_VS2008のいずれかの列挙値を返します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[クラス](../../mfc/reference/cframewndex-class.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)<br/>
[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)
