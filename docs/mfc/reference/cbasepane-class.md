---
title: Cベースウィンドウクラス
ms.date: 11/06/2018
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
ms.openlocfilehash: 941f32dfadffd97210586edd7c2aa63c3c1708cd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752993"
---
# <a name="cbasepane-class"></a>Cベースウィンドウクラス

MFC のすべてのペインの基本クラス。

## <a name="syntax"></a>構文

```
class CBasePane : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CBasePane::CBasePane`|既定のコンストラクターです。|
|`CBasePane::~CBasePane`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CBasePane::accHitTest`|画面上の指定された位置にある子要素または子オブジェクトを取得するために、フレームワークによって呼び出されます。 [(CWnd をオーバーライドします。::アヒットテスト](../../mfc/reference/cwnd-class.md#acchittest).)|
|`CBasePane::accLocation`|指定したオブジェクトの現在の画面位置を取得するために、フレームワークによって呼び出されます。 [(CWnd をオーバーライドします。:アロケーション](../../mfc/reference/cwnd-class.md#acclocation).)|
|[ウィンドウ::アック通知オブジェクトフォーカスイベント](#accnotifyobjectfocusevent)|`CBasePane`このメソッドは使用しません。|
|`CBasePane::accSelect`|選択を変更するため、または指定されたオブジェクトのキーボード フォーカスを移動するために、フレームワークによって呼び出されます。 [(CWnd をオーバーライドします::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|
|[Cベースペイン::ペインの追加](#addpane)|ドッキング マネージャーにペインを追加します。|
|[CBase ペイン::調整ドッキングレイアウト](#adjustdockinglayout)|ドッキング マネージャーに呼び出しをリダイレクトしてドッキング レイアウトを調整します。|
|[ウィンドウ::レイアウトの調整](#adjustlayout)|ペインが内部レイアウトを調整する必要があるときに、フレームワークによって呼び出されます。|
|[Cベースペイン::計算式レイアウト](#calcfixedlayout)|コントロール バーの水平方向のサイズを計算します。|
|[C ベースペイン::缶アクセプウィンドウ](#canacceptpane)|別のペインをペインにドッキングできるかどうかを判断します。|
|[CBase ペイン::缶自動非表示](#canautohide)|ペインが自動非表示モードをサポートするかどうかを決定します。|
|[Cベースペイン::缶詰添付](#canbeattached)|ペインを別のペインにドッキングできるかどうかを判断します。|
|[Cベースペイン::缶詰閉](#canbeclosed)|ペインを閉じることができるかどうかを判断します。|
|[Cベースペイン::缶詰](#canbedocked)|ペインを別のペインにドッキングできるかどうかを判断します。|
|[Cベースペイン::缶ベサイズ](#canberesized)|ペインのサイズを変更できるかどうかを決定します。|
|[ウィンドウペイン::缶ベタブベドドキュメント](#canbetabbeddocument)|ペインを MDI タブ付きドキュメントに変換できるかどうかを指定します。|
|[Cベースペイン::缶詰](#canfloat)|ペインをフロートできるかどうかを判断します。|
|[Cベースペイン::缶フォーカス](#canfocus)|ペインがフォーカスを受け取ることができるかどうかを指定します。|
|[Cベースペイン::コピーステート](#copystate)|指定されたペインの状態をコピーします。|
|[Cベースペイン::デフォルトミニフレームの作成](#createdefaultminiframe)|ペインをフローティングできる場合は、ミニフレーム ウィンドウを作成します。|
|[Cベースペイン::作成Ex](#createex)|ペイン コントロールを作成します。|
|[Cベースペイン::Dロックウィンドウ](#dockpane)|ペインを別のペインまたはフレーム ウィンドウにドッキングします。|
|[Cベースペイン::DオックパネusingRTTI](#dockpaneusingrtti)|実行時の型情報を使用してペインをドッキングします。|
|[ウィンドウ:Dロックウィンドウ](#docktoframewindow)|ドッキング可能なペインをフレームにドッキングします。|
|[前に挿入:D](#doesallowdyninsertbefore)|このペインと親フレームの間に別のペインを動的に挿入できるかどうかを指定します。|
|[CBase ペイン::有効化ドッキング](#enabledocking)|ペインをメイン フレームにドッキングできるようにします。|
|[Cベースペイン::イネーブルグリッパー](#enablegripper)|グリッパーを有効または無効にします。 グリッパーが有効になっている場合、ユーザーはそれをドラッグしてペインの位置を変更できます。|
|`CBasePane::FillWindowRect`|内部使用。|
|[Cベースペイン::フロートペイン](#floatpane)|ペインをフローティングします。|
|`CBasePane::get_accChild`|指定された子の `IDispatch` インターフェイスのアドレスを取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild)をオーバーライドします。|
|`CBasePane::get_accChildCount`|このオブジェクトに属する子の数を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount)をオーバーライドします。|
|`CBasePane::get_accDefaultAction`|オブジェクトの既定のアクションを記述する文字列を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction)をオーバーライドします。|
|`CBasePane::get_accDescription`|指定されたオブジェクトの外観を記述する文字列を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription)をオーバーライドします。|
|`CBasePane::get_accFocus`|キーボード フォーカスを保持するオブジェクトを取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus)をオーバーライドします。|
|`CBasePane::get_accHelp`|オブジェクトのヘルプ プロパティ文字列を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp)をオーバーライドします。|
|[Cベースペイン::get_accHelpTopic](#get_acchelptopic)|指定したオブジェクトに関連付けられている WinHelp ファイルの完全パスとそのファイル内の適切なトピックの識別子を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic)をオーバーライドします。|
|`CBasePane::get_accKeyboardShortcut`|オブジェクトの指定されたショートカット キーを取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut)をオーバーライドします。|
|`CBasePane::get_accName`|指定されたオブジェクトの名前を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname)をオーバーライドします。|
|`CBasePane::get_accParent`|オブジェクトの親のインターフェイスを`IDispatch`取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accParent](../../mfc/reference/cwnd-class.md#get_accparent)をオーバーライドします。|
|`CBasePane::get_accRole`|指定されたオブジェクトの役割を記述する情報を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole)をオーバーライドします。|
|[Cベースペイン::get_accSelection](#get_accselection)|このオブジェクトの選択されている子を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection)をオーバーライドします。|
|`CBasePane::get_accState`|指定されたオブジェクトの現在の状態を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate)をオーバーライドします。|
|`CBasePane::get_accValue`|指定されたオブジェクトの値を取得するために、フレームワークによって呼び出されます。 [(CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue)をオーバーライドします。|
|[ウィンドウ::ゲットキャプションハイト](#getcaptionheight)|キャプションの高さを返します。|
|[ウィンドウ::コントロールバースタイルを取得します。](#getcontrolbarstyle)|コントロール バーのスタイルを返します。|
|[ウィンドウ::取得カレントアライメント](#getcurrentalignment)|現在のペインの配置を返します。|
|[Cベースペイン::取得ドッキングモード](#getdockingmode)|ペインの現在のドッキング モードを返します。|
|[ウィンドウ::ゲットドックサイトフレームウンド](#getdocksiteframewnd)|ペインのドッキング サイトであるウィンドウへのポインターを返します。|
|[ウィンドウ::取得有効化アライメント](#getenabledalignment)|ペインに適用されるCBRS_ALIGN_スタイルを返します。|
|[ウィンドウ::ゲットMFCスタイル](#getmfcstyle)|MFC に固有のペイン スタイルを返します。|
|[Cベースペイン::ゲットペインアイコン](#getpaneicon)|ペイン アイコンへのハンドルを返します。|
|`CBasePane::GetPaneRect`|内部使用。|
|[Cベースペイン::ゲットペインロウ](#getpanerow)|ペインがドッキングされている[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)オブジェクトへのポインターを返します。|
|[ウィンドウ::ゲットペインスタイル](#getpanestyle)|ペインのスタイルを返します。|
|[Cベースペイン::ゲットペアレントドックサイト](#getparentdocksite)|親ドッキング サイトへのポインターを返します。|
|[ウィンドウ::ゲットペアレントミニフレーム](#getparentminiframe)|親ミニフレーム ウィンドウへのポインターを返します。|
|[Cベースペイン::ゲットペアレントタブベドペイン](#getparenttabbedpane)|親タブ付きペインへのポインターを返します。|
|[ウィンドウ::ゲットペアタブンド](#getparenttabwnd)|タブ内にある親ウィンドウへのポインターを返します。|
|[ウィンドウ::取得最新の可視状態](#getrecentvisiblestate)|ペインがアーカイブから復元されると、フレームワークはこのメソッドを呼び出します。|
|[ウィンドウ::非表示印刷プレビューモード](#hideinprintpreviewmode)|印刷プレビューでペインを非表示にするかどうかを指定します。|
|[CBase ペイン::挿入ペイン](#insertpane)|ドッキング マネージャーに指定されたペインを登録します。|
|[ウィンドウ::Is アクセシビリティ互換](#isaccessibilitycompatible)|ペインがアクティブなアクセシビリティをサポートするかどうかを指定します。|
|[CBase ペイン::IsAutoHideモード](#isautohidemode)|ペインが自動非表示モードかどうかを判断します。|
|[ウィンドウ::IsDialog コントロール](#isdialogcontrol)|ペインがダイアログ コントロールであるかどうかを指定します。|
|[Cベースペイン::IsDocked](#isdocked)|ペインがドッキングされているかどうかを判断します。|
|[Cベースペイン::イズフローティング](#isfloating)|ペインがフローティング状態かどうかを判断します。|
|[Cベースペイン::イス水平](#ishorizontal)|ペインが水平方向にドッキングされているかどうかを判断します。|
|[ウィンドウ::イインフローティングマルチペインフレームオーニング](#isinfloatingmultipaneframewnd)|ペインが複数のペインのフレーム ウィンドウにあるかどうかを指定します。|
|[Cベースペイン::イスムディタブベド](#ismditabbed)|ウィンドウがタブ付きドキュメントとして MDI 子ウィンドウに追加されているかどうかを判断します。|
|[Cベースペイン::イズペインビジブル](#ispanevisible)|ペインにWS_VISIBLEフラグを設定するかどうかを指定します。|
|[Cベースペイン::イスポイントニアドックサイト](#ispointneardocksite)|指定したポイントがドッキング サイトの近くにあるかどうかを判断します。|
|[Cベースペイン::イズリジブル](#isresizable)|ペインのサイズを変更できるかどうかを決定します。|
|[次のレジストリを使用します。](#isrestoredfromregistry)|ペインをレジストリから復元するかどうかを決定します。|
|[Cベースペイン::イタブベド](#istabbed)|タブ付きウィンドウのタブ コントロールにペインが挿入されているかどうかを判断します。|
|`CBasePane::IsTooltipTopmost`|内部使用。|
|[Cベースペイン::イズビジブル](#isvisible)|ペインが表示されているかどうかを判断します。|
|[ウィンドウ::ロードステート](#loadstate)|レジストリからペインの状態を読み込みます。|
|[ウィンドウの移動](#movewindow)|ペインを移動します。|
|[ウィンドウ::オンアフターチェンジペアレント](#onafterchangeparent)|ペインの親が変更されたときに、フレームワークによって呼び出されます。|
|[Cベースペイン::オン・オン・チェンジチェンジ・ペアレント](#onbeforechangeparent)|ペインが親ウィンドウを変更する直前に、フレームワークによって呼び出されます。|
|[ウィンドウ::オンドローキャプション](#ondrawcaption)|キャプションが描画されるときに、フレームワークはこのメソッドを呼び出します。|
|[Cベースペイン::オンムーブペインディバイダー](#onmovepanedivider)|このメソッドは現在使用されていません。|
|[C ベースペイン::オンペインコンテキストメニュー](#onpanecontextmenu)|ペインの一覧を含むメニューを構築するときに、フレームワークによって呼び出されます。|
|[Cベースペイン::オン除去ミニフレーム](#onremovefromminiframe)|ペインが親ミニ フレーム ウィンドウから削除されたときに、フレームワークによって呼び出されます。|
|[Cベースペイン::オンセットアクデータ](#onsetaccdata)|`CBasePane`このメソッドは使用しません。|
|`CBasePane::OnUpdateCmdUI`|内部使用。|
|[ソースペイン::Pアネフロトポイント](#panefrompoint)|指定したポイントを含むペインを返します。|
|`CBasePane::PreTranslateMessage`|クラス[CWinApp](../../mfc/reference/cwinapp-class.md)がウィンドウ メッセージを変換するために使用し、[変換メッセージ](/windows/win32/api/winuser/nf-winuser-translatemessage)および[ディスパッチ メッセージ](/windows/win32/api/winuser/nf-winuser-dispatchmessage)Windows 関数にディスパッチします。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[Cベースペイン::リカルクレイアウト](#recalclayout)|`CBasePane`このメソッドは使用しません。|
|[ウィンドウ::ウィンドウから削除します。](#removepanefromdockmanager)|ペインの登録を解除し、ドッキング マネージャーのリストから削除します。|
|[ウィンドウ::セーブステート](#savestate)|レジストリにペインの状態を保存します。|
|[ウィンドウ::デフォルトフォントの選択](#selectdefaultfont)|指定したデバイス コンテキストの既定のフォントを選択します。|
|`CBasePane::Serialize`|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|
|[ウィンドウ::コントロールバースタイルを設定します。](#setcontrolbarstyle)|コントロール バーのスタイルを設定します。|
|[Cベースペイン::セットドッキングモード](#setdockingmode)|ペインのドッキング モードを設定します。|
|`CBasePane::SetMDITabbed`|内部使用。|
|[ウィンドウスペイン::セットペイン配置](#setpanealignment)|ペインの配置を設定します。|
|`CBasePane::SetPaneRect`|内部使用。|
|[Cベースペイン::セットペインスタイル](#setpanestyle)|ペインのスタイルを設定します。|
|`CBasePane::SetRestoredFromRegistry`|内部使用。|
|[ウィンドウペイン::セットウィンドウポス](#setwindowpos)|ペインのサイズ、位置、および Z オーダーを変更します。|
|[Cベースペイン::ショーペイン](#showpane)|ウィンドウの表示/非表示を切り替えます。|
|[Cベースペイン::ストレッチペイン](#stretchpane)|垂直または水平方向にウィンドウを拡大します。|
|[CBase ペイン::ドッキング解除ペイン](#undockpane)|ドッキング サイト、既定のスライダー、または現在ドッキングされているミニフレーム ウィンドウからペインを削除します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ウィンドウペイン::Doペイント](#dopaint)|ペインの背景を塗りつぶします。|

## <a name="remarks"></a>解説

MFC で使用できる拡張ドッキング機能をサポートするペイン クラスを作成する場合は[、CPane](../../mfc/reference/cpane-class.md)Class`CBasePane`から派生させる必要があります。

## <a name="customization-tips"></a>カスタマイズのヒント

次のカスタマイズのヒントは、`CBasePane Class`およびそれを継承するすべてのクラスに関連します。

- ペインを作成する場合、いくつかの新しいスタイルを適用できます。

  - AFX_CBRS_FLOATペインを浮動させます。

  - AFX_CBRS_AUTOHIDEは自動非表示モードを有効にします。

  - AFX_CBRS_CLOSEを使用すると、ウィンドウを閉じる (非表示) できます。

  これらはビットごとの OR 演算で組み合わせることができるフラグです。

`CBasePane`これらのフラグを反映するために、次の仮想ブール型メソッドを実装[します。](#canbeclosed) [CBasePane::CanAutoHide](#canautohide) [CBasePane::CanFloat](#canfloat) 派生クラスでオーバーライドして動作をカスタマイズできます。

- ドッキング動作をカスタマイズするには[、CBasePane::CanAcceptPane](#canacceptpane)をオーバーライドします。 別のペインがドッキングされないようにするには、このメソッドからペインに FALSE を返してもらいます。

- フローティングできない静的ペインを作成し、その前に他のウィンドウがドッキングされないようにする場合 (OutlookDemo の例では Outlook バーと同様)、非フローティングウィンドウとして作成し[、CBasePane::DoesAllowDynInsertBefore を](#doesallowdyninsertbefore)オーバーライドして FALSE を返します。 ペインがAFX_CBRS_FLOATスタイルなしで作成された場合、既定の実装は FALSE を返します。

- 1 以外の ID を持つすべてのペインを作成します。

- ペインの表示を確認するには[、CBasePane::IsVisible](#isvisible)を使用します。 タブ付きモードと自動非表示モードでの可視性の状態を正しく処理します。

- 変更可能なフローティングウィンドウを作成する場合は、AFX_CBRS_FLOATスタイルを使用せずに作成し[、CFrameWnd::DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar)を呼び出します。

- ドッキング レイアウトからペインを除外したり、ドッキング バーからツール バーを削除したりするには[、CBasePane::UndockPane](#undockpane)を呼び出します。 自動非表示モードのペイン、またはタブ付きウィンドウのタブに存在するペインについては、このメソッドを呼び出しません。

- 自動非表示モードのペインをフローティングまたはドッキング解除する場合は、CBasePane::フロートペインまたは[CBasePane::ドッキングペイン](#undockpane)を呼び出す前に、最初の引数として False を使用して[CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode)を呼び出す必要があります。 [CBasePane::FloatPane](#floatpane)

## <a name="example"></a>例

`CBasePane` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、`CFrameWndEx`クラスからペインを取得する方法と、ドッキング モード、ペインの配置、およびペイン スタイルを設定する方法を示します。 コードは[ワード パッドのサンプル](../../overview/visual-cpp-samples.md)です。

[!code-cpp[NVC_MFC_WordPad#2](../../mfc/reference/codesnippet/cpp/cbasepane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxbasepane.h

## <a name="cbasepaneaccnotifyobjectfocusevent"></a><a name="accnotifyobjectfocusevent"></a>ウィンドウ::アック通知オブジェクトフォーカスイベント

`CBasePane`このメソッドは使用しません。

```
virtual void AccNotifyObjectFocusEvent(int);
```

### <a name="parameters"></a>パラメーター

*int*<br/>
[in]使用されていません。

## <a name="cbasepaneaddpane"></a><a name="addpane"></a>Cベースペイン::ペインの追加

ドッキング マネージャーにペインを追加します。

```cpp
void AddPane(CBasePane* pBar);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]追加するペインへのポインター。

