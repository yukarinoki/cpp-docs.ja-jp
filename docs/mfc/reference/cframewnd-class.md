---
title: CFrameWnd クラス
ms.date: 11/04/2016
f1_keywords:
- CFrameWnd
- AFXWIN/CFrameWnd
- AFXWIN/CFrameWnd::CFrameWnd
- AFXWIN/CFrameWnd::ActivateFrame
- AFXWIN/CFrameWnd::BeginModalState
- AFXWIN/CFrameWnd::Create
- AFXWIN/CFrameWnd::CreateView
- AFXWIN/CFrameWnd::DockControlBar
- AFXWIN/CFrameWnd::EnableDocking
- AFXWIN/CFrameWnd::EndModalState
- AFXWIN/CFrameWnd::FloatControlBar
- AFXWIN/CFrameWnd::GetActiveDocument
- AFXWIN/CFrameWnd::GetActiveFrame
- AFXWIN/CFrameWnd::GetActiveView
- AFXWIN/CFrameWnd::GetControlBar
- AFXWIN/CFrameWnd::GetDockState
- AFXWIN/CFrameWnd::GetMenuBarState
- AFXWIN/CFrameWnd::GetMenuBarVisibility
- AFXWIN/CFrameWnd::GetMessageBar
- AFXWIN/CFrameWnd::GetMessageString
- AFXWIN/CFrameWnd::GetTitle
- AFXWIN/CFrameWnd::InitialUpdateFrame
- AFXWIN/CFrameWnd::InModalState
- AFXWIN/CFrameWnd::IsTracking
- AFXWIN/CFrameWnd::LoadAccelTable
- AFXWIN/CFrameWnd::LoadBarState
- AFXWIN/CFrameWnd::LoadFrame
- AFXWIN/CFrameWnd::NegotiateBorderSpace
- AFXWIN/CFrameWnd::OnBarCheck
- AFXWIN/CFrameWnd::OnContextHelp
- AFXWIN/CFrameWnd::OnSetPreviewMode
- AFXWIN/CFrameWnd::OnUpdateControlBarMenu
- AFXWIN/CFrameWnd::RecalcLayout
- AFXWIN/CFrameWnd::SaveBarState
- AFXWIN/CFrameWnd::SetActivePreviewView
- AFXWIN/CFrameWnd::SetActiveView
- AFXWIN/CFrameWnd::SetDockState
- AFXWIN/CFrameWnd::SetMenuBarState
- AFXWIN/CFrameWnd::SetMenuBarVisibility
- AFXWIN/CFrameWnd::SetMessageText
- AFXWIN/CFrameWnd::SetProgressBarPosition
- AFXWIN/CFrameWnd::SetProgressBarRange
- AFXWIN/CFrameWnd::SetProgressBarState
- AFXWIN/CFrameWnd::SetTaskbarOverlayIcon
- AFXWIN/CFrameWnd::SetTitle
- AFXWIN/CFrameWnd::ShowControlBar
- AFXWIN/CFrameWnd::ShowOwnedWindows
- AFXWIN/CFrameWnd::OnCreateClient
- AFXWIN/CFrameWnd::OnHideMenuBar
- AFXWIN/CFrameWnd::OnShowMenuBar
- AFXWIN/CFrameWnd::m_bAutoMenuEnable
- AFXWIN/CFrameWnd::rectDefault
helpviewer_keywords:
- CFrameWnd [MFC], CFrameWnd
- CFrameWnd [MFC], ActivateFrame
- CFrameWnd [MFC], BeginModalState
- CFrameWnd [MFC], Create
- CFrameWnd [MFC], CreateView
- CFrameWnd [MFC], DockControlBar
- CFrameWnd [MFC], EnableDocking
- CFrameWnd [MFC], EndModalState
- CFrameWnd [MFC], FloatControlBar
- CFrameWnd [MFC], GetActiveDocument
- CFrameWnd [MFC], GetActiveFrame
- CFrameWnd [MFC], GetActiveView
- CFrameWnd [MFC], GetControlBar
- CFrameWnd [MFC], GetDockState
- CFrameWnd [MFC], GetMenuBarState
- CFrameWnd [MFC], GetMenuBarVisibility
- CFrameWnd [MFC], GetMessageBar
- CFrameWnd [MFC], GetMessageString
- CFrameWnd [MFC], GetTitle
- CFrameWnd [MFC], InitialUpdateFrame
- CFrameWnd [MFC], InModalState
- CFrameWnd [MFC], IsTracking
- CFrameWnd [MFC], LoadAccelTable
- CFrameWnd [MFC], LoadBarState
- CFrameWnd [MFC], LoadFrame
- CFrameWnd [MFC], NegotiateBorderSpace
- CFrameWnd [MFC], OnBarCheck
- CFrameWnd [MFC], OnContextHelp
- CFrameWnd [MFC], OnSetPreviewMode
- CFrameWnd [MFC], OnUpdateControlBarMenu
- CFrameWnd [MFC], RecalcLayout
- CFrameWnd [MFC], SaveBarState
- CFrameWnd [MFC], SetActivePreviewView
- CFrameWnd [MFC], SetActiveView
- CFrameWnd [MFC], SetDockState
- CFrameWnd [MFC], SetMenuBarState
- CFrameWnd [MFC], SetMenuBarVisibility
- CFrameWnd [MFC], SetMessageText
- CFrameWnd [MFC], SetProgressBarPosition
- CFrameWnd [MFC], SetProgressBarRange
- CFrameWnd [MFC], SetProgressBarState
- CFrameWnd [MFC], SetTaskbarOverlayIcon
- CFrameWnd [MFC], SetTitle
- CFrameWnd [MFC], ShowControlBar
- CFrameWnd [MFC], ShowOwnedWindows
- CFrameWnd [MFC], OnCreateClient
- CFrameWnd [MFC], OnHideMenuBar
- CFrameWnd [MFC], OnShowMenuBar
- CFrameWnd [MFC], m_bAutoMenuEnable
- CFrameWnd [MFC], rectDefault
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
ms.openlocfilehash: b31e8d28cba5199d0a40a050bb2b284cfafc5c55
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212424"
---
# <a name="cframewnd-class"></a>CFrameWnd クラス

ウィンドウを管理するメンバーと共に、Windows のシングル ドキュメント インターフェイス (SDI: Single Document Interface) のオーバーラップ フレーム ウィンドウまたはポップアップ フレーム ウィンドウの機能を提供します。

## <a name="syntax"></a>構文

