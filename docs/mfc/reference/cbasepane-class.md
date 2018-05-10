---
title: CBasePane クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBasePane
- AFXBASEPANE/CBasePane
- AFXBASEPANE/CBasePane::AccNotifyObjectFocusEvent
- AFXBASEPANE/CBasePane::AddPane
- AFXBASEPANE/CBasePane::AdjustDockingLayout
- AFXBASEPANE/CBasePane::AdjustLayout
- AFXBASEPANE/CBasePane::CalcFixedLayout
- AFXBASEPANE/CBasePane::CanAcceptPane
- AFXBASEPANE/CBasePane::CanAutoHide
- AFXBASEPANE/CBasePane::CanBeAttached
- AFXBASEPANE/CBasePane::CanBeClosed
- AFXBASEPANE/CBasePane::CanBeDocked
- AFXBASEPANE/CBasePane::CanBeResized
- AFXBASEPANE/CBasePane::CanBeTabbedDocument
- AFXBASEPANE/CBasePane::CanFloat
- AFXBASEPANE/CBasePane::CanFocus
- AFXBASEPANE/CBasePane::CopyState
- AFXBASEPANE/CBasePane::CreateDefaultMiniframe
- AFXBASEPANE/CBasePane::CreateEx
- AFXBASEPANE/CBasePane::DockPane
- AFXBASEPANE/CBasePane::DockPaneUsingRTTI
- AFXBASEPANE/CBasePane::DockToFrameWindow
- AFXBASEPANE/CBasePane::DoesAllowDynInsertBefore
- AFXBASEPANE/CBasePane::EnableDocking
- AFXBASEPANE/CBasePane::EnableGripper
- AFXBASEPANE/CBasePane::FloatPane
- AFXBASEPANE/CBasePane::get_accHelpTopic
- AFXBASEPANE/CBasePane::get_accSelection
- AFXBASEPANE/CBasePane::GetCaptionHeight
- AFXBASEPANE/CBasePane::GetControlBarStyle
- AFXBASEPANE/CBasePane::GetCurrentAlignment
- AFXBASEPANE/CBasePane::GetDockingMode
- AFXBASEPANE/CBasePane::GetDockSiteFrameWnd
- AFXBASEPANE/CBasePane::GetEnabledAlignment
- AFXBASEPANE/CBasePane::GetMFCStyle
- AFXBASEPANE/CBasePane::GetPaneIcon
- AFXBASEPANE/CBasePane::GetPaneRow
- AFXBASEPANE/CBasePane::GetPaneStyle
- AFXBASEPANE/CBasePane::GetParentDockSite
- AFXBASEPANE/CBasePane::GetParentMiniFrame
- AFXBASEPANE/CBasePane::GetParentTabbedPane
- AFXBASEPANE/CBasePane::GetParentTabWnd
- AFXBASEPANE/CBasePane::GetRecentVisibleState
- AFXBASEPANE/CBasePane::HideInPrintPreviewMode
- AFXBASEPANE/CBasePane::InsertPane
- AFXBASEPANE/CBasePane::IsAccessibilityCompatible
- AFXBASEPANE/CBasePane::IsAutoHideMode
- AFXBASEPANE/CBasePane::IsDialogControl
- AFXBASEPANE/CBasePane::IsDocked
- AFXBASEPANE/CBasePane::IsFloating
- AFXBASEPANE/CBasePane::IsHorizontal
- AFXBASEPANE/CBasePane::IsInFloatingMultiPaneFrameWnd
- AFXBASEPANE/CBasePane::IsMDITabbed
- AFXBASEPANE/CBasePane::IsPaneVisible
- AFXBASEPANE/CBasePane::IsPointNearDockSite
- AFXBASEPANE/CBasePane::IsResizable
- AFXBASEPANE/CBasePane::IsRestoredFromRegistry
- AFXBASEPANE/CBasePane::IsTabbed
- AFXBASEPANE/CBasePane::IsVisible
- AFXBASEPANE/CBasePane::LoadState
- AFXBASEPANE/CBasePane::MoveWindow
- AFXBASEPANE/CBasePane::OnAfterChangeParent
- AFXBASEPANE/CBasePane::OnBeforeChangeParent
- AFXBASEPANE/CBasePane::OnDrawCaption
- AFXBASEPANE/CBasePane::OnMovePaneDivider
- AFXBASEPANE/CBasePane::OnPaneContextMenu
- AFXBASEPANE/CBasePane::OnRemoveFromMiniFrame
- AFXBASEPANE/CBasePane::OnSetAccData
- AFXBASEPANE/CBasePane::PaneFromPoint
- AFXBASEPANE/CBasePane::RecalcLayout
- AFXBASEPANE/CBasePane::RemovePaneFromDockManager
- AFXBASEPANE/CBasePane::SaveState
- AFXBASEPANE/CBasePane::SelectDefaultFont
- AFXBASEPANE/CBasePane::SetControlBarStyle
- AFXBASEPANE/CBasePane::SetDockingMode
- AFXBASEPANE/CBasePane::SetPaneAlignment
- AFXBASEPANE/CBasePane::SetPaneStyle
- AFXBASEPANE/CBasePane::SetWindowPos
- AFXBASEPANE/CBasePane::ShowPane
- AFXBASEPANE/CBasePane::StretchPane
- AFXBASEPANE/CBasePane::UndockPane
- AFXBASEPANE/CBasePane::DoPaint
dev_langs:
- C++
helpviewer_keywords:
- CBasePane [MFC], AccNotifyObjectFocusEvent
- CBasePane [MFC], AddPane
- CBasePane [MFC], AdjustDockingLayout
- CBasePane [MFC], AdjustLayout
- CBasePane [MFC], CalcFixedLayout
- CBasePane [MFC], CanAcceptPane
- CBasePane [MFC], CanAutoHide
- CBasePane [MFC], CanBeAttached
- CBasePane [MFC], CanBeClosed
- CBasePane [MFC], CanBeDocked
- CBasePane [MFC], CanBeResized
- CBasePane [MFC], CanBeTabbedDocument
- CBasePane [MFC], CanFloat
- CBasePane [MFC], CanFocus
- CBasePane [MFC], CopyState
- CBasePane [MFC], CreateDefaultMiniframe
- CBasePane [MFC], CreateEx
- CBasePane [MFC], DockPane
- CBasePane [MFC], DockPaneUsingRTTI
- CBasePane [MFC], DockToFrameWindow
- CBasePane [MFC], DoesAllowDynInsertBefore
- CBasePane [MFC], EnableDocking
- CBasePane [MFC], EnableGripper
- CBasePane [MFC], FloatPane
- CBasePane [MFC], get_accHelpTopic
- CBasePane [MFC], get_accSelection
- CBasePane [MFC], GetCaptionHeight
- CBasePane [MFC], GetControlBarStyle
- CBasePane [MFC], GetCurrentAlignment
- CBasePane [MFC], GetDockingMode
- CBasePane [MFC], GetDockSiteFrameWnd
- CBasePane [MFC], GetEnabledAlignment
- CBasePane [MFC], GetMFCStyle
- CBasePane [MFC], GetPaneIcon
- CBasePane [MFC], GetPaneRow
- CBasePane [MFC], GetPaneStyle
- CBasePane [MFC], GetParentDockSite
- CBasePane [MFC], GetParentMiniFrame
- CBasePane [MFC], GetParentTabbedPane
- CBasePane [MFC], GetParentTabWnd
- CBasePane [MFC], GetRecentVisibleState
- CBasePane [MFC], HideInPrintPreviewMode
- CBasePane [MFC], InsertPane
- CBasePane [MFC], IsAccessibilityCompatible
- CBasePane [MFC], IsAutoHideMode
- CBasePane [MFC], IsDialogControl
- CBasePane [MFC], IsDocked
- CBasePane [MFC], IsFloating
- CBasePane [MFC], IsHorizontal
- CBasePane [MFC], IsInFloatingMultiPaneFrameWnd
- CBasePane [MFC], IsMDITabbed
- CBasePane [MFC], IsPaneVisible
- CBasePane [MFC], IsPointNearDockSite
- CBasePane [MFC], IsResizable
- CBasePane [MFC], IsRestoredFromRegistry
- CBasePane [MFC], IsTabbed
- CBasePane [MFC], IsVisible
- CBasePane [MFC], LoadState
- CBasePane [MFC], MoveWindow
- CBasePane [MFC], OnAfterChangeParent
- CBasePane [MFC], OnBeforeChangeParent
- CBasePane [MFC], OnDrawCaption
- CBasePane [MFC], OnMovePaneDivider
- CBasePane [MFC], OnPaneContextMenu
- CBasePane [MFC], OnRemoveFromMiniFrame
- CBasePane [MFC], OnSetAccData
- CBasePane [MFC], PaneFromPoint
- CBasePane [MFC], RecalcLayout
- CBasePane [MFC], RemovePaneFromDockManager
- CBasePane [MFC], SaveState
- CBasePane [MFC], SelectDefaultFont
- CBasePane [MFC], SetControlBarStyle
- CBasePane [MFC], SetDockingMode
- CBasePane [MFC], SetPaneAlignment
- CBasePane [MFC], SetPaneStyle
- CBasePane [MFC], SetWindowPos
- CBasePane [MFC], ShowPane
- CBasePane [MFC], StretchPane
- CBasePane [MFC], UndockPane
- CBasePane [MFC], DoPaint
ms.assetid: 8163dd51-d7c7-4def-9c74-61f8ecdfad82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cbd24042e7f309a28cea5e72b6a134f3205e541
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cbasepane-class"></a>CBasePane クラス
MFC のすべてのウィンドウの基底クラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CBasePane : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CBasePane::CBasePane`|既定のコンストラクター|  
|`CBasePane::~CBasePane`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CBasePane::accHitTest`|画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest))。|  
|`CBasePane::accLocation`|指定したオブジェクトの現在の画面位置を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation))。|  
|[CBasePane::AccNotifyObjectFocusEvent](#accnotifyobjectfocusevent)|`CBasePane` このメソッドは使用されません。|  
|`CBasePane::accSelect`|選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます。 (上書き[CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect))。|  
|[CBasePane::AddPane](#addpane)|ペインをドッキング マネージャーに追加します。|  
|[Cbasepane::adjustdockinglayout](#adjustdockinglayout)|ドッキング レイアウトを調整するには、ドッキング マネージャーに呼び出しをリダイレクトします。|  
|[Cbasepane::adjustlayout](#adjustlayout)|ウィンドウの内部レイアウトを調整する必要があるときに、フレームワークによって呼び出されます。|  
|[Cbasepane::calcfixedlayout](#calcfixedlayout)|コントロール バーの水平方向のサイズを計算します。|  
|[Cbasepane::canacceptpane](#canacceptpane)|別のウィンドウをペインにドッキングできるかどうかを判断します。|  
|[CBasePane::CanAutoHide](#canautohide)|ペインが自動的に隠すモードをサポートするかどうかを判断します。|  
|[CBasePane::CanBeAttached](#canbeattached)|別のペインに、ウィンドウをドッキングできるかどうかを判断します。|  
|[Cbasepane::canbeclosed](#canbeclosed)|ウィンドウを閉じることができるかどうかを判断します。|  
|[CBasePane::CanBeDocked](#canbedocked)|別のペインに、ウィンドウをドッキングできるかどうかを判断します。|  
|[CBasePane::CanBeResized](#canberesized)|ウィンドウのサイズを変更できるかどうかを判断します。|  
|[CBasePane::CanBeTabbedDocument](#canbetabbeddocument)|MDI タブ付きドキュメントに、ウィンドウを変換できるかどうかを指定します。|  
|[CBasePane::CanFloat](#canfloat)|ペインをフローティングできるかどうかを判断します。|  
|[CBasePane::CanFocus](#canfocus)|ウィンドウがフォーカスを受け取るかどうかを指定します。|  
|[CBasePane::CopyState](#copystate)|指定されたウィンドウの状態をコピーします。|  
|[CBasePane::CreateDefaultMiniframe](#createdefaultminiframe)|ペインをフローティングできる場合は、ミニフレーム ウィンドウを作成します。|  
|[Cbasepane::createex](#createex)|ウィンドウ コントロールを作成します。|  
|[Cbasepane::dockpane](#dockpane)|別のウィンドウまたはフレーム ウィンドウには、ペインをドッキングします。|  
|[CBasePane::DockPaneUsingRTTI](#dockpaneusingrtti)|実行時の型情報を使用して、ウィンドウをドッキングします。|  
|[CBasePane::DockToFrameWindow](#docktoframewindow)|フレームにドッキング可能ペインをドッキングします。|  
|[Cbasepane::doesallowdyninsertbefore](#doesallowdyninsertbefore)|このペインと、親フレームの間で別のペインを動的に挿入するかどうかを判断します。|  
|[CBasePane::EnableDocking](#enabledocking)|メイン フレーム ウィンドウのドッキングを有効にします。|  
|[CBasePane::EnableGripper](#enablegripper)|有効またはグリッパーを無効にします。 グリッパーが有効になっている場合、ユーザーは、ウィンドウの位置を変更することをドラッグできます。|  
|`CBasePane::FillWindowRect`|内部的に使用します。|  
|[CBasePane::FloatPane](#floatpane)|ペインをフローティング状態です。|  
|`CBasePane::get_accChild`|指定された子の `IDispatch` インターフェイスのアドレスを取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild))。|  
|`CBasePane::get_accChildCount`|このオブジェクトに属する子の数を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount))。|  
|`CBasePane::get_accDefaultAction`|オブジェクトの既定のアクションを説明する文字列を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction))。|  
|`CBasePane::get_accDescription`|指定されたオブジェクトの外観を記述する文字列を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription))。|  
|`CBasePane::get_accFocus`|キーボード フォーカスを保持するオブジェクトを取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus))。|  
|`CBasePane::get_accHelp`|オブジェクトのヘルプ プロパティ文字列を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp))。|  
|[CBasePane::get_accHelpTopic](#get_acchelptopic)|指定したオブジェクトに関連付けられている WinHelp ファイルの完全なパスと、そのファイルに適切なトピックの識別子を取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic))。|  
|`CBasePane::get_accKeyboardShortcut`|オブジェクトの指定されたショートカット キーを取得するためにフレームワークによって呼び出されます。 (上書き[CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut))。|  
|`CBasePane::get_accName`|指定されたオブジェクトの名前を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname))。|  
|`CBasePane::get_accParent`|取得するためにフレームワークによって呼び出される、`IDispatch`オブジェクトの親のインターフェイスです。 (上書き[CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent))。|  
|`CBasePane::get_accRole`|指定されたオブジェクトの役割を記述する情報を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole))。|  
|[CBasePane::get_accSelection](#get_accselection)|このオブジェクトの選択されている子を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection))。|  
|`CBasePane::get_accState`|指定されたオブジェクトの現在の状態を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate))。|  
|`CBasePane::get_accValue`|指定されたオブジェクトの値を取得するために、フレームワークによって呼び出されます。 (上書き[CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue))。|  
|[Cbasepane::getcaptionheight](#getcaptionheight)|キャプションの高さを返します。|  
|[CBasePane::GetControlBarStyle](#getcontrolbarstyle)|コントロール バーのスタイルを返します。|  
|[CBasePane::GetCurrentAlignment](#getcurrentalignment)|現在のウィンドウの配置を返します。|  
|[Cbasepane::getdockingmode](#getdockingmode)|ウィンドウの現在のドッキング モードを返します。|  
|[CBasePane::GetDockSiteFrameWnd](#getdocksiteframewnd)|ウィンドウのドッキング サイト ウィンドウへのポインターを返します。|  
|[CBasePane::GetEnabledAlignment](#getenabledalignment)|ウィンドウに適用される cbrs_align _ スタイルを返します。|  
|[CBasePane::GetMFCStyle](#getmfcstyle)|MFC を特定のペインのスタイルを返します。|  
|[CBasePane::GetPaneIcon](#getpaneicon)|ウィンドウのアイコンへのハンドルを返します。|  
|`CBasePane::GetPaneRect`|内部的に使用します。|  
|[CBasePane::GetPaneRow](#getpanerow)|ポインターを返します、 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)ウィンドウがドッキングされているオブジェクト。|  
|[CBasePane::GetPaneStyle](#getpanestyle)|ウィンドウ スタイルを返します。|  
|[CBasePane::GetParentDockSite](#getparentdocksite)|親のドッキング サイトへのポインターを返します。|  
|[CBasePane::GetParentMiniFrame](#getparentminiframe)|親ミニフレーム ウィンドウへのポインターを返します。|  
|[CBasePane::GetParentTabbedPane](#getparenttabbedpane)|親のタブ付きペインへのポインターを返します。|  
|[CBasePane::GetParentTabWnd](#getparenttabwnd)|タブ内にある親ウィンドウへのポインターを返します。|  
|[CBasePane::GetRecentVisibleState](#getrecentvisiblestate)|フレームワークは、ペインをアーカイブから復元するときに、このメソッドを呼び出します。|  
|[CBasePane::HideInPrintPreviewMode](#hideinprintpreviewmode)|印刷プレビューで、ウィンドウが非表示かどうかを指定します。|  
|[CBasePane::InsertPane](#insertpane)|指定したウィンドウをドッキング マネージャーに登録します。|  
|[CBasePane::IsAccessibilityCompatible](#isaccessibilitycompatible)|ペインがアクティブなユーザー補助機能をサポートするかどうかを指定します。|  
|[CBasePane::IsAutoHideMode](#isautohidemode)|ペインが自動的に隠すモードかどうかを判断します。|  
|[CBasePane::IsDialogControl](#isdialogcontrol)|ダイアログ コントロールは、ウィンドウがあるかどうかを指定します。|  
|[CBasePane::IsDocked](#isdocked)|ウィンドウがドッキングされているかどうかを判断します。|  
|[CBasePane::IsFloating](#isfloating)|ペインがフローティング状態かどうかを判断します。|  
|[CBasePane::IsHorizontal](#ishorizontal)|ウィンドウが水平にドッキングされているかどうかを判断します。|  
|[CBasePane::IsInFloatingMultiPaneFrameWnd](#isinfloatingmultipaneframewnd)|複数のウィンドウ フレーム ウィンドウのウィンドウがかどうかを指定します。|  
|[CBasePane::IsMDITabbed](#ismditabbed)|タブ付きドキュメントとしての MDI 子ウィンドウに、ウィンドウが追加されているかどうかを判断します。|  
|[CBasePane::IsPaneVisible](#ispanevisible)|指定するかどうか、`WS_VISIBLE`のウィンドウでフラグを設定します。|  
|[CBasePane::IsPointNearDockSite](#ispointneardocksite)|指定したポイントがドッキング サイトの近くにいるかどうかを判断します。|  
|[Cbasepane::isresizable](#isresizable)|ウィンドウのサイズを変更できるかどうかを判断します。|  
|[CBasePane::IsRestoredFromRegistry](#isrestoredfromregistry)|レジストリからペインが復元されるかどうかを判断します。|  
|[CBasePane::IsTabbed](#istabbed)|タブ付きウィンドウのタブ コントロールに、ウィンドウが挿入されたかどうかを判断します。|  
|`CBasePane::IsTooltipTopmost`|内部的に使用します。|  
|[CBasePane::IsVisible](#isvisible)|ウィンドウが表示されているかどうかを判断します。|  
|[CBasePane::LoadState](#loadstate)|レジストリからペインの状態を読み込みます。|  
|[CBasePane::MoveWindow](#movewindow)|ウィンドウを移動します。|  
|[CBasePane::OnAfterChangeParent](#onafterchangeparent)|ウィンドウの親が変更されたときに、フレームワークによって呼び出されます。|  
|[CBasePane::OnBeforeChangeParent](#onbeforechangeparent)|ウィンドウは、親ウィンドウを変更する前に、フレームワークによって呼び出されます。|  
|[CBasePane::OnDrawCaption](#ondrawcaption)|フレームワークは、キャプションを描画するときに、このメソッドを呼び出します。|  
|[CBasePane::OnMovePaneDivider](#onmovepanedivider)|このメソッドは現在使用されていません。|  
|[CBasePane::OnPaneContextMenu](#onpanecontextmenu)|ウィンドウのリストを持つメニューを作成するときに、フレームワークによって呼び出されます。|  
|[CBasePane::OnRemoveFromMiniFrame](#onremovefromminiframe)|親ミニフレーム ウィンドウから、ウィンドウが削除されたときに、フレームワークによって呼び出されます。|  
|[Cbasepane::onsetaccdata](#onsetaccdata)|`CBasePane` このメソッドは使用されません。|  
|`CBasePane::OnUpdateCmdUI`|内部的に使用します。|  
|[CBasePane::PaneFromPoint](#panefrompoint)|指定したポイントを含むウィンドウを返します。|  
|`CBasePane::PreTranslateMessage`|[TranslateMessage](../../mfc/reference/cwinapp-class.md) および [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) の各 Windows 関数にディスパッチされる前に、ウィンドウ メッセージを変換するためにクラス [CWinApp](http://msdn.microsoft.com/library/windows/desktop/ms644934) で使用されます。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|  
|[CBasePane::RecalcLayout](#recalclayout)|`CBasePane` このメソッドは使用されません。|  
|[CBasePane::RemovePaneFromDockManager](#removepanefromdockmanager)|ペインの登録を解除し、ドッキング マネージャーの一覧から削除します。|  
|[CBasePane::SaveState](#savestate)|レジストリにペインの状態を保存します。|  
|[CBasePane::SelectDefaultFont](#selectdefaultfont)|指定されたデバイス コンテキストの既定のフォントを選択します。|  
|`CBasePane::Serialize`|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|  
|[CBasePane::SetControlBarStyle](#setcontrolbarstyle)|コントロール バーのスタイルを設定します。|  
|[CBasePane::SetDockingMode](#setdockingmode)|ペインのドッキングのモードを設定します。|  
|`CBasePane::SetMDITabbed`|内部的に使用します。|  
|[CBasePane::SetPaneAlignment](#setpanealignment)|ウィンドウの配置を設定します。|  
|`CBasePane::SetPaneRect`|内部的に使用します。|  
|[CBasePane::SetPaneStyle](#setpanestyle)|ウィンドウのスタイルを設定します。|  
|`CBasePane::SetRestoredFromRegistry`|内部的に使用します。|  
|[CBasePane::SetWindowPos](#setwindowpos)|サイズ、位置、およびウィンドウの Z オーダーを変更します。|  
|[CBasePane::ShowPane](#showpane)|ペインの表示と非表示を切り替えます。|  
|[Cbasepane::stretchpane](#stretchpane)|垂直または水平方向にウィンドウを拡大します。|  
|[CBasePane::UndockPane](#undockpane)|ドッキング サイト、既定のスライダーまたはミニフレーム ウィンドウの現在のドッキング位置から、ウィンドウを削除します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBasePane::DoPaint](#dopaint)|ウィンドウの背景を塗りつぶします。|  
  
## <a name="remarks"></a>コメント  
 MFC で使用できる拡張のドッキング機能をサポートするウィンドウ クラスを作成する場合をから派生する必要があります`CBasePane`またはから[CPane クラス](../../mfc/reference/cpane-class.md)です。  
  
## <a name="customization-tips"></a>カスタマイズのヒント  
 次のカスタマイズのヒントに関係するもの、`CBasePane Class`およびそれを継承するクラス。  
  
-   ウィンドウを作成するときは、いくつかの新しいスタイルを適用できます。  
  
    - `AFX_CBRS_FLOAT` ペインをフローティングをによりします。  
  
    - `AFX_CBRS_AUTOHIDE` により自動的に隠すモード。  
  
    - `AFX_CBRS_CLOSE` (非表示)、終了するウィンドウを有効にします。  
  
     これらは、フラグのビットごとの OR 操作と組み合わせることができます。  
  
 `CBasePane` これらのフラグを反映するために次の仮想ブール メソッドを実装する: [cbasepane::canbeclosed](#canbeclosed)、 [CBasePane::CanAutoHide](#canautohide)、 [CBasePane::CanFloat](#canfloat)です。 動作をカスタマイズする派生クラスでオーバーライドできます。  
  
-   ドッキングの動作をカスタマイズするには、オーバーライドすることで[cbasepane::canacceptpane](#canacceptpane)です。 ウィンドウを返す、`FALSE`別のウィンドウをドッキングされないようにするには、このメソッドからです。  
  
-   ウィンドウを作成、静的フローティングすることはできず、妨げている他のウィンドウにドッキング (OutlookDemo 例では、Outlook バーに似ています)、フローティングでないとして作成し、オーバーライド、する場合[cbasepane::doesallowdyninsertbefore](#doesallowdyninsertbefore)を返す`FALSE`です。 既定の実装を返します`FALSE`せず、ペインが作成された場合、`AFX_CBRS_FLOAT`スタイル。  
  
-   -1 以外の Id を持つすべてのウィンドウを作成します。  
  
-   ウィンドウの可視性を調べるには使用[CBasePane::IsVisible](#isvisible)です。 可視性の状態が正常に処理タブ付きモードと自動非表示モード。  
  
-   非浮動小数点のサイズ変更可能なウィンドウを作成する場合は、作成せず、`AFX_CBRS_FLOAT`スタイル、および呼び出し[CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)です。  
  
-   ペインをドッキング レイアウトから除外する、またはそのドッキング バーからツールバーを削除するには、呼び出す[CBasePane::UndockPane](#undockpane)です。 自動非表示モードのペインまたはウィンドウのタブ付きウィンドウのタブに存在するには、このメソッドを呼び出さないでください。  
  
-   浮動小数点数を自動的に隠すモードになっているペインをドッキング解除するか、呼び出す必要があります[CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode)で`FALSE`を呼び出す前に、最初の引数として[CBasePane::FloatPane](#floatpane)または[CBasePane::UndockPane](#undockpane)です。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CBasePane`クラスです。 ウィンドウを取得する方法の例、`CFrameWndEx`クラスとドッキングのモード、ペインの配置、およびウィンドウのスタイルを設定する方法です。 コードは、 [Word パッド サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxbasepane.h  
  
##  <a name="accnotifyobjectfocusevent"></a>  CBasePane::AccNotifyObjectFocusEvent  
 `CBasePane` このメソッドは使用されません。  
  
```  
virtual void AccNotifyObjectFocusEvent(int);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `int`  
 使用しません。  
  
##  <a name="addpane"></a>  CBasePane::AddPane  
 ペインをドッキング マネージャーに追加します。  
  
```  
void AddPane(CBasePane* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 追加するウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 これは、ペインをドッキング マネージャーに追加する便利なメソッドです。 このメソッドを使用すると、親のフレームの型を分析するコードを記述する必要はありません。  
  
 詳細については、次を参照してください。 [CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)と[CMDIFrameWndEx::AddPane](../../mfc/reference/cmdiframewndex-class.md#addpane)です。  
  
##  <a name="adjustdockinglayout"></a>  Cbasepane::adjustdockinglayout  
 ドッキング レイアウトを調整するには、ドッキング マネージャーに呼び出しをリダイレクトします。  
  
```  
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `hdwp`  
 複数のウィンドウの位置を含む構造体へのハンドル。  
  
### <a name="remarks"></a>コメント  
 これは、ドッキング レイアウトを調整する便利なメソッドです。 このメソッドを使用すると、親のフレームの型を分析するコードを記述する必要はありません。  
  
 詳細については、次を参照してください[CDockingManager::AdjustDockingLayout。](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)  
  
##  <a name="adjustlayout"></a>  Cbasepane::adjustlayout  
 ウィンドウの内部レイアウトを調整するためにフレームワークによって呼び出されます。  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインの内部レイアウトを調整するときに、このメソッドを呼び出します。 基底の実装では、何も行われません。  
  
##  <a name="calcfixedlayout"></a>  Cbasepane::calcfixedlayout  
 コントロール バーの水平方向のサイズを計算します。  
  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bStretch`  
 フレームのサイズ、バーを拡大するかどうかを示します。 `bStretch`と、バー ドッキング バー (ドッキングは使用できません) ではない場合は 0 は、ドッキングまたはフローティング (ドッキング使用可能) は、パラメーターが 0 以外の値。  
  
 [入力] `bHorz`  
 バーが水平方向または垂直方向であることを示します。 `bHorz`バーが水平方向および垂直方向である場合は 0 の場合は、パラメーターが 0 以外。  
  
### <a name="return-value"></a>戻り値  
 コントロール バーのサイズ (ピクセル単位) の`CSize`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 「解説」を参照してください[CControlBar::CalcFixedLayout](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)  
  
##  <a name="canacceptpane"></a>  Cbasepane::canacceptpane  
 別のウィンドウをペインにドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 ドッキング ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は別のペインを受け入れることができません。それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定されたウィンドウをドッキングする前に、フレームワークはこのメソッドを呼び出して`pBar`現在のペインにします。  
  
 このメソッドを使用して、 [CBasePane::CanBeDocked](#canbedocked)ウィンドウが、アプリケーション内の他のウィンドウにドッキングする方法を制御する方法です。  
  
 既定の実装では、`FALSE` が返されます。  
  
##  <a name="canautohide"></a>  CBasePane::CanAutoHide  
 ペインが自動的に隠すモードをサポートするかどうかを判断します。  
  
```  
virtual BOOL CanAutoHide() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このウィンドウは、自動非表示モードをサポートしている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインが自動的に隠すモードをサポートするかどうかを判断するには、この関数を呼び出します。  
  
 構築時に、この機能を設定を渡すことによって、`AFX_CBRS_AUTOHIDE`フラグを[cbasepane::createex](#createex)です。  
  
 既定の実装、`AFX_CBRS_AUTOHIDE`フラグ。 この動作をカスタマイズする派生クラスでこのメソッドをオーバーライドします。  
  
##  <a name="canbeattached"></a>  CBasePane::CanBeAttached  
 別のウィンドウまたはフレーム ウィンドウに、ウィンドウをドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanBeAttached() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 別のウィンドウまたはフレーム ウィンドウに、ウィンドウをドッキングできる場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、`FALSE` が返されます。 このメソッドを有効にするにまたはを呼び出さずにドッキングする機能を無効にする派生クラスでオーバーライド[CBasePane::EnableDocking](#enabledocking)です。  
  
##  <a name="canbeclosed"></a>  Cbasepane::canbeclosed  
 ウィンドウを閉じることができるかどうかを判断します。  
  
```  
virtual BOOL CanBeClosed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウを閉じることができます。それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ウィンドウを閉じることができるかどうかを決定するには、このメソッドを呼び出します。 メソッドを返す場合`TRUE`、**閉じる**ペインのタイトル バーにボタンが追加または、ペインをフローティング ミニフレーム ウィンドウのタイトル バーに、します。  
  
 構築時に、この機能を設定を渡すことによって、`AFX_CBRS_CLOSE`フラグを[cbasepane::createex](#createex)です。  
  
 既定の実装、`AFX_CBRS_CLOSE`フラグ。  
  
##  <a name="canbedocked"></a>  CBasePane::CanBeDocked  
 別のペインに、ウィンドウをドッキングできるかどうかを判断します。  
  
```  
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockBar`  
 別のウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` このペインを別のペインにドッキングできる場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定されたウィンドウをドッキングする前に、フレームワークはこのメソッドを呼び出して`pDockBar`現在のペインにします。  
  
 このメソッドを使用して、 [cbasepane::canacceptpane](#canacceptpane)ウィンドウが、アプリケーション内の他のウィンドウにドッキングする方法を制御する方法です。  
  
 既定の実装では、`FALSE` が返されます。  
  
##  <a name="canberesized"></a>  CBasePane::CanBeResized  
 ウィンドウのサイズを変更できるかどうかを判断します。  
  
```  
virtual BOOL CanBeResized() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウのサイズを変更する場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドはの確認、`AFX_CBRS_RESIZE`フラグは、既定で指定された`CBasePane::OnCreate`です。 このフラグが指定されていない場合、ドッキング マネージャーは、内部的にドッキングするの代わりに、特定のウィンドウをフラグします。  
  
##  <a name="canbetabbeddocument"></a>  CBasePane::CanBeTabbedDocument  
 MDI タブ付きドキュメントに、ウィンドウを変換できるかどうかを指定します。  
  
```  
virtual BOOL CanBeTabbedDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインをタブ付きドキュメントに変換できる場合それ以外の場合、`FALSE`です。 `CBasePane::CanBeTabbedDocument` は常に `FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 特定のオブジェクトのみ`CBasePane`-など、型の派生、 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)、タブ付きドキュメントに変換することができます。  
  
##  <a name="canfloat"></a>  CBasePane::CanFloat  
 ペインをフローティングできるかどうかを判断します。  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインをフローティングできる; 場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインをフローティングできるかどうかを決定するには、このメソッドを呼び出します。  
  
 構築時に、この機能を設定を渡すことによって、`AFX_CBRS_FLOAT`フラグを[cbasepane::createex](#createex)です。  
  
> [!NOTE]
>  フレームワークは、非フローティング ペインが静的であると、ドッキング状態を変更できないことを想定します。 そのため、フレームワークでは、非フローティング ペインのドッキング状態は保存されません。  
  
 既定の実装、`AFX_CBRS_FLOAT`スタイル。  
  
##  <a name="canfocus"></a>  CBasePane::CanFocus  
 ウィンドウがフォーカスを受け取るかどうかを指定します。  
  
```  
virtual BOOL CanFocus() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウがフォーカスを受け取ることができます。それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フォーカスを制御する派生クラスでこのメソッドをオーバーライドします。 たとえば、ツールバーには、フォーカスを受け取ることはできません、ためこのメソッドが返されます。`FALSE`ツール バー オブジェクトで呼び出されます。  
  
 フレームワークは、ペインはドッキングまたはドッキング解除時に入力フォーカスを設定しようとします。  
  
##  <a name="copystate"></a>  CBasePane::CopyState  
 指定されたウィンドウの状態をコピーします。  
  
```  
virtual void CopyState(CBasePane* pOrgBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOrgBar`  
 別のウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、状態をコピー`pOrgBar`このペインにします。  
  
##  <a name="createdefaultminiframe"></a>  CBasePane::CreateDefaultMiniframe  
 ペインをフローティングできる場合、このメソッドは、そのミニフレーム ウィンドウを作成します。  
  
```  
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectInitial`  
 ミニフレーム ウィンドウの初期の座標を指定します。  
  
### <a name="return-value"></a>戻り値  
 新しいミニフレーム ウィンドウへのポインターまたは`NULL`場合は、作成に失敗しました。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインがフローティング状態に切り替わるときに、このメソッドを呼び出します。 メソッドは、ミニフレーム ウィンドウを作成し、このウィンドウのウィンドウにアタッチします。  
  
 既定の実装では、`NULL` が返されます。  
  
##  <a name="createex"></a>  Cbasepane::createex  
 ウィンドウ コントロールを作成します。  
  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    DWORD dwControlBarStyle=0,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwStyleEx`  
 拡張スタイル (を参照してください[とき](../../mfc/reference/cwnd-class.md#createex)詳細については)。  
  
 [入力] `lpszClassName`  
 ウィンドウ クラスの名前。  
  
 [入力] `lpszWindowName`  
 ウィンドウの名前。  
  
 [入力] `dwStyle`  
 ウィンドウ スタイル (を参照してください[とき](../../mfc/reference/cwnd-class.md#createex))。  
  
 [入力] `rect`  
 初期の四角形。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。  
  
 [入力] `nID`  
 ウィンドウの ID を指定します 一意である必要があります。  
  
 [入力] `dwControlBarStyle`  
 ウィンドウのスタイル フラグです。  
  
 [入力] `pContext`  
 ポインター `CcreateContext`  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインが正常に作成された場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 クラスのウィンドウを作成`lpszClassName`です。 指定した場合`WS_CAPTION`、このメソッドは、クリア、`WS_CAPTION`スタイル ビットとセット`CBasePane::m_bHasCaption`に`TRUE`ライブラリがキャプションを含むウィンドウをサポートしていないため、します。  
  
 子ウィンドウのスタイルと MFC コントロール バー (cbrs _) スタイルの任意の組み合わせを使用することができます。  
  
 ライブラリは、ウィンドウのいくつかの新しいスタイルを追加します。 次の表では、新しいスタイルについて説明します。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|ペインをフローティングできます。|  
|`AFX_CBRS_AUTOHIDE`|ペインが自動的に隠すモードをサポートします。|  
|`AFX_CBRS_RESIZE`|ウィンドウのサイズを変更できます。 **重要:** このスタイルが実装されていません。|  
|`AFX_CBRS_CLOSE`|ペインを閉じることができます。|  
|`AFX_CBRS_AUTO_ROLLUP`|フローティング状態の場合、ウィンドウをロール アップをできます。|  
|`AFX_CBRS_REGULAR_TABS`|1 つのペインをドッキングこのスタイルを持つ別のペインに、通常のタブ付きウィンドウが作成されます。 (詳細については、次を参照してください[派生クラス](../../mfc/reference/ctabbedpane-class.md)。)。|  
|`AFX_CBRS_OUTLOOK_TABS`|1 つのペインは、このスタイルを持つ別のペインにドッキング、Outlook スタイルのタブ付きウィンドウが作成されます。 (詳細については、次を参照してください[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)。)。|  
  
 新しいスタイルを使用するには、指定することで`dwControlBarStyle`です。  
  
##  <a name="dockpane"></a>  Cbasepane::dockpane  
 別のウィンドウまたはフレーム ウィンドウには、ペインをドッキングします。  
  
```  
virtual BOOL DockPane(
    CBasePane* pDockBar,  
    LPCRECT lpRect,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDockBar`  
 別のウィンドウへのポインター。  
  
 [入力] `lpRect`  
 先の四角形を指定します。  
  
 [入力] `dockMethod`  
 ドッキング方法を指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` コントロール バーが正常にドッキング可能な場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 別のペインをドッキング バー ペインをドッキングするには、この関数を呼び出します ( [CDockSite クラス](../../mfc/reference/cdocksite-class.md)) で指定された`pDockBar`、またはメイン フレームに場合`pDockBar`は`NULL`します。  
  
 `dockMethod` ペインをドッキングする方法を指定します。 参照してください[CPane::DockPane](../../mfc/reference/cpane-class.md#dockpane)使用可能な値の一覧についてはします。  
  
##  <a name="dockpaneusingrtti"></a>  CBasePane::DockPaneUsingRTTI  
 実行時の型情報を使用して、ウィンドウをドッキングします。  
  
```  
void DockPaneUsingRTTI(BOOL bUseDockSite);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bUseDockSite`  
 場合`TRUE`、ドッキング サイトにドッキングします。 場合`FALSE`親のフレームにドッキングします。  
  
##  <a name="docktoframewindow"></a>  CBasePane::DockToFrameWindow  
 フレームにドッキング可能ペインをドッキングします。  
  
```  
virtual BOOL DockToFrameWindow(
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL,  
    DWORD dwDockFlags = DT_DOCK_LAST,  
    CBasePane* pRelativeBar = NULL,  
    int nRelativeIndex = -1,  
    BOOL bOuterEdge = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ペインをドッキングする親フレームの側です。  
  
 [入力] `lpRect`  
 必要なサイズ。  
  
 [入力] `dwDockFlags`  
 無視されます。  
  
 [入力] `pRelativeBar`  
 無視されます。  
  
 [入力] `nRelativeIndex`  
 無視されます。  
  
 [入力] `bOuterEdge`  
 場合`TRUE`で指定された側にドッキング可能なその他のウィンドウがあると`dwAlignment`、他のウィンドウの外側のウィンドウがドッキングされている親フレームの端に近い方です。 場合`FALSE`、近いクライアント領域の中央に、ペインはドッキングします。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功した場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは失敗ペイン分割バー ( [CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)) を作成できません。 それ以外の場合、常に返します`TRUE`です。  
  
##  <a name="doesallowdyninsertbefore"></a>  Cbasepane::doesallowdyninsertbefore  
 このペインと、親フレームの間で別のペインを動的に挿入するかどうかを判断します。  
  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ユーザーが別のペインを挿入できる場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ユーザーがこのペインの前にウィンドウを動的に挿入できるかどうかを決定するには、このメソッドを呼び出します。  
  
 たとえば、アプリケーション (Outlook バー) など、フレームの左側にドッキングされているペインを作成します。 ユーザーが、最初のペインの左側に別のペインのドッキングをするを防ぐためにこのメソッドをオーバーライドし、返す`FALSE`です。  
  
 このメソッドをオーバーライドし、返すことをお勧め`FALSE`から派生した非フローティング ペイン[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)です。  
  
 既定の実装では、`TRUE` が返されます。  
  
##  <a name="dopaint"></a>  CBasePane::DoPaint  
 ウィンドウの背景を塗りつぶします。  
  
```  
virtual void DoPaint(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装を呼び出す背景の塗りつぶしに現在のビジュアル マネージャー ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground))。  
  
##  <a name="enabledocking"></a>  CBasePane::EnableDocking  
 メイン フレーム ウィンドウのドッキングを有効にします。  
  
```  
virtual void EnableDocking(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 ドッキングの配置を有効にするを指定します。  
  
### <a name="remarks"></a>コメント  
 メイン フレームにドッキングの配置を有効にするには、このメソッドを呼び出します。 組み合わせを渡すことができます`CBRS_ALIGN_`フラグ (詳細については、次を参照してください。 [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking))。  
  
 `EnableDocking` 内部フラグを設定`CBasePane::m_dwEnabledAlignment`とペインがドッキングされているときに、フレームワークがこのフラグを確認します。  
  
 呼び出す[CBasePane::GetEnabledAlignment](#getenabledalignment)ペインのドッキングのアラインメントを決定します。  
  
##  <a name="enablegripper"></a>  CBasePane::EnableGripper  
 有効またはグリッパーを無効にします。 グリッパーが有効になっている場合、ユーザーは、ウィンドウの位置を変更することをドラッグできます。  
  
```  
virtual void EnableGripper(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` グリッパー; を有効にするには`FALSE`を無効にします。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、このメソッドを使用して、使用する代わりのグリップを有効にする、`WS_CAPTION`スタイル。  
  
##  <a name="floatpane"></a>  CBasePane::FloatPane  
 ペインをフローティング状態です。  
  
```  
virtual BOOL FloatPane(
    CRect rectFloat,  
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,  
    bool bShow=true);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rectFloat`  
 フローティング ペインが表示される画面座標を指定します。  
  
 [入力] `dockMethod`  
 使用してペインをフローティングするドッキング メソッドを指定します。  
  
 [入力] `bShow`  
 フローティング ペインが表示されているかどうかを指定します ( `TRUE`) または非表示 ( `FALSE`)。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ウィンドウが正常に; フローティングそれ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定した画面位置にあるペインをフローティング`rectFloat`です。  
  
##  <a name="get_acchelptopic"></a>  CBasePane::get_accHelpTopic  
 フレームワークの完全なパスを取得するには、このメソッドを呼び出して、`WinHelp`指定したオブジェクトと、そのファイルに適切なトピックの識別子に関連付けられているファイル。  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pszHelpFile`  
 アドレス、`BSTR`の完全なパスを受け取る、`WinHelp`存在する場合に、指定したオブジェクトに関連付けられているファイル。  
  
 [入力] `varChild`  
 取得するヘルプ トピックが、オブジェクトまたはオブジェクトの子要素のいずれかのかどうかを指定します。 このパラメーターには、いずれかを指定できます`CHILDID_SELF`(を取得するオブジェクトのヘルプ トピック) または (子のいずれかのオブジェクトの要素のヘルプ トピックを取得) する子の ID。  
  
 [入力] `pidTopic`  
 識別、`Help`指定したオブジェクトに関連付けられているファイルのトピックです。  
  
### <a name="return-value"></a>戻り値  
 `CBasePane` このメソッドを実装しません。 したがって、`CBasePane::get_accHelpTopic`は常に返します`S_FALSE`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、MFC での Active Accessibility のサポートの一部です。 オブジェクトに関するヘルプ情報を提供する派生クラスでは、この関数をオーバーライドします。  
  
##  <a name="get_accselection"></a>  CBasePane::get_accSelection  
 フレームワークは、このオブジェクトの選択された子を取得するには、このメソッドを呼び出します。  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pvarChildren`  
 選択された子を識別する情報を受け取ります。  
  
### <a name="return-value"></a>戻り値  
 `CBasePane` このメソッドを実装しません。 `pvarChildren` が `NULL` の場合、このメソッドは `E_INVALIDARG` を返します。 このメソッドを返しますそれ以外の場合、`DISP_E_MEMBERNOTFOUND`です。  
  
### <a name="remarks"></a>コメント  
 この関数は、MFC での Active Accessibility のサポートの一部です。 ウィンドウなしの ActiveX コントロール以外のウィンドウを持つユーザー インターフェイス要素がある場合は、派生クラスでは、この関数をオーバーライドします。  
  
##  <a name="getcaptionheight"></a>  Cbasepane::getcaptionheight  
 キャプションの高さを返します。  
  
```  
virtual int GetCaptionHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 キャプションの高さ。  
  
##  <a name="getcontrolbarstyle"></a>  CBasePane::GetControlBarStyle  
 コントロール バーのスタイルを返します。  
  
```  
virtual DWORD GetControlBarStyle() const 
```  
  
### <a name="return-value"></a>戻り値  
 Afx_cbrs _ フラグのビットごとの OR の組み合わせ。  
  
### <a name="remarks"></a>コメント  
 戻り値は、次の値の組み合わせです。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|コントロール バー float になります。|  
|`AFX_CBRS_AUTOHIDE`|により自動的に隠すモード。|  
|`AFX_CBRS_RESIZE`|コントロール バーのサイズを変更できるようにします。 このフラグが設定されている場合は、ドッキング可能なウィンドウで、コントロール バーを配置できます。|  
|`AFX_CBRS_CLOSE`|コントロール バーの非表示を有効にします。|  
  
##  <a name="getcurrentalignment"></a>  CBasePane::GetCurrentAlignment  
 現在のウィンドウの配置を返します。  
  
```  
virtual DWORD GetCurrentAlignment() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール バーの現在の配置。 次の表は、使用可能な値を示しています。  
  
|[値]|アラインメント|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|左揃え。|  
|`CBRS_ALIGN_RIGHT`|右揃え。|  
|`CBRS_ALIGN_TOP`|上揃え。|  
|`CBRS_ALIGN_BOTTOM`|下揃え。|  
  
##  <a name="getdockingmode"></a>  Cbasepane::getdockingmode  
 ウィンドウの現在のドッキング モードを返します。  
  
```  
virtual AFX_DOCK_TYPE GetDockingMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 DT_STANDARD、ウィンドウをドラッグする場合は、画面にドラッグ四角形によって示されます。 DT_IMMEDIATE ペインの内容をドラッグした場合。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ウィンドウの現在のドッキング モードを確認するには、このメソッドを呼び出します。  
  
 場合`CBasePane::m_dockMode`が未定義のドッキング モードは、グローバルのドッキング モードから取得し、(DT_UNDEFINED) ( `AFX_GLOBAL_DATA::m_dockModeGlobal`)。  
  
 設定して`m_dockMode`やオーバーライド`GetDockingMode`各ペインのドッキングのモードを制御することができます。  
  
##  <a name="getdocksiteframewnd"></a>  CBasePane::GetDockSiteFrameWnd  
 ポインターを返します、 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)ウィンドウがドッキングされているオブジェクト。  
  
```  
virtual CWnd* GetDockSiteFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのドッキング サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、ウィンドウのドッキング サイトへのポインターを取得します。 ドッキング サイトには、ペインがフローティング状態の場合、ウィンドウが、メイン フレームにドッキングされている場合は、メイン フレーム ウィンドウまたはミニフレーム ウィンドウのいずれかを指定できます。  
  
##  <a name="getenabledalignment"></a>  CBasePane::GetEnabledAlignment  
 ウィンドウに適用される cbrs_align _ スタイルを返します。  
  
```  
virtual DWORD GetEnabledAlignment() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Cbrs_align _ スタイルの組み合わせ。 次の表は、有効なスタイルを示しています。  
  
|フラグ|有効な配置|  
|----------|-----------------------|  
|`CBRS_ALIGN_LEFT`|左。|  
|`CBRS_ALIGN_RIGHT`|そうです。|  
|`CBRS_ALIGN_TOP`|ページのトップへ。|  
|`CBRS_ALIGN_BOTTOM`|下部にあります。|  
|`CBRS_ALIGN_ANY`|すべてのフラグの組み合わせ。|  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、ウィンドウの有効な配置を決定します。 有効な配置では、ペインをドッキングできるメイン フレーム ウィンドウの辺を意味します。  
  
 使用してドッキング配置を有効にする[CBasePane::EnableDocking](#enabledocking)です。  
  
##  <a name="getmfcstyle"></a>  CBasePane::GetMFCStyle  
 MFC に固有のペインのスタイルを返します。  
  
```  
virtual DWORD GetMFCStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 特定のライブラリ (afx_cbrs _) ペインのスタイルの組み合わせ。  
  
##  <a name="getpaneicon"></a>  CBasePane::GetPaneIcon  
 ウィンドウのアイコンへのハンドルを返します。  
  
```  
virtual HICON GetPaneIcon(BOOL bBigIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bBigIcon`  
 場合は、32 ピクセルのアイコンによって 32 ピクセルを指定`TRUE`; 場合は、16 ピクセルのアイコンで 16 ピクセルを指定`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウのアイコンへのハンドル。 失敗した場合、返します`NULL`です。  
  
### <a name="remarks"></a>コメント  
 既定の実装[CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon)です。  
  
##  <a name="getpanerow"></a>  CBasePane::GetPaneRow  
 ポインターを返します、 [CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)ウィンドウがドッキングされているオブジェクト。  
  
```  
CDockingPanesRow* GetPaneRow();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター `CDockingPanesRow` 、ウィンドウがドッキングされている場合または`NULL`がフローティングする場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して、ウィンドウがドッキングされている行にアクセスします。 たとえば、特定の行でウィンドウを配置するを呼び出す`GetPaneRow`し[CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes)です。  
  
##  <a name="getpanestyle"></a>  CBasePane::GetPaneStyle  
 ウィンドウ スタイルを返します。  
  
```  
virtual DWORD GetPaneStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 コントロール バーのスタイル (cbrs _ スタイルを含む) によって設定されたの組み合わせ、 [CBasePane::SetPaneStyle](#setpanestyle)メソッドの作成時にします。  
  
##  <a name="getparentdocksite"></a>  CBasePane::GetParentDockSite  
 親のドッキング サイトへのポインターを返します。  
  
```  
virtual CDockSite* GetParentDockSite() const;  
```  
  
### <a name="return-value"></a>戻り値  
 親のドッキング サイトです。  
  
##  <a name="getparentminiframe"></a>  CBasePane::GetParentMiniFrame  
 親ミニフレーム ウィンドウへのポインターを返します。  
  
```  
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bNoAssert`  
 場合`TRUE`、このメソッドは無効なポインターをチェックしません。 アプリケーションの終了時にこのメソッドを呼び出す場合は、このパラメーターを設定`TRUE`です。  
  
### <a name="return-value"></a>戻り値  
 親ミニフレーム ウィンドウのウィンドウが固定されていない場合に有効なポインターそれ以外の場合`NULL`です。  
  
### <a name="remarks"></a>コメント  
 親ミニフレーム ウィンドウへのポインターを取得するには、この関数を呼び出します。 このメソッドは、すべての親を反復処理およびから派生したオブジェクトのチェック[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)です。  
  
 使用して`GetParentMiniFrame`ペインがフローティング状態かどうかを決定します。  
  
##  <a name="getparenttabbedpane"></a>  CBasePane::GetParentTabbedPane  
 親のタブ付きペインへのポインターを返します。  
  
```  
CBaseTabbedPane* GetParentTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 存在する場合は、親のタブ付きペインへのポインターそれ以外の場合`NULL`です。  
  
##  <a name="getparenttabwnd"></a>  CBasePane::GetParentTabWnd  
 タブ内にある親ウィンドウへのポインターを返します。  
  
```  
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `hWndTab`  
 戻り値がない場合`NULL`、このパラメーターには、親のタブ付きウィンドウへのハンドルが含まれています。  
  
### <a name="return-value"></a>戻り値  
 親への有効なポインターがタブ付きウィンドウまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、親のタブ付きウィンドウへのポインターを取得できます。 場合によってを呼び出すのに十分な`GetParent`ペインがドッキング ラッパー内であるので、( [CDockablePaneAdapter クラス](../../mfc/reference/cdockablepaneadapter-class.md)) 内またはウィンドウ アダプター ( [CDockablePaneAdapter クラス](../../mfc/reference/cdockablepaneadapter-class.md))。 使用して`GetParentTabWnd`(親はタブ付きウィンドウであると仮定) このような場合、有効なポインターを取得することができます。  
  
##  <a name="getrecentvisiblestate"></a>  CBasePane::GetRecentVisibleState  
 フレームワークは、ペインをアーカイブから復元するときに、このメソッドを呼び出します。  
  
```  
virtual BOOL GetRecentVisibleState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`BOOL`最近使用した表示状態を指定します。 場合`TRUE`ペインが表示される場合に、シリアル化され、復元するときに表示されている必要があります。 場合`FALSE`、シリアル化および復元するときに非表示にするときに、ウィンドウが非表示にします。  
  
##  <a name="hideinprintpreviewmode"></a>  CBasePane::HideInPrintPreviewMode  
 印刷プレビューで、ウィンドウが非表示かどうかを指定します。  
  
```  
virtual BOOL HideInPrintPreviewMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 印刷プレビューでは、ウィンドウが表示されない場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 印刷プレビューでは、基本ウィンドウは表示されません。 そのため、このメソッドは常`TRUE`です。  
  
##  <a name="insertpane"></a>  CBasePane::InsertPane  
 指定したウィンドウをドッキング マネージャーに登録します。  
  
```  
BOOL InsertPane(
    CBasePane* pControlBar,  
    CBasePane* pTarget,  
    BOOL bAfter = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pControlBar`  
 挿入するウィンドウへのポインター。  
  
 [入力] `pTarget`  
 隣のウィンドウへのポインター。  
  
 [入力] `bAfter`  
 場合`TRUE`、`pControlBar`の後に挿入`pTarget`です。 場合`FALSE`、`pControlBar`前に、挿入は`pTarget`します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` メソッドが成功すると、`FALSE`それ以外の場合。  
  
##  <a name="isaccessibilitycompatible"></a>  CBasePane::IsAccessibilityCompatible  
 ペインがアクティブなユーザー補助機能をサポートするかどうかを指定します。  
  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウには、Active Accessibility; がサポートされている場合それ以外の場合、`FALSE`です。  
  
##  <a name="isautohidemode"></a>  CBasePane::IsAutoHideMode  
 ペインが自動的に隠すモードかどうかを判断します。  
  
```  
virtual BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが自動的に隠すモードである場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 基本ウィンドウできない自動的に隠すです。 このメソッドは常に `FALSE` を返します。  
  
##  <a name="isdialogcontrol"></a>  CBasePane::IsDialogControl  
 ダイアログ ボックス コントロールは、ウィンドウがあるかどうかを指定します。  
  
```  
BOOL IsDialogControl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ペインには、ダイアログ ボックス コントロールです。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、このメソッドを使用して、すべてのペインのレイアウトの一貫性を確保します。  
  
##  <a name="isdocked"></a>  CBasePane::IsDocked  
 ウィンドウがドッキングされているかどうかを判断します。  
  
```  
virtual BOOL IsDocked() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウの親がミニ フレームではない場合、またはミニフレームで別のペインで、ペインがフローティング状態の場合それ以外の場合、`FALSE`です。  
  
##  <a name="isfloating"></a>  CBasePane::IsFloating  
 ペインがフローティング状態かどうかを判断します。  
  
```  
virtual BOOL IsFloating() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ペインがフローティングそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドの逆の値を返します[CBasePane::IsDocked](#isdocked)です。  
  
##  <a name="ishorizontal"></a>  CBasePane::IsHorizontal  
 ウィンドウが水平にドッキングされているかどうかを判断します。  
  
```  
virtual BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウが水平方向にドッキングされている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 既定の実装で、チェックの現在のドッキング配置`CBRS_ORIENT_HORZ`です。  
  
##  <a name="isinfloatingmultipaneframewnd"></a>  CBasePane::IsInFloatingMultiPaneFrameWnd  
 複数のウィンドウ フレーム ウィンドウのウィンドウがかどうかを指定します ( [CMultiPaneFrameWnd クラス](../../mfc/reference/cmultipaneframewnd-class.md))。  
  
```  
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 複数のウィンドウ フレーム ウィンドウが、ウィンドウの場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 複数のウィンドウ フレーム ウィンドウのみドッキング可能ペインをフローティングできます。 したがって、`CBasePane::IsInFloatingMultiPaneFrameWnd`は常に返します`FALSE`です。  
  
##  <a name="ismditabbed"></a>  CBasePane::IsMDITabbed  
 タブ付きドキュメントとしての MDI 子ウィンドウに、ウィンドウが追加されているかどうかを判断します。  
  
```  
virtual BOOL IsMDITabbed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ウィンドウがタブ付きドキュメントとして MDI 子ウィンドウに追加した場合それ以外の場合、`FALSE`です。  
  
##  <a name="ispanevisible"></a>  CBasePane::IsPaneVisible  
 指定するかどうか、`WS_VISIBLE`のウィンドウでフラグを設定します。  
  
```  
BOOL IsPaneVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合`WS_VISIBLE`、それ以外の設定は、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 使用して[CBasePane::IsVisible](#isvisible)をウィンドウの可視性を判断します。  
  
##  <a name="ispointneardocksite"></a>  CBasePane::IsPointNearDockSite  
 指定したポイントがドッキング サイトの近くにいるかどうかを判断します。  
  
```  
BOOL IsPointNearDockSite(
    CPoint point,  
    DWORD& dwBarAlignment,  
    BOOL& bOuterEdge) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 指定された点です。  
  
 [出力] `dwBarAlignment`  
 点が近い端を指定します。 指定できる値は`CBRS_ALIGN_LEFT`、 `CBRS_ALIGN_RIGHT`、 `CBRS_ALIGN_TOP`、および `CBRS_ALIGN_BOTTOM`  
  
 [出力] `bOuterEdge`  
 `TRUE` ドッキング サイトの外側の境界線の近くのポイントがある場合`FALSE`それ以外の場合。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ドッキング サイトの近くのポイントがある場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 点は、ドッキング マネージャーで設定された感度内にある場合、ドッキング サイトに近いです。 既定値と小文字の区別は、15 ピクセルです。  
  
##  <a name="isresizable"></a>  Cbasepane::isresizable  
 ウィンドウのサイズを変更できるかどうかを判断します。  
  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ユーザーが、ウィンドウのサイズを変更できる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ペインの[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)サイズを変更することができます。  
  
 ステータス バー ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) とドッキング バー ( [CDockSite クラス](../../mfc/reference/cdocksite-class.md)) サイズを変更できません。  
  
##  <a name="isrestoredfromregistry"></a>  CBasePane::IsRestoredFromRegistry  
 レジストリからペインが復元されるかどうかを判断します。  
  
```  
virtual BOOL IsRestoredFromRegistry() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` レジストリからペインが復元される場合それ以外の場合、`FALSE`です。  
  
##  <a name="istabbed"></a>  CBasePane::IsTabbed  
 タブ付きウィンドウのタブ コントロールに、ウィンドウが挿入されたかどうかを判断します。  
  
```  
virtual BOOL IsTabbed() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` タブ付きウィンドウのタブで、コントロール バーが挿入された場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、直接の親へのポインターを取得し、かどうかを親のランタイム クラス[CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)です。  
  
##  <a name="isvisible"></a>  CBasePane::IsVisible  
 ウィンドウが表示されているかどうかを判断します。  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインが表示されている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの表示を指定するのにには、このメソッドを使用します。 `::IsWindowVisible` は使用しないでください。  
  
 場合は、ウィンドウがタブ付きされません (を参照してください[CBasePane::IsTabbed](#istabbed))、このメソッドを確認、`WS_VISIBLE`スタイル。 場合は、ウィンドウのタブは、このメソッドは、親タブ付きウィンドウの可視性を確認します。 親ウィンドウが表示されている場合、関数は、ウィンドウ タブを使用して、可視性[CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible)です。  
  
##  <a name="loadstate"></a>  CBasePane::LoadState  
 レジストリからペインの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `nIndex`  
 プロファイルのインデックス。  
  
 [入力] `uiID`  
 ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` ペインの状態が正常に読み込まれている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、レジストリからペインの状態を読み込むには、このメソッドを呼び出します。 によって保存された追加の情報を読み込む派生クラスでオーバーライド[CBasePane::SaveState](#savestate)です。  
  
##  <a name="movewindow"></a>  CBasePane::MoveWindow  
 ウィンドウを移動します。  
  
```  
virtual HDWP MoveWindow(
    CRect& rect,  
    BOOL bRepaint = TRUE,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `rect`  
 新しい場所と、ウィンドウのサイズを指定する四角形。  
  
 [入力] `bRepaint`  
 場合`TRUE`ウィンドウが再描画します。 場合`FALSE`ウィンドウが再描画されません。  
  
 [入力] `hdwp`  
 遅延ウィンドウ位置構造体へのハンドルします。  
  
### <a name="return-value"></a>戻り値  
 遅延のウィンドウの位置の構造体へのハンドルまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
 渡す場合`NULL`として、`hdwp`パラメーター、このメソッドは通常ウィンドウを移動します。 ハンドルを渡す場合、このメソッドは、遅延のウィンドウの移動を実行します。 呼び出すことによって、ハンドルを取得することができます[BeginDeferWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms632672)またはこのメソッドを前回呼び出したときの戻り値を格納することによりします。  
  
##  <a name="onafterchangeparent"></a>  CBasePane::OnAfterChangeParent  
 ウィンドウの親の変更後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndOldParent`  
 以前の親へのポインター。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインの親変更されたら、通常、ドッキングまたはフローティング操作のために、このメソッドを呼び出します。  
  
 既定の実装では、何も行われません。  
  
##  <a name="onbeforechangeparent"></a>  CBasePane::OnBeforeChangeParent  
 ウィンドウは、親ウィンドウを変更する前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,  
    BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndNewParent`  
 新しい親ウィンドウへのポインター。  
  
 [入力] `bDelay`  
 レイアウト調整を遅延する必要があるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークはドッキング、フローティング、または自動非表示操作のため、通常、ウィンドウの親の変更の直前にこのメソッドを呼び出します。  
  
 既定の実装では、何も行われません。  
  
##  <a name="ondrawcaption"></a>  CBasePane::OnDrawCaption  
 フレームワークは、キャプションを描画するときに、このメソッドを呼び出します。  
  
```  
virtual void OnDrawCaption();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドのための機能はありません、`CBasePane`クラスです。  
  
##  <a name="onmovepanedivider"></a>  CBasePane::OnMovePaneDivider  
 このメソッドは現在使用されていません。  
  
```  
virtual void OnMovePaneDivider(CPaneDivider*);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `CPaneDivider*`  
 使用しません。  
  
##  <a name="onpanecontextmenu"></a>  CBasePane::OnPaneContextMenu  
 ウィンドウのリストを持つメニューを作成するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParentFrame`  
 親フレームへのポインター。  
  
 [入力] `point`  
 ショートカット メニューの場所を指定します。  
  
### <a name="remarks"></a>コメント  
 `OnPaneContextMenu` 現在のフレーム ウィンドウに属しているウィンドウの一覧を保持する、ドッキング マネージャーを呼び出します。 このメソッドは、ショートカット メニューに、ウィンドウの名前を追加し、それを表示します。 メニューのコマンドは、表示または個別のペインを非表示にします。  
  
 この動作をカスタマイズするには、このメソッドをオーバーライドします。  
  
##  <a name="onremovefromminiframe"></a>  CBasePane::OnRemoveFromMiniFrame  
 親ミニフレーム ウィンドウから、ウィンドウが削除されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMiniFrame`  
 ミニフレーム ウィンドウのウィンドウの削除元となるへのポインター。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、親ミニフレーム ウィンドウ (ドッキングなど) の結果から、ウィンドウが削除されたときに、このメソッドを呼び出します。  
  
 既定の実装では、何も行われません。  
  
##  <a name="onsetaccdata"></a>  Cbasepane::onsetaccdata  
 `CBasePane` このメソッドは使用されません。  
  
```  
virtual BOOL OnSetAccData(long lVal);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lVal`  
 使用しません。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="panefrompoint"></a>  CBasePane::PaneFromPoint  
 指定したポイントを含むウィンドウを返します。  
  
```  
CBasePane* PaneFromPoint(
    CPoint point,  
    int nSensitivity,  
    bool bExactBar = false,  
    CRuntimeClass* pRTCBarType = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 確認の画面座標で、ポイントを指定します。  
  
 [入力] `nSensitivity`  
 この量によって、検索の領域を増やします。 指定された点が拡大された領域の場合、ペインは検索条件を満たします。  
  
 [入力] `bExactBar`  
 `TRUE` 無視する、`nSensitivity`パラメーターです。 それ以外の場合、`FALSE`です。  
  
 [入力] `pRTCBarType`  
 ない場合`NULL`、指定した型のペインのみが検索されます。  
  
### <a name="return-value"></a>戻り値  
 `CBasePane`-特定のポイントを格納しているオブジェクトを派生または`NULL`ウィンドウが見つからなかった場合です。  
  
##  <a name="recalclayout"></a>  CBasePane::RecalcLayout  
 `CBasePane` このメソッドは使用されません。  
  
```  
virtual void RecalcLayout();
```  
  
##  <a name="removepanefromdockmanager"></a>  CBasePane::RemovePaneFromDockManager  
 ペインの登録を解除し、ドッキング マネージャーの一覧から削除します。  
  
```  
void RemovePaneFromDockManager(
    CBasePane* pBar,  
    BOOL bDestroy = TRUE,  
    BOOL bAdjustLayout = FALSE,  
    BOOL bAutoHide = FALSE,  
    CBasePane* pBarReplacement = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 削除するウィンドウへのポインター。  
  
 [入力] `bDestroy`  
 場合`TRUE`、削除されたウィンドウが破棄されます。  
  
 [入力] `bAdjustLayout`  
 場合`TRUE`、すぐにドッキング レイアウトを調整します。  
  
 [入力] `bAutoHide`  
 場合`TRUE`、ドッキング レイアウトは自動的に隠すバーのリストに関連します。 場合`FALSE`、ドッキング レイアウトは標準のペインの一覧に関連します。  
  
 [入力] `pBarReplacement`  
 削除されるペインに置き換えられるペインへのポインター。  
  
##  <a name="savestate"></a>  CBasePane::SaveState  
 レジストリにペインの状態を保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,  
    int nIndex=-1,  
    UINT uiID=(UINT)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 プロファイルの名前。  
  
 [入力] `nIndex`  
 プロファイルのインデックス。  
  
 [入力] `uiID`  
 ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 状態が正常に保存されている場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ペインの状態をレジストリに保存するときに、このメソッドを呼び出します。 オーバーライド`SaveState`追加情報を格納する派生クラスでします。  
  
##  <a name="selectdefaultfont"></a>  CBasePane::SelectDefaultFont  
 指定されたデバイス コンテキストの既定のフォントを選択します。  
  
```  
CFont* SelectDefaultFont(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキスト。  
  
### <a name="return-value"></a>戻り値  
 既定値へのポインター [CFont クラス](../../mfc/reference/cfont-class.md)オブジェクト。  
  
##  <a name="setcontrolbarstyle"></a>  CBasePane::SetControlBarStyle  
 コントロール バーのスタイルを設定します。  
  
```  
virtual void SetControlBarStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwNewStyle`  
 次の値のビットごとの OR の組み合わせ。  
  
|スタイル|説明|  
|-----------|-----------------|  
|`AFX_CBRS_FLOAT`|コントロール バー float になります。|  
|`AFX_CBRS_AUTOHIDE`|により自動的に隠すモード。|  
|`AFX_CBRS_RESIZE`|コントロール バーのサイズを変更できるようにします。 このフラグが設定されている場合は、ドッキング可能なウィンドウで、コントロール バーを配置できます。|  
|`AFX_CBRS_CLOSE`|コントロール バーの非表示を有効にします。|  
  
##  <a name="setdockingmode"></a>  CBasePane::SetDockingMode  
 ペインのドッキングのモードを設定します。  
  
```  
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dockModeNew`  
 ウィンドウのドッキング モードを指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、次の 2 つのドッキング モードをサポートしています: standard および即時です。  
  
 標準ドッキング モードで、ウィンドウやミニフレーム ウィンドウがドラッグ四角形の使用を中心に移動されます。 イミディ エイトのドッキング モードでコントロール バーおよびミニフレーム ウィンドウは移動すぐがコンテキストでします。  
  
 ドッキングのモードがグローバルに定義されている最初に、 [CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal)です。 使用して個別に各ペインのドッキングのモードを設定することができます、`SetDockingMode`メソッドです。  
  
##  <a name="setpanealignment"></a>  CBasePane::SetPaneAlignment  
 ウィンドウの配置を設定します。  
  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwAlignment`  
 新しい配置を指定します。  
  
### <a name="remarks"></a>コメント  
 通常は、フレームワークは、別にメイン フレームの一方の側から、ウィンドウがドッキングされているときに、このメソッドを呼び出します。  
  
 次の表は、可能な値を示しています`dwAlignment`:。  
  
|[値]|アラインメント|  
|-----------|---------------|  
|`CBRS_ALIGN_LEFT`|左揃え。|  
|`CBRS_ALIGN_RIGHT`|右揃え。|  
|`CBRS_ALIGN_TOP`|上揃え。|  
|`CBRS_ALIGN_BOTTOM`|下揃え。|  
  
##  <a name="setpanestyle"></a>  CBasePane::SetPaneStyle  
 ウィンドウのスタイルを設定します。  
  
```  
virtual void SetPaneStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwNewStyle`  
 設定する新しいスタイルを指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、afxres.h 内で定義されている cbrs _ スタイルのいずれかの設定を使用できます。 ウィンドウ スタイルとウィンドウの配置は一緒に格納されるので、次のように現在の配置と組み合わせることにより、新しいスタイルを設定します。  
  
 `pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`  
  
##  <a name="setwindowpos"></a>  CBasePane::SetWindowPos  
 サイズ、位置、およびウィンドウの Z オーダーを変更します。  
  
```  
virtual HDWP SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags,  
    HDWP hdwp = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndInsertAfter`  
 識別、`CWnd`これの前に来るオブジェクト`CWnd`Z オーダー内のオブジェクト。 詳細については、次を参照してください。 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)です。  
  
 [入力] `x`  
 ウィンドウの左側の位置を指定します。  
  
 [入力] `y`  
 ウィンドウの上端の位置を指定します。  
  
 [入力] `cx`  
 ウィンドウの幅を指定します。  
  
 [入力] `cy`  
 ウィンドウの高さを指定します。  
  
 [入力] `nFlags`  
 サイズと位置のオプションを指定します。 詳細については、次を参照してください。 [CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)です。  
  
 [入力] `hdwp`  
 1 つまたは複数のウィンドウのサイズと位置情報を格納する構造体へのハンドルします。  
  
### <a name="return-value"></a>戻り値  
 更新された遅延ウィンドウ位置構造体へのハンドルまたは`NULL`です。  
  
### <a name="remarks"></a>コメント  
 場合`pWndInsertAfter`は`NULL`、このメソッドを呼び出す[CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)です。 場合`pWndInsertAfter`以外`NULL`、このメソッドを呼び出す`DeferWindowPos`です。  
  
##  <a name="showpane"></a>  CBasePane::ShowPane  
 ペインの表示と非表示を切り替えます。  
  
```  
virtual void ShowPane(
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShow`  
 表示するかどうかを指定します ( `TRUE`) の表示と非 ( `FALSE`) ペインです。  
  
 [入力] `bDelay`  
 場合`TRUE`、ドッキング レイアウトを再計算が遅延します。  
  
 [入力] `bActivate`  
 場合`TRUE`ペインが表示されているときにアクティブです。  
  
### <a name="remarks"></a>コメント  
 このメソッドまたはウィンドウを非表示にします。 代わりにこのメソッドを使用して`ShowWindow`のため、このメソッドは、ペインの表示の変更に関する関連する、ドッキング マネージャーに通知します。  
  
 使用して[CBasePane::IsVisible](#isvisible)をウィンドウの現在の可視性を判断します。  
  
##  <a name="stretchpane"></a>  Cbasepane::stretchpane  
 垂直または水平方向にウィンドウを拡大します。  
  
```  
virtual CSize StretchPane(
    int nLength,  
    BOOL bVert);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nLength`  
 ウィンドウを拡大する長さ。  
  
 [入力] `bVert`  
 場合`TRUE`、垂直方向のウィンドウを拡大します。 場合`FALSE`、水平方向のウィンドウを拡大します。  
  
### <a name="return-value"></a>戻り値  
 ストレッチされたウィンドウのサイズ。  
  
##  <a name="undockpane"></a>  CBasePane::UndockPane  
 ドッキング サイト、既定のスライダーまたはミニフレーム ウィンドウの現在のドッキング位置から、ウィンドウを削除します。  
  
```  
virtual void UndockPane(BOOL bDelay=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDelay`  
 TRUE の場合、ドッキング レイアウトはすぐに再計算されません。  
  
### <a name="remarks"></a>コメント  
 ペインの状態を操作またはペインをドッキング レイアウトから除外するには、このメソッドを呼び出します。  
  
 引き続きこのペインを使用する場合は、いずれかを呼び出す[cbasepane::dockpane](#dockpane)または[CBasePane::FloatPane](#floatpane)このメソッドを呼び出す前にします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CPane](../../mfc/reference/cbasepane-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)