### <a name="remarks"></a>解説

これは、ドッキング マネージャーにペインを追加する便利なメソッドです。 このメソッドを使用すると、親フレームの型を分析するコードを記述する必要はありません。

詳細については[、「CDockingManager クラス](../../mfc/reference/cdockingmanager-class.md)」および[「CMDIFrameWndEx::AddPane」を参照してください](../../mfc/reference/cmdiframewndex-class.md#addpane)。

## <a name="cbasepaneadjustdockinglayout"></a><a name="adjustdockinglayout"></a>CBase ペイン::調整ドッキングレイアウト

ドッキング マネージャーに呼び出しをリダイレクトしてドッキング レイアウトを調整します。

```
virtual void AdjustDockingLayout(HDWP hdwp=NULL);
```

### <a name="parameters"></a>パラメーター

*hdwp*<br/>
[アウト]複数のウィンドウ位置を含む構造体へのハンドル。

### <a name="remarks"></a>解説

これは、ドッキング レイアウトを調整する便利な方法です。 このメソッドを使用すると、親フレームの型を分析するコードを記述する必要はありません。

詳細については、[次を](../../mfc/reference/cdockingmanager-class.md#adjustdockinglayout)参照してください。

## <a name="cbasepaneadjustlayout"></a><a name="adjustlayout"></a>ウィンドウ::レイアウトの調整

ペインの内部レイアウトを調整するために、フレームワークによって呼び出されます。

```
virtual void AdjustLayout();
```

### <a name="remarks"></a>解説

フレームワークは、ペインが内部レイアウトを調整する必要がある場合に、このメソッドを呼び出します。 基本実装では何も実行されません。

## <a name="cbasepanecalcfixedlayout"></a><a name="calcfixedlayout"></a>Cベースペイン::計算式レイアウト

コントロール バーの水平方向のサイズを計算します。

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*bストレッチ*<br/>
[in]バーをフレームのサイズまで拡大するかどうかを示します。 バーがドッキング バー (ドッキングには使用できません) でない場合は *、bStretch*パラメーターは 0 以外であり、ドッキングまたはフローティング (ドッキングに使用可能) の場合は 0 です。

*bHorz*<br/>
[in]バーが水平方向または垂直方向であることを示します。 バーが水平方向の場合は*bHorz*パラメータは 0 以外で、縦方向の場合は 0 です。

### <a name="return-value"></a>戻り値

オブジェクトのコントロール バーのサイズ (`CSize`ピクセル単位)。

### <a name="remarks"></a>解説

CControlBar の解説セクションを参照[してください::計算固定レイアウト](../../mfc/reference/ccontrolbar-class.md#calcfixedlayout)

## <a name="cbasepanecanacceptpane"></a><a name="canacceptpane"></a>C ベースペイン::缶アクセプウィンドウ

別のペインをペインにドッキングできるかどうかを判断します。

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]ドッキングするペインへのポインター。

### <a name="return-value"></a>戻り値

別のペインを受け入れ可能な場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは *、pBar*で指定されたペインを現在のペインにドッキングする前に、このメソッドを呼び出します。

このメソッドと[CBasePane::CanBeDocked](#canbedocked)メソッドを使用して、アプリケーション内の他のペインにペインをドッキングする方法を制御します。

既定の実装では FALSE が返されます。

## <a name="cbasepanecanautohide"></a><a name="canautohide"></a>CBase ペイン::缶自動非表示

ペインが自動非表示モードをサポートするかどうかを決定します。

```
virtual BOOL CanAutoHide() const;
```

### <a name="return-value"></a>戻り値

このペインが自動非表示モードをサポートする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、ペインが自動非表示モードをサポートしているかどうかを判断するために、この関数を呼び出します。

構築時に[、CBasePane::CreateEx](#createex)にAFX_CBRS_AUTOHIDEフラグを渡すことによって、この機能を設定できます。

既定の実装では、AFX_CBRS_AUTOHIDE フラグがチェックされます。 この動作をカスタマイズするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cbasepanecanbeattached"></a><a name="canbeattached"></a>Cベースペイン::缶詰添付

ペインを別のペインまたはフレーム ウィンドウにドッキングできるかどうかを決定します。

```
virtual BOOL CanBeAttached() const;
```

### <a name="return-value"></a>戻り値

ペインを別のペインまたはフレーム ウィンドウにドッキングできる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

既定の実装では FALSE が返されます。 [CBasePane](#enabledocking)を呼び出さずにドッキングする機能を有効または無効にするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cbasepanecanbeclosed"></a><a name="canbeclosed"></a>Cベースペイン::缶詰閉

ペインを閉じることができるかどうかを判断します。

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>戻り値

ペインを閉じることができる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、ペインを閉じることができるかどうかを判断するために、このメソッドを呼び出します。 メソッドが TRUE を返す場合は、ペインのタイトル バーに**閉じる**ボタンが追加されるか、ペインがフローティング状態の場合は、ペインのミニフレーム ウィンドウのタイトル バーに追加されます。

構築中に[、CBasePane::CreateEx](#createex)にAFX_CBRS_CLOSEフラグを渡すことによって、この機能を設定できます。

既定の実装では、AFX_CBRS_CLOSE フラグがチェックされます。

## <a name="cbasepanecanbedocked"></a><a name="canbedocked"></a>Cベースペイン::缶詰

ペインを別のペインにドッキングできるかどうかを判断します。

```
virtual BOOL CanBeDocked(CBasePane* pDockBar) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]別のペインへのポインター。

### <a name="return-value"></a>戻り値

このペインを別のペインにドッキングできる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは *、pDockBar*で指定されたペインを現在のペインにドッキングする前に、このメソッドを呼び出します。

このメソッドと[CBasePane::CanAcceptPane](#canacceptpane)メソッドを使用して、ペインをアプリケーション内の他のペインにドッキングする方法を制御します。

既定の実装では FALSE が返されます。

## <a name="cbasepanecanberesized"></a><a name="canberesized"></a>Cベースペイン::缶ベサイズ

ペインのサイズを変更できるかどうかを決定します。

```
virtual BOOL CanBeResized() const;
```

### <a name="return-value"></a>戻り値

ペインのサイズを変更できる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、既定で指定されている AFX_CBRS_RESIZE フラグを`CBasePane::OnCreate`チェックします。 このフラグを指定しない場合、ドッキング マネージャーはペインをドッキングするのではなく、内部で不動のフラグとしてフラグを設定します。

## <a name="cbasepanecanbetabbeddocument"></a><a name="canbetabbeddocument"></a>ウィンドウペイン::缶ベタブベドドキュメント

ペインを MDI タブ付きドキュメントに変換できるかどうかを指定します。

```
virtual BOOL CanBeTabbedDocument() const;
```

### <a name="return-value"></a>戻り値

ペインをタブ付きドキュメントに変換できる場合は TRUE。それ以外の場合は FALSE。 `CBasePane::CanBeTabbedDocument`常に FALSE を返します。

### <a name="remarks"></a>解説

`CBasePane` [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)などの特定の派生型のオブジェクトのみをタブ付きドキュメントに変換できます。

## <a name="cbasepanecanfloat"></a><a name="canfloat"></a>Cベースペイン::缶詰

ペインをフロートできるかどうかを判断します。

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>戻り値

ペインがフローティングできる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、ペインをフローティングできるかどうかを判断するために、このメソッドを呼び出します。

構築時に[、CBasePane::CreateEx](#createex)にAFX_CBRS_FLOATフラグを渡すことによって、この機能を設定できます。

> [!NOTE]
> フレームワークは、非フローティング ペインが静的であり、ドッキング状態を変更できないと想定しています。 したがって、フレームワークは非フローティング ペインのドッキング状態を保存しません。

既定の実装では、AFX_CBRS_FLOATスタイルがチェックされます。

## <a name="cbasepanecanfocus"></a><a name="canfocus"></a>Cベースペイン::缶フォーカス

ペインがフォーカスを受け取ることができるかどうかを指定します。

```
virtual BOOL CanFocus() const;
```

### <a name="return-value"></a>戻り値

ペインがフォーカスを受け取ることができる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フォーカスを制御するには、派生クラスでこのメソッドをオーバーライドします。 たとえば、ツール バーはフォーカスを受け取ることができないため、このメソッドはツール バー オブジェクトで呼び出されたときに FALSE を返します。

フレームワークは、ペインがドッキングまたはフロートされたときに入力フォーカスを設定しようとします。

## <a name="cbasepanecopystate"></a><a name="copystate"></a>Cベースペイン::コピーステート

指定されたペインの状態をコピーします。

```
virtual void CopyState(CBasePane* pOrgBar);
```

### <a name="parameters"></a>パラメーター

*グループバー*<br/>
[in]別のペインへのポインター。

### <a name="remarks"></a>解説

このメソッドは *、pOrgBar*からこのペインに状態をコピーします。

## <a name="cbasepanecreatedefaultminiframe"></a><a name="createdefaultminiframe"></a>Cベースペイン::デフォルトミニフレームの作成

ペインをフローティングできる場合、このメソッドは、そのミニフレーム ウィンドウを作成します。

```
virtual CPaneFrameWnd* CreateDefaultMiniframe(CRect rectInitial);
```

### <a name="parameters"></a>パラメーター

*レクトイニシャル*<br/>
[in]ミニフレーム ウィンドウの初期座標を指定します。

### <a name="return-value"></a>戻り値

作成に失敗した場合は、新しいミニフレーム ウィンドウへのポインター。

### <a name="remarks"></a>解説

フレームワークは、ペインがフローティング状態に切り替わったときにこのメソッドを呼び出します。 このメソッドは、ミニフレーム ウィンドウを作成し、ウィンドウをこのウィンドウにアタッチします。

既定の実装では NULL が返されます。

## <a name="cbasepanecreateex"></a><a name="createex"></a>Cベースペイン::作成Ex

ペイン コントロールを作成します。

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

*ドウスタイルエックス*<br/>
[in]拡張スタイル (詳細については[、CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)を参照してください)。

*クラス名*<br/>
[in]ウィンドウ クラス名。

*名前をクリックします。*<br/>
[in]ウィンドウ名。

*Dwstyle*<br/>
[in]ウィンドウ スタイル[(CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)を参照)。

*Rect*<br/>
[in]初期の四角形。

*pParentWnd*<br/>
[in]親ウィンドウへのポインター。

*nID*<br/>
[in]ペイン ID を指定します。 一意である必要があります。

*コントロール バースタイル*<br/>
[in]ペインのスタイル フラグ。

*pContext*<br/>
[in]へのポインタ`CcreateContext`

### <a name="return-value"></a>戻り値

ペインが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

クラス`lpszClassName`のウィンドウを作成します。 WS_CAPTION指定すると、ライブラリはキャプション付きのペインをサポートしていないため、`CBasePane::m_bHasCaption`このメソッドはWS_CAPTION スタイル ビットをクリアし、TRUE に設定します。

子ウィンドウ スタイルと MFC コントロール バー (CBRS_) スタイルを任意に組み合わせて使用できます。

ライブラリは、ペインに複数の新しいスタイルを追加します。 次の表に、新しいスタイルを示します。

|Style|説明|
|-----------|-----------------|
|AFX_CBRS_FLOAT|ペインはフローティング可能です。|
|AFX_CBRS_AUTOHIDE|このペインは自動非表示モードをサポートしています。|
|AFX_CBRS_RESIZE|ウィンドウのサイズを変更できます。 **重要:** このスタイルは実装されていません。|
|AFX_CBRS_CLOSE|ウィンドウを閉じることができます。|
|AFX_CBRS_AUTO_ROLLUP|ウィンドウは、フローティング時にロールアップできます。|
|AFX_CBRS_REGULAR_TABS|1 つのペインがこのスタイルを持つ別のペインにドッキングすると、通常のタブ付きウィンドウが作成されます。 (詳細については[、「CTabbedPane クラス](../../mfc/reference/ctabbedpane-class.md)」を参照してください)。|
|AFX_CBRS_OUTLOOK_TABS|1 つのペインがこのスタイルの別のペインにドッキングすると、Outlook スタイルのタブ付きウィンドウが作成されます。 (詳細については、「[クラスを参照してください](../../mfc/reference/cmfcoutlookbar-class.md)。|

新しいスタイルを使用するには *、dwControlBarStyle*で指定します。

## <a name="cbasepanedockpane"></a><a name="dockpane"></a>Cベースペイン::Dロックウィンドウ

ペインを別のペインまたはフレーム ウィンドウにドッキングします。

```
virtual BOOL DockPane(
    CBasePane* pDockBar,
    LPCRECT lpRect,
    AFX_DOCK_METHOD dockMethod);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]別のペインへのポインター。

*Lprect*<br/>
[in]目的の四角形を指定します。

*ドックメソッド*<br/>
[in]ドッキング方法を指定します。

### <a name="return-value"></a>戻り値

コントロール バーが正常にドッキングされた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*pDockBar*で指定されている別のペインまたはドッキング バー ( [CDockSite クラス](../../mfc/reference/cdocksite-class.md)) にペインをドッキングする場合、または*pDockBar*が NULL の場合はメイン フレームにペインをドッキングします。

*ドッキング方法を*指定します。 可能な値のリストについては[、「CPane::DockPane」](../../mfc/reference/cpane-class.md#dockpane)を参照してください。

## <a name="cbasepanedockpaneusingrtti"></a><a name="dockpaneusingrtti"></a>Cベースペイン::DオックパネusingRTTI

実行時の型情報を使用してペインをドッキングします。

```cpp
void DockPaneUsingRTTI(BOOL bUseDockSite);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
[in]TRUE の場合は、ドッキング サイトにドッキングします。 FALSE の場合は、親フレームにドッキングします。

## <a name="cbasepanedocktoframewindow"></a><a name="docktoframewindow"></a>ウィンドウ:Dロックウィンドウ

ドッキング可能なペインをフレームにドッキングします。

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

*dw配置*<br/>
[in]ペインをドッキングする親フレームの辺。

*Lprect*<br/>
[in]目的のサイズ。

*ドウドックフラグ*<br/>
[in]無視。

*を使用する*<br/>
[in]無視。

*相対インデックス*<br/>
[in]無視。

*ボターエッジ*<br/>
[in]true の場合 *、dwAlignment*で指定した側に他のドッキング可能なペインがある場合、ペインは親フレームの端に近い他のペインの外側にドッキングされます。 FALSE の場合、ペインはクライアント領域の中心に近い位置にドッキングされます。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ペインの区分線 ( [CPaneDivider クラス](../../mfc/reference/cpanedivider-class.md)) を作成できない場合、このメソッドは失敗します。 それ以外の場合は、常に TRUE を返します。

## <a name="cbasepanedoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>前に挿入:D

このペインと親フレームの間に別のペインを動的に挿入できるかどうかを指定します。

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

ユーザーが別のペインを挿入できる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを呼び出して、ユーザーがこのペインの前に動的にペインを挿入できるかどうかを判断します。

たとえば、アプリケーションがフレームの左側にドッキングされたペイン (Outlook バーなど) を作成するとします。 ユーザーが最初のペインの左側に別のペインをドッキングできないようにするには、このメソッドをオーバーライドして FALSE を返します。

このメソッドをオーバーライドし[、CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)から派生したフローティングウィンドウ以外のペインに対して FALSE を返すようにすることをお勧めします。

既定の実装では TRUE が返されます。

## <a name="cbasepanedopaint"></a><a name="dopaint"></a>ウィンドウペイン::Doペイント

ペインの背景を塗りつぶします。

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

既定の実装は、現在のビジュアル マネージャーを呼び出してバックグラウンドを埋めます ( [CMFCVisualManager::OnFillBarBackground](../../mfc/reference/cmfcvisualmanager-class.md#onfillbarbackground))。

## <a name="cbasepaneenabledocking"></a><a name="enabledocking"></a>CBase ペイン::有効化ドッキング

ペインをメイン フレームにドッキングできるようにします。

```
virtual void EnableDocking(DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

*dw配置*<br/>
[in]有効にするドッキングの配置を指定します。

### <a name="remarks"></a>解説

メイン フレームへのドッキング配置を有効にします。 CBRS_ALIGN_フラグの組み合わせを渡すことができます (詳細については[、「CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)」を参照してください)。

`EnableDocking`は内部フラグ`CBasePane::m_dwEnabledAlignment`を設定し、フレームワークはペインがドッキングされたときにこのフラグをチェックします。

ウィンドウのドッキングの配置を決定するには[、CBasePane::GetEnabledAlignment](#getenabledalignment)を呼び出します。

## <a name="cbasepaneenablegripper"></a><a name="enablegripper"></a>Cベースペイン::イネーブルグリッパー

グリッパーを有効または無効にします。 グリッパーが有効になっている場合、ユーザーはそれをドラッグしてペインの位置を変更できます。

```
virtual void EnableGripper(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]グリッパーを有効にする場合は TRUE。無効にする場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを使用して、WS_CAPTION スタイルを使用する代わりにグリッパーを有効にします。

## <a name="cbasepanefloatpane"></a><a name="floatpane"></a>Cベースペイン::フロートペイン

ペインをフローティングします。

```
virtual BOOL FloatPane(
    CRect rectFloat,
    AFX_DOCK_METHOD dockMethod=DM_UNKNOWN,
    bool bShow=true);
```

### <a name="parameters"></a>パラメーター

*レクトフロート*<br/>
[in]フローティング ペインが表示される画面座標を指定します。

*ドックメソッド*<br/>
[in]ペインのフロートに使用するドッキング メソッドを指定します。

*bショー*<br/>
[in]フローティング ペインを表示 (TRUE) または非表示 (FALSE) にするかどうかを指定します。

### <a name="return-value"></a>戻り値

ペインが正常にフロートされた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*rectFloat*で指定された画面位置にペインをフローティングします。

## <a name="cbasepaneget_acchelptopic"></a><a name="get_acchelptopic"></a>Cベースペイン::get_accHelpTopic

フレームワークは、指定したオブジェクトに関連付けられている**WinHelp**ファイルの完全なパスとそのファイル内の適切なトピックの識別子を取得するには、このメソッドを呼び出します。

```
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,
    VARIANT varChild,
    long* pidTopic);
```

### <a name="parameters"></a>パラメーター

*ファイル*<br/>
[in]指定したオブジェクトに関連付けられている**WinHelp**ファイルの完全パスを受け取る BSTR のアドレス (存在する場合)。

*子*<br/>
[in]取得するヘルプ トピックがオブジェクトのトピックであるか、オブジェクトの子要素のどれであるかを指定します。 このパラメーターは、CHILDID_SELF (オブジェクトのヘルプ トピックを取得する場合) または子 ID (オブジェクトの子要素の 1 つに対するヘルプ トピックを取得する場合) のいずれかです。

*ピッドトピック*<br/>
[in]指定したオブジェクトに関連付けられている**ヘルプ**ファイル トピックを識別します。

### <a name="return-value"></a>戻り値

`CBasePane`このメソッドは実装されません。 したがって、`CBasePane::get_accHelpTopic`常にS_FALSE返します。

### <a name="remarks"></a>解説

この関数は、MFC のアクティブ なアクセシビリティ サポートの一部です。 オブジェクトに関するヘルプ情報を提供するには、派生クラスでこの関数をオーバーライドします。

## <a name="cbasepaneget_accselection"></a><a name="get_accselection"></a>Cベースペイン::get_accSelection

フレームワークは、このメソッドを呼び出して、このオブジェクトの選択された子を取得します。

```
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```

### <a name="parameters"></a>パラメーター

*pvar子供たち*<br/>
[in]選択した子を識別する情報を受信します。

### <a name="return-value"></a>戻り値

`CBasePane`このメソッドは実装されません。 *pvarChildren*が NULL の場合、このメソッドはE_INVALIDARG返します。 それ以外の場合、このメソッドはDISP_E_MEMBERNOTFOUND返します。

### <a name="remarks"></a>解説

この関数は、MFC のアクティブ なアクセシビリティ サポートの一部です。 ウィンドウなしの ActiveX コントロール以外のウィンドウのないユーザー インターフェイス要素がある場合は、派生クラスでこの関数をオーバーライドします。

## <a name="cbasepanegetcaptionheight"></a><a name="getcaptionheight"></a>ウィンドウ::ゲットキャプションハイト

キャプションの高さを返します。

```
virtual int GetCaptionHeight() const;
```

### <a name="return-value"></a>戻り値

キャプションの高さ。

## <a name="cbasepanegetcontrolbarstyle"></a><a name="getcontrolbarstyle"></a>ウィンドウ::コントロールバースタイルを取得します。

コントロール バーのスタイルを返します。

```
virtual DWORD GetControlBarStyle() const
```

### <a name="return-value"></a>戻り値

AFX_CBRS_ フラグのビットごとの OR の組み合わせ。

### <a name="remarks"></a>解説

戻り値は、次の値の組み合わせです。

|Style|説明|
|-----------|-----------------|
|AFX_CBRS_FLOAT|コントロール バーをフロートします。|
|AFX_CBRS_AUTOHIDE|自動非表示モードを有効にします。|
|AFX_CBRS_RESIZE|コントロール バーのサイズ変更を有効にします。 このフラグを設定すると、コントロール バーをドッキング可能なペインに配置できます。|
|AFX_CBRS_CLOSE|コントロール バーの非表示を有効にします。|

## <a name="cbasepanegetcurrentalignment"></a><a name="getcurrentalignment"></a>ウィンドウ::取得カレントアライメント

現在のペインの配置を返します。

```
virtual DWORD GetCurrentAlignment() const;
```

### <a name="return-value"></a>戻り値

コントロール バーの現在の配置。 次の表に、使用できる値を示します。

|値|Alignment|
|-----------|---------------|
|CBRS_ALIGN_LEFT|左揃え。|
|CBRS_ALIGN_RIGHT|右揃え。|
|CBRS_ALIGN_TOP|上部の配置。|
|CBRS_ALIGN_BOTTOM|下部の配置。|

## <a name="cbasepanegetdockingmode"></a><a name="getdockingmode"></a>Cベースペイン::取得ドッキングモード

ペインの現在のドッキング モードを返します。

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>戻り値

DT_STANDARDペインをドラッグすると、ドラッグ矩形で画面上に表示されます。 DT_IMMEDIATEペインの内容をドラッグする場合。

### <a name="remarks"></a>解説

フレームワークは、ペインの現在のドッキング モードを確認するために、このメソッドを呼び出します。

未`CBasePane::m_dockMode`定義 (DT_UNDEFINED) の場合、ドッキング モードはグローバル ドッキング モード (`AFX_GLOBAL_DATA::m_dockModeGlobal`) から取得されます。

*m_dockMode*設定するか、またはオーバーライド`GetDockingMode`することで、各ペインのドッキング モードを制御できます。

## <a name="cbasepanegetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>ウィンドウ::ゲットドックサイトフレームウンド

ペインがドッキングされている[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)オブジェクトへのポインターを返します。

```
virtual CWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>戻り値

ペインのドッキング サイトへのポインター。

### <a name="remarks"></a>解説

ペインのドッキング サイトへのポインターを取得します。 ドッキング サイトは、ペインがメイン フレームにドッキングされている場合はメイン フレーム ウィンドウ、ペインがフローティング状態の場合はミニフレーム ウィンドウのいずれかになります。

## <a name="cbasepanegetenabledalignment"></a><a name="getenabledalignment"></a>ウィンドウ::取得有効化アライメント

ペインに適用されるCBRS_ALIGN_スタイルを返します。

```
virtual DWORD GetEnabledAlignment() const;
```

### <a name="return-value"></a>戻り値

CBRS_ALIGN_ スタイルの組み合わせ。 次の表に、使用できるスタイルを示します。

|フラグ|有効な配置|
|----------|-----------------------|
|CBRS_ALIGN_LEFT|左。|
|CBRS_ALIGN_RIGHT|そうです。|
|CBRS_ALIGN_TOP|上。|
|CBRS_ALIGN_BOTTOM|下部。|
|CBRS_ALIGN_ANY|すべてのフラグの組み合わせ。|

### <a name="remarks"></a>解説

ペインに対して有効な配置を確認します。 有効な配置とは、ペインをドッキングできるメイン フレーム ウィンドウの辺を意味します。

CBasePane を使用してドッキングの配置[を有効にします。::ドッキングを有効に](#enabledocking)します。

## <a name="cbasepanegetmfcstyle"></a><a name="getmfcstyle"></a>ウィンドウ::ゲットMFCスタイル

MFC に固有のペイン スタイルを返します。

```
virtual DWORD GetMFCStyle() const;
```

### <a name="return-value"></a>戻り値

ライブラリ固有の (AFX_CBRS_) ペイン スタイルの組み合わせ。

## <a name="cbasepanegetpaneicon"></a><a name="getpaneicon"></a>Cベースペイン::ゲットペインアイコン

ペイン アイコンへのハンドルを返します。

```
virtual HICON GetPaneIcon(BOOL bBigIcon);
```

### <a name="parameters"></a>パラメーター

*ビグビコン*<br/>
[in]TRUE の場合は 32 ピクセル x 32 ピクセルのアイコンを指定します。FALSE の場合、16 ピクセル x 16 ピクセルのアイコンを指定します。

### <a name="return-value"></a>戻り値

ペイン アイコンへのハンドル。 失敗した場合は NULL を返します。

### <a name="remarks"></a>解説

既定の実装は[、CWnd::GetIcon](../../mfc/reference/cwnd-class.md#geticon)を呼び出します。

## <a name="cbasepanegetpanerow"></a><a name="getpanerow"></a>Cベースペイン::ゲットペインロウ

ペインがドッキングされている[CDockingPanesRow](../../mfc/reference/cdockingpanesrow-class.md)オブジェクトへのポインターを返します。

```
CDockingPanesRow* GetPaneRow();
```

### <a name="return-value"></a>戻り値

ペイン`CDockingPanesRow`がドッキングされているかどうかを示すポインター。

### <a name="remarks"></a>解説

ペインがドッキングされている行にアクセスします。 たとえば、特定の行にペインを配置するには`GetPaneRow`[、CDockingPanesRow::ArrangePanes](../../mfc/reference/cdockingpanesrow-class.md#arrangepanes)を呼び出して呼び出します。

## <a name="cbasepanegetpanestyle"></a><a name="getpanestyle"></a>ウィンドウ::ゲットペインスタイル

ペインのスタイルを返します。

```
virtual DWORD GetPaneStyle() const;
```

### <a name="return-value"></a>戻り値

[CBasePane::SetPaneStyle](#setpanestyle)メソッドによって設定されたコントロール バー スタイル (CBRS_ スタイルを含む) の組み合わせです。

## <a name="cbasepanegetparentdocksite"></a><a name="getparentdocksite"></a>Cベースペイン::ゲットペアレントドックサイト

親ドッキング サイトへのポインターを返します。

```
virtual CDockSite* GetParentDockSite() const;
```

### <a name="return-value"></a>戻り値

親ドッキング サイト。

## <a name="cbasepanegetparentminiframe"></a><a name="getparentminiframe"></a>ウィンドウ::ゲットペアレントミニフレーム

親ミニフレーム ウィンドウへのポインターを返します。

```
virtual CPaneFrameWnd* GetParentMiniFrame(BOOL bNoAssert=FALSE) const;
```

### <a name="parameters"></a>パラメーター

*アサート*<br/>
[in]TRUE の場合、このメソッドは無効なポインターをチェックしません。 アプリケーションの終了時にこのメソッドを呼び出す場合は、このパラメーターを TRUE に設定します。

### <a name="return-value"></a>戻り値

ペインがフローティング状態の場合は、親ミニフレーム ウィンドウへの有効なポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

親ミニフレーム ウィンドウへのポインターを取得します。 このメソッドは、すべての親を反復処理し[、CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)から派生したオブジェクトをチェックします。

ペイン`GetParentMiniFrame`がフローティング状態かどうかを判断するために使用します。

## <a name="cbasepanegetparenttabbedpane"></a><a name="getparenttabbedpane"></a>Cベースペイン::ゲットペアレントタブベドペイン

親タブ付きペインへのポインターを返します。

```
CBaseTabbedPane* GetParentTabbedPane() const;
```

### <a name="return-value"></a>戻り値

親タブ付きペインが存在する場合は、そのペインへのポインター。それ以外の場合は NULL。

## <a name="cbasepanegetparenttabwnd"></a><a name="getparenttabwnd"></a>ウィンドウ::ゲットペアタブンド

タブ内にある親ウィンドウへのポインターを返します。

```
CMFCBaseTabCtrl* GetParentTabWnd(HWND& hWndTab) const;
```

### <a name="parameters"></a>パラメーター

*フーンドタブ*<br/>
[アウト]戻り値が NULL でない場合、このパラメーターには親タブ付きウィンドウへのハンドルが含まれます。

### <a name="return-value"></a>戻り値

親タブ付きウィンドウまたは NULL への有効なポインター。

### <a name="remarks"></a>解説

この関数は、親タブ付きウィンドウへのポインターを取得するために使います。 ペインがドッキング ラッパー ( `GetParent`CDockablePaneAdapter クラス ) 内にあるか、ペイン アダプタ ( [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)[クラス](../../mfc/reference/cdockablepaneadapter-class.md)) の内部にある可能性があるため、呼び出しに十分でない場合があります。 この`GetParentTabWnd`場合、親がタブ付きウィンドウであると仮定して、有効なポインタを取得することができます。

## <a name="cbasepanegetrecentvisiblestate"></a><a name="getrecentvisiblestate"></a>ウィンドウ::取得最新の可視状態

ペインがアーカイブから復元されると、フレームワークはこのメソッドを呼び出します。

```
virtual BOOL GetRecentVisibleState() const;
```

### <a name="return-value"></a>戻り値

最近の表示状態を指定する BOOL。 TRUE の場合、ウィンドウはシリアル化されたときに表示され、復元時に表示されます。 FALSE の場合、ペインはシリアル化時に非表示になり、復元時には非表示にする必要があります。

## <a name="cbasepanehideinprintpreviewmode"></a><a name="hideinprintpreviewmode"></a>ウィンドウ::非表示印刷プレビューモード

印刷プレビューでペインを非表示にするかどうかを指定します。

```
virtual BOOL HideInPrintPreviewMode() const;
```

### <a name="return-value"></a>戻り値

ペインが印刷プレビューに表示されない場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

基本ウィンドウは印刷プレビューに表示されません。 したがって、このメソッドは常に TRUE を返します。

## <a name="cbasepaneinsertpane"></a><a name="insertpane"></a>CBase ペイン::挿入ペイン

ドッキング マネージャーに指定されたペインを登録します。

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>パラメーター

*コントロールバー*<br/>
[in]挿入するペインへのポインター。

*pターゲット*<br/>
[in]隣接するペインへのポインター。

*bアフター*<br/>
[in]TRUE の場合は *、p コントロール バー*が*pTarget*の後に挿入されます。 FALSE の場合 *、p コントロール バー*は*pTarget*の前に挿入されます。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE、それ以外の場合は FALSE。

## <a name="cbasepaneisaccessibilitycompatible"></a><a name="isaccessibilitycompatible"></a>ウィンドウ::Is アクセシビリティ互換

ペインがアクティブなアクセシビリティをサポートするかどうかを指定します。

```
virtual BOOL IsAccessibilityCompatible();
```

### <a name="return-value"></a>戻り値

ペインがアクティブなアクセシビリティをサポートする場合は TRUE。それ以外の場合は FALSE。

## <a name="cbasepaneisautohidemode"></a><a name="isautohidemode"></a>CBase ペイン::IsAutoHideモード

ペインが自動非表示モードかどうかを判断します。

```
virtual BOOL IsAutoHideMode() const;
```

### <a name="return-value"></a>戻り値

ペインが自動非表示モードの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ベース ペインは自動的に非表示にできません。 このメソッドは常に FALSE を返します。

## <a name="cbasepaneisdialogcontrol"></a><a name="isdialogcontrol"></a>ウィンドウ::IsDialog コントロール

ペインがダイアログ ボックス コントロールであるかどうかを指定します。

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>戻り値

ペインがダイアログ ボックス コントロールの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを使用して、すべてのペインのレイアウトの一貫性を確保します。

## <a name="cbasepaneisdocked"></a><a name="isdocked"></a>Cベースペイン::IsDocked

ペインがドッキングされているかどうかを判断します。

```
virtual BOOL IsDocked() const;
```

### <a name="return-value"></a>戻り値

ペインの親がミニフレームでない場合、またはペインが別のペインと共にミニフレームにフローティングされている場合は TRUE。それ以外の場合は FALSE。

## <a name="cbasepaneisfloating"></a><a name="isfloating"></a>Cベースペイン::イズフローティング

ペインがフローティング状態かどうかを判断します。

```
virtual BOOL IsFloating() const;
```

### <a name="return-value"></a>戻り値

ペインがフローティング状態の場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは[、CBasePane::IsDocked](#isdocked)の反対の値を返します。

## <a name="cbasepaneishorizontal"></a><a name="ishorizontal"></a>Cベースペイン::イス水平

ペインが水平方向にドッキングされているかどうかを判断します。

```
virtual BOOL IsHorizontal() const;
```

### <a name="return-value"></a>戻り値

ペインが水平方向にドッキングされている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

既定の実装では、現在のドッキング位置をチェックCBRS_ORIENT_HORZ。

## <a name="cbasepaneisinfloatingmultipaneframewnd"></a><a name="isinfloatingmultipaneframewnd"></a>ウィンドウ::イインフローティングマルチペインフレームオーニング

ペインがマルチペイン フレーム ウィンドウ[(CMultiPaneFrameWnd クラス](../../mfc/reference/cmultipaneframewnd-class.md)) 内にあるかどうかを指定します。

```
virtual BOOL IsInFloatingMultiPaneFrameWnd() const;
```

### <a name="return-value"></a>戻り値

ペインが複数枠のフレーム ウィンドウにある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

マルチペイン フレーム ウィンドウにフローティングできるペインのみ。 したがって、`CBasePane::IsInFloatingMultiPaneFrameWnd`常に FALSE を返します。

## <a name="cbasepaneismditabbed"></a><a name="ismditabbed"></a>Cベースペイン::イスムディタブベド

ウィンドウがタブ付きドキュメントとして MDI 子ウィンドウに追加されているかどうかを判断します。

```
virtual BOOL IsMDITabbed() const;
```

### <a name="return-value"></a>戻り値

ペインがタブ付きドキュメントとして MDI 子ウィンドウに追加された場合は TRUE。それ以外の場合は FALSE。

## <a name="cbasepaneispanevisible"></a><a name="ispanevisible"></a>Cベースペイン::イズペインビジブル

ペインにWS_VISIBLEフラグを設定するかどうかを指定します。

```
BOOL IsPaneVisible() const;
```

### <a name="return-value"></a>戻り値

WS_VISIBLEが設定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

[ウィンドウの表示設定を決定するには、CBasePane::IsVisible](#isvisible)を使用します。

## <a name="cbasepaneispointneardocksite"></a><a name="ispointneardocksite"></a>Cベースペイン::イスポイントニアドックサイト

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
[アウト]ポイントの近くにあるエッジを指定します。 指定できる値は、CBRS_ALIGN_LEFT、CBRS_ALIGN_RIGHT、CBRS_ALIGN_TOP、およびCBRS_ALIGN_BOTTOM

*ボターエッジ*<br/>
[アウト]ポイントがドッキング サイトの外側の境界付近にある場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ポイントがドッキング サイトの近くにある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ドッキング マネージャーで設定されている感度内にある場合、ポイントはドッキング サイトの近くにあります。 既定の感度は 15 ピクセルです。

## <a name="cbasepaneisresizable"></a><a name="isresizable"></a>Cベースペイン::イズリジブル

ペインのサイズを変更できるかどうかを決定します。

```
virtual BOOL IsResizable() const;
```

### <a name="return-value"></a>戻り値

ユーザーがペインのサイズを変更できる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

[CDockablePane クラスのペイン](../../mfc/reference/cdockablepane-class.md)のサイズを変更できます。

ステータス バー ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) とドッキング バー ( [CDockSite クラス](../../mfc/reference/cdocksite-class.md)) のサイズを変更することはできません。

## <a name="cbasepaneisrestoredfromregistry"></a><a name="isrestoredfromregistry"></a>次のレジストリを使用します。

ペインをレジストリから復元するかどうかを決定します。

```
virtual BOOL IsRestoredFromRegistry() const;
```

### <a name="return-value"></a>戻り値

ペインがレジストリから復元される場合は TRUE。それ以外の場合は FALSE。

## <a name="cbasepaneistabbed"></a><a name="istabbed"></a>Cベースペイン::イタブベド

タブ付きウィンドウのタブ コントロールにペインが挿入されているかどうかを判断します。

```
virtual BOOL IsTabbed() const;
```

### <a name="return-value"></a>戻り値

コントロール バーがタブ付きウィンドウのタブに挿入される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、直接の親へのポインターを取得し、親のランタイム クラスが[CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)かどうかを判断します。

## <a name="cbasepaneisvisible"></a><a name="isvisible"></a>Cベースペイン::イズビジブル

ペインが表示されているかどうかを判断します。

```
virtual BOOL IsVisible() const;
```

### <a name="return-value"></a>戻り値

ペインが表示されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ペインの表示/非表示を決定するために使います。 `::IsWindowVisible` は使用しないでください。

ペインがタブ付きでない場合[(「CBasePane::IsTabbed」](#istabbed)を参照)、このメソッドはWS_VISIBLEスタイルをチェックします。 ペインがタブ付きの場合、このメソッドは親タブ付きウィンドウの表示を確認します。 親ウィンドウが表示されている場合、関数は[CMFCBaseTabCtrl::IsTabVisible](../../mfc/reference/cmfcbasetabctrl-class.md#istabvisible)を使用してペイン タブの可視性をチェックします。

## <a name="cbasepaneloadstate"></a><a name="loadstate"></a>ウィンドウ::ロードステート

レジストリからペインの状態を読み込みます。

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName=NULL,
    int nIndex=-1,
    UINT uiID=(UINT)-1);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]プロファイル名。

*nIndex*<br/>
[in]プロファイル インデックス。

*Uiid*<br/>
[in]ペイン ID。

### <a name="return-value"></a>戻り値

ペインの状態が正常に読み込まれた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを呼び出して、レジストリからペイン状態を読み込みます。 派生クラスでオーバーライドして[、CBasePane](#savestate)によって保存された追加情報を読み込みます。

## <a name="cbasepanemovewindow"></a><a name="movewindow"></a>ウィンドウの移動

ペインを移動します。

```
virtual HDWP MoveWindow(
    CRect& rect,
    BOOL bRepaint = TRUE,
    HDWP hdwp = NULL);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]ペインの新しい場所とサイズを指定する四角形。

*brepaint*<br/>
[in]TRUE の場合、ペインは再描画されます。 FALSE の場合、ペインは再描画されません。

*hdwp*<br/>
[in]遅延ウィンドウ位置構造体へのハンドル。

### <a name="return-value"></a>戻り値

遅延ウィンドウ位置構造体へのハンドル、または NULL。

### <a name="remarks"></a>解説

*hdwp*パラメーターとして NULL を渡すと、このメソッドはウィンドウを通常どおりに移動します。 ハンドルを渡すと、このメソッドは遅延ウィンドウ移動を実行します。 ハンドルを取得するには[、BeginDeferWindowPos](/windows/win32/api/winuser/nf-winuser-begindeferwindowpos)を呼び出すか、このメソッドへの以前の呼び出しの戻り値を格納します。

## <a name="cbasepaneonafterchangeparent"></a><a name="onafterchangeparent"></a>ウィンドウ::オンアフターチェンジペアレント

ペインの親が変更された後に、フレームワークによって呼び出されます。

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]前の親へのポインター。

### <a name="remarks"></a>解説

フレームワークは、通常、ドッキング操作またはフローティング操作が原因で、ペインの親が変更された後にこのメソッドを呼び出します。

既定の実装では、何も行われません。

## <a name="cbasepaneonbeforechangeparent"></a><a name="onbeforechangeparent"></a>Cベースペイン::オン・オン・チェンジチェンジ・ペアレント

ペインが親ウィンドウを変更する直前に、フレームワークによって呼び出されます。

```
virtual void OnBeforeChangeParent(
    CWnd* pWndNewParent,
    BOOL bDelay=FALSE);
```

### <a name="parameters"></a>パラメーター

*新しい親*<br/>
[in]新しい親ウィンドウへのポインター。

*bディレイ*<br/>
[in]レイアウト調整を遅延させるかどうかを指定します。

### <a name="remarks"></a>解説

フレームワークは、通常、ドッキング、フローティング、または自動非表示操作のために、ペインの親が変更される直前にこのメソッドを呼び出します。

既定の実装では、何も行われません。

## <a name="cbasepaneondrawcaption"></a><a name="ondrawcaption"></a>ウィンドウ::オンドローキャプション

キャプションが描画されるときに、フレームワークはこのメソッドを呼び出します。

```
virtual void OnDrawCaption();
```

### <a name="remarks"></a>解説

このメソッドには、クラスの`CBasePane`機能はありません。

## <a name="cbasepaneonmovepanedivider"></a><a name="onmovepanedivider"></a>Cベースペイン::オンムーブペインディバイダー

このメソッドは現在使用されていません。

```
virtual void OnMovePaneDivider(CPaneDivider* /* unused */);
```

### <a name="parameters"></a>パラメーター

*未使用*<br/>
[in]使用されていません。

## <a name="cbasepaneonpanecontextmenu"></a><a name="onpanecontextmenu"></a>C ベースペイン::オンペインコンテキストメニュー

ペインの一覧を含むメニューを構築するときに、フレームワークによって呼び出されます。

```
virtual void OnPaneContextMenu(
    CWnd* pParentFrame,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
[in]親フレームへのポインター。

*ポイント*<br/>
[in]ショートカット メニューの場所を指定します。

### <a name="remarks"></a>解説

`OnPaneContextMenu`現在のフレーム ウィンドウに属するペインの一覧を保持するドッキング マネージャーを呼び出します。 このメソッドは、ペインの名前をショートカット メニューに追加して表示します。 メニューのコマンドは、個々のペインを表示または非表示にします。

この動作をカスタマイズするには、このメソッドをオーバーライドします。

## <a name="cbasepaneonremovefromminiframe"></a><a name="onremovefromminiframe"></a>Cベースペイン::オン除去ミニフレーム

ペインが親ミニ フレーム ウィンドウから削除されたときに、フレームワークによって呼び出されます。

```
virtual void OnRemoveFromMiniFrame(CPaneFrameWnd* pMiniFrame);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
[in]ペインが削除されるミニフレーム ウィンドウへのポインター。

### <a name="remarks"></a>解説

フレームワークは、ペインが親ミニフレーム ウィンドウから削除されたときにこのメソッドを呼び出します (ドッキングの結果など)。

既定の実装では、何も行われません。

## <a name="cbasepaneonsetaccdata"></a><a name="onsetaccdata"></a>Cベースペイン::オンセットアクデータ

`CBasePane`このメソッドは使用しません。

```
virtual BOOL OnSetAccData(long lVal);
```

### <a name="parameters"></a>パラメーター

*lヴァル*<br/>
[in]使用されていません。

### <a name="return-value"></a>戻り値

このメソッドは常に TRUE を返します。

### <a name="remarks"></a>解説

## <a name="cbasepanepanefrompoint"></a><a name="panefrompoint"></a>ソースペイン::Pアネフロトポイント

指定したポイントを含むペインを返します。

```
CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar = false,
    CRuntimeClass* pRTCBarType = NULL) const;
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]チェックする点を画面座標で指定します。

*n感度*<br/>
[in]検索領域をこの量だけ増やします。 指定したポイントが増加した領域に入ると、ペインは検索条件を満たします。

*をクリックします。*<br/>
[in]n感度パラメータを無視する*場合は*TRUE。それ以外の場合は FALSE。

*タイプを変更します。*<br/>
[in]NULL でない場合、メソッドは指定された種類のペインのみを検索します。

### <a name="return-value"></a>戻り値

指定`CBasePane`したポイントを含む派生オブジェクト。

## <a name="cbasepanerecalclayout"></a><a name="recalclayout"></a>Cベースペイン::リカルクレイアウト

`CBasePane`このメソッドは使用しません。

```
virtual void RecalcLayout();
```

## <a name="cbasepaneremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>ウィンドウ::ウィンドウから削除します。

ペインの登録を解除し、ドッキング マネージャーのリストから削除します。

```cpp
void RemovePaneFromDockManager(
    CBasePane* pBar,
    BOOL bDestroy = TRUE,
    BOOL bAdjustLayout = FALSE,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]削除するペインへのポインター。

*bデストロイ*<br/>
[in]TRUE の場合、削除されたペインは破棄されます。

*レイアウトを調整する*<br/>
[in]TRUE の場合は、ドッキング レイアウトをすぐに調整します。

*b 自動非表示*<br/>
[in]TRUE の場合、ドッキング レイアウトは自動非表示バーのリストに関連付けられています。 FALSE の場合、ドッキング レイアウトは通常のペインのリストに関連付けられています。

*交換用*<br/>
[in]削除されたペインを置き換えるペインへのポインター。

## <a name="cbasepanesavestate"></a><a name="savestate"></a>ウィンドウ::セーブステート

レジストリにペインの状態を保存します。

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName=NULL,
    int nIndex=-1,
    UINT uiID=(UINT)-1);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]プロファイル名。

*nIndex*<br/>
[in]プロファイル インデックス。

*Uiid*<br/>
[in]ペイン ID。

### <a name="return-value"></a>戻り値

状態が正常に保存された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークは、ペインの状態をレジストリに保存するときに、このメソッドを呼び出します。 派生`SaveState`クラスでオーバーライドして、追加情報を格納します。

## <a name="cbasepaneselectdefaultfont"></a><a name="selectdefaultfont"></a>ウィンドウ::デフォルトフォントの選択

指定したデバイス コンテキストの既定のフォントを選択します。

```
CFont* SelectDefaultFont(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキスト。

### <a name="return-value"></a>戻り値

既定の[CFont クラス](../../mfc/reference/cfont-class.md)オブジェクトへのポインター。

## <a name="cbasepanesetcontrolbarstyle"></a><a name="setcontrolbarstyle"></a>ウィンドウ::コントロールバースタイルを設定します。

コントロール バーのスタイルを設定します。

```
virtual void SetControlBarStyle(DWORD dwNewStyle);
```

### <a name="parameters"></a>パラメーター

*ドウニュースタイル*<br/>
[in]次の値のビットごとの OR の組み合わせ。

|Style|説明|
|-----------|-----------------|
|AFX_CBRS_FLOAT|コントロール バーをフロートします。|
|AFX_CBRS_AUTOHIDE|自動非表示モードを有効にします。|
|AFX_CBRS_RESIZE|コントロール バーのサイズ変更を有効にします。 このフラグを設定すると、コントロール バーをドッキング可能なペインに配置できます。|
|AFX_CBRS_CLOSE|コントロール バーの非表示を有効にします。|

## <a name="cbasepanesetdockingmode"></a><a name="setdockingmode"></a>Cベースペイン::セットドッキングモード

ペインのドッキング モードを設定します。

```cpp
void SetDockingMode(AFX_DOCK_TYPE dockModeNew);
```

### <a name="parameters"></a>パラメーター

*ドックモード新しい*<br/>
[in]ペインの新しいドッキング モードを指定します。

### <a name="remarks"></a>解説

フレームワークは、標準モードと即時ドッキングモードの 2 つをサポートします。

標準ドッキング モードでは、ペインとミニフレーム ウィンドウはドラッグ四角形を使用して移動されます。 即時ドッキング モードでは、コントロール バーとミニフレーム ウィンドウは、コンテキストと一緒に直ちに移動します。

最初は、ドッキング モードは[CDockingManager::m_dockModeGlobal](../../mfc/reference/cdockingmanager-class.md#m_dockmodeglobal)によってグローバルに定義されます。 このメソッドを使用して、各ペインのドッキング モードを`SetDockingMode`個別に設定できます。

## <a name="cbasepanesetpanealignment"></a><a name="setpanealignment"></a>ウィンドウスペイン::セットペイン配置

ペインの配置を設定します。

```
virtual void SetPaneAlignment(DWORD dwAlignment);
```

### <a name="parameters"></a>パラメーター

*dw配置*<br/>
[in]新しい配置を指定します。

### <a name="remarks"></a>解説

通常、フレームワークは、ペインがメイン フレームの一方の側から別の側にドッキングされている場合に、このメソッドを呼び出します。

次の表は *、dwAlignment*の値を示しています。

|値|Alignment|
|-----------|---------------|
|CBRS_ALIGN_LEFT|左揃え。|
|CBRS_ALIGN_RIGHT|右揃え。|
|CBRS_ALIGN_TOP|上部の配置。|
|CBRS_ALIGN_BOTTOM|下部の配置。|

## <a name="cbasepanesetpanestyle"></a><a name="setpanestyle"></a>Cベースペイン::セットペインスタイル

ペインのスタイルを設定します。

```
virtual void SetPaneStyle(DWORD dwNewStyle);
```

### <a name="parameters"></a>パラメーター

*ドウニュースタイル*<br/>
[in]設定する新しいスタイルを指定します。

### <a name="remarks"></a>解説

このメソッドを使用して、afxres.h で定義されているCBRS_スタイルのいずれかを設定できます。 ペイン スタイルとペイン配置は一緒に格納されるため、新しいスタイルを現在の配置と組み合わせて設定します。

`pPane->SetPaneStyle (pPane->GetCurrentAlignment() | CBRS_TOOLTIPS);`

## <a name="cbasepanesetwindowpos"></a><a name="setwindowpos"></a>ウィンドウペイン::セットウィンドウポス

ペインのサイズ、位置、および Z オーダーを変更します。

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

*後に挿入します。*<br/>
[in]この`CWnd`オブジェクトの`CWnd`前に来るオブジェクトを Z オーダーで識別します。 詳細については[、「CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)」を参照してください。

*x*<br/>
[in]ウィンドウの左側の位置を指定します。

*Y*<br/>
[in]ウィンドウの上端の位置を指定します。

*Cx*<br/>
[in]ウィンドウの幅を指定します。

*Cy*<br/>
[in]ウィンドウの高さを指定します。

*Nflags*<br/>
[in]サイズと位置のオプションを指定します。 詳細については[、「CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)」を参照してください。

*hdwp*<br/>
[in]1 つ以上のウィンドウのサイズと位置情報を含む構造体へのハンドル。

### <a name="return-value"></a>戻り値

更新された遅延ウィンドウ位置構造体へのハンドル、または NULL。

### <a name="remarks"></a>解説

*場合は、NULL*の後、このメソッドは[、CWnd::SetWindowPos](../../mfc/reference/cwnd-class.md#setwindowpos)を呼び出します。 *場合は、この*メソッドを呼び出します`DeferWindowPos`。

## <a name="cbasepaneshowpane"></a><a name="showpane"></a>Cベースペイン::ショーペイン

ウィンドウの表示/非表示を切り替えます。

```
virtual void ShowPane(
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]ペインを表示 (TRUE) または非表示 (FALSE) にするかどうかを指定します。

*bディレイ*<br/>
[in]TRUE の場合、ドッキング レイアウトの再計算が遅延します。

*bアクティブ化*<br/>
[in]TRUE の場合、ペインは表示されるときにアクティブになります。

### <a name="remarks"></a>解説

このメソッドは、ペインの表示と非表示を切り替えます。 このメソッドは、関連`ShowWindow`するドッキング マネージャーにペインの表示の変更を通知するため、このメソッドではなく使用します。

[CBasePane を使用::IsVisible](#isvisible)ペインの現在の可視性を決定します。

## <a name="cbasepanestretchpane"></a><a name="stretchpane"></a>Cベースペイン::ストレッチペイン

垂直または水平方向にウィンドウを拡大します。

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>パラメーター

*nレングス*<br/>
[in]ペインを拡大する長さ。

*bVert*<br/>
[in]TRUE の場合は、ペインを垂直方向に拡大します。 FALSE の場合は、ペインを水平方向に伸ばします。

### <a name="return-value"></a>戻り値

拡大されたペインのサイズ。

## <a name="cbasepaneundockpane"></a><a name="undockpane"></a>CBase ペイン::ドッキング解除ペイン

ドッキング サイト、既定のスライダー、または現在ドッキングされているミニフレーム ウィンドウからペインを削除します。

```
virtual void UndockPane(BOOL bDelay=FALSE);
```

### <a name="parameters"></a>パラメーター

*bディレイ*<br/>
TRUE の場合、ドッキング レイアウトはすぐに再計算されません。

### <a name="remarks"></a>解説

ペインの状態を操作するか、ドッキング レイアウトからペインを除外します。

このウィンドウを引き続き使用する場合は、このメソッドを呼び出す前に[CBasePane::DockPane](#dockpane)または[CBasePane::FloatPane のいずれかを](#floatpane)呼び出します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CPane](../../mfc/reference/cbasepane-class.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)