```
class CFrameWnd : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFrameWnd:: CFrameWnd](#cframewnd)|`CFrameWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFrameWnd:: アクティブフレーム](#activateframe)|フレームを表示し、ユーザーが使用できるようにします。|
|[CFrameWnd:: BeginModalState](#beginmodalstate)|フレームウィンドウをモーダルに設定します。|
|[CFrameWnd:: Create](#create)|を呼び出して、オブジェクトに関連付けられた Windows フレームウィンドウを作成し、初期化し `CFrameWnd` ます。|
|[CFrameWnd:: CreateView](#createview)|から派生していないフレーム内にビューを作成し `CView` ます。|
|[CFrameWnd::D ockControlBar](#dockcontrolbar)|コントロールバーをドッキングします。|
|[CFrameWnd:: EnableDocking](#enabledocking)|コントロールバーをドッキングできるようにします。|
|[CFrameWnd:: EndModalState](#endmodalstate)|フレームウィンドウのモーダル状態を終了します。 によって無効にされているすべてのウィンドウを有効に `BeginModalState` します。|
|[CFrameWnd:: FloatControlBar](#floatcontrolbar)|コントロールバーをフローティングします。|
|[CFrameWnd:: GetActiveDocument](#getactivedocument)|アクティブなオブジェクトを返し `CDocument` ます。|
|[CFrameWnd:: GetActiveFrame](#getactiveframe)|アクティブなオブジェクトを返し `CFrameWnd` ます。|
|[CFrameWnd:: GetActiveView](#getactiveview)|アクティブなオブジェクトを返し `CView` ます。|
|[CFrameWnd:: GetControlBar](#getcontrolbar)|コントロールバーを取得します。|
|[CFrameWnd:: GetDockState](#getdockstate)|フレームウィンドウのドッキング状態を取得します。|
|[CFrameWnd:: GetMenuBarState](#getmenubarstate)|現在の MFC アプリケーションのメニューの表示状態を取得します。|
|[CFrameWnd:: GetMenuBarVisibility](#getmenubarvisibility)|現在の MFC アプリケーションのメニューの既定の動作が非表示または表示されているかどうかを示します。|
|[CFrameWnd:: GetMessageBar](#getmessagebar)|フレームウィンドウに属しているステータスバーへのポインターを返します。|
|[CFrameWnd:: GetMessageString](#getmessagestring)|コマンド ID に対応するメッセージを取得します。|
|[CFrameWnd:: GetTitle](#gettitle)|関連するコントロールバーのタイトルを取得します。|
|[CFrameWnd:: InitialUpdateFrame](#initialupdateframe)|`OnInitialUpdate`フレームウィンドウ内のすべてのビューに属するメンバー関数を呼び出すようにします。|
|[CFrameWnd:: InModalState](#inmodalstate)|フレームウィンドウがモーダル状態であるかどうかを示す値を返します。|
|[CFrameWnd:: IsTracking](#istracking)|分割バーを現在移動しているかどうかを判断します。|
|[CFrameWnd:: LoadAccelTable](#loadacceltable)|を呼び出して、アクセラレータテーブルを読み込みます。|
|[CFrameWnd:: LoadBarState](#loadbarstate)|を呼び出して、コントロールバーの設定を復元します。|
|[CFrameWnd:: LoadFrame](#loadframe)|を呼び出して、リソース情報からフレームウィンドウを動的に作成します。|
|[CFrameWnd:: NegotiateBorderSpace](#negotiateborderspace)|フレームウィンドウの境界領域をネゴシエートします。|
|[CFrameWnd:: OnBarCheck](#onbarcheck)|指定されたコントロールバーに対してアクションが実行されるたびに呼び出されます。|
|[CFrameWnd:: OnContextHelp](#oncontexthelp)|インプレース項目の SHIFT + F1 ヘルプを処理します。|
|[CFrameWnd:: OnSetPreviewMode](#onsetpreviewmode)|アプリケーションのメインフレームウィンドウを印刷プレビューモードに設定します。|
|[CFrameWnd:: OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|関連付けられたメニューが更新されたときにフレームワークによって呼び出されます。|
|[CFrameWnd:: RecalcLayout](#recalclayout)|オブジェクトのコントロールバーを移動 `CFrameWnd` します。|
|[CFrameWnd:: SaveBarState](#savebarstate)|を呼び出して、コントロールバーの設定を保存します。|
|[CFrameWnd:: Setactiveプレビュービュー](#setactivepreviewview)|指定したビューをリッチプレビューのアクティブビューに指定します。|
|[CFrameWnd:: SetActiveView](#setactiveview)|アクティブなオブジェクトを設定 `CView` します。|
|[CFrameWnd:: SetDockState](#setdockstate)|を呼び出して、メインウィンドウにフレームウィンドウをドッキングします。|
|[CFrameWnd:: SetMenuBarState](#setmenubarstate)|現在の MFC アプリケーションのメニューの表示状態を非表示または表示に設定します。|
|[CFrameWnd:: SetMenuBarVisibility](#setmenubarvisibility)|現在の MFC アプリケーションのメニューの既定の動作を、非表示にするか表示するかを設定します。|
|[CFrameWnd:: SetMessageText](#setmessagetext)|標準ステータスバーのテキストを設定します。|
|[CFrameWnd:: Setて Barposition](#setprogressbarposition)|タスクバーに表示される Windows 7 のプログレスバーの現在の位置を設定します。|
|[CFrameWnd:: Set進捗を Barrange](#setprogressbarrange)|タスクバーに表示される Windows 7 のプログレスバーの範囲を設定します。|
|[CFrameWnd:: Set進捗 Barstate](#setprogressbarstate)|タスクバーボタンに表示される進行状況インジケーターの種類と状態を設定します。|
|[CFrameWnd:: SetTaskbarOverlayIcon](#settaskbaroverlayicon)|オーバーロードされます。 タスクバーボタンにオーバーレイを適用して、アプリケーションの状態やユーザーへの通知を示します。|
|[CFrameWnd:: SetTitle](#settitle)|関連するコントロールバーのタイトルを設定します。|
|[CFrameWnd:: ShowControlBar](#showcontrolbar)|を呼び出して、コントロールバーを表示します。|
|[CFrameWnd:: ShowOwnedWindows](#showownedwindows)|オブジェクトの子孫であるすべてのウィンドウを表示 `CFrameWnd` します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CFrameWnd:: OnCreateClient](#oncreateclient)|フレームのクライアントウィンドウを作成します。|
|[CFrameWnd:: OnHideMenuBar](#onhidemenubar)|現在の MFC アプリケーションのメニューが非表示になる前に呼び出されます。|
|[CFrameWnd:: OnShowMenuBar](#onshowmenubar)|現在の MFC アプリケーションのメニューが表示される前に呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CFrameWnd:: m_bAutoMenuEnable](#m_bautomenuenable)|メニュー項目の自動有効化および無効化機能を制御します。|
|[CFrameWnd:: rectDefault](#rectdefault)|オブジェクトを作成するときに、この静的 `CRect` をパラメーターとして渡して、 `CFrameWnd` ウィンドウの初期サイズと位置を Windows が選択できるようにします。|

## <a name="remarks"></a>解説

アプリケーション用の便利なフレームウィンドウを作成するには、からクラスを派生させ `CFrameWnd` ます。 アプリケーションに固有のデータを格納するために、派生クラスにメンバー変数を追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

フレームウィンドウを構築するには、次の3つの方法があります。

- [Create](#create)を使用して直接作成します。

- [LoadFrame](#loadframe)を使用して直接作成します。

- ドキュメントテンプレートを使用して間接的に構築します。

`Create`またはを呼び出す前に `LoadFrame` 、C++ の演算子を使用して、ヒープ上にフレームウィンドウオブジェクトを構築する必要があり **`new`** ます。 を呼び出す前に `Create` 、ウィンドウクラスを[AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)グローバル関数に登録して、フレームのアイコンとクラスのスタイルを設定することもできます。

メンバー関数を使用し `Create` て、フレームの作成パラメーターをイミディエイト引数として渡します。

`LoadFrame`に必要な引数がより少なく `Create` 、代わりに、フレームのキャプション、アイコン、アクセラレータテーブル、メニューなど、リソースからほとんどの既定値を取得します。 によってアクセスできるようにするには `LoadFrame` 、これらすべてのリソースが同じリソース ID を持つ必要があります (たとえば、IDR_MAINFRAME)。

オブジェクトに `CFrameWnd` ビューとドキュメントが含まれている場合は、プログラマが直接作成するのではなく、フレームワークによって間接的に作成されます。 オブジェクトは、 `CDocTemplate` フレームの作成、含まれるビューの作成、および適切なドキュメントへのビューの接続を調整します。 コンストラクターのパラメーターは、 `CDocTemplate` 関連する `CRuntimeClass` 3 つのクラス (ドキュメント、フレーム、およびビュー) のを指定します。 `CRuntimeClass`オブジェクトは、ユーザーが指定したときに新しいフレームを動的に作成するために、フレームワークによって使用されます (たとえば、[ファイル] [新規作成] コマンドまたは [マルチドキュメントインターフェイス (MDI)] ウィンドウの [新規作成] コマンドを使用します)。

上の RUNTIME_CLASS 機構を正しく動作させるには、から派生したフレームウィンドウクラスを `CFrameWnd` DECLARE_DYNCREATE で宣言する必要があります。

には、 `CFrameWnd` Windows 用の一般的なアプリケーションでメインウィンドウの次の機能を実行するための既定の実装が含まれています。

- `CFrameWnd`フレームウィンドウは、Windows のアクティブウィンドウまたは現在の入力フォーカスに依存しない、現在アクティブなビューを追跡します。 フレームが再アクティブ化されると、アクティブなビューはを呼び出すことによって通知され `CView::OnActivateView` ます。

- コマンドメッセージと、の、、および関数によって処理されるメッセージなど、多くの一般的なフレーム通知メッセージ `OnSetFocus` `OnHScroll` は、 `OnVScroll` `CWnd` フレームウィンドウによって `CFrameWnd` 現在アクティブなビューに委任されます。

- 現在アクティブなビュー (MDI フレームの場合は、現在アクティブな MDI 子フレームウィンドウ) は、フレームウィンドウのキャプションを決定できます。 フレームウィンドウの FWS_ADDTOTITLE スタイルビットをオフにすることで、この機能を無効にすることができます。

- フレーム `CFrameWnd` ウィンドウは、フレームウィンドウのクライアント領域内のコントロールバー、ビュー、およびその他の子ウィンドウの配置を管理します。 また、フレームウィンドウでは、ツールバーとその他のコントロールバーボタンがアイドル時に更新されます。 `CFrameWnd`また、フレームウィンドウには、ツールバーとステータスバーのオンとオフを切り替えるためのコマンドが既定で実装されています。

- `CFrameWnd`メインメニューバーは、フレームウィンドウによって管理されます。 ポップアップメニューが表示されている場合、フレームウィンドウでは、UPDATE_COMMAND_UI メカニズムを使用して、有効、無効、またはチェックするメニュー項目を決定します。 ユーザーがメニュー項目を選択すると、フレームウィンドウは、そのコマンドのメッセージ文字列を使用してステータスバーを更新します。

- `CFrameWnd`フレームウィンドウには、キーボードアクセラレータを自動的に変換するオプションのアクセラレータテーブルがあります。

- `CFrameWnd`フレームウィンドウには、で設定されたオプションのヘルプ ID があり `LoadFrame` ます。これは、状況依存のヘルプに使用されます。 フレームウィンドウは、状況依存のヘルプ (SHIFT + F1) や印刷プレビューモードなど、semimodal の状態の主要な orchestrator です。

- `CFrameWnd`ファイルマネージャーからドラッグしてフレームウィンドウにドロップしたファイルがフレームウィンドウに表示されます。 ファイル拡張子が登録され、アプリケーションに関連付けられている場合、フレームウィンドウは、ユーザーがファイルマネージャーでデータファイルを開いたとき、または `ShellExecute` Windows 関数が呼び出されたときに発生する、dynamic data exchange (DDE) open 要求に応答します。

- フレームウィンドウがメインアプリケーションウィンドウ (つまり) の場合、ユーザーがアプリケーションを終了すると、フレームウィンドウによって、変更され `CWinThread::m_pMainWnd` たドキュメントを保存するように求められます (との場合 `OnClose` `OnQueryEndSession` )。

- フレームウィンドウがメインアプリケーションウィンドウである場合、フレームウィンドウは WinHelp を実行するためのコンテキストです。 このアプリケーションのヘルプ用にフレームウィンドウを閉じると、WINHELP.EXE がシャットダウンされます。

C++ の演算子を使用して **`delete`** フレームウィンドウを破棄しないでください。 代わりに `CWnd::DestroyWindow` を使用してください `CFrameWnd`の実装は、 `PostNcDestroy` ウィンドウが破棄されたときに C++ オブジェクトを削除します。 ユーザーがフレームウィンドウを閉じると、既定の `OnClose` ハンドラーはを呼び出し `DestroyWindow` ます。

の詳細につい `CFrameWnd` ては、「[フレームウィンドウ](../../mfc/frame-windows.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cframewndactivateframe"></a><a name="activateframe"></a>CFrameWnd:: アクティブフレーム

このメンバー関数を呼び出して、フレームウィンドウをアクティブにして、ユーザーが使用できるようにします。

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>パラメーター

*nCmdShow*<br/>
[CWnd:: ShowWindow](../../mfc/reference/cwnd-class.md#showwindow)に渡すパラメーターを指定します。 既定では、フレームが表示され、正しく復元されます。

### <a name="remarks"></a>解説

通常、このメンバー関数は、DDE、OLE などの非ユーザーインターフェイスイベントの後、またはフレームウィンドウまたはその内容をユーザーに表示する可能性のある他のイベントの後に呼び出されます。

既定の実装では、フレームがアクティブになり、Z オーダーの一番上に表示されます。必要に応じて、アプリケーションのメインフレームウィンドウに対しても同じ手順が実行されます。

このメンバー関数をオーバーライドして、フレームのアクティブ化方法を変更します。 たとえば、MDI 子ウィンドウを強制的に最大化することができます。 適切な機能を追加し、明示的な*Ncmdshow*を使用して基本クラスのバージョンを呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

## <a name="cframewndbeginmodalstate"></a><a name="beginmodalstate"></a>CFrameWnd:: BeginModalState

フレーム ウィンドウをモーダルにします。

```
virtual void BeginModalState();
```

## <a name="cframewndcframewnd"></a><a name="cframewnd"></a>CFrameWnd:: CFrameWnd

オブジェクトを構築し `CFrameWnd` ますが、表示されるフレームウィンドウは作成しません。

```
CFrameWnd();
```

### <a name="remarks"></a>解説

`Create`を呼び出して、表示されるウィンドウを作成します。

## <a name="cframewndcreate"></a><a name="create"></a>CFrameWnd:: Create

を呼び出して、オブジェクトに関連付けられた Windows フレームウィンドウを作成し、初期化し `CFrameWnd` ます。

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CWnd* pParentWnd = NULL,
    LPCTSTR lpszMenuName = NULL,
    DWORD dwExStyle = 0,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszClassName*<br/>
Windows クラスに名前を指定する null で終わる文字列を指します。 クラス名には、 `AfxRegisterWndClass` グローバル関数または Windows 関数に登録されている任意の名前を指定でき `RegisterClass` ます。 NULL の場合、は定義済みの既定の属性を使用し `CFrameWnd` ます。

*lpszWindowName*<br/>
ウィンドウ名を表す null で終わる文字列を指します。 タイトルバーのテキストとして使用されます。

*dwStyle*<br/>
ウィンドウ[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)属性を指定します。 ウィンドウに表示されるドキュメントの名前をタイトルバーに自動的に表示する場合は、FWS_ADDTOTITLE スタイルを指定します。

*rect*<br/>
ウィンドウのサイズと位置を指定します。 *RectDefault*値を使用すると、ウィンドウで新しいウィンドウのサイズと位置を指定できます。

*pParentWnd*<br/>
このフレームウィンドウの親ウィンドウを指定します。 最上位レベルのフレームウィンドウでは、このパラメーターは NULL にする必要があります。

*lpszMenuName*<br/>
ウィンドウで使用するメニューリソースの名前を識別します。 メニューに文字列ではなく整数の ID が含まれている場合は、MAKEINTRESOURCE を使用します。 このパラメーターには NULL を指定できます。

*dwExStyle*<br/>
ウィンドウの拡張[スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)属性を指定します。

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体へのポインターを指定します。 このパラメーターには NULL を指定できます。

### <a name="return-value"></a>戻り値

初期化が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

`CFrameWnd`2 つの手順でオブジェクトを構築します。 まず、オブジェクトを構築するコンストラクターを呼び出し、 `CFrameWnd` 次にを呼び出し `Create` ます。これにより、Windows フレームウィンドウが作成され、オブジェクトにアタッチされ `CFrameWnd` ます。 `Create`ウィンドウのクラス名とウィンドウ名を初期化し、そのスタイル、親、および関連付けられているメニューの既定値を登録します。

`LoadFrame` `Create` 引数を指定する代わりに、リソースからフレームウィンドウを読み込むのではなく、を使用します。

## <a name="cframewndcreateview"></a><a name="createview"></a>CFrameWnd:: CreateView

を呼び出して `CreateView` 、フレーム内にビューを作成します。

```
CWnd* CreateView(
    CCreateContext* pContext,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
ビューとドキュメントの種類を指定します。

*nID*<br/>
ビューの ID 番号。

### <a name="return-value"></a>戻り値

`CWnd`成功した場合はオブジェクトへのポインター、それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメンバー関数は `CView` 、フレーム内で派生していない "views" を作成するために使用します。 を呼び出した後は `CreateView` 、手動でビューをアクティブに設定し、表示されるように設定する必要があります。これらのタスクは、によって自動的には実行されません `CreateView` 。

## <a name="cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a>CFrameWnd::D ockControlBar

コントロールバーをフレームウィンドウにドッキングします。

```cpp
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
ドッキングされるコントロールバーをポイントします。

*nDockBarID*<br/>
ドッキング時に考慮するフレームウィンドウの辺を決定します。 0または次のいずれかを指定できます。

- フレームウィンドウの上部にドッキング AFX_IDW_DOCKBAR_TOP ます。

- フレームウィンドウの下部にドッキング AFX_IDW_DOCKBAR_BOTTOM ます。

- フレームウィンドウの左側にドッキング AFX_IDW_DOCKBAR_LEFT ます。

- フレームウィンドウの右側にドッキング AFX_IDW_DOCKBAR_RIGHT ます。

0の場合、対象のフレームウィンドウでドッキング可能な任意の辺にコントロールバーをドッキングできます。

*lpRect*<br/>
移動先のフレームウィンドウの非クライアント領域にコントロールバーがドッキングされる位置を画面座標で決定します。

### <a name="remarks"></a>解説

コントロールバーは、 [CControlBar:: EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)と[CFrameWnd:: EnableDocking](#enabledocking)の両方の呼び出しで指定されたフレームウィンドウのいずれかの辺にドッキングされます。 選択した辺は、 *nDockBarID*によって決定されます。

## <a name="cframewndenabledocking"></a><a name="enabledocking"></a>CFrameWnd:: EnableDocking

フレームウィンドウでドッキング可能なコントロールバーを有効にするには、この関数を呼び出します。

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

*dwDockStyle*<br/>
コントロールバーのドッキングサイトとして使用できるフレームウィンドウの辺を指定します。 次の1つまたは複数を指定できます。

- CBRS_ALIGN_TOP を使用すると、クライアント領域の上部にドッキングできます。

- CBRS_ALIGN_BOTTOM を使用すると、クライアント領域の下部にドッキングできます。

- CBRS_ALIGN_LEFT を使用すると、クライアント領域の左側にドッキングできます。

- CBRS_ALIGN_RIGHT を使用すると、クライアント領域の右側にドッキングできます。

- CBRS_ALIGN_ANY を使用すると、クライアント領域の任意の側でドッキングできます。

### <a name="remarks"></a>解説

既定では、コントロールバーは、[上]、[下]、[左]、[右] の順に、フレームウィンドウの辺にドッキングされます。

### <a name="example"></a>例

  「 [CToolBar:: Create](../../mfc/reference/ctoolbar-class.md#create)」の例を参照してください。

## <a name="cframewndendmodalstate"></a><a name="endmodalstate"></a>CFrameWnd:: EndModalState

フレーム ウィンドウをモーダルからモードレスに変更します。

```
virtual void EndModalState();
```

### <a name="remarks"></a>解説

`EndModalState`[BeginModalState](#beginmodalstate)によって無効にされたすべての windows を有効にします。

## <a name="cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a>CFrameWnd:: FloatControlBar

この関数を呼び出すと、コントロールバーがフレームウィンドウにドッキングされません。

```cpp
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
フローティングされるコントロールバーをポイントします。

*視点*<br/>
コントロールバーの左上隅が配置される位置 (画面座標)。

*dwStyle*<br/>
新しいフレームウィンドウ内でコントロールバーを水平方向または垂直方向に揃えるかどうかを指定します。 次のいずれかを指定できます。

- CBRS_ALIGN_TOP コントロールバーを垂直方向に向きます。

- CBRS_ALIGN_BOTTOM コントロールバーを垂直方向に向きます。

- CBRS_ALIGN_LEFT コントロールバーを水平方向に向きます。

- CBRS_ALIGN_RIGHT コントロールバーを水平方向に向きます。

水平方向と垂直方向の両方を指定してスタイルを渡すと、水平方向にツールバーが表示されます。

### <a name="remarks"></a>解説

通常、これは、プログラムが前回の実行から設定を復元するときに、アプリケーションの起動時に実行されます。

この関数は、ドッキングできない場所にコントロールバーをドラッグしているときに、ユーザーがマウスの左ボタンを離すことによってドロップ操作を行うと、フレームワークによって呼び出されます。

## <a name="cframewndgetactivedocument"></a><a name="getactivedocument"></a>CFrameWnd:: GetActiveDocument

`CDocument`現在のアクティブなビューにアタッチされている現在のへのポインターを取得するには、このメンバー関数を呼び出します。

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>戻り値

現在の[CDocument](../../mfc/reference/cdocument-class.md)へのポインター。 現在のドキュメントがない場合は、NULL を返します。

## <a name="cframewndgetactiveframe"></a><a name="getactiveframe"></a>CFrameWnd:: GetActiveFrame

MDI フレームウィンドウのアクティブなマルチドキュメントインターフェイス (MDI) 子ウィンドウへのポインターを取得するには、このメンバー関数を呼び出します。

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>戻り値

アクティブな MDI 子ウィンドウへのポインター。 アプリケーションが SDI アプリケーションである場合、または MDI フレームウィンドウにアクティブなドキュメントがない場合は、暗黙的な **`this`** ポインターが返されます。

### <a name="remarks"></a>解説

アクティブな MDI 子がない場合、またはアプリケーションがシングルドキュメントインターフェイス (SDI) の場合は、暗黙的な **`this`** ポインターが返されます。

## <a name="cframewndgetactiveview"></a><a name="getactiveview"></a>CFrameWnd:: GetActiveView

このメンバー関数を呼び出して、フレームウィンドウにアタッチされているアクティブなビュー (存在する場合) へのポインターを取得し `CFrameWnd` ます ()。

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>戻り値

現在の[CView](../../mfc/reference/cview-class.md)へのポインター。 現在のビューが存在しない場合、は NULL を返します。

### <a name="remarks"></a>解説

この関数は、MDI メインフレームウィンドウ () に対して呼び出された場合に NULL を返し `CMDIFrameWnd` ます。 MDI アプリケーションでは、MDI メインフレームウィンドウにビューが関連付けられていません。 代わりに、個々の子ウィンドウ ( `CMDIChildWnd` ) には1つ以上のビューが関連付けられています。 MDI アプリケーションのアクティブなビューを取得するには、まずアクティブな MDI 子ウィンドウを検索し、その子ウィンドウのアクティブなビューを検索します。 アクティブな MDI 子ウィンドウは、 `MDIGetActive` 次に示すように、関数を呼び出すことによって見つけることができ `GetActiveFrame` ます。

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

## <a name="cframewndgetcontrolbar"></a><a name="getcontrolbar"></a>CFrameWnd:: GetControlBar

`GetControlBar`を呼び出して、ID に関連付けられているコントロールバーへのアクセス権を取得します。

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロールバーの ID 番号。

### <a name="return-value"></a>戻り値

ID に関連付けられているコントロールバーへのポインター。

### <a name="remarks"></a>解説

*NID*パラメーターは、コントロールバーのメソッドに渡される一意の識別子を参照し `Create` ます。 コントロールバーの詳細については、「[コントロールバー](../../mfc/control-bars.md)」を参照してください。

`GetControlBar`はフローティング状態であっても、現在はフレームの子ウィンドウではないコントロールバーを返します。

## <a name="cframewndgetdockstate"></a><a name="getdockstate"></a>CFrameWnd:: GetDockState

このメンバー関数を呼び出して、オブジェクトのフレームウィンドウのコントロールバーに関する状態情報を格納し `CDockState` ます。

```cpp
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
返されたときのフレームウィンドウのコントロールバーの現在の状態を格納します。

### <a name="remarks"></a>解説

その後、 `CDockState` またはを使用して、の内容をストレージに書き込むことができ `CDockState::SaveState` `Serialize` ます。 後でコントロールバーを前の状態に復元する場合は、またはを使用して状態を読み込み、 `CDockState::LoadState` `Serialize` を呼び出して、 `SetDockState` 前の状態をフレームウィンドウのコントロールバーに適用します。

## <a name="cframewndgetmenubarstate"></a><a name="getmenubarstate"></a>CFrameWnd:: GetMenuBarState

現在の MFC アプリケーションのメニューの表示状態を取得します。

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>戻り値

戻り値には、次の値を指定できます。

- AFX_MBS_VISIBLE (0x01)-メニューが表示されます。

- AFX_MBS_HIDDEN (0x02)-メニューは非表示になっています。

### <a name="remarks"></a>解説

ランタイムエラーが発生した場合、このメソッドはデバッグモードでアサートし、 [CException](../../mfc/reference/cexception-class.md)クラスから派生した例外を発生させます。

## <a name="cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a>CFrameWnd:: GetMenuBarVisibility

現在の MFC アプリケーションのメニューの既定の状態が非表示であるか表示されているかを示します。

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>戻り値

このメソッドは、次のいずれかの値を返します。

- AFX_MBV_KEEPVISIBLE (0x01)-メニューは常に表示され、既定ではフォーカスがありません。

- AFX_MBV_DISPLAYONFOCUS (0x02)-メニューは既定では非表示になっています。 メニューが非表示になっている場合は、ALT キーを押してメニューを表示し、フォーカスを与えます。 メニューが表示されている場合は、ALT キーまたは ESC キーを押して非表示にします。

- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (ビットごとの組み合わせ (OR))-メニューは既定では非表示になっています。 メニューが非表示になっている場合は、F10 キーを押してメニューを表示し、フォーカスを与えます。 メニューが表示されている場合は、F10 キーを押して、メニューにフォーカスを設定します。 メニューが表示されるのは、ALT キーまたは ESC キーを押すと非表示になります。

### <a name="remarks"></a>解説

ランタイムエラーが発生した場合、このメソッドはデバッグモードでアサートし、 [CException](../../mfc/reference/cexception-class.md)クラスから派生した例外を発生させます。

## <a name="cframewndgetmessagebar"></a><a name="getmessagebar"></a>CFrameWnd:: GetMessageBar

ステータスバーへのポインターを取得するには、このメンバー関数を呼び出します。

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>戻り値

ステータスバーウィンドウへのポインター。

## <a name="cframewndgetmessagestring"></a><a name="getmessagestring"></a>CFrameWnd:: GetMessageString

コマンド Id のカスタム文字列を提供するには、この関数をオーバーライドします。

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
目的のメッセージのリソース ID。

*rMessage*<br/>
`CString`メッセージを配置するオブジェクト。

### <a name="remarks"></a>解説

既定の実装では、 *nID*によって指定された文字列がリソースファイルから読み込まれます。 この関数は、ステータスバーのメッセージ文字列を更新する必要があるときにフレームワークによって呼び出されます。

## <a name="cframewndgettitle"></a><a name="gettitle"></a>CFrameWnd:: GetTitle

ウィンドウオブジェクトのタイトルを取得します。

```
CString GetTitle() const;
```

### <a name="return-value"></a>戻り値

ウィンドウオブジェクトの現在のタイトルを格納している[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

## <a name="cframewndinitialupdateframe"></a><a name="initialupdateframe"></a>CFrameWnd:: InitialUpdateFrame

`IntitialUpdateFrame`を使用して新しいフレームを作成した後に、を呼び出し `Create` ます。

```cpp
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
フレームウィンドウが関連付けられているドキュメントを指します。 NULL にすることができます。

*bMakeVisible*<br/>
TRUE の場合、フレームが表示され、アクティブになることを示します。 FALSE の場合、子孫は表示されません。

### <a name="remarks"></a>解説

これにより、そのフレームウィンドウ内のすべてのビューが呼び出しを受信 `OnInitialUpdate` します。

また、以前にアクティブなビューがない場合は、フレームウィンドウのプライマリビューがアクティブになります。 プライマリビューは、AFX_IDW_PANE_FIRST の子 ID を持つビューです。 最後に、 *Bmakevisible*が0以外の場合、フレームウィンドウが表示されます。 *Bmakevisible*が0の場合、フレームウィンドウの現在のフォーカスと可視状態は変更されません。 フレームワークの File New と File Open の実装を使用する場合は、この関数を呼び出す必要はありません。

## <a name="cframewndinmodalstate"></a><a name="inmodalstate"></a>CFrameWnd:: InModalState

フレームウィンドウがモーダルであるかモードレスであるかを確認するには、このメンバー関数を呼び出します。

```
BOOL InModalState() const;
```

### <a name="return-value"></a>戻り値

Yes の場合は0以外。それ以外の場合は0です。

## <a name="cframewndistracking"></a><a name="istracking"></a>CFrameWnd:: IsTracking

このメンバー関数を呼び出して、ウィンドウの分割バーが現在移動されているかどうかを確認します。

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>戻り値

スプリッター操作が進行中の場合は0以外。それ以外の場合は0です。

## <a name="cframewndloadacceltable"></a><a name="loadacceltable"></a>CFrameWnd:: LoadAccelTable

を呼び出して、指定されたアクセラレータテーブルを読み込みます。

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
アクセラレータリソースの名前を識別します。 リソースに整数の ID が指定されている場合は、MAKEINTRESOURCE を使用します。

### <a name="return-value"></a>戻り値

アクセラレータテーブルが正常に読み込まれた場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

一度に読み込むことができるテーブルは1つだけです。

リソースから読み込まれたアクセラレータテーブルは、アプリケーションの終了時に自動的に解放されます。

を呼び出して `LoadFrame` フレームウィンドウを作成すると、フレームワークはメニューとアイコンリソースと共にアクセラレータテーブルを読み込みます。その後、このメンバー関数への後続の呼び出しは不要になります。

## <a name="cframewndloadbarstate"></a><a name="loadbarstate"></a>CFrameWnd:: LoadBarState

フレームウィンドウによって所有されている各コントロールバーの設定を復元するには、この関数を呼び出します。

```cpp
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
初期化 (INI) ファイルのセクション名、または状態情報が格納されている Windows レジストリ内のキー。

### <a name="remarks"></a>解説

復元される情報には、表示、水平/垂直方向、ドッキング状態、およびコントロールバーの位置が含まれます。

を呼び出す前に、復元する設定をレジストリに書き込む必要があり `LoadBarState` ます。 [CWinApp:: SetRegistryKey](../../mfc/reference/cwinapp-class.md#setregistrykey)を呼び出して、レジストリに情報を書き込みます。 [Savebarstate](#savebarstate)を呼び出して、INI ファイルに情報を書き込みます。

## <a name="cframewndloadframe"></a><a name="loadframe"></a>CFrameWnd:: LoadFrame

を呼び出して、リソース情報からフレームウィンドウを動的に作成します。

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

*nIDResource*<br/>
フレームウィンドウに関連付けられている共有リソースの ID。

*dwDefaultStyle*<br/>
フレームの[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)。 ウィンドウに表示されるドキュメントの名前をタイトルバーに自動的に表示する場合は、FWS_ADDTOTITLE スタイルを指定します。

*pParentWnd*<br/>
フレームの親へのポインター。

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体へのポインター。 このパラメーターには NULL を指定できます。

### <a name="remarks"></a>解説

`CFrameWnd`2 つの手順でオブジェクトを構築します。 まず、コンストラクターを呼び出します。このコンストラクターは、オブジェクトを構築し、 `CFrameWnd` `LoadFrame` を呼び出します。これにより、Windows フレームウィンドウと関連付けられたリソースが読み込まれ、フレームウィンドウがオブジェクトにアタッチされ `CFrameWnd` ます。 *NIDResource*パラメーターは、メニュー、アクセラレータテーブル、アイコン、およびフレームウィンドウのタイトルの文字列リソースを指定します。

すべての `Create` `LoadFrame` フレームウィンドウの作成パラメーターを指定する場合は、ではなくメンバー関数を使用します。

フレームワークは、 `LoadFrame` ドキュメントテンプレートオブジェクトを使用してフレームウィンドウを作成するときにを呼び出します。

フレームワークでは、 *pContext*引数を使用して、フレームウィンドウに接続するオブジェクトを指定します。これには、包含ビューオブジェクトも含まれます。 を呼び出すときに、 *pContext*引数を NULL に設定でき `LoadFrame` ます。

## <a name="cframewndm_bautomenuenable"></a><a name="m_bautomenuenable"></a>CFrameWnd:: m_bAutoMenuEnable

このデータメンバーが有効になっている場合 (既定)、ON_UPDATE_COMMAND_UI または ON_COMMAND のハンドラーを持たないメニュー項目は、ユーザーがメニューを取得すると自動的に無効になります。

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>解説

ON_COMMAND ハンドラーを持つが、ON_UPDATE_COMMAND_UI ハンドラーがないメニュー項目は自動的に有効になります。

このデータメンバーが設定されていると、ツールバーボタンが有効になっているのと同じ方法でメニュー項目が自動的に有効になります。

> [!NOTE]
> `m_bAutoMenuEnable`トップレベルのメニュー項目には影響しません。

このデータメンバーにより、現在の選択に基づいて省略可能なコマンドの実装が簡略化され、メニュー項目を有効または無効にするための ON_UPDATE_COMMAND_UI ハンドラーを記述する必要がなくなります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

## <a name="cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWnd:: NegotiateBorderSpace

このメンバー関数を呼び出して、OLE インプレースアクティベーション中にフレームウィンドウの境界領域をネゴシエートします。

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>パラメーター

*nBorderCmd*<br/>
には、の次のいずれかの値が含まれ `enum BorderCmd` ます。

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*lpRectBorder*<br/>
境界線の座標を指定する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、 `CFrameWnd` OLE 罫線スペースネゴシエーションの実装です。

## <a name="cframewndonbarcheck"></a><a name="onbarcheck"></a>CFrameWnd:: OnBarCheck

指定されたコントロールバーに対してアクションが実行されるたびに呼び出されます。

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
表示されるコントロールバーの ID。

### <a name="return-value"></a>戻り値

コントロールバーが存在する場合は0以外の。それ以外の場合は0です。

## <a name="cframewndoncontexthelp"></a><a name="oncontexthelp"></a>CFrameWnd:: OnContextHelp

インプレース項目の SHIFT + F1 ヘルプを処理します。

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>解説

状況依存のヘルプを有効にするには、

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

ステートメントを `CFrameWnd` クラスメッセージマップに追加します。また、アクセラレータテーブルのエントリ (通常は SHIFT + F1 キー) を追加して、このメンバー関数を有効にします。

アプリケーションが OLE コンテナーの場合、は、 `OnContextHelp` フレームウィンドウオブジェクト内に含まれるすべてのインプレース項目をヘルプモードにします。 カーソルが矢印と疑問符に変わり、ユーザーはマウスポインターを移動し、マウスの左ボタンを押して、ダイアログボックス、ウィンドウ、メニュー、またはコマンドボタンを選択できます。 このメンバー関数は、 `WinHelp` カーソルの下にあるオブジェクトのヘルプコンテキストで Windows 関数を呼び出します。

## <a name="cframewndoncreateclient"></a><a name="oncreateclient"></a>CFrameWnd:: OnCreateClient

の実行中にフレームワークによって呼び出され `OnCreate` ます。

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>パラメーター

*lpcs*<br/>
Windows [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw)構造体へのポインター。

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は呼び出さないでください。

この関数の既定の実装では、 `CView` 可能であれば、 *pContext*に指定された情報からオブジェクトが作成されます。

オブジェクトで渡される値をオーバーライドし `CCreateContext` たり、フレームウィンドウのメインクライアント領域のコントロールの作成方法を変更したりするには、この関数をオーバーライドします。 `CCreateContext`オーバーライドできるメンバーについては、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)クラスを参照してください。

> [!NOTE]
> 構造体で渡された値を置換しません `CREATESTRUCT` 。 情報提供のみを目的としています。 たとえば、初期ウィンドウの四角形をオーバーライドする場合は、 `CWnd` メンバー関数[PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow)をオーバーライドします。

## <a name="cframewndonhidemenubar"></a><a name="onhidemenubar"></a>CFrameWnd:: OnHideMenuBar

この関数は、システムが現在の MFC アプリケーションのメニューバーを非表示にしようとしているときに呼び出されます。

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>解説

このイベントハンドラーを使用すると、アプリケーションは、システムがメニューを非表示にするときにカスタムアクションを実行できます。 メニューが非表示になるのを防ぐことはできませんが、たとえば、メニュースタイルや状態を取得するために他のメソッドを呼び出すことはできます。

## <a name="cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWnd:: OnSetPreviewMode

印刷プレビュー モードの内外にアプリケーションのメイン フレーム ウィンドウを設定するには、このメンバー関数を呼び出します。

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>パラメーター

*bPreview*<br/>
アプリケーションを印刷プレビューモードに配置するかどうかを指定します。 印刷プレビューに配置する場合は TRUE に設定します。プレビューモードをキャンセルする場合は FALSE に設定します。

*pState*<br/>
構造体へのポインター `CPrintPreviewState` 。

### <a name="remarks"></a>解説

既定の実装では、標準のツールバーがすべて無効になり、メインメニューとメインクライアントウィンドウが非表示になります。 これにより、MDI フレームウィンドウが一時的な SDI フレームウィンドウに変わります。

このメンバー関数をオーバーライドすると、印刷プレビュー中のコントロールバーとその他のフレームウィンドウパーツの表示と非表示をカスタマイズできます。 オーバーライドされたバージョン内から基底クラスの実装を呼び出します。

## <a name="cframewndonshowmenubar"></a><a name="onshowmenubar"></a>CFrameWnd:: OnShowMenuBar

この関数は、システムが現在の MFC アプリケーションでメニューバーを表示しようとしているときに呼び出されます。

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>解説

このイベントハンドラーを使用すると、メニューが表示されようとしているときに、アプリケーションでカスタムアクションを実行できます。 メニューが表示されないようにすることはできませんが、たとえば、メニュースタイルや状態を取得するために他のメソッドを呼び出すことはできます。

## <a name="cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a>CFrameWnd:: OnUpdateControlBarMenu

関連付けられたメニューが更新されたときにフレームワークによって呼び出されます。

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*pCmdUI*<br/>
Update コマンドを生成したメニューを表す[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトへのポインター。 更新ハンドラーは、PCmdUI を介してオブジェクトの[Enable](../../mfc/reference/ccmdui-class.md#enable)メンバー関数を呼び出し、 `CCmdUI` ユーザーインターフェイスを更新します。 *pCmdUI*

## <a name="cframewndrecalclayout"></a><a name="recalclayout"></a>CFrameWnd:: RecalcLayout

標準コントロールバーのオン/オフを切り替えるか、またはフレームウィンドウのサイズが変更されたときに、フレームワークによって呼び出されます。

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*bNotify*<br/>
フレームウィンドウのアクティブなインプレース項目がレイアウト変更の通知を受信するかどうかを決定します。 TRUE の場合、項目には通知されます。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメンバー関数の既定の実装では、 `CWnd` メンバー関数を呼び出し `RepositionBars` て、フレーム内のすべてのコントロールバーと、メインクライアントウィンドウ (通常 `CView` はまたは MDICLIENT) の位置を変更します。

このメンバー関数をオーバーライドして、フレームウィンドウのレイアウトが変更された後のコントロールバーの外観と動作を制御します。 たとえば、コントロールバーのオン/オフを切り替えたり、別のコントロールバーを追加したりするときに、このメソッドを呼び出します。

## <a name="cframewndrectdefault"></a><a name="rectdefault"></a>CFrameWnd:: rectDefault

ウィンドウを作成するときに、ウィンドウ `CRect` の初期サイズと位置を Windows が選択できるように、この静的をパラメーターとして渡します。

```
static AFX_DATA const CRect rectDefault;
```

## <a name="cframewndsavebarstate"></a><a name="savebarstate"></a>CFrameWnd:: SaveBarState

フレームウィンドウによって所有されている各コントロールバーに関する情報を格納するには、この関数を呼び出します。

```cpp
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
初期化ファイル内のセクションの名前、または状態情報が格納されている Windows レジストリ内のキー。

### <a name="remarks"></a>解説

この情報は、 [Loadbarstate](#loadbarstate)を使用して初期化ファイルから読み取ることができます。 格納される情報には、表示、水平/垂直方向、ドッキング状態、およびコントロールバーの位置が含まれます。

## <a name="cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a>CFrameWnd:: Setactiveプレビュービュー

指定したビューをリッチプレビューのアクティブビューに指定します。

```cpp
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>パラメーター

*pViewNew*<br/>
アクティブにするビューへのポインター。

### <a name="remarks"></a>解説

## <a name="cframewndsetactiveview"></a><a name="setactiveview"></a>CFrameWnd:: SetActiveView

アクティブなビューを設定するには、このメンバー関数を呼び出します。

```cpp
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*pViewNew*<br/>
[CView](../../mfc/reference/cview-class.md)オブジェクトへのポインターを指定します。または、アクティブなビューがない場合は NULL を指定します。

*bNotify*<br/>
ビューにアクティベーションが通知されるかどうかを指定します。 TRUE の場合、 `OnActivateView` 新しいビューに対してが呼び出されます。 FALSE の場合、は呼び出されません。

### <a name="remarks"></a>解説

ユーザーがフレームウィンドウ内のビューにフォーカスを変更すると、フレームワークはこの関数を自動的に呼び出します。 明示的 `SetActiveView` にを呼び出して、指定されたビューにフォーカスを移すことができます。

## <a name="cframewndsetdockstate"></a><a name="setdockstate"></a>CFrameWnd:: SetDockState

オブジェクトに格納されている状態情報を `CDockState` フレームウィンドウのコントロールバーに適用するには、このメンバー関数を呼び出します。

```cpp
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
格納されている状態をフレームウィンドウのコントロールバーに適用します。

### <a name="remarks"></a>解説

コントロールバーの以前の状態を復元するには、格納されている状態を `CDockState::LoadState` またはで読み込み `Serialize` 、を使用し `SetDockState` てフレームウィンドウのコントロールバーに適用します。 以前の状態は、 `CDockState` と共にオブジェクトに格納されます。`GetDockState`

## <a name="cframewndsetmenubarstate"></a><a name="setmenubarstate"></a>CFrameWnd:: SetMenuBarState

現在の MFC アプリケーションのメニューの表示状態を非表示または表示に設定します。

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nState*|からメニューを表示するか非表示にするかを指定します。 *NState*パラメーターには、次の値を指定できます。<br /><br />-AFX_MBS_VISIBLE (0x01)-非表示になっている場合にメニューを表示しますが、表示されている場合は効果がありません。<br />-AFX_MBS_HIDDEN (0x02)-メニューが表示されている場合は非表示にしますが、非表示になっている場合は効果がありません。|

### <a name="return-value"></a>戻り値

このメソッドがメニューの状態を正常に変更した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ランタイムエラーが発生した場合、このメソッドはデバッグモードでアサートし、 [CException](../../mfc/reference/cexception-class.md)クラスから派生した例外を発生させます。

## <a name="cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a>CFrameWnd:: SetMenuBarVisibility

現在の MFC アプリケーションのメニューの既定の動作を、非表示にするか表示するかを設定します。

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nStyle*|からメニューが既定で非表示になるか、表示され、フォーカスがあるかを指定します。 *Nstyle*パラメーターには、次の値を指定できます。<br /><br />-AFX_MBV_KEEPVISIBLE (0x01)-<br />     メニューは常に表示され、既定ではフォーカスがありません。<br />-AFX_MBV_DISPLAYONFOCUS (0x02)-<br />     既定では、このメニューは非表示になっています。 メニューが非表示になっている場合は、ALT キーを押してメニューを表示し、フォーカスを与えます。 メニューが表示されている場合は、ALT キーまたは ESC キーを押してメニューを非表示にします。<br />-AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (ビットごとの組み合わせ (または))-メニューは既定で非表示になっています。 メニューが非表示になっている場合は、F10 キーを押してメニューを表示し、フォーカスを与えます。 メニューが表示されている場合は、F10 キーを押して、メニューにフォーカスを設定します。 メニューが表示されるのは、ALT キーまたは ESC キーを押すと非表示になります。|

### <a name="remarks"></a>解説

*Nstyle*パラメーターの値が有効でない場合、このメソッドはデバッグモードでアサートし、リリースモードで[Cinvalidargexception](../../mfc/reference/cinvalidargexception-class.md)を発生させます。 他のランタイムエラーが発生した場合、このメソッドはデバッグモードでアサートし、 [CException](../../mfc/reference/cexception-class.md)クラスから派生した例外を発生させます。

このメソッドは、Windows Vista 以降用に作成されたアプリケーションのメニューの状態に影響します。

## <a name="cframewndsetmessagetext"></a><a name="setmessagetext"></a>CFrameWnd:: SetMessageText

ID が0のステータスバーペインに文字列を配置するには、この関数を呼び出します。

```cpp
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
ステータスバーに配置する文字列をポイントします。

*nID*<br/>
ステータスバーに配置する文字列の文字列リソース ID。

### <a name="remarks"></a>解説

これは、通常、ステータスバーの左端、最長のウィンドウです。

## <a name="cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a>CFrameWnd:: Setて Barposition

タスクバーに表示される Windows 7 プログレスバーの現在位置を設定します。

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>パラメーター

*N進行 Spos*<br/>
設定する位置を指定します。 この値は、によって設定された範囲内である必要があり `SetProgressBarRange` ます。

### <a name="remarks"></a>解説

## <a name="cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a>CFrameWnd:: Set進捗を Barrange

タスクバーに表示される Windows 7 のプログレスバーの範囲を設定します。

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>パラメーター

*nRangeMin*<br/>
最小値。

*nRangeMax*<br/>
最大値。

### <a name="remarks"></a>解説

## <a name="cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a>CFrameWnd:: Set進捗 Barstate

タスクバーボタンに表示される進行状況インジケーターの種類と状態を設定します。

```cpp
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>パラメーター

*tbpFlags*<br/>
プログレスボタンの現在の状態を制御するフラグ。 すべての状態が相互に排他的であるため、次のフラグのいずれか1つだけを指定してください: TBPF_NOPROGRESS、TBPF_INDETERMINATE、TBPF_NORMAL、TBPF_ERROR、TBPF_PAUSED。

### <a name="remarks"></a>解説

## <a name="cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a>CFrameWnd:: SetTaskbarOverlayIcon

オーバーロードされます。 タスクバーボタンにオーバーレイを適用して、アプリケーションの状態を示すか、ユーザーに通知します。

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);

BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>パラメーター

*nIDResource*<br/>
オーバーレイとして使用するアイコンのリソース ID を指定します。 詳細については、 *hIcon*の説明を参照してください。

*lpcszDescr*<br/>
ユーザー補助のためにオーバーレイによって伝達される情報の代替テキストバージョンを提供する文字列へのポインター。

*hIcon*<br/>
オーバーレイとして使用するアイコンのハンドル。 これは小さいアイコンで、96のドット/インチ (dpi) で16x16 ピクセルを測定する必要があります。 オーバーレイアイコンが既にタスクバーボタンに適用されている場合は、既存のオーバーレイが置き換えられます。 この値には NULL を指定できます。 NULL 値の処理方法は、タスクバーボタンが1つのウィンドウまたはウィンドウのグループを表すかどうかによって異なります。 必要なくなったときに、そのアプリケーションが*hIcon*を解放する必要があります。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。OS のバージョンが Windows 7 より小さい場合、またはアイコンの設定中にエラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cframewndsettitle"></a><a name="settitle"></a>CFrameWnd:: SetTitle

ウィンドウオブジェクトのタイトルを設定します。

```cpp
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>パラメーター

*lpszTitle*<br/>
ウィンドウオブジェクトのタイトルを含む文字列へのポインター。

## <a name="cframewndshowcontrolbar"></a><a name="showcontrolbar"></a>CFrameWnd:: ShowControlBar

このメンバー関数を呼び出して、コントロールバーの表示と非表示を切り替えます。

```cpp
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
表示または非表示にするコントロールバーへのポインター。

*bShow*<br/>
TRUE の場合は、コントロールバーを表示することを指定します。 FALSE の場合は、コントロールバーを非表示にすることを指定します。

*bDelay*<br/>
TRUE の場合、コントロールバーが表示されます。 FALSE の場合は、コントロールバーをすぐに表示します。

## <a name="cframewndshowownedwindows"></a><a name="showownedwindows"></a>CFrameWnd:: ShowOwnedWindows

このメンバー関数を呼び出して、オブジェクトの子孫であるすべてのウィンドウを表示し `CFrameWnd` ます。

```cpp
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
所有しているウィンドウを表示するか非表示にするかを指定します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CRuntimeClass 構造体](../../mfc/reference/cruntimeclass-structure.md)
