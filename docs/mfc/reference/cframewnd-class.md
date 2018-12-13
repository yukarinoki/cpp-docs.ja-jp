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
ms.openlocfilehash: 3259780d73004c9d1654c26434b55627923cfe23
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178793"
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
|[CFrameWnd::CFrameWnd](#cframewnd)|`CFrameWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFrameWnd::ActivateFrame](#activateframe)|フレームを表示および使用できるユーザーを作成します。|
|[CFrameWnd::BeginModalState](#beginmodalstate)|フレーム ウィンドウをモーダルに設定します。|
|[CFrameWnd::Create](#create)|作成し、初期化に関連付けられている Windows フレーム ウィンドウへの呼び出し、`CFrameWnd`オブジェクト。|
|[CFrameWnd::CreateView](#createview)|派生していないフレーム内でビューを作成します`CView`します。|
|[CFrameWnd::DockControlBar](#dockcontrolbar)|コントロール バーをドッキングします。|
|[CFrameWnd::EnableDocking](#enabledocking)|ドッキング コントロール バーを使用できます。|
|[CFrameWnd::EndModalState](#endmodalstate)|フレーム ウィンドウのモーダル状態を終了します。 により、すべてのウィンドウで無効になって`BeginModalState`します。|
|[切り離すには](#floatcontrolbar)|コントロール バーを寄せて配置されます。|
|[CFrameWnd::GetActiveDocument](#getactivedocument)|返します、アクティブな`CDocument`オブジェクト。|
|[CFrameWnd::GetActiveFrame](#getactiveframe)|返します、アクティブな`CFrameWnd`オブジェクト。|
|[CFrameWnd::GetActiveView](#getactiveview)|返します、アクティブな`CView`オブジェクト。|
|[CFrameWnd::GetControlBar](#getcontrolbar)|コントロール バーを取得します。|
|[CFrameWnd::GetDockState](#getdockstate)|フレーム ウィンドウのドッキング状態を取得します。|
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|現在の MFC アプリケーションのメニューの表示状態を取得します。|
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|現在の MFC アプリケーションのメニューの既定の動作をまたは非表示にするかどうかを示します。|
|[CFrameWnd::GetMessageBar](#getmessagebar)|ステータス バーのフレーム ウィンドウに属するへのポインターを返します。|
|[CFrameWnd::GetMessageString](#getmessagestring)|コマンド ID に対応するメッセージを取得します。|
|[CFrameWnd::GetTitle](#gettitle)|関連するコントロール バーのタイトルを取得します。|
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|により、`OnInitialUpdate`メンバー関数が呼び出されるフレーム ウィンドウのすべてのビューに属しています。|
|[CFrameWnd::InModalState](#inmodalstate)|フレーム ウィンドウがモーダル状態かどうかを示す値を返します。|
|[CFrameWnd::IsTracking](#istracking)|分割バーは現在移動中かを決定します。|
|[CFrameWnd::LoadAccelTable](#loadacceltable)|アクセラレータ テーブルの読み込みに呼び出します。|
|[CFrameWnd::LoadBarState](#loadbarstate)|コントロール バーの設定を復元する場合に呼び出します。|
|[CFrameWnd::LoadFrame](#loadframe)|リソースの情報からフレーム ウィンドウを動的に作成するを呼び出します。|
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|フレーム ウィンドウの境界領域をネゴシエートします。|
|[CFrameWnd::OnBarCheck](#onbarcheck)|指定したコントロール バーで、アクションが実行されるたびに呼び出されます。|
|[受信](#oncontexthelp)|インプレース項目については、shift キーを押しながら f1 キーを処理します。|
|[Cframewnd::onsetpreviewmode](#onsetpreviewmode)|印刷プレビュー モードの内外には、アプリケーションのメイン フレーム ウィンドウを設定します。|
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|関連付けられているメニューが更新されたときに、フレームワークによって呼び出されます。|
|[表示](#recalclayout)|コントロール バーの位置を変更、`CFrameWnd`オブジェクト。|
|[CFrameWnd::SaveBarState](#savebarstate)|コントロール バーの設定を保存する呼び出しです。|
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|リッチ プレビュー用のアクティブなビューを指定されたビューを指定します。|
|[CFrameWnd::SetActiveView](#setactiveview)|アクティブな設定`CView`オブジェクト。|
|[CFrameWnd::SetDockState](#setdockstate)|メイン ウィンドウで、フレーム ウィンドウのドッキングを呼び出します。|
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|非表示または表示は、現在の MFC アプリケーションで、メニューの表示状態を設定します。|
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|非表示または非表示には、現在の MFC アプリケーションで、メニューの既定の動作を設定します。|
|[CFrameWnd::SetMessageText](#setmessagetext)|標準的なステータス バーのテキストを設定します。|
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|タスク バーに表示される Windows 7 の進行状況バーの現在位置を設定します。|
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|タスク バーに表示される Windows 7 の進行状況バーの範囲を設定します。|
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|タスク バー ボタンに表示される進行状況インジケーターの状態の種類を設定します。|
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|オーバーロードされます。 アプリケーションの状態をユーザーに通知するかを示すタスク バー ボタンにオーバーレイが適用されます。|
|[CFrameWnd::SetTitle](#settitle)|関連するコントロール バーのタイトルを設定します。|
|[CFrameWnd::ShowControlBar](#showcontrolbar)|コントロール バーを表示する呼び出しです。|
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|子孫であるすべてのウィンドウを示しています、`CFrameWnd`オブジェクト。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CFrameWnd::OnCreateClient](#oncreateclient)|フレームのクライアント ウィンドウを作成します。|
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|現在の MFC アプリケーションのメニューを非表示にする前に呼び出されます。|
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|現在の MFC アプリケーションのメニューが表示される前に呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|コントロールに自動では、有効にし、メニュー項目の機能を無効にします。|
|[CFrameWnd::rectDefault](#rectdefault)|この静的渡す`CRect`の作成時にパラメーターとして、`CFrameWnd`ウィンドウの初期サイズと位置を選択する Windows を許可するオブジェクト。|

## <a name="remarks"></a>Remarks

アプリケーション用の便利なフレーム ウィンドウを作成するには、派生クラスを`CFrameWnd`します。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

フレーム ウィンドウを作成する 3 つの方法はあります。

- 使用して直接構築[作成](#create)です。

- 使用して直接構築[LoadFrame](#loadframe)します。

- 間接的に構築ドキュメント テンプレートを使用します。

いずれかを呼び出す前に`Create`または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウ オブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に`Create`、ウィンドウ クラスを登録することも、 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。

使用して、`Create`メンバー関数は、イミディ エイト引数フレームの作成パラメーターを渡す。

`LoadFrame` も少ない引数が必要です`Create`、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースからほとんどの既定値を取得します。 アクセスできる`LoadFrame`、これらすべてのリソースは resource ID (たとえば、IDR_MAINFRAME) が同じである必要があります。

ときに、`CFrameWnd`オブジェクトには、ビューやドキュメントが含まれています、これらは間接的に作成、プログラマが直接の代わりに、フレームワークによって。 `CDocTemplate`オブジェクトは、フレームの作成、コンテナーのビューの作成と適切なドキュメント ビューの接続を調整します。 パラメーター、`CDocTemplate`コンス トラクターを指定、 `CRuntimeClass` 3 つのクラスの関係 (ドキュメント、フレーム、および表示)。 A`CRuntimeClass`オブジェクトが動的に (たとえば、ファイルの新しいコマンドや複数ドキュメント インターフェイス (MDI) ウィンドウの新しいコマンドを使用) して、ユーザーが指定したときに、新しいフレームを作成するために、フレームワークによって使用されます。

フレーム ウィンドウ クラスから派生した`CFrameWnd`RUNTIME_CLASS 機構が正常に動作する上記の順序で DECLARE_DYNCREATE で宣言する必要があります。

A `CFrameWnd` Windows の一般的なアプリケーションのメイン ウィンドウの次の関数を実行する既定の実装が含まれています。

- A`CFrameWnd`フレーム ウィンドウには、Windows のアクティブなウィンドウの現在の入力フォーカスから独立している現在アクティブなビューの追跡。 アクティブなビューを呼び出すことによって通知、フレームが再アクティブ化された`CView::OnActivateView`します。

- コマンド メッセージおよびによって処理されるものも含め、多くの一般的なフレーム通知メッセージ、 `OnSetFocus`、 `OnHScroll`、および`OnVScroll`関数の`CWnd`、委任することは、`CFrameWnd`フレーム ウィンドウ、現在アクティブなビュー。

- 現在アクティブなビュー (またはの場合は、MDI フレームの現在アクティブな MDI 子フレーム ウィンドウ) には、フレーム ウィンドウのキャプションを判断できます。 フレーム ウィンドウの FWS_ADDTOTITLE スタイル ビットをオフにすることで、この機能を無効にできます。

- A`CFrameWnd`フレーム ウィンドウは、コントロール バー、ビュー、および他の子ウィンドウ フレーム ウィンドウのクライアント領域内の位置を管理します。 フレーム ウィンドウは、ツールバーとその他のコントロール バーのボタンのアイドル時間の更新も行います。 A`CFrameWnd`フレーム ウィンドウはオンとオフ、ツールバーとステータス バーを切り替えるためのコマンドの既定の実装もあります。

- A`CFrameWnd`フレーム ウィンドウは、メイン メニュー バーを管理します。 ポップアップ メニューが表示されたら、フレーム ウィンドウ、UPDATE_COMMAND_UI メカニズムを使用して、どのメニュー項目を有効、無効になっている、またはチェックを決定します。 ユーザーがメニュー項目を選択、フレーム ウィンドウは、そのコマンドのメッセージ文字列でステータス バーを更新します。

- A`CFrameWnd`フレーム ウィンドウがキーボード アクセラレータを自動的に変換するオプションのアクセラレータ テーブル。

- A`CFrameWnd`フレーム ウィンドウに設定する省略可能なヘルプ ID`LoadFrame`状況依存のヘルプに使用されます。 フレーム ウィンドウは、メイン セミモーダル状態 (SHIFT + F1) 状況依存のヘルプと印刷プレビュー モードなどのオーケストレーターです。

- A`CFrameWnd`フレーム ウィンドウのフレーム ウィンドウにファイル マネージャーからのドラッグ アンド ドロップのファイルが開きます。 フレーム ウィンドウはまたはユーザーがファイル マネージャーで、データ ファイルを開いたときに発生しますダイナミック データ エクス (チェンジ DDE) オープン要求に応答ファイルの拡張子が登録され、アプリケーションに関連付けられている場合、 `ShellExecute` Windows 関数が呼び出されます。

- フレーム ウィンドウがアプリケーションのメイン ウィンドウの場合 (つまり、 `CWinThread::m_pMainWnd`)、ユーザーは、アプリケーションを閉じるときに、フレーム ウィンドウには、ユーザー、変更されたドキュメントを保存するメッセージが表示されます (の`OnClose`と`OnQueryEndSession`)。

- フレーム ウィンドウがアプリケーションのメイン ウィンドウの場合は、フレーム ウィンドウ、WinHelp を実行するためのコンテキストです。 WINHELP をシャット ダウンは、フレーム ウィンドウを終了します。EXE 場合、このアプリケーションのヘルプを起動されたことができます。

C++ を使用しないでください**削除**フレーム ウィンドウを破棄する演算子。 代わりに、`CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ のオブジェクトが削除されます。 ユーザーが既定値であるフレーム ウィンドウを閉じるときに`OnClose`ハンドラーが呼び出す`DestroyWindow`します。

詳細については`CFrameWnd`を参照してください[フレーム Windows](../../mfc/frame-windows.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="activateframe"></a>  CFrameWnd::ActivateFrame

アクティブ化し、ユーザーに表示および使用できるにするように、フレーム ウィンドウを復元するには、このメンバー関数を呼び出します。

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>パラメーター

*nCmdShow*<br/>
渡すパラメーターを指定します[また](../../mfc/reference/cwnd-class.md#showwindow)します。 既定では、フレームが表示され、正しく復元します。

### <a name="remarks"></a>Remarks

このメンバー関数は通常、DDE、OLE、フレーム ウィンドウまたはその内容を表示することがありますをユーザーにその他のイベントなどの非ユーザー インターフェイス イベントの後に呼び出されます。

既定の実装、フレームがアクティブに Z オーダーの最上位し、必要に応じて、アプリケーションのメイン フレーム ウィンドウと同じ手順を実行します。

フレームがアクティブにする方法を変更するには、このメンバー関数をオーバーライドします。 たとえば、MDI 子ウィンドウを最大化を強制することができます。 適切な機能を追加し、明示的な基底クラスのバージョンを呼び出す*nCmdShow*します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

##  <a name="beginmodalstate"></a>  CFrameWnd::BeginModalState

フレーム ウィンドウをモーダルにします。

```
virtual void BeginModalState();
```

##  <a name="cframewnd"></a>  CFrameWnd::CFrameWnd

構築、`CFrameWnd`オブジェクトしますが、表示されるフレーム ウィンドウは作成されません。

```
CFrameWnd();
```

### <a name="remarks"></a>Remarks

呼び出す`Create`表示のウィンドウを作成します。

##  <a name="create"></a>  CFrameWnd::Create

作成し、初期化に関連付けられている Windows フレーム ウィンドウへの呼び出し、`CFrameWnd`オブジェクト。

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
Windows クラスの名前を示す文字の null で終わる文字列を指します。 クラス名が登録されている任意の名前を指定できます、`AfxRegisterWndClass`グローバル関数または`RegisterClass`Windows 関数。 NULL の場合は、定義済みの既定値を使用して`CFrameWnd`属性。

*したとき*<br/>
ウィンドウの名前を表す null で終わる文字列へのポインター。 タイトル バーのテキストとして使用します。

*dwStyle*<br/>
ウィンドウを指定[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)属性。 タイトル バーのウィンドウで表されるドキュメントの名前を自動的に表示する場合は、FWS_ADDTOTITLE スタイルが含まれます。

*rect*<br/>
ウィンドウの位置とサイズを指定します。 *RectDefault*値により、Windows を新しいウィンドウの位置とサイズを指定します。

*pParentWnd*<br/>
このフレーム ウィンドウの親ウィンドウを指定します。 このパラメーターは、最上位レベルのフレーム ウィンドウの NULL を指定する必要があります。

*lpszMenuName*<br/>
ウィンドウで使用する] メニューの [リソースの名前を識別します。 メニューに、文字列ではなく整数 ID がある場合は、されるときを使用します。 このパラメーターは、NULL を指定できます。

*dwExStyle*<br/>
ウィンドウの拡張[スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)属性。

*pContext*<br/>
ポインターを指定します、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターは、NULL を指定できます。

### <a name="return-value"></a>戻り値

初期化が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

構築、 `CFrameWnd` 2 つのステップ内のオブジェクト。 最初に、構築するコンス トラクターを呼び出す、`CFrameWnd`オブジェクトを呼び出して`Create`、Windows フレーム ウィンドウを作成しにアタッチする`CFrameWnd`オブジェクト。 `Create` ウィンドウのクラス名とウィンドウの名前を初期化し、そのスタイル、親、および関連メニューの既定値を登録します。

使用`LoadFrame`なく`Create`引数を指定する代わりに、そのリソースからフレーム ウィンドウを読み込めません。

##  <a name="createview"></a>  CFrameWnd::CreateView

呼び出す`CreateView`フレーム内でビューを作成します。

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

ポインター、`CWnd`成功。 それ以外の場合に NULL の場合は、オブジェクト。

### <a name="remarks"></a>Remarks

「ビュー」を作成するこのないメンバー関数を使用して`CView`-フレーム内で派生します。 呼び出した後`CreateView`、手動でアクティブにビューを設定し、表示されるように設定する必要があります。 によってこれらのタスクが自動的に実行されない`CreateView`します。

##  <a name="dockcontrolbar"></a>  CFrameWnd::DockControlBar

フレーム ウィンドウにドッキング コントロール バーをによりします。

```
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
ドッキング コントロール バーへのポインター。

*辺*<br/>
フレーム ウィンドウにドッキングのどの辺を決定します。 0 または 1 つ以上の次を指定できます。

- フレーム ウィンドウの最上位の側にドッキングする AFX_IDW_DOCKBAR_TOP。

- フレーム ウィンドウの下の辺に AFX_IDW_DOCKBAR_BOTTOM ドッキングします。

- フレーム ウィンドウの左側にドッキングする AFX_IDW_DOCKBAR_LEFT。

- フレーム ウィンドウの右側にドッキングする AFX_IDW_DOCKBAR_RIGHT。

0 の場合は、コントロール バーをドッキング先のフレーム ウィンドウの任意の辺にドッキングできます。

*lpRect*<br/>
変換先のフレーム ウィンドウの非クライアント領域内のコントロール バーのドッキング先の画面座標で決定します。

### <a name="remarks"></a>Remarks

コントロール バーの両方への呼び出しで指定されたフレーム ウィンドウの辺のいずれかにドッキング[CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)と[CFrameWnd::EnableDocking](#enabledocking)します。 選択した証明書側はによって決まります*辺*します。

##  <a name="enabledocking"></a>  CFrameWnd::EnableDocking

フレーム ウィンドウのドッキング可能なコントロール バーを有効にするには、この関数を呼び出します。

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

*dwDockStyle*<br/>
フレーム ウィンドウのどの辺がドッキング コントロール バーに対してサイトとして使用できるかを指定します。 次の 1 つ以上を指定できます。

- CBRS_ALIGN_TOP は、クライアント領域の上部にドッキングできます。

- CBRS_ALIGN_BOTTOM は、クライアント領域の下部にドッキングできます。

- CBRS_ALIGN_LEFT は、クライアント領域の左側にドッキングできます。

- CBRS_ALIGN_RIGHT は、クライアント領域の右側にドッキングできます。

- CBRS_ALIGN_ANY は、クライアント領域の任意の辺にドッキングできます。

### <a name="remarks"></a>Remarks

既定では、コントロール バーの次の順序で、フレーム ウィンドウの端にドッキング: top、bottom、left、right。

### <a name="example"></a>例

  例をご覧ください[用意されて](../../mfc/reference/ctoolbar-class.md#create)します。

##  <a name="endmodalstate"></a>  CFrameWnd::EndModalState

フレーム ウィンドウをモーダルからモードレスに変更します。

```
virtual void EndModalState();
```

### <a name="remarks"></a>Remarks

`EndModalState` により、すべてのウィンドウで無効になって[BeginModalState](#beginmodalstate)します。

##  <a name="floatcontrolbar"></a>  切り離すには

この関数をいないフレーム ウィンドウにドッキング コントロール バーを呼び出します。

```
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
フローティングするコントロール バーへのポインター。

*ポイント*<br/>
内の位置を画面座標では、コントロール バーの左上隅を配置する場所。

*dwStyle*<br/>
新しいフレーム ウィンドウ内で、コントロール バーを水平方向または垂直方向に配置するかどうかを指定します。 次のいずれかを指定できます。

- CBRS_ALIGN_TOP では、コントロール バーが垂直方向に印刷します。

- CBRS_ALIGN_BOTTOM では、コントロール バーが垂直方向に印刷します。

- CBRS_ALIGN_LEFT では、コントロール バーが水平方向します。

- CBRS_ALIGN_RIGHT では、コントロール バーが水平方向します。

水平および垂直方向の両方の方向を指定するスタイルが渡された場合、ツールバーは方向に配置する水平方向にします。

### <a name="remarks"></a>Remarks

通常、これは、アプリケーションの起動時にプログラムが前回の実行から設定を復元するときにします。

ユーザーがコントロール バーをドッキングが利用でない場所にドラッグするときにマウスの左ボタンを解放することによってドロップ操作を起こしたとき、この関数は、フレームワークによって呼び出されます。

##  <a name="getactivedocument"></a>  CFrameWnd::GetActiveDocument

現在のポインターを取得するには、このメンバー関数を呼び出す`CDocument`現在アクティブなビューにアタッチします。

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>戻り値

現在へのポインター [CDocument](../../mfc/reference/cdocument-class.md)します。 現在のドキュメントがない場合は、NULL を返します。

##  <a name="getactiveframe"></a>  CFrameWnd::GetActiveFrame

マルチ ドキュメント インターフェイス (MDI) 子ウィンドウの MDI フレーム ウィンドウ、アクティブなへのポインターを取得するには、このメンバー関数を呼び出します。

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>戻り値

アクティブな MDI 子ウィンドウへのポインター。 かどうか、アプリケーションは、SDI アプリケーション、または MDI フレーム ウィンドウがアクティブなドキュメント、暗黙の型を持たない**この**ポインターが返されます。

### <a name="remarks"></a>Remarks

アクティブな MDI 子がないかどうか、またはアプリケーションは、暗黙的なシングル ドキュメント インターフェイス (SDI)**この**ポインターが返されます。

##  <a name="getactiveview"></a>  CFrameWnd::GetActiveView

フレーム ウィンドウにアタッチされているアクティブなビュー (あれば) へのポインターを取得するには、このメンバー関数を呼び出す ( `CFrameWnd`)。

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>戻り値

現在へのポインター [CView](../../mfc/reference/cview-class.md)します。 現在のビューがない場合は、NULL を返します。

### <a name="remarks"></a>Remarks

この関数は、MDI メイン フレーム ウィンドウの呼び出されたときに NULL を返します ( `CMDIFrameWnd`)。 MDI アプリケーションでは、MDI メイン フレーム ウィンドウに関連付けられているビューはありません。 代わりに、各個々 の子ウィンドウ ( `CMDIChildWnd`) は 1 つまたは複数の関連するビューがあります。 MDI アプリケーションでアクティブなビューは、まずアクティブな MDI 子ウィンドウを検索して、その子ウィンドウのアクティブなビューを検索して取得できます。 関数を呼び出すことによってアクティブな MDI 子ウィンドウが見つかりません`MDIGetActive`または`GetActiveFrame`の次のとおり。

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

##  <a name="getcontrolbar"></a>  CFrameWnd::GetControlBar

呼び出す`GetControlBar`ID に関連付けられているコントロール バーにアクセスするには

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロール バーの ID 番号。

### <a name="return-value"></a>戻り値

ID に関連付けられているコントロール バーへのポインター

### <a name="remarks"></a>Remarks

*NID*パラメーターに渡される一意の識別子を指す、`Create`コントロール バーのメソッド。 コントロール バーの詳細については、のトピックを参照してください[コントロール バー](../../mfc/control-bars.md)します。

`GetControlBar` コントロール バーを返す場合でも、それが固定されていない、現在フレームの子ウィンドウはできません。

##  <a name="getdockstate"></a>  CFrameWnd::GetDockState

内のフレーム ウィンドウのコントロール バーの状態情報を格納するには、このメンバー関数を呼び出す、`CDockState`オブジェクト。

```
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>パラメーター

*state*<br/>
戻り時に、フレーム ウィンドウのコントロール バーの現在の状態が含まれています。

### <a name="remarks"></a>Remarks

内容を記述することができますし、`CDockState`を使用してストレージ`CDockState::SaveState`または`Serialize`します。 後で、コントロール バーを以前の状態に復元する場合での状態を読み込む`CDockState::LoadState`または`Serialize`、呼び出して`SetDockState`フレーム ウィンドウのコントロール バーに、以前の状態を適用します。

##  <a name="getmenubarstate"></a>  CFrameWnd::GetMenuBarState

現在の MFC アプリケーションのメニューの表示状態を取得します。

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>戻り値

戻り値は、次の値を持つことができます。

- AFX_MBS_VISIBLE (0x01) で、メニューが表示されます。

- AFX_MBS_HIDDEN (0x02) - メニューは表示されません。

### <a name="remarks"></a>Remarks

このメソッドはデバッグ モードでアサートし、派生した例外を発生させます。 ランタイム エラーが発生した場合、 [CException](../../mfc/reference/cexception-class.md)クラス。

##  <a name="getmenubarvisibility"></a>  CFrameWnd::GetMenuBarVisibility

現在の MFC アプリケーションのメニューの既定の状態を表示または非表示にするかどうかを示します。

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>戻り値

このメソッドは、次の値のいずれかを返します。

- AFX_MBV_KEEPVISIBLE (0x01) で、メニューが表示されるすべての時間、および既定値には、フォーカスはありません。

- AFX_MBV_DISPLAYONFOCUS (0x02) - 既定では、メニューは表示されません。 メニューが表示されない場合は、メニューを表示し、フォーカスに ALT キーを押します。 メニューが表示される場合は、非表示にする、alt キーまたは ESC キーを押します。

- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (ビットごとの組み合わせ (OR)) - 既定では、メニューは表示されません。 メニューが表示されない場合は、メニューを表示し、フォーカスを F10 キーを押します。 メニューが表示される場合は、オンまたはオフ、メニューにフォーカスを切り替える F10 キーを押します。 非表示にする、alt キーまたは ESC キーを押すまで、メニューが表示されます。

### <a name="remarks"></a>Remarks

このメソッドはデバッグ モードでアサートし、派生した例外を発生させます。 ランタイム エラーが発生した場合、 [CException](../../mfc/reference/cexception-class.md)クラス。

##  <a name="getmessagebar"></a>  CFrameWnd::GetMessageBar

ステータス バーにポインターを取得するには、このメンバー関数を呼び出します。

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>戻り値

ステータス バーのウィンドウへのポインター。

##  <a name="getmessagestring"></a>  CFrameWnd::GetMessageString

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
`CString` メッセージを格納するオブジェクトです。

### <a name="remarks"></a>Remarks

既定の実装がで指定された文字列を単に読み込みます*nID*リソース ファイルから。 ステータス バーのメッセージ文字列は、更新が必要なときに、この関数は、フレームワークによって呼び出されます。

##  <a name="gettitle"></a>  CFrameWnd::GetTitle

ウィンドウ オブジェクトのタイトルを取得します。

```
CString GetTitle() const;
```

### <a name="return-value"></a>戻り値

A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ウィンドウ オブジェクトの現在のタイトルを含むオブジェクト。

##  <a name="initialupdateframe"></a>  CFrameWnd::InitialUpdateFrame

呼び出す`IntitialUpdateFrame`で新しいフレームを作成した後`Create`します。

```
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
フレーム ウィンドウが関連付けられているドキュメントへのポインター。 NULL にすることができます。

*bMakeVisible*<br/>
TRUE の場合は、フレームは、表示され、アクティブになる必要がありますを示します。 FALSE の場合、子孫は一切表示します。

### <a name="remarks"></a>Remarks

これにより、受信するには、そのフレーム ウィンドウ内のすべてのビュー、`OnInitialUpdate`呼び出し。

また場合は、存在していなかった以前、アクティブなビュー、フレーム ウィンドウのプライマリ ビューがアクティブになります。 プライマリ ビューは、子 AFX_IDW_PANE_FIRST の ID を持つビューです。 最後に、フレーム ウィンドウが表示される場合*bMakeVisible*が 0 以外。 場合*bMakeVisible*が 0 の場合、現在フォーカスをフレーム ウィンドウの表示状態は変更されません。 新しいファイルとファイルを開くのフレームワークの実装を使用する場合は、この関数を呼び出す必要はありません。

##  <a name="inmodalstate"></a>  CFrameWnd::InModalState

フレーム ウィンドウをモーダルまたはモードレス チェックするには、このメンバー関数を呼び出します。

```
BOOL InModalState() const;
```

### <a name="return-value"></a>戻り値

以外の場合は yes です。それ以外の場合 0 を返します。

##  <a name="istracking"></a>  CFrameWnd::IsTracking

ウィンドウのスプリッター バーは現在移動中かを判断するには、このメンバー関数を呼び出します。

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>戻り値

以外の場合は、分割操作が進行中です。それ以外の場合 0 を返します。

##  <a name="loadacceltable"></a>  CFrameWnd::LoadAccelTable

指定されたアクセラレータ テーブルの読み込みに呼び出します。

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
アクセラレータ リソースの名前を識別します。 場合は、リソースは整数の ID で識別されるときを使用します。

### <a name="return-value"></a>戻り値

アクセラレータ テーブルが正常に読み込まれた場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

1 つのテーブルは、同時に読み込むことができます。

リソースから読み込まれたアクセラレータ テーブルは、アプリケーションの終了時に自動的に解放されます。

呼び出す場合`LoadFrame`フレーム ウィンドウを作成するために、フレームワークがメニューおよびアイコンのリソースと一緒にアクセラレータ テーブルを読み込むし、このメンバー関数への後続の呼び出しは、し、必要な。

##  <a name="loadbarstate"></a>  CFrameWnd::LoadBarState

フレーム ウィンドウが所有するそれぞれのコントロール バーの設定を復元するには、この関数を呼び出します。

```
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
初期化 (INI) ファイルのセクションまたは状態情報が格納されている Windows レジストリのキーの名前。

### <a name="remarks"></a>Remarks

復元情報には、可視性、水平、垂直方向、ドッキング状態、およびコントロール バーの位置が含まれます。

呼び出す前に、レジストリに書き込まれる設定を復元する`LoadBarState`します。 呼び出すことによって、情報をレジストリに書き込む[書き込むに](../../mfc/reference/cwinapp-class.md#setregistrykey)します。 呼び出すことによって、INI ファイルに情報を書き込む[に](#savebarstate)します。

##  <a name="loadframe"></a>  CFrameWnd::LoadFrame

リソースの情報からフレーム ウィンドウを動的に作成するを呼び出します。

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

*可能*<br/>
フレーム ウィンドウに関連付けられている共有リソースの ID。

*dwDefaultStyle*<br/>
フレームの[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。 タイトル バーのウィンドウで表されるドキュメントの名前を自動的に表示する場合は、FWS_ADDTOTITLE スタイルが含まれます。

*pParentWnd*<br/>
フレームの親へのポインター。

*pContext*<br/>
ポインターを[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターは、NULL を指定できます。

### <a name="remarks"></a>Remarks

構築、 `CFrameWnd` 2 つのステップ内のオブジェクト。 最初に、構築するコンス トラクターを呼び出す、`CFrameWnd`オブジェクトを呼び出して`LoadFrame`、Windows フレーム ウィンドウと関連付けられているリソースを読み込みし、フレーム ウィンドウをアタッチする`CFrameWnd`オブジェクト。 *可能*パラメーターは、メニューのアクセラレータ テーブルで、アイコン、およびフレーム ウィンドウのタイトルの文字列リソースを指定します。

使用して、`Create`メンバー関数はなく`LoadFrame`すべてのフレーム ウィンドウの作成パラメーターを指定する場合。

Framework 呼び出し`LoadFrame`とドキュメント テンプレート オブジェクトを使用して、フレーム ウィンドウが作成されます。

フレームワークを使用して、 *pContext*も含めて、フレーム ウィンドウに接続しているオブジェクトを指定する引数に含まれるオブジェクトを表示します。 設定することができます、 *pContext*を呼び出すときに NULL 引数`LoadFrame`します。

##  <a name="m_bautomenuenable"></a>  CFrameWnd::m_bAutoMenuEnable

このデータ メンバーには、(つまり、既定値) が有効な場合は、ON_UPDATE_COMMAND_UI または ON_COMMAND ハンドラーがないメニュー項目が自動的に無効になる、ユーザーがメニューをプルダウンします。

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>Remarks

ON_COMMAND ハンドラーが ON_UPDATE_COMMAND_UI ハンドラーを持つメニュー項目を自動的に有効になりません。

このデータ メンバーを設定すると、メニュー項目がツール バー ボタンが有効になっていることと同じ方法で自動的に有効にします。

> [!NOTE]
> `m_bAutoMenuEnable` 最上位のメニュー項目に影響を与えません。

このデータ メンバーは、現在の選択に基づくオプションのコマンドの実装を簡素化しを有効にして、メニュー項目を無効化の ON_UPDATE_COMMAND_UI ハンドラーを記述する必要性が軽減します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

##  <a name="negotiateborderspace"></a>  CFrameWnd::NegotiateBorderSpace

OLE インプレース アクティブ化時にフレーム ウィンドウの境界領域をネゴシエートするには、このメンバー関数を呼び出します。

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>パラメーター

*nBorderCmd*<br/>
次の値のいずれかが含まれています、 `enum BorderCmd`:

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*lpRectBorder*<br/>
ポインターを[RECT](/windows/desktop/api/windef/ns-windef-tagrect)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)罫線の座標を指定するオブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、 `CFrameWnd` OLE 境界領域の調整を実装します。

##  <a name="onbarcheck"></a>  CFrameWnd::OnBarCheck

指定したコントロール バーで、アクションが実行されるたびに呼び出されます。

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
バーの表示されているコントロールの ID。

### <a name="return-value"></a>戻り値

コントロール バーが存在する場合は 0 以外それ以外の場合 0 を返します。

##  <a name="oncontexthelp"></a>  受信

インプレース項目については、shift キーを押しながら f1 キーを処理します。

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Remarks

状況依存のヘルプを有効にする追加する必要があります、

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

ステートメントを`CFrameWnd`メッセージ マップのクラスし、も通常は shift キーを押しながら f1 キー、このメンバー関数を有効にする、アクセラレータ テーブル エントリを追加します。

アプリケーションが OLE コンテナー、`OnContextHelp`ヘルプ モードには、フレーム ウィンドウ オブジェクト内に含まれるすべての場所で項目を格納します。 矢印と疑問符 (?) と、ユーザーがカーソルの変更は、マウス ポインターを移動し、 ダイアログ ボックス、ウィンドウ、メニューのまたはコマンド ボタンを選択するマウスの左ボタンを押します。 このメンバー関数は、Windows 関数を呼び出す`WinHelp`カーソルの下にあるオブジェクトのヘルプ コンテキストを使用します。

##  <a name="oncreateclient"></a>  CFrameWnd::OnCreateClient

実行中に、フレームワークによって呼び出されます`OnCreate`します。

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>パラメーター

*lpc*<br/>
Windows へのポインター [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa)構造体。

*pContext*<br/>
ポインターを[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

この関数を呼び出すことはありません。

この関数の既定の実装を作成、`CView`オブジェクトで指定された情報から*pContext*可能であれば、します。

渡された値を上書きするには、この関数をオーバーライド、`CCreateContext`オブジェクトまたは変更するフレーム ウィンドウのメインのクライアント領域内を制御する方法が作成されます。 `CCreateContext`オーバーライドできるメンバーが記載されて、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)クラス。

> [!NOTE]
>  渡された値を置き換えないで、`CREATESTRUCT`構造体。 これらは情報目的のみです。 初期ウィンドウの四角形をオーバーライドする場合は、たとえば、オーバーライド、`CWnd`メンバー関数は[PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow)します。

##  <a name="onhidemenubar"></a>  CFrameWnd::OnHideMenuBar

システムが現在の MFC アプリケーションのメニュー バーを非表示にすると、この関数が呼び出されます。

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>Remarks

このイベント ハンドラーは、システムは、メニューを非表示にするときに、カスタム アクションを実行するアプリケーションを使用します。 非表示から、メニューを防ぐことはできませんが、たとえば、メニューのスタイルまたは状態を取得するには、その他のメソッドを呼び出すことができます。

##  <a name="onsetpreviewmode"></a>  Cframewnd::onsetpreviewmode

印刷プレビュー モードの内外にアプリケーションのメイン フレーム ウィンドウを設定するには、このメンバー関数を呼び出します。

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>パラメーター

*bPreview*<br/>
印刷プレビュー モードでアプリケーションを配置するかどうかを指定します。 印刷プレビューをプレビュー モードをキャンセルする場合は FALSE を TRUE に設定します。

*pState*<br/>
ポインター、`CPrintPreviewState`構造体。

### <a name="remarks"></a>Remarks

既定の実装では、すべての標準ツールバーを無効になり、メイン メニューと、クライアントのメイン ウィンドウを非表示になります。 これは、MDI フレーム ウィンドウが一時的な SDI フレーム ウィンドウになります。

非表示と印刷プレビュー時にコントロール バー、およびその他のフレーム ウィンドウの一部の表示をカスタマイズするには、このメンバー関数をオーバーライドします。 オーバーライドされたバージョン内から基底クラスの実装を呼び出します。

##  <a name="onshowmenubar"></a>  CFrameWnd::OnShowMenuBar

システムが現在の MFC アプリケーションでメニュー バーを表示するときは、この関数が呼び出されます。

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>Remarks

このイベント ハンドラーは、メニューが表示されるときに、カスタム アクションを実行するアプリケーションを使用します。 表示されてから、メニューを防ぐことはできませんが、たとえば、メニューのスタイルまたは状態を取得するには、その他のメソッドを呼び出すことができます。

##  <a name="onupdatecontrolbarmenu"></a>  CFrameWnd::OnUpdateControlBarMenu

関連付けられているメニューが更新されたときに、フレームワークによって呼び出されます。

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*対応付けられました。*<br/>
ポインターを[CCmdUI](../../mfc/reference/ccmdui-class.md) update コマンドが生成されるメニューを表すオブジェクト。 更新ハンドラーは、[を有効にする](../../mfc/reference/ccmdui-class.md#enable)のメンバー関数、`CCmdUI`オブジェクト*対応付けられた*ユーザー インターフェイスを更新します。

##  <a name="recalclayout"></a>  表示

オンまたはオフに標準のコントロール バーが切り替えられたときに、またはフレーム ウィンドウのサイズが変更されたときに、フレームワークによって呼び出されます。

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*bNotify*<br/>
フレーム ウィンドウのアクティブなインプレース アイテムがレイアウトの変更の通知を受け取るかどうかを判断します。 TRUE の場合、項目が通知されます。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

このメンバー関数の既定の実装、`CWnd`メンバー関数は`RepositionBars`フレームも、クライアントのメイン ウィンドウのように、すべてのコントロール バーの位置を変更する (通常、`CView`または クイック ウォッチ)。

フレーム ウィンドウのレイアウトが変更された後に、コントロール バーの動作と外観を制御するには、このメンバー関数をオーバーライドします。 たとえば、コントロール バーを有効または無効にするか、別のコントロール バーを追加するときに、それを呼び出します。

##  <a name="rectdefault"></a>  CFrameWnd::rectDefault

この静的渡す`CRect`ウィンドウの初期サイズと位置を選択する Windows を許可するウィンドウを作成する場合に、パラメーターとして。

```
static AFX_DATA const CRect rectDefault;
```

##  <a name="savebarstate"></a>  CFrameWnd::SaveBarState

この関数では、フレーム ウィンドウが所有するそれぞれのコントロール バーに関する情報を格納します。

```
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
初期化ファイルのセクションまたは状態情報が格納されている Windows レジストリのキーの名前。

### <a name="remarks"></a>Remarks

この情報を使用して、初期化ファイルから読み取ることができます[戻す](#loadbarstate)します。 格納されている情報には、可視性、水平、垂直方向、ドッキング状態、およびコントロール バーの位置が含まれています。

##  <a name="setactivepreviewview"></a>  CFrameWnd::SetActivePreviewView

リッチ プレビュー用のアクティブなビューを指定されたビューを指定します。

```
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>パラメーター

*pViewNew*<br/>
アクティブ化するためのビューへのポインター。

### <a name="remarks"></a>Remarks

##  <a name="setactiveview"></a>  CFrameWnd::SetActiveView

アクティブなビューを設定するには、このメンバー関数を呼び出します。

```
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*pViewNew*<br/>
ポインターを指定します、 [CView](../../mfc/reference/cview-class.md)オブジェクト、または NULL でないアクティブなビュー。

*bNotify*<br/>
ビューをアクティブ化の通知を受けるかどうかを指定します。 TRUE の場合、`OnActivateView`は、FALSE、それがない場合、新しいビューに対して呼び出されます。

### <a name="remarks"></a>Remarks

フレームワークは、この関数、ユーザーは、フレーム ウィンドウ内のビューにフォーカスを変更すると自動的に呼び出します。 明示的に呼び出すことができます`SetActiveView`を指定されたビューにフォーカスを変更します。

##  <a name="setdockstate"></a>  CFrameWnd::SetDockState

格納されている状態情報を適用するには、このメンバー関数を呼び出し、`CDockState`フレーム ウィンドウのコントロール バー オブジェクト。

```
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>パラメーター

*state*<br/>
フレーム ウィンドウのコントロール バーには、格納されている状態を適用します。

### <a name="remarks"></a>Remarks

コントロール バーの以前の状態を復元するに格納されている状態を読み込むことができます`CDockState::LoadState`または`Serialize`を使用して`SetDockState`フレーム ウィンドウのコントロール バーに適用します。 以前の状態が格納されている、`CDockState`でオブジェクトです。 `GetDockState`

##  <a name="setmenubarstate"></a>  CFrameWnd::SetMenuBarState

非表示または表示は、現在の MFC アプリケーションで、メニューの表示状態を設定します。

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*状態*|[in]メニューを表示または非表示にするかどうかを指定します。 *状態*パラメーターは、次の値を持つことができます。<br /><br />AFX_MBS_VISIBLE (0x01) - 場合は、非表示が表示されている場合は、効果はありませんが、メニューを表示します。<br />AFX_MBS_HIDDEN (0x02) - には、メニューが非表示に、表示されても、非表示になっている場合は、効果がありません。|

### <a name="return-value"></a>戻り値

このメソッドは、メニューの状態を正常に変更された場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドはデバッグ モードでアサートし、派生した例外を発生させます。 ランタイム エラーが発生した場合、 [CException](../../mfc/reference/cexception-class.md)クラス。

##  <a name="setmenubarvisibility"></a>  CFrameWnd::SetMenuBarVisibility

非表示または非表示には、現在の MFC アプリケーションで、メニューの既定の動作を設定します。

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nStyle*|[in]かどうか、メニューは既定では、非表示が表示されるやフォーカスがあるを指定します。 *NStyle*パラメーターは、次の値を持つことができます。<br /><br />AFX_MBV_KEEPVISIBLE (0X01)-<br />     メニューは、常に表示され、既定ではありませんが、フォーカス。<br />AFX_MBV_DISPLAYONFOCUS (0X02)-<br />     既定では、メニューは表示されません。 メニューが表示されない場合は、メニューを表示し、フォーカスに ALT キーを押します。 メニューが表示される場合は、メニューを非表示に alt キーまたは ESC キーを押します。<br />-AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (ビットごとの組み合わせ (OR)) - 既定では、メニューは表示されません。 メニューが表示されない場合は、メニューを表示し、フォーカスを F10 キーを押します。 メニューが表示される場合は、オンまたはオフ、メニューにフォーカスを切り替える F10 キーを押します。 非表示にする、alt キーまたは ESC キーを押すまで、メニューが表示されます。|

### <a name="remarks"></a>Remarks

場合の値、 *nStyle*パラメーターが有効でないこのメソッドはデバッグ モードで発生させ、アサート[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)リリース モードでします。 このメソッドはデバッグ モードでアサートし、派生した例外を発生させます。 その他のランタイム エラーが発生した場合、 [CException](../../mfc/reference/cexception-class.md)クラス。

このメソッドでは、Windows Vista 以降に作成されたアプリケーションのメニューの状態に影響します。

##  <a name="setmessagetext"></a>  CFrameWnd::SetMessageText

ステータス バー ペインを持つ ID は 0 の文字列を配置するには、この関数を呼び出します。

```
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
ステータス バーに表示する文字列を指します。

*nID*<br/>
ステータス バーに配置される、文字列のリソース ID の文字列を指定します。

### <a name="remarks"></a>Remarks

これは、通常、ステータス バーの一番左、および最も長い、ウィンドウです。

##  <a name="setprogressbarposition"></a>  CFrameWnd::SetProgressBarPosition

タスク バーに表示される Windows 7 の進行状況バーの現在位置を設定します。

```
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>パラメーター

*nProgressPos*<br/>
設定する位置を指定します。 設定の範囲でなければなりません`SetProgressBarRange`します。

### <a name="remarks"></a>Remarks

##  <a name="setprogressbarrange"></a>  CFrameWnd::SetProgressBarRange

タスク バーに表示される Windows 7 の進行状況バーの範囲を設定します。

```
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>パラメーター

*nRangeMin*<br/>
最小値。

*nRangeMax*<br/>
最大値。

### <a name="remarks"></a>Remarks

##  <a name="setprogressbarstate"></a>  CFrameWnd::SetProgressBarState

タスク バー ボタンに表示される進行状況インジケーターの状態の種類を設定します。

```
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>パラメーター

*tbpFlags*<br/>
進捗状況ボタンの現在の状態を制御するフラグ。 すべての状態は相互に排他的であるため、次のフラグの 1 つだけを指定します。TBPF_NOPROGRESS、TBPF_INDETERMINATE、TBPF_NORMAL、TBPF_ERROR、TBPF_PAUSED します。

### <a name="remarks"></a>Remarks

##  <a name="settaskbaroverlayicon"></a>  CFrameWnd::SetTaskbarOverlayIcon

オーバーロードされます。 または、ユーザーに通知をアプリケーションの状態を示すためには、タスク バー ボタンにオーバーレイが適用されます。

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);

BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>パラメーター

*可能*<br/>
オーバーレイを使用するアイコンのリソース ID を指定します。 説明を参照してください。 *hIcon*詳細についてはします。

*lpcszDescr*<br/>
アクセシビリティのために、オーバーレイによって伝えられる情報版が代替テキストを提供する文字列へのポインター。

*hIcon*<br/>
オーバーレイとして使用するアイコンのハンドル。 96 ドット/インチ (dpi) での 16 x 16 ピクセルを測定する、小さいアイコンがあります。 オーバーレイ アイコンは、タスク バー ボタンに既に適用されて、既存のオーバーレイが置き換えられます。 この値は NULL を指定できます。 NULL 値が処理される方法は、タスク バー ボタンが 1 つのウィンドウまたは windows のグループを表すかどうかによって異なります。 解放する呼び出し元アプリケーションの役割は*hIcon*が不要になった場合。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。OS のバージョンは Windows 7 よりも小さい場合、またはアイコンの設定にエラーが発生した場合は FALSE です。

### <a name="remarks"></a>Remarks

##  <a name="settitle"></a>  CFrameWnd::SetTitle

ウィンドウ オブジェクトのタイトルを設定します。

```
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>パラメーター

*lpszTitle*<br/>
ウィンドウ オブジェクトのタイトルを含む文字列へのポインター。

##  <a name="showcontrolbar"></a>  CFrameWnd::ShowControlBar

コントロール バーを非表示には、このメンバー関数を呼び出します。

```
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

*pBar*<br/>
表示/非表示のコントロール バーへのポインター。

*bShow*<br/>
TRUE の場合は、コントロール バーが表示されることを指定します。 FALSE の場合は、コントロール バーが非表示にすることを指定します。

*bDelay*<br/>
TRUE の場合、コントロール バーの表示を遅延します。 FALSE の場合は、すぐにバー コントロールを表示します。

##  <a name="showownedwindows"></a>  CFrameWnd::ShowOwnedWindows

子孫であるすべてのウィンドウを表示するには、このメンバー関数を呼び出す、`CFrameWnd`オブジェクト。

```
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
所有しているウィンドウを表示/非表示にするかどうかを指定します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[CRuntimeClass 構造体](../../mfc/reference/cruntimeclass-structure.md)
