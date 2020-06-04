---
title: CMDIChildWndEx クラス
ms.date: 10/18/2018
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
ms.openlocfilehash: cdc82ef48bacfe4d5b8d90222e7055c5fbe8b4a1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754559"
---
# <a name="cmdichildwndex-class"></a>CMDIChildWndEx クラス

この`CMDIChildWndEx`クラスは、Windows マルチ ドキュメント インターフェイス (MDI) 子ウィンドウの機能を提供します。 これは、[クラス CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)の機能を拡張します。 ある特定の MFC クラスを MDI アプリケーションで使用するときは、フレームワークにこのクラスが必要です。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMDIChildWndEx : public CMDIChildWnd
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をアクティブにします。](#activatetoplevelframe)|アプリケーションをタスク バー タブからアクティブにする必要があるときに、最上位のフレームをアクティブにするために、フレームワークによって内部的に呼び出されます。|
|`CMDIChildWndEx::AddDockSite`|このメソッドは使用も実装もされません。|
|[次の操作を行います。](#addpane)|ペインを追加します。|
|[次のコマンドを使用します。](#addtabbedpane)|タブ付きペインを追加します。|
|[コマンドリングペインドエクスックス::アジャスタッキングレイアウト](#adjustdockinglayout)|ドッキング レイアウトを調整します。|
|[ボミチャイルドンデックス::カンショーオンムディタブ](#canshowonmditabs)||
|[コマンドイチャイルドンデックス::缶ショーオンタスクバータブ](#canshowontaskbartabs)|この MDI 子を Windows 7 のタスク バー タブに表示できるかどうかをフレームワークに通知します。|
|[ウィンドウズ・デックス::カンショーオンウィンドウズリスト](#canshowonwindowslist)|MDI 子ウィンドウ名が[CMFCWindowsManagerDialog クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)ダイアログ ボックスに表示できる場合は TRUE を返します。 それ以外の場合は、FALSE を返します。|
|`CMDIChildWndEx::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって呼び出されます。|
|[ボクティチャイルドンデックス::Dオックペイン](#dockpane)|ペインをドッキングします。|
|[ボミチャイルドンデックス::Dオックパネレフト](#dockpaneleftof)|ウィンドウを別のウィンドウの左側にドッキングします。|
|[コミチャイルドンデックス::自動ハイドペインを有効にする](#enableautohidepanes)|ウィンドウの指定した辺にペインがドッキングされている場合、ペインの自動非表示モードを有効にします。|
|[ドッキングを有効にする](#enabledocking)|メイン フレームへの子ウィンドウのドッキングを有効にします。|
|[CMDIChildWndEx::タスクバーサムネールクリップレックを有効にします。](#enabletaskbarthumbnailcliprect)|ウィンドウのクライアント領域の一部を、そのウィンドウのサムネイルとしてタスク バーに表示する自動選択を有効または無効にします。|
|[コマンドリングマネージャー::取得](#getdockingmanager)||
|[ファイル名を取得します。](#getdocumentname)|MDI 子ウィンドウに表示されるドキュメントの名前を返します。|
|[コミチャイルドンデックス::ゲットフレームアイコン](#getframeicon)|MDI 子ウィンドウ アイコンを取得するために、フレームワークによって呼び出されます。|
|[をクリックします。](#getframetext)|MDI 子ウィンドウのテキストを取得するために、フレームワークによって呼び出されます。|
|[ド・ジュ・ド・エックス::ゲット・ペイン](#getpane)|指定したコントロール ID でペインを検索します。|
|[ソースグループを取得します。](#getrelatedtabgroup)||
|[コマンドーニチャイルドンデックス::ゲットタブベドペイン](#gettabbedpane)|タブ付きドキュメントに変換された埋め込みドッキング ペインへのポインターを返します。|
|[を使用します。](#gettabproxywnd)|実際に Windows 7 タスク バー タブに登録されているタブ プロキシ ウィンドウを返します。|
|[コマンドイチャイルドンデックス:::タスクバープレビューウンド](#gettaskbarpreviewwnd)|Windows 7 のタスク バー タブのサムネイルに表示される子ウィンドウ (通常はビューまたは分割ウィンドウ) を取得する必要がある場合に、フレームワークによって呼び出されます。|
|[CMDIChildWndEx:::タスクバーサムネールクリップレックを取得します](#gettaskbarthumbnailcliprect)|ウィンドウのサムネイルとしてタスク バーに表示するウィンドウのクライアント領域の一部を選択する必要がある場合に、フレームワークによって呼び出されます。|
|`CMDIChildWndEx::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって呼び出されます。|
|[ツールヒントテキスト::ツールボタン](#gettoolbarbuttontooltiptext)|ツール バー ボタンのツールヒントを取得するために、フレームワークによって呼び出されます。|
|[ソース::ペインの挿入](#insertpane)|ドッキング マネージャーに指定されたペインを登録します。|
|[コミチャイルドンデックス::イニシブアイコニックビットマップ](#invalidateiconicbitmaps)|MDI 子のアイコンビットマップ表現を無効にします。|
|[ア・アイ・チャイルド・ウンド・エクスックス::イスポイントニアドックサイト](#ispointneardocksite)|指定したポイントがドッキング サイトの近くにあるかどうかを判断します。|
|[デ・イ・アイル・オン・デックス](#isreadonly)|子ウィンドウに表示されるドキュメントが読み取り専用の場合は TRUE を返します。 それ以外の場合は、FALSE を返します。|
|[タスクバータブ::IsRegisteredとタスクバータブ](#isregisteredwithtaskbartabs)|MDI 子が Windows 7 タスク バー タブに正常に登録された場合は TRUE を返します。|
|[次のコマンド::イタブドペイン](#istabbedpane)|MDI 子ウィンドウにドッキング ペインが含まれている場合は TRUE を返します。 それ以外の場合は、FALSE を返します。|
|[サポートをサポートします。](#istaskbartabssupportenabled)|MDI 子が Windows 7 のタスク バー タブに表示できるかどうかを示します。|
|[CMDIChildWndEx::Isタスクバーサムネイルクリップレック有効](#istaskbarthumbnailcliprectenabled)|ウィンドウのサムネイルをタスク バーに表示するウィンドウのクライアント領域の一部を自動的に選択するかどうかを示します。|
|[ア・ミジド・ウニ・エックス:m_dwDefaultTaskbarTabPropertyFlags](#m_dwdefaulttaskbartabpropertyflags)|Windows 7 のタスク バー タブでタブ (MDI 子) が登録されているときに、フレームワークによって SetTaskbarTabProperties メソッドに渡されるフラグの組み合わせ。 既定の組み合わせは、&#124;STPF_USEAPPPEEKWHENACTIVESTPF_USEAPPTHUMBNAILWHENACTIVE。|
|[コミチャイルドンデックス::アイコン化ライブプレビュービットマップ](#ongeticoniclivepreviewbitmap)|MDI 子のライブ プレビュー用のビットマップを取得する必要がある場合に、フレームワークによって呼び出されます。|
|[コミチャイルドンデックス::オンゲットアイコニックサムネイル](#ongeticonicthumbnail)|MDI 子のアイコンサムネイルのビットマップを取得する必要がある場合に、フレームワークによって呼び出されます。|
|[デ・ア・オン・ムーブ・ミニフレーム](#onmoveminiframe)|ミニフレーム ウィンドウを移動するために、フレームワークによって呼び出されます。|
|[コマンドイチャイルドウンドEx::オンプレスタスクバーThmbnail閉じるボタン](#onpresstaskbarthmbnailclosebutton)|ユーザーがタスク バー タブのサムネイルの閉じるボタンを押したときに、フレームワークによって呼び出されます。|
|[を設定します。](#onsetpreviewmode)|印刷プレビュー モードを開始または終了するために、フレームワークによって呼び出されます。|
|[コマンドールタブサムネイルアクティブ](#ontaskbartabthumbnailactivate)|タスク バー タブのサムネイルがメッセージを処理する必要がある場合に、フレームワークによって呼び出WM_ACTIVATE。|
|[コマンドイチャイルドンデックス::タスクバータブサムネイルマウスアクティブ](#ontaskbartabthumbnailmouseactivate)|タスク バー タブのサムネイルがメッセージを処理する必要がある場合に、フレームワークによって呼び出WM_MOUSEACTIVATE。|
|[コマンドールタブサムネイルストレッチ::タスクバータブサムネイルストレッチ](#ontaskbartabthumbnailstretch)|MDI 子の Windows 7 タスク バー タブのサムネイル プレビュー用のビットマップを拡大する必要がある場合に、フレームワークによって呼び出されます。|
|[次の表に従って、次の操作を行います。](#onupdateframetitle)|フレーム タイトルを更新するために、フレームワークによって呼び出されます。 ( `CMDIChildWnd::OnUpdateFrameTitle`をオーバーライドします)。|
|[アナン・フロルポイント::Pアンネ](#panefrompoint)|指定したポイントを含むペインを返します。|
|`CMDIChildWndEx::PreTranslateMessage`|クラス[CWinApp](../../mfc/reference/cwinapp-class.md)がウィンドウ メッセージを変換するために使用し、[変換メッセージ](/windows/win32/api/winuser/nf-winuser-translatemessage)および[ディスパッチ メッセージ](/windows/win32/api/winuser/nf-winuser-dispatchmessage)Windows 関数にディスパッチします。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[コミチャイルドンデックス::レカルクレイアウト](#recalclayout)|ウィンドウのレイアウトを再計算します。|
|[コマンド・タスク・タブを登録する](#registertaskbartab)|Windows 7 タスク バー タブを使用して MDI 子を登録します。|
|[次のコマンドを使用します。](#removepanefromdockmanager)|ドッキング マネージャーからペインを削除します。|
|[ソース:::セット関連タブグループ](#setrelatedtabgroup)||
|[コマンドバータブアクティブを設定します。](#settaskbartabactive)|対応する Windows 7 タスク バー タブをアクティブにします。|
|[コマンドバータブオーダー::タスクバータブオーダーの設定](#settaskbartaborder)|Windows 7 タスク バー タブで指定したウィンドウの前に MDI 子を挿入します。|
|[CMDIChildWndEx::SetTaskbarTabProperties](#settaskbartabproperties)|Windows 7 のタスクバー タブのプロパティを設定します。|
|[CMDIChildWndEx:::タスクバーサムネールクリップレックを設定します](#settaskbarthumbnailcliprect)|ウィンドウのクライアント領域の一部を選択してウィンドウのサムネイルとしてタスク バーに表示するように、クリッピング四角形を設定するために、フレームワークによって内部的に呼び出されます。|
|[コマンドウィンドウズエクスックス::ショーペイン](#showpane)||
|[コマンド・タスク・タブの登録解除](#unregistertaskbartab)|Windows 7 タスク バー タブから MDI 子を削除します。|
|[コミチャイルドウンドエクスックス::アップデートタスクバータブアイコン](#updatetaskbartabicon)|Windows 7 タスク バー タブ アイコンを更新します。|

## <a name="remarks"></a>解説

MDI アプリケーションの拡張ドッキング機能を利用するには`CMDIChildWndEx`[、CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)ではなく、アプリケーションの MDI 子ウィンドウ クラスを派生させます。

## <a name="example"></a>例

クラスを派生させる例を次に`CMDIChildWndEx`示します。 このコード スニペットは、[次のサンプルから](../../overview/visual-cpp-samples.md)来ています: MFC Visual Studio アプリケーション 。

[!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/cpp/cmdichildwndex-class_1.h)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)

[CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxMDIチャイルドウンドEx.h

## <a name="cmdichildwndexaddpane"></a><a name="addpane"></a>次の操作を行います。

ペインを追加します。

```
BOOL AddPane(
    CBasePane* pControlBar,
    BOOL bTail = TRUE);
```

### <a name="parameters"></a>パラメーター

*コントロールバー*<br/>
[in]ペインへのポインター。

*bTail*<br/>
[in]ドッキング マネージャーのペインの一覧の末尾にペインを追加する場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ペインがドッキング マネージャーに正常に登録された場合は TRUE。それ以外の場合は FALSE。

## <a name="cmdichildwndexaddtabbedpane"></a><a name="addtabbedpane"></a>次のコマンドを使用します。

タブ付きペインを追加します。

```cpp
void AddTabbedPane(CDockablePane* pControlBar);
```

### <a name="parameters"></a>パラメーター

*コントロールバー*<br/>
[in]ペインへのポインター。

## <a name="cmdichildwndexadjustdockinglayout"></a><a name="adjustdockinglayout"></a>コマンドリングペインドエクスックス::アジャスタッキングレイアウト

ドッキング レイアウトを調整します。

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>パラメーター

*hdwp*<br/>
[in]遅延ウィンドウ位置構造体へのハンドル。

## <a name="cmdichildwndexcanshowonmditabs"></a><a name="canshowonmditabs"></a>ボミチャイルドンデックス::カンショーオンムディタブ

```
virtual BOOL CanShowOnMDITabs();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmdichildwndexcanshowonwindowslist"></a><a name="canshowonwindowslist"></a>ウィンドウズ・デックス::カンショーオンウィンドウズリスト

MDI 子ウィンドウ名を[表示](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)できるかどうかを指定します。

```
virtual BOOL CanShowOnWindowsList();
```

### <a name="return-value"></a>戻り値

**ウィンドウ**が Windows ダイアログ ボックスに表示される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ウィンドウが**Windows**ダイアログ ボックスに表示されない場合は、派生クラスでこのメソッドをオーバーライドし、FALSE を返します。 この関数は`CMFCWindowsManagerDialog`から呼び出されます。

## <a name="cmdichildwndexdockpane"></a><a name="dockpane"></a>ボクティチャイルドンデックス::Dオックペイン

ペインをドッキングします。

```cpp
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
[in]ペインへのポインター。

*nドックバーID*<br/>
[in]ペインの ID。

*Lprect*<br/>
[in]四角形へのポインター。

### <a name="remarks"></a>解説

*lpRect*パラメーターは使用されません。

## <a name="cmdichildwndexdockpaneleftof"></a><a name="dockpaneleftof"></a>ボミチャイルドンデックス::Dオックパネレフト

ウィンドウを別のウィンドウの左側にドッキングします。

```
BOOL DockPaneLeftOf(
    CPane* pBar,
    CPane* pLeftOf);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
ドッキングするペインへのポインター。

*の*<br/>
参照ポイントとして機能するペインへのポインター。

### <a name="return-value"></a>戻り値

成功時は TRUE、失敗時は FALSE。

### <a name="remarks"></a>解説

このメソッドは *、pBar*で指定されたペインを受け取り *、pLeftOf*で指定されたペインの左側にドッキングします。

いくつかのペインを定義済みの順序でドッキングする場合は、このメソッドを呼び出します。

## <a name="cmdichildwndexenableautohidepanes"></a><a name="enableautohidepanes"></a>コミチャイルドンデックス::自動ハイドペインを有効にする

ウィンドウの指定した辺にペインがドッキングされている場合、ペインの自動非表示モードを有効にします。

```
BOOL EnableAutoHidePanes(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

*ドウドックスタイル*<br/>
[in]有効にするメイン フレーム ウィンドウの辺を指定します。 次のフラグの 1 つ以上を使用します。

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="cmdichildwndexenabledocking"></a><a name="enabledocking"></a>ドッキングを有効にする

メイン フレームへの子ウィンドウのドッキングを有効にします。

```
BOOL EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

*ドウドックスタイル*<br/>
[in]有効にするドッキングの配置を指定します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

メイン フレームへのドッキング配置を有効にします。 CBRS_ALIGN_フラグの組み合わせを渡すことができます (詳細については[、「CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)」を参照してください)。

## <a name="cmdichildwndexgetdockingmanager"></a><a name="getdockingmanager"></a>コマンドリングマネージャー::取得

```
CDockingManager* GetDockingManager();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmdichildwndexgetdocumentname"></a><a name="getdocumentname"></a>ファイル名を取得します。

MDI 子ウィンドウに表示されるドキュメントの名前を返します。

```
virtual LPCTSTR GetDocumentName(CObject** pObj);
```

### <a name="return-value"></a>戻り値

ドキュメントの名前を含む文字列へのポインター。

### <a name="remarks"></a>解説

ドキュメントは、MDI 子ウィンドウに表示される内容です。 通常、ウィンドウには、ファイルから読み込まれたデータまたはファイルに保存されたデータが表示されます。 したがって、ドキュメントの名前はファイルの名前になります。 の既定の`GetDocumentName`実装は、 から`CDocument::GetPathName`取得した文字列を返します。

ファイルから読み込まれていないドキュメントがウィンドウに表示される場合は、派生クラスでこのメソッドをオーバーライドし、一意のドキュメント識別子を返します。

`GetDocumentName`は、開いているすべてのドキュメントの状態を保存するときに、フレームワークによって呼び出されます。 返された文字列はレジストリに書き込まれます。

フレームワークが後で状態を復元する場合、ドキュメント名はレジストリから読み取られ[、CMDIFrameWndEx::CreateDocumentWindow](../../mfc/reference/cmdiframewndex-class.md#createdocumentwindow)に渡されます。 [CMDIFrameWndEx](../../mfc/reference/cmdiframewndex-class.md)-派生クラスでこのメソッドをオーバーライドし、この名前を持つドキュメントを作成または開き、この名前を持つファイルを読み取ります。 ドキュメントがファイルに基づいていない場合は、ドキュメント識別子自体に基づいてドキュメントを作成します。 ドキュメントを保存および復元する場合にのみ、上記の操作を行う必要があります。

### <a name="example"></a>例

`GetDocumentName` メソッドの使用例を次に示します。 このコード スニペットは、[次のサンプルから](../../overview/visual-cpp-samples.md)来ています: MFC Visual Studio アプリケーション 。

[!code-cpp[NVC_MFC_VisualStudioDemo#17](../../mfc/codesnippet/cpp/cmdichildwndex-class_2.cpp)]

## <a name="cmdichildwndexgetframeicon"></a><a name="getframeicon"></a>コミチャイルドンデックス::ゲットフレームアイコン

MDI 子ウィンドウのアイコンを取得するために、フレームワークによって呼び出されます。

```
virtual HICON GetFrameIcon() const;
```

### <a name="return-value"></a>戻り値

ウィンドウ アイコンへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、MDI 子フレーム ウィンドウを含む MDI タブに表示するアイコンを決定するために、フレームワークによって呼び出されます。

既定では、このメソッドはウィンドウ アイコンを返します。 この`GetFrameIcon`動作を`CMDIChildWndEx`カスタマイズするには、派生クラスでオーバーライドします。

## <a name="cmdichildwndexgetframetext"></a><a name="getframetext"></a>をクリックします。

MDI 子ウィンドウのテキストを取得するために、フレームワークによって呼び出されます。

```
virtual CString GetFrameText() const;
```

### <a name="return-value"></a>戻り値

フレーム ウィンドウのテキストを含む文字列。

### <a name="remarks"></a>解説

このメソッドは、MDI 子フレーム ウィンドウを含む MDI タブに表示するテキストを決定するために、フレームワークによって呼び出されます。

既定では、このメソッドはウィンドウ テキストを返します。 この`GetFrameText`動作を`CMDIChildWndEx`カスタマイズするには、派生クラスでオーバーライドします。

## <a name="cmdichildwndexgetpane"></a><a name="getpane"></a>ド・ジュ・ド・エックス::ゲット・ペイン

指定したコントロール ID でペインを検索します。

```
CBasePane* GetPane(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]検索するペインのコントロール ID。

### <a name="return-value"></a>戻り値

見つかった場合はペインへのポインター。

## <a name="cmdichildwndexgetrelatedtabgroup"></a><a name="getrelatedtabgroup"></a>ソースグループを取得します。

```
CMFCTabCtrl* GetRelatedTabGroup();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmdichildwndexgettabbedpane"></a><a name="gettabbedpane"></a>コマンドーニチャイルドンデックス::ゲットタブベドペイン

MDI タブ付きドキュメントのグループの一部であるドッキング ペインへのポインターを返します。

```
CDockablePane* GetTabbedPane() const;
```

### <a name="return-value"></a>戻り値

MDI タブ付きドキュメントのグループの一部であるドッキング ペインへのポインター。

## <a name="cmdichildwndexgettoolbarbuttontooltiptext"></a><a name="gettoolbarbuttontooltiptext"></a>ツールヒントテキスト::ツールボタン

ツール バー ボタンのツールヒントを取得するために、フレームワークによって呼び出されます。

```
virtual BOOL GetToolbarButtonToolTipText(
    CMFCToolBarButton*,
    CString&);
```

### <a name="return-value"></a>戻り値

ツールヒントが表示されている場合は TRUE。 既定の実装では FALSE が返されます。

### <a name="remarks"></a>解説

ツール バー ボタンのカスタム ツール ヒントを表示する場合は、このメソッドをオーバーライドします。

## <a name="cmdichildwndexinsertpane"></a><a name="insertpane"></a>ソース::ペインの挿入

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

## <a name="cmdichildwndexispointneardocksite"></a><a name="ispointneardocksite"></a>ア・アイ・チャイルド・ウンド・エクスックス::イスポイントニアドックサイト

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
[in]ポイントの近くにあるエッジを指定します。 指定できる値は、CBRS_ALIGN_LEFT、CBRS_ALIGN_RIGHT、CBRS_ALIGN_TOP、およびCBRS_ALIGN_BOTTOM

*ボターエッジ*<br/>
[in]ポイントがドッキング サイトの外側の境界付近にある場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

ポイントがドッキング サイトの近くにある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ドッキング マネージャーで設定されている感度内にある場合、ポイントはドッキング サイトの近くにあります。 既定の感度は 15 ピクセルです。

## <a name="cmdichildwndexisreadonly"></a><a name="isreadonly"></a>デ・イ・アイル・オン・デックス

子ウィンドウに表示される文書を読み取り専用にするかどうかを指定します。

```
virtual BOOL IsReadOnly();
```

### <a name="return-value"></a>戻り値

ドキュメントが読み取り専用の場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数は、読み取り専用ドキュメントの保存を禁止するために使用されます。

### <a name="example"></a>例

メソッドをオーバーライドする例を次に`IsReadOnly`示します。 このコード スニペットは、[次のサンプルから](../../overview/visual-cpp-samples.md)来ています: MFC Visual Studio アプリケーション 。

[!code-cpp[NVC_MFC_VisualStudioDemo#2](../../mfc/codesnippet/cpp/cmdichildwndex-class_3.cpp)]

## <a name="cmdichildwndexistabbedpane"></a><a name="istabbedpane"></a>次のコマンド::イタブドペイン

MDI 子ウィンドウにドッキング ペインが含まれるかどうかを指定します。

```
BOOL IsTabbedPane() const;
```

### <a name="return-value"></a>戻り値

MDI 子ウィンドウに、タブ付きドキュメントに変換されたドッキング ペインが含まれている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmdichildwndexonmoveminiframe"></a><a name="onmoveminiframe"></a>デ・ア・オン・ムーブ・ミニフレーム

ミニフレーム ウィンドウを移動するために、フレームワークによって呼び出されます。

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>パラメーター

*フレーム*<br/>
[in]ミニフレーム ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE、それ以外の場合は FALSE。

## <a name="cmdichildwndexonsetpreviewmode"></a><a name="onsetpreviewmode"></a>を設定します。

印刷プレビュー モードを開始または終了するために、フレームワークによって呼び出されます。

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>パラメーター

*bプレビュー*<br/>
[in]TRUE の場合は、印刷プレビュー モードを入力します。 FALSE の場合は、印刷プレビュー モードを終了します。

*pステート*<br/>
[in]印刷プレビュー状態構造体へのポインター。

## <a name="cmdichildwndexonupdateframetitle"></a><a name="onupdateframetitle"></a>次の表に従って、次の操作を行います。

フレーム タイトルを更新するために、フレームワークによって呼び出されます。

```
virtual void OnUpdateFrameTitle(BOOL bAddToTitle);
```

### <a name="parameters"></a>パラメーター

*タイトルを追加します。*<br/>
[in]TRUE の場合は、タイトルにドキュメント名を追加します。

## <a name="cmdichildwndexpanefrompoint"></a><a name="panefrompoint"></a>アナン・フロルポイント::Pアンネ

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

*ポイント*<br/>
[in]チェックする点を画面座標で指定します。

*n感度*<br/>
[in]検索領域をこの量だけ増やします。 指定したポイントが増加した領域に入った場合、ペインは検索条件を満たします。

*をクリックします。*<br/>
[in]n感度パラメータを無視する*場合は*TRUE。それ以外の場合は FALSE。

*タイプを変更します。*<br/>
[in]NULL でない場合、メソッドは指定された種類のペインのみを検索します。

*dw配置*<br/>
[in]指定したポイントにペインが見つかった場合、このパラメーターには、指定したポイントに最も近いペインの辺が含まれます。 詳細については、「解説」を参照してください。

### <a name="return-value"></a>戻り値

指定したポイントを`CBasePane`含む派生オブジェクトへのポインター。

### <a name="remarks"></a>解説

ランタイム クラスや可視性などの指定された条件に従って、ペインに指定したポイントが含まれているかどうかを調べます。

関数が返り、ペインが見つかった場合 *、dwAlignment*には指定した点の配置が含まれます。 たとえば、ポイントがペインの最上部に最も近い場合は *、dwAlignment*がCBRS_ALIGN_TOPに設定されます。

## <a name="cmdichildwndexrecalclayout"></a><a name="recalclayout"></a>コミチャイルドンデックス::レカルクレイアウト

ウィンドウのレイアウトを再計算します。

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*通知する*<br/>
[in]TRUE の場合、ウィンドウのアクティブなインプレース項目は、レイアウトの変更の通知を受け取ります。

## <a name="cmdichildwndexremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>次のコマンドを使用します。

ドッキング マネージャーからペインを削除します。

```cpp
void RemovePaneFromDockManager(
    CBasePane* pControlBar,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide,
    CBasePane* pBarReplacement);
```

### <a name="parameters"></a>パラメーター

*コントロールバー*<br/>
[in]削除するペインへのポインター。

*bデストロイ*<br/>
[in]TRUE の場合、削除されたペインは破棄されます。

*レイアウトを調整する*<br/>
[in]TRUE の場合は、ドッキング レイアウトをすぐに調整します。

*b 自動非表示*<br/>
[in]TRUE の場合、ドッキング レイアウトは自動非表示バーのリストに関連付けられています。 FALSE の場合、ドッキング レイアウトは通常のペインのリストに関連付けられています。

*交換用*<br/>
[in]削除されたペインを置き換えるペインへのポインター。

## <a name="cmdichildwndexsetrelatedtabgroup"></a><a name="setrelatedtabgroup"></a>ソース:::セット関連タブグループ

```cpp
void SetRelatedTabGroup(CMFCTabCtrl* p);
```

### <a name="parameters"></a>パラメーター

[in]*p*<br/>

### <a name="remarks"></a>解説

## <a name="cmdichildwndexshowpane"></a><a name="showpane"></a>コマンドウィンドウズエクスックス::ショーペイン

```cpp
void ShowPane(
    CBasePane* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

[in]*pバー*<br/>

[in]*bショー*<br/>

[in]*bディレイ*<br/>

[in]*bアクティブ化*<br/>

### <a name="remarks"></a>解説

## <a name="cmdichildwndexupdatetaskbartabicon"></a><a name="updatetaskbartabicon"></a>コミチャイルドウンドエクスックス::アップデートタスクバータブアイコン

Windows 7 タスク バー タブ アイコンを更新します。

```
virtual void UpdateTaskbarTabIcon(HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*Hicon*<br/>
Windows 7 タスク バー タブに表示するアイコンへのハンドル。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexunregistertaskbartab"></a><a name="unregistertaskbartab"></a>コマンド・タスク・タブの登録解除

Windows 7 タスク バー タブから MDI 子を削除します。

```cpp
void UnregisterTaskbarTab(BOOL bCheckRegisteredMDIChildCount = TRUE);
```

### <a name="parameters"></a>パラメーター

*登録されたMDIチャイルドカウントを確認します。*<br/>
この関数が MDI タブに登録されている MDI 子の数をチェックする必要があるかどうかを指定します。 この数値が 0 の場合、この関数は、アプリケーションのタスク バーのサムネイルからクリッピング四角形を削除します。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexsettaskbarthumbnailcliprect"></a><a name="settaskbarthumbnailcliprect"></a>CMDIChildWndEx:::タスクバーサムネールクリップレックを設定します

ウィンドウのクライアント領域の一部を選択して、ウィンドウのサムネイルとしてタスク バーに表示されるように、クリッピング四角形を設定するためにフレームワークによって呼び出されます。

```
virtual BOOL SetTaskbarThumbnailClipRect(CRect rect);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
新しいクリッピング四角形を指定します。 四角形が空または null の場合、クリッピングは削除されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexsettaskbartabproperties"></a><a name="settaskbartabproperties"></a>コマンドバータブプロパティ::タスクバータブプロパティ

Windows 7 のタスクバー タブのプロパティを設定します。

```cpp
void SetTaskbarTabProperties(DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
STPFLAG の値の組み合わせ。 詳細については[、「ITaskbarList4::SetTabProperties](/windows/win32/api/shobjidl_core/nf-shobjidl_core-itaskbarlist4-settabproperties)」を参照してください。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexsettaskbartaborder"></a><a name="settaskbartaborder"></a>コマンドバータブオーダー::タスクバータブオーダーの設定

Windows 7 のタスク バー タブで指定したウィンドウの前に MDI 子を挿入します。

```cpp
void SetTaskbarTabOrder(CMDIChildWndEx* pWndBefore = NULL);
```

### <a name="parameters"></a>パラメーター

*前に*<br/>
サムネイルが左に挿入される MDI 子ウィンドウへのポインター。 このウィンドウは、 を通`RegisterTaskbarTab`じて既に登録されている必要があります。 この値が NULL の場合、新しいサムネイルがリストの末尾に追加されます。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexsettaskbartabactive"></a><a name="settaskbartabactive"></a>コマンドバータブアクティブを設定します。

対応する Windows 7 タスク バー タブをアクティブにします。

```cpp
void SetTaskbarTabActive();
```

### <a name="remarks"></a>解説

## <a name="cmdichildwndexregistertaskbartab"></a><a name="registertaskbartab"></a>コマンド・タスク・タブを登録する

Windows 7 タスク バー タブを使用して MDI 子を登録します。

```
virtual void RegisterTaskbarTab(CMDIChildWndEx* pWndBefore = NULL);
```

### <a name="parameters"></a>パラメーター

*前に*<br/>
サムネイルが左に挿入される MDI 子ウィンドウへのポインター。 このウィンドウは、 を通`RegisterTaskbarTab`じて既に登録されている必要があります。 この値が NULL の場合、新しいサムネイルがリストの末尾に追加されます。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexontaskbartabthumbnailstretch"></a><a name="ontaskbartabthumbnailstretch"></a>コマンドールタブサムネイルストレッチ::タスクバータブサムネイルストレッチ

MDI 子の Windows 7 タスク バー タブのサムネイル プレビュー用にビットマップを拡大する必要がある場合に、フレームワークによって呼び出されます。

```
virtual BOOL OnTaskbarTabThumbnailStretch(
    HBITMAP hBmpDst,
    const CRect& rectDst,
    HBITMAP hBmpSrc,
    const CRect& rectSrc);
```

### <a name="parameters"></a>パラメーター

*hBmpDst*<br/>
コピー先のビットマップへのハンドル。

*レクトドスト*<br/>
目的の四角形を指定します。

*hBmpSrc*<br/>
ソース ビットマップへのハンドル。

*レクトスrc*<br/>
ソースの四角形を指定します。

### <a name="remarks"></a>解説

要件 : afxmdichildwndex.h

## <a name="cmdichildwndexontaskbartabthumbnailmouseactivate"></a><a name="ontaskbartabthumbnailmouseactivate"></a>コマンドイチャイルドンデックス::タスクバータブサムネイルマウスアクティブ

タスク バー タブのサムネイルがWM_MOUSEACTIVATE メッセージを処理する必要があるときに、フレームワークによって呼び出されます。

```
virtual int OnTaskbarTabThumbnailMouseActivate(
    CWnd* pDesktopWnd,
    UINT nHitTest,
    UINT message);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
アクティブにするウィンドウの最上位レベルの親ウィンドウへのポインターを指定します。 ポインターは一時的なポインターである可能性があり、格納しないでください。

*ヒットテスト*<br/>
ヒット テストの市外局番を指定します。 ヒット テストは、カーソルの位置を決定するテストです。

*message*<br/>
マウス メッセージ番号を指定します。

### <a name="remarks"></a>解説

既定の実装では、関連する MDI 子フレームがアクティブになります。

## <a name="cmdichildwndexontaskbartabthumbnailactivate"></a><a name="ontaskbartabthumbnailactivate"></a>コマンドールタブサムネイルアクティブ

タスク バー タブのサムネイルがWM_ACTIVATE メッセージを処理する必要があるときに、フレームワークによって呼び出されます。

```
virtual void OnTaskbarTabThumbnailActivate(
    UINT nState,
    CWnd* pWndOther,
    BOOL bMinimized);
```

### <a name="parameters"></a>パラメーター

*nステート*<br/>
が`CWnd`アクティブ化されているか、または非アクティブ化されるかを指定します。

*その他*<br/>
アクティブ化または`CWnd`非アクティブ化されているポインター。 ポインターは NULL にすることができ、一時的なポインターである場合もあります。

*b最小化*<br/>
アクティブ化または非アクティブ化の`CWnd`最小化状態を指定します。 TRUE の値は、ウィンドウが最小化されていることを示します。

### <a name="remarks"></a>解説

既定の実装では、関連する MDI 子フレームがアクティブになります。

## <a name="cmdichildwndexonpresstaskbarthmbnailclosebutton"></a><a name="onpresstaskbarthmbnailclosebutton"></a>コマンドイチャイルドウンドEx::オンプレスタスクバーThmbnail閉じるボタン

ユーザーがタスク バー タブのサムネイル上の閉じるボタンを押したときに、フレームワークによって呼び出されます。

```
virtual void OnPressTaskbarThmbnailCloseButton();
```

### <a name="remarks"></a>解説

## <a name="cmdichildwndexongeticonicthumbnail"></a><a name="ongeticonicthumbnail"></a>コミチャイルドンデックス::オンゲットアイコニックサムネイル

MDI 子のアイコンサムネイルのビットマップを取得する必要がある場合に、フレームワークによって呼び出されます。

```
virtual HBITMAP OnGetIconicThumbnail(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>パラメーター

*n幅*<br/>
必要なビットマップの幅を指定します。

*nHeight*<br/>
必要なビットマップの高さを指定します。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexongeticoniclivepreviewbitmap"></a><a name="ongeticoniclivepreviewbitmap"></a>コミチャイルドンデックス::アイコン化ライブプレビュービットマップ

MDI 子のライブ プレビュー用のビットマップを取得する必要がある場合に、フレームワークによって呼び出されます。

```
virtual HBITMAP OnGetIconicLivePreviewBitmap(
    BOOL bIsMDIChildActive,
    CPoint& ptLocation);
```

### <a name="parameters"></a>パラメーター

*ビスムディチャイルドアクティブ*<br/>
このパラメーターは、ビットマップが現在アクティブでメイン ウィンドウが最小化されていない MDI 子に対して要求された場合は TRUE です。 この場合のデフォルトの処理は、メインウィンドウのスナップショットを取得します。

*場所*<br/>
メイン (最上位) ウィンドウのクライアント座標内のビットマップの位置を指定します。 この点は、呼び出し先によって提供される必要があります。

### <a name="return-value"></a>戻り値

処理された場合は、有効な 32bpp ビットマップへのハンドルを返します。

### <a name="remarks"></a>解説

派生クラスでこのメソッドをオーバーライドし、MDI 子のライブ プレビュー用に有効な 32 bpp ビットマップを返します。 このメソッドは、Windows 7 のタスク バー タブに MDI 子が表示されている場合にのみ呼び出されます。 NULL を返す場合、MFC は既定のハンドラーを呼び`PrintClient`出`PrintWindow`し、 または を使用してビットマップを取得します。

## <a name="cmdichildwndexm_dwdefaulttaskbartabpropertyflags"></a><a name="m_dwdefaulttaskbartabpropertyflags"></a>ア・ミジド・ウニ・エックス:m_dwDefaultTaskbarTabPropertyFlags

Windows 7 のタスク バー タブでタブ`SetTaskbarTabProperties`(MDI 子) が登録されているときに、フレームワークによってメソッドに渡されるフラグの組み合わせ。

```
AFX_IMPORT_DATA static DWORD m_dwDefaultTaskbarTabPropertyFlags;
```

### <a name="remarks"></a>解説

既定の組み合わせは、&#124;STPF_USEAPPPEEKWHENACTIVESTPF_USEAPPTHUMBNAILWHENACTIVE。

## <a name="cmdichildwndexistaskbarthumbnailcliprectenabled"></a><a name="istaskbarthumbnailcliprectenabled"></a>CMDIChildWndEx::Isタスクバーサムネイルクリップレック有効

ウィンドウのサムネイルをタスク バーに表示するウィンドウのクライアント領域の一部を自動的に選択するかどうかを示します。

```
BOOL IsTaskbarThumbnailClipRectEnabled() const;
```

### <a name="return-value"></a>戻り値

表示するウィンドウのクライアント領域の一部を自動的に選択する場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexistaskbartabssupportenabled"></a><a name="istaskbartabssupportenabled"></a>サポートをサポートします。

MDI 子が Windows 7 のタスク バー タブに表示できるかどうかを示します。

```
BOOL IsTaskbarTabsSupportEnabled();
```

### <a name="return-value"></a>戻り値

MDI の子が Windows 7 タスク バー タブに表示される場合は TRUE。MDI 子が Windows 7 タスク バー のタブに表示されない場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexisregisteredwithtaskbartabs"></a><a name="isregisteredwithtaskbartabs"></a>タスクバータブ::IsRegisteredとタスクバータブ

MDI 子が Windows 7 タスク バー タブに正常に登録された場合は TRUE を返します。

```
BOOL IsRegisteredWithTaskbarTabs();
```

### <a name="return-value"></a>戻り値

MDI 子が Windows 7 タスク バー タブに登録されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexinvalidateiconicbitmaps"></a><a name="invalidateiconicbitmaps"></a>コミチャイルドンデックス::イニシブアイコニックビットマップ

MDI 子のアイコンビットマップ表現を無効にします。

```
BOOL InvalidateIconicBitmaps();
```

### <a name="return-value"></a>戻り値

Windows 7 タスク バーサポートが無効になっている場合、または MDI 子が Windows 7 タスク バー タブに登録されていない場合は FALSE を返します。それ以外の場合は TRUE を返します。

### <a name="remarks"></a>解説

MDI 子のライブ コンテンツまたはサイズが変更されたときに呼び出す必要があります。

## <a name="cmdichildwndexgettaskbarthumbnailcliprect"></a><a name="gettaskbarthumbnailcliprect"></a>CMDIChildWndEx:::タスクバーサムネールクリップレックを取得します

ウィンドウのサムネイルとしてタスク バーに表示するウィンドウのクライアント領域の一部を選択する必要がある場合に、フレームワークによって呼び出されます。

```
virtual CRect GetTaskbarThumbnailClipRect() const;
```

### <a name="return-value"></a>戻り値

ウィンドウ座標の四角形。 この四角形は、最上位フレームのクライアント領域にマップされます。 クリッピング四角形をクリアするには、四角形を空にする必要があります。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexgettaskbarpreviewwnd"></a><a name="gettaskbarpreviewwnd"></a>コマンドイチャイルドンデックス:::タスクバープレビューウンド

Windows 7 のタスク バー タブのサムネイルに表示される子ウィンドウ (通常はビューまたは分割ウィンドウ) を取得する必要があるときに、フレームワークによって呼び出されます。

```
virtual CWnd* GetTaskbarPreviewWnd();
```

### <a name="return-value"></a>戻り値

この MDI 子に`CWnd`関連する Windows 7 タスク バー タブにプレビューを表示するオブジェクトへの有効なポインターを返す必要があります。 既定の実装では、コントロール ID (通常は派生クラス) を持つこの`CView`MDI 子ウィンドウAFX_IDW_PANE_FIRST返します。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexgettabproxywnd"></a><a name="gettabproxywnd"></a>を使用します。

Windows 7 タスク バー タブに登録されているタブ プロキシ ウィンドウを返します。

```
CMDITabProxyWnd* GetTabProxyWnd();
```

### <a name="return-value"></a>戻り値

Windows 7`CMDITabProxyWnd`のタスク バー タブに登録されているオブジェクトへのポインター。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexenabletaskbarthumbnailcliprect"></a><a name="enabletaskbarthumbnailcliprect"></a>CMDIChildWndEx::タスクバーサムネールクリップレックを有効にします。

ウィンドウのクライアント領域の一部を、そのウィンドウのサムネイルとしてタスク バーに表示する自動選択を有効または無効にします。

```cpp
void EnableTaskbarThumbnailClipRect(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
ウィンドウのクライアント領域の一部を表示する場合に、有効 (TRUE) または無効 (FALSE) を指定します。

### <a name="remarks"></a>解説

## <a name="cmdichildwndexcanshowontaskbartabs"></a><a name="canshowontaskbartabs"></a>コマンドイチャイルドンデックス::缶ショーオンタスクバータブ

この MDI 子を Windows 7 のタスク バー タブに表示できるかどうかをフレームワークに通知します。

```
virtual BOOL CanShowOnTaskBarTabs();
```

### <a name="return-value"></a>戻り値

True の場合、MDI 子の内容を Windows 7 のタスク バーのサムネイルに表示できます。

### <a name="remarks"></a>解説

派生クラスでこのメソッドをオーバーライドし、False を返して、Windows 7 タスク バー タブでこの MDI 子の外観を無効にします。

## <a name="cmdichildwndexactivatetoplevelframe"></a><a name="activatetoplevelframe"></a>をアクティブにします。

アプリケーションがタスク バー タブからアクティブになったときに、最上位のフレームをアクティブにするためにフレームワークによって呼び出されます。

```
virtual void ActivateTopLevelFrame();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)<br/>
[クラス](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)<br/>
[クラスを作成します。](../../mfc/reference/cmdiframewndex-class.md)
