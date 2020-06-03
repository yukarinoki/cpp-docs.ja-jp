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
ms.openlocfilehash: 3bb93420b39be5d6fb9a6691cec8300fdccb0e73
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754980"
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
|[フレームウンド::フレームウンド](#cframewnd)|`CFrameWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[フレーム化::アクティブフレーム](#activateframe)|フレームを表示し、ユーザーが使用できるようにします。|
|[フレームオンド::開始モーダルステート](#beginmodalstate)|フレーム ウィンドウをモーダルに設定します。|
|[フレームウンド::作成](#create)|オブジェクトに関連付けられた Windows フレーム ウィンドウを`CFrameWnd`作成して初期化する呼び出し。|
|[フレーム化::ビューの作成](#createview)|から`CView`派生していないフレーム内にビューを作成します。|
|[:Dロックコントロールバー](#dockcontrolbar)|コントロール バーをドッキングします。|
|[CFrameWnd::ドッキングを有効にする](#enabledocking)|コントロール バーをドッキングできます。|
|[フレームオンド::エンドモーダルステート](#endmodalstate)|フレーム ウィンドウのモーダル状態を終了します。 によって無効になっているすべてのウィンドウを有効`BeginModalState`にします。|
|[フレーム化::フロートコントロールバー](#floatcontrolbar)|コントロール バーをフローティングします。|
|[フレーム化::取得作業中のドキュメント](#getactivedocument)|アクティブな`CDocument`オブジェクトを返します。|
|[フレームを組み合わせた::アクティブフレームを取得します。](#getactiveframe)|アクティブな`CFrameWnd`オブジェクトを返します。|
|[フレームを組み合わせた::アクティブビュー](#getactiveview)|アクティブな`CView`オブジェクトを返します。|
|[フレーム化::コントロールバーを取得します。](#getcontrolbar)|コントロール バーを取得します。|
|[フレームウンド::ゲットドックステート](#getdockstate)|フレーム ウィンドウのドッキング状態を取得します。|
|[フレーム化::メニューバーステート](#getmenubarstate)|現在の MFC アプリケーションのメニューの表示状態を取得します。|
|[フレーム化::メニューバーの可視性](#getmenubarvisibility)|現在の MFC アプリケーションのメニューの既定の動作が非表示か表示中かを示します。|
|[フレーム化::メッセージバーを取得します。](#getmessagebar)|フレーム ウィンドウに属するステータス バーへのポインターを返します。|
|[メッセージ文字列を取得します。](#getmessagestring)|コマンド ID に対応するメッセージを取得します。|
|[フレームウンド::ゲットタイトル](#gettitle)|関連するコントロール バーのタイトルを取得します。|
|[フレーム化::初期更新フレーム](#initialupdateframe)|フレーム`OnInitialUpdate`ウィンドウ内のすべてのビューに属するメンバー関数を呼び出します。|
|[フレームオンド::インモーダルステート](#inmodalstate)|フレーム ウィンドウがモーダル状態かどうかを示す値を返します。|
|[フレームウンド::イズトラッキング](#istracking)|分割バーが現在移動中かどうかを判断します。|
|[フレームウンド::ロードアクセルテーブル](#loadacceltable)|アクセラレータ テーブルを読み込むための呼び出し。|
|[フレーム化::ロードバーステート](#loadbarstate)|コントロール バーの設定を復元するために呼び出します。|
|[フレーム化::ロードフレーム](#loadframe)|リソース情報からフレーム ウィンドウを動的に作成する呼び出し。|
|[フレーム化::ネゴシエートボーダースペース](#negotiateborderspace)|フレーム ウィンドウ内の境界領域をネゴシエートします。|
|[フレームオンド::オンバーチェック](#onbarcheck)|指定されたコントロール バーでアクションが実行されるたびに呼び出されます。|
|[フレーム化::オンコンテキストヘルプ](#oncontexthelp)|インプレース項目の Shift + F1 ヘルプを処理します。|
|[フレームウィンドウ::オンセットプレビューモード](#onsetpreviewmode)|アプリケーションのメイン フレーム ウィンドウを印刷プレビュー モードに設定または印刷モードから外します。|
|[次の項目を使用します。](#onupdatecontrolbarmenu)|関連付けられたメニューが更新されたときに、フレームワークによって呼び出されます。|
|[フレーム化::レカルクレイアウト](#recalclayout)|`CFrameWnd`オブジェクトのコントロール バーを再配置します。|
|[フレーム化::セーブバーステート](#savebarstate)|コントロール バーの設定を保存するために呼び出します。|
|[フレームウィンドウ::アクティブプレビュービュー](#setactivepreviewview)|リッチ プレビューのアクティブ ビューとして指定したビューを指定します。|
|[フレーム化::アクティブビュー](#setactiveview)|アクティブな`CView`オブジェクトを設定します。|
|[フレームウンド::セットドックステート](#setdockstate)|フレーム ウィンドウをメイン ウィンドウにドッキングする呼び出し。|
|[フレーム化::セットメニューバーステート](#setmenubarstate)|現在の MFC アプリケーションのメニューの表示状態を非表示または表示に設定します。|
|[フレーム化::セットメニューバーの可視性](#setmenubarvisibility)|現在の MFC アプリケーションのメニューの既定の動作を、非表示または表示に設定します。|
|[フレームテキスト::メッセージテキスト](#setmessagetext)|標準ステータス バーのテキストを設定します。|
|[フレームの割り込み:::設定プログレスバーポジション](#setprogressbarposition)|タスク バーに表示される Windows 7 プログレス バーの現在位置を設定します。|
|[フレームの種類::設定プログレスバーレンジ](#setprogressbarrange)|タスク バーに表示される Windows 7 プログレス バーの範囲を設定します。|
|[フレーム化::設定プログレスバーステート](#setprogressbarstate)|タスク バー ボタンに表示される進行状況インジケーターの種類と状態を設定します。|
|[フレームアイコン::タスクバーオーバーレイアイコン](#settaskbaroverlayicon)|オーバーロードされます。 タスク バー ボタンにオーバーレイを適用して、アプリケーションの状態を示すか、ユーザーに通知します。|
|[フレームを組み合わせた::セットタイトル](#settitle)|関連するコントロール バーのタイトルを設定します。|
|[フレーム化::ショーコントロールバー](#showcontrolbar)|コントロール バーを表示するために呼び出します。|
|[フレームウンド::ショー所有のウィンドウズ](#showownedwindows)|オブジェクトの子孫であるすべてのウィンドウを`CFrameWnd`表示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[フレームオンド::オンCreateクライアント](#oncreateclient)|フレームのクライアント ウィンドウを作成します。|
|[フレーム化::オンハイドメニューバー](#onhidemenubar)|現在の MFC アプリケーションのメニューが非表示になる前に呼び出されます。|
|[フレームオンド::オンショーメニューバー](#onshowmenubar)|現在の MFC アプリケーションのメニューが表示される前に呼び出されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[フレームウンド::m_bAutoMenuEnable](#m_bautomenuenable)|メニュー項目の自動有効/無効機能を制御します。|
|[フレームの種類::既定](#rectdefault)|Windows が`CRect`ウィンドウの初期サイズと位置`CFrameWnd`を選択できるように、オブジェクトを作成するときにこの静的をパラメーターとして渡します。|

## <a name="remarks"></a>解説

アプリケーションに便利なフレーム ウィンドウを作成するには、 から`CFrameWnd`クラスを派生させます。 派生クラスにメンバー変数を追加して、アプリケーション固有のデータを格納します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

フレーム ウィンドウを構築するには、次の 3 つの方法があります。

- [Create](#create)を使用して直接構築します。

- [直接ロードフレーム](#loadframe)を使用してそれを構築します。

- ドキュメント テンプレートを使用して間接的に構築します。

または`Create``LoadFrame`を呼び出す前に、C++ **new**演算子を使用して、ヒープ上にフレーム ウィンドウ オブジェクトを構築する必要があります。 を呼`Create`び出す前に、AfxRegisterWndClass グローバル関数を使用してウィンドウ クラスを登録して、フレームのアイコンスタイルとクラス スタイルを設定することもできます。 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)

メンバー関数`Create`を使用して、フレームの作成パラメーターを即時引数として渡します。

`LoadFrame`必要な引数は`Create`よりも少なく、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、メニューなど、リソースからその既定値のほとんどを取得します。 で`LoadFrame`アクセスできるようにするには、これらすべてのリソースに同じリソース ID (IDR_MAINFRAME など) が必要です。

オブジェクトに`CFrameWnd`ビューとドキュメントが含まれている場合、それらはプログラマが直接作成するのではなく、フレームワークによって間接的に作成されます。 オブジェクト`CDocTemplate`は、フレームの作成、含むビューの作成、およびビューの適切なドキュメントへの接続を調整します。 コンストラクターのパラメーターは`CDocTemplate`、関連する`CRuntimeClass`3 つのクラス (ドキュメント、フレーム、ビュー) の を指定します。 オブジェクト`CRuntimeClass`は、ユーザーが指定した場合 (たとえば、File New コマンドまたはマルチ ドキュメント インターフェイス (MDI) ウィンドウ New コマンドを使用して、新しいフレームを動的に作成するために、フレームワークによって使用されます。

上記のRUNTIME_CLASS機構が正しく`CFrameWnd`機能するためには、派生したフレーム ウィンドウ クラスをDECLARE_DYNCREATEで宣言する必要があります。

には`CFrameWnd`、Windows の一般的なアプリケーションでメイン ウィンドウの次の機能を実行するための既定の実装が含まれています。

- フレーム`CFrameWnd`ウィンドウは、Windows アクティブ ウィンドウまたは現在の入力フォーカスに依存しない現在アクティブなビューを追跡します。 フレームが再アクティブ化されると、 を呼び出`CView::OnActivateView`してアクティブなビューに通知されます。

- コマンド メッセージと`OnSetFocus`、 、、`OnHScroll`および`OnVScroll`関数`CWnd`によって処理されるメッセージを含む多くの一般的なフレーム通知メッセージ`CFrameWnd`は、フレーム ウィンドウによって現在アクティブなビューに委任されます。

- 現在アクティブなビュー (または MDI フレームの場合は、現在アクティブな MDI 子フレーム ウィンドウ) は、フレーム ウィンドウのキャプションを決定できます。 この機能は、フレーム ウィンドウのFWS_ADDTOTITLE スタイル ビットをオフにすることで無効にできます。

- フレーム`CFrameWnd`ウィンドウは、コントロール バー、ビュー、およびフレーム ウィンドウのクライアント領域内のその他の子ウィンドウの位置を管理します。 また、フレーム ウィンドウは、ツール バーやその他のコントロール バー ボタンのアイドルタイム更新も行います。 `CFrameWnd`フレーム ウィンドウには、ツールバーとステータス バーのオンとオフを切り替えるコマンドの既定の実装もあります。

- フレーム`CFrameWnd`ウィンドウはメイン メニュー バーを管理します。 ポップアップ メニューが表示されている場合、フレーム ウィンドウはUPDATE_COMMAND_UIメカニズムを使用して、どのメニュー項目を有効にするか、無効にするか、またはチェックするかを決定します。 ユーザーがメニュー項目を選択すると、フレーム ウィンドウは、そのコマンドのメッセージ文字列でステータス バーを更新します。

- `CFrameWnd`フレーム ウィンドウには、キーボード アクセラレータを自動的に変換するオプションのアクセラレータ テーブルがあります。

- `CFrameWnd`フレーム ウィンドウには、状況依存のヘルプに`LoadFrame`使用されるオプションのヘルプ ID が設定されています。 フレーム ウィンドウは、状況依存のヘルプ (Shift + F1) や印刷プレビュー モードなどの半モーダル状態のメイン オーケストレーターです。

- フレーム`CFrameWnd`ウィンドウは、ファイル マネージャからドラッグしてフレーム ウィンドウにドロップされたファイルを開きます。 ファイル拡張子が登録され、アプリケーションに関連付けられている場合、フレーム ウィンドウは、ユーザーがファイル マネージャーでデータ ファイルを開いたとき、または Windows 関数が呼び出されたときに発生する動的データ`ShellExecute`交換 (DDE) のオープン要求に応答します。

- フレーム ウィンドウがメイン アプリケーション ウィンドウ (つまり、`CWinThread::m_pMainWnd`アプリケーションを閉じるとき) の場合、フレーム ウィンドウは、変更されたドキュメント (`OnClose`および`OnQueryEndSession`用) を保存するようにユーザーに求めるメッセージを表示します。

- フレーム ウィンドウがメイン アプリケーション ウィンドウの場合、WinHelp を実行するためのコンテキストはフレーム ウィンドウです。 フレーム ウィンドウを閉じると WINHELP がシャットダウンします。EXE は、このアプリケーションのヘルプのために起動された場合。

C++**の delete**演算子を使用してフレーム ウィンドウを破棄しないでください。 代わりに `CWnd::DestroyWindow` を使用してください の`CFrameWnd``PostNcDestroy`実装は、ウィンドウが破棄されると C++ オブジェクトを削除します。 ユーザーがフレーム ウィンドウを閉じると、既定`OnClose`のハンドラーが`DestroyWindow`呼び出されます。

詳細については、「`CFrameWnd`フレーム[ウィンドウ](../../mfc/frame-windows.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cframewndactivateframe"></a><a name="activateframe"></a>フレーム化::アクティブフレーム

フレーム ウィンドウをアクティブにして復元し、ユーザーが表示できるように、このメンバー関数を呼び出します。

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow)に渡すパラメータを指定します。 デフォルトでは、フレームが表示され、正しく復元されます。

### <a name="remarks"></a>解説

このメンバー関数は、通常、フレーム ウィンドウまたはその内容をユーザーに表示する DDE、OLE、またはその他のイベントなどの非ユーザー インターフェイス イベントの後に呼び出されます。

既定の実装では、フレームがアクティブ化され、Z オーダーの先頭に移動し、必要に応じて、アプリケーションのメイン フレーム ウィンドウに対して同じ手順が実行されます。

フレームのアクティブ化方法を変更するには、このメンバー関数をオーバーライドします。 たとえば、MDI 子ウィンドウを強制的に最大化できます。 適切な機能を追加し、明示的な*nCmdShow*を使用して基本クラスのバージョンを呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

## <a name="cframewndbeginmodalstate"></a><a name="beginmodalstate"></a>フレームオンド::開始モーダルステート

フレーム ウィンドウをモーダルにします。

```
virtual void BeginModalState();
```

## <a name="cframewndcframewnd"></a><a name="cframewnd"></a>フレームウンド::フレームウンド

オブジェクトを`CFrameWnd`構築しますが、表示されるフレーム ウィンドウは作成しません。

```
CFrameWnd();
```

### <a name="remarks"></a>解説

表示`Create`ウィンドウを作成する呼び出し。

## <a name="cframewndcreate"></a><a name="create"></a>フレームウンド::作成

オブジェクトに関連付けられた Windows フレーム ウィンドウを`CFrameWnd`作成して初期化する呼び出し。

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

*クラス名*<br/>
Windows クラスの名前を示す null で終わる文字列を指します。 クラス名は、グローバル関数または Windows`AfxRegisterWndClass`関数に登録された`RegisterClass`任意の名前にすることができます。 NULL の場合は、定義済みの`CFrameWnd`デフォルト属性を使用します。

*名前をクリックします。*<br/>
ウィンドウ名を表す null で終わる文字列を指します。 タイトル バーのテキストとして使用されます。

*Dwstyle*<br/>
ウィンドウ[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)の属性を指定します。 ウィンドウに表示されるドキュメントの名前をタイトル バーに自動的に表示する場合は、FWS_ADDTOTITLE スタイルを含めます。

*Rect*<br/>
ウィンドウのサイズと位置を指定します。 *rectDefault*値を使用すると、ウィンドウは新しいウィンドウのサイズと位置を指定できます。

*pParentWnd*<br/>
このフレーム ウィンドウの親ウィンドウを指定します。 最上位のフレーム ウィンドウでは、このパラメータは NULL にする必要があります。

*メニュー名*<br/>
ウィンドウで使用するメニュー リソースの名前を識別します。 メニューに文字列ではなく整数 ID がある場合は、MAKEINTRESOURCE を使用します。 このパラメーターは NULL にすることができます。

*ドウェエクススタイル*<br/>
ウィンドウ拡張[スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)属性を指定します。

*pContext*<br/>
[構造体](../../mfc/reference/ccreatecontext-structure.md)へのポインターを指定します。 このパラメーターは NULL にすることができます。

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

2`CFrameWnd`つの手順でオブジェクトを作成します。 まず、オブジェクトを構築するコンストラクターを`CFrameWnd`呼び出し、次に`Create``CFrameWnd`を呼び出します。 `Create`ウィンドウのクラス名とウィンドウ名を初期化し、スタイル、親、および関連付けられたメニューの既定値を登録します。

引数`LoadFrame`を指定`Create`するのではなく、リソースからフレーム ウィンドウを読み込むのではなく、使用します。

## <a name="cframewndcreateview"></a><a name="createview"></a>フレーム化::ビューの作成

フレーム`CreateView`内にビューを作成する呼び出し。

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

成功した場合`CWnd`はオブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメンバー関数を使用して、フレーム内に派生していない`CView`"ビュー" を作成します。 を呼`CreateView`び出した後、ビューを手動でアクティブに設定し、表示されるように設定する必要があります。これらのタスクは、 によって`CreateView`自動的に実行されるわけではありません。

## <a name="cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a>:Dロックコントロールバー

コントロール バーをフレーム ウィンドウにドッキングします。

```cpp
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
ドッキングするコントロール バーへのポイント。

*nドックバーID*<br/>
ドッキングを考慮するフレーム ウィンドウの辺を決定します。 0 または、次の 1 つ以上を指定できます。

- AFX_IDW_DOCKBAR_TOP フレーム ウィンドウの上端にドッキングします。

- AFX_IDW_DOCKBAR_BOTTOM フレーム ウィンドウの下部にドッキングします。

- AFX_IDW_DOCKBAR_LEFT フレーム ウィンドウの左側にドッキングします。

- AFX_IDW_DOCKBAR_RIGHT フレーム ウィンドウの右側にドッキングします。

0 の場合、コントロール バーは、移動先フレーム ウィンドウでドッキングが有効になっている任意の側にドッキングできます。

*Lprect*<br/>
コントロール バーが移動先フレーム ウィンドウの非クライアント領域にドッキングされる画面座標を指定します。

### <a name="remarks"></a>解説

コントロール バーは[、CControlBar:::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)と[CFrameWnd::EnableDocking](#enabledocking)の両方への呼び出しで指定されたフレーム ウィンドウの片方にドッキングされます。 選択される側は*nDockBarID*によって決まります。

## <a name="cframewndenabledocking"></a><a name="enabledocking"></a>CFrameWnd::ドッキングを有効にする

フレーム ウィンドウでドッキング可能なコントロール バーを有効にします。

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>パラメーター

*ドウドックスタイル*<br/>
フレーム ウィンドウのどの辺がコントロール バーのドッキング サイトとして機能するかを指定します。 次の 1 つ以上を指定できます。

- CBRS_ALIGN_TOP クライアント領域の上部にドッキングできます。

- CBRS_ALIGN_BOTTOM クライアント領域の下部にドッキングできます。

- CBRS_ALIGN_LEFT クライアント領域の左側にドッキングできます。

- CBRS_ALIGN_RIGHT クライアント領域の右側にドッキングできます。

- CBRS_ALIGN_ANY クライアント領域の任意の側にドッキングできます。

### <a name="remarks"></a>解説

既定では、コントロール バーは、上、下、左、右の順序でフレーム ウィンドウの横にドッキングされます。

### <a name="example"></a>例

  [CToolBar::作成](../../mfc/reference/ctoolbar-class.md#create)の例を参照してください。

## <a name="cframewndendmodalstate"></a><a name="endmodalstate"></a>フレームオンド::エンドモーダルステート

フレーム ウィンドウをモーダルからモードレスに変更します。

```
virtual void EndModalState();
```

### <a name="remarks"></a>解説

`EndModalState`によって無効になっているすべてのウィンドウ[を有効にします](#beginmodalstate)。

## <a name="cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a>フレーム化::フロートコントロールバー

コントロール バーをフレーム ウィンドウにドッキングしないようにします。

```cpp
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
浮動するコントロール バーへのポイント。

*ポイント*<br/>
コントロール バーの左上隅が配置される画面座標での位置。

*Dwstyle*<br/>
新しいフレーム ウィンドウ内でコントロール バーを水平または垂直に揃えるかどうかを指定します。 次のいずれかの方法を使用できます。

- CBRS_ALIGN_TOP コントロール バーの垂直方向を向けます。

- CBRS_ALIGN_BOTTOM コントロール バーの垂直方向を垂直方向に配置します。

- CBRS_ALIGN_LEFT コントロール バーの水平方向を左右に配置します。

- CBRS_ALIGN_RIGHT コントロール バーの水平方向を設定します。

水平方向と垂直方向の両方を指定してスタイルが渡される場合、ツールバーは水平方向に配置されます。

### <a name="remarks"></a>解説

通常、これは、プログラムが前回の実行から設定を復元するときに、アプリケーションの起動時に行われます。

この関数は、ドッキングできない位置にコントロール バーをドラッグしながら、マウスの左ボタンを離してドロップ操作を行うと、フレームワークによって呼び出されます。

## <a name="cframewndgetactivedocument"></a><a name="getactivedocument"></a>フレーム化::取得作業中のドキュメント

現在アクティブなビューにアタッチされている現在`CDocument`のビューへのポインターを取得します。

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>戻り値

現在の[CDocument](../../mfc/reference/cdocument-class.md)へのポインター。 現在のドキュメントがない場合は、NULL を返します。

## <a name="cframewndgetactiveframe"></a><a name="getactiveframe"></a>フレームを組み合わせた::アクティブフレームを取得します。

MDI フレーム ウィンドウのアクティブなマルチ ドキュメント インターフェイス (MDI) 子ウィンドウへのポインターを取得します。

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>戻り値

アクティブな MDI 子ウィンドウへのポインター。 アプリケーションが SDI アプリケーションの場合、または MDI フレーム ウィンドウにアクティブなドキュメントがない場合は、**暗黙的なこの**ポインターが返されます。

### <a name="remarks"></a>解説

アクティブな MDI 子ノードがない場合、またはアプリケーションが単一のドキュメント インターフェイス (SDI) である場合は、暗黙的**な this ポインター**が返されます。

## <a name="cframewndgetactiveview"></a><a name="getactiveview"></a>フレームを組み合わせた::アクティブビュー

フレーム ウィンドウ ( ) にアタッチされているアクティブ ビューへのポインターを取得します。 `CFrameWnd`

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>戻り値

現在の[CView](../../mfc/reference/cview-class.md)へのポインター。 現在のビューがない場合は、NULL を返します。

### <a name="remarks"></a>解説

この関数は、MDI メイン フレーム ウィンドウ ()`CMDIFrameWnd`を呼び出すと NULL を返します。 MDI アプリケーションでは、MDI メイン フレーム ウィンドウにビューが関連付けされていません。 代わりに、個々の子ウィンドウ`CMDIChildWnd`( ) には 1 つ以上のビューが関連付けられます。 MDI アプリケーションのアクティブ ビューは、まずアクティブな MDI 子ウィンドウを見つけてから、その子ウィンドウのアクティブ ビューを見つけることによって取得できます。 アクティブな MDI 子ウィンドウは、関数`MDIGetActive`を呼び`GetActiveFrame`出すか、次に示すように呼び出して見つけることができます。

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

## <a name="cframewndgetcontrolbar"></a><a name="getcontrolbar"></a>フレーム化::コントロールバーを取得します。

ID`GetControlBar`に関連付けられているコントロール バーへのアクセスを取得するために呼び出します。

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
コントロール バーの ID 番号。

### <a name="return-value"></a>戻り値

ID に関連付けられているコントロール バーへのポインター。

### <a name="remarks"></a>解説

*nID*パラメータは、コントロール バーのメソッドに`Create`渡される一意の識別子を参照します。 コントロール バーの詳細については、「[コントロール](../../mfc/control-bars.md)バー」というトピックを参照してください。

`GetControlBar`コントロール バーがフローティング状態にある場合でも、現在はフレームの子ウィンドウではない場合でも、コントロール バーを返します。

## <a name="cframewndgetdockstate"></a><a name="getdockstate"></a>フレームウンド::ゲットドックステート

オブジェクト内の`CDockState`フレーム ウィンドウのコントロール バーに関する状態情報を格納します。

```cpp
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>パラメーター

*state*<br/>
フレーム ウィンドウのコントロール バーが返された場合の現在の状態を格納します。

### <a name="remarks"></a>解説

その後、 または を`CDockState`使用して`CDockState::SaveState`、`Serialize`の内容をストレージに書き込むことができます。 後でコントロール バーを以前の状態に戻す場合は、 または`CDockState::LoadState``Serialize`を呼び出`SetDockState`して、フレーム ウィンドウのコントロール バーに前の状態を適用します。

## <a name="cframewndgetmenubarstate"></a><a name="getmenubarstate"></a>フレーム化::メニューバーステート

現在の MFC アプリケーションのメニューの表示状態を取得します。

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>戻り値

戻り値には、次の値を指定できます。

- AFX_MBS_VISIBLE (0x01) - メニューが表示されます。

- AFX_MBS_HIDDEN (0x02) - メニューが非表示になります。

### <a name="remarks"></a>解説

ランタイム エラーが発生した場合、このメソッドはデバッグ モードでアサートし[、CException](../../mfc/reference/cexception-class.md)クラスから派生した例外を発生させます。

## <a name="cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a>フレーム化::メニューバーの可視性

現在の MFC アプリケーションのメニューの既定の状態が非表示か表示状態かを示します。

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>戻り値

このメソッドは、次のいずれかの値を返します。

- AFX_MBV_KEEPVISIBLE (0x01) - メニューは常に表示され、デフォルトではフォーカスがありません。

- AFX_MBV_DISPLAYONFOCUS (0x02) - メニューはデフォルトで非表示になっています。 メニューが非表示になっている場合は、Alt キーを押してメニューを表示し、フォーカスを移動します。 メニューが表示されている場合は、Alt キーまたは Esc キーを押して非表示にします。

- AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (ビットごとの組み合わせ (OR)) - メニューはデフォルトで非表示になっています。 メニューが非表示の場合は、F10 キーを押してメニューを表示し、フォーカスを移動します。 メニューが表示されている場合は、F10 キーを押して、フォーカスをメニューのオンまたはオフに切り替えます。 メニューは、Alt キーまたは Esc キーを押して非表示にするまで表示されます。

### <a name="remarks"></a>解説

ランタイム エラーが発生した場合、このメソッドはデバッグ モードでアサートし[、CException](../../mfc/reference/cexception-class.md)クラスから派生した例外を発生させます。

## <a name="cframewndgetmessagebar"></a><a name="getmessagebar"></a>フレーム化::メッセージバーを取得します。

ステータス バーへのポインターを取得します。

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>戻り値

ステータス バー ウィンドウへのポインター。

## <a name="cframewndgetmessagestring"></a><a name="getmessagestring"></a>メッセージ文字列を取得します。

コマンド ID にカスタム文字列を提供するには、この関数をオーバーライドします。

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
目的のメッセージのリソース ID。

*rメッセージ*<br/>
`CString`メッセージを配置するオブジェクト。

### <a name="remarks"></a>解説

既定の実装では *、nID*で指定された文字列をリソース ファイルから読み込みます。 この関数は、ステータス バーのメッセージ文字列を更新する必要がある場合に、フレームワークによって呼び出されます。

## <a name="cframewndgettitle"></a><a name="gettitle"></a>フレームウンド::ゲットタイトル

ウィンドウ オブジェクトのタイトルを取得します。

```
CString GetTitle() const;
```

### <a name="return-value"></a>戻り値

ウィンドウ オブジェクトの現在のタイトルを含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

## <a name="cframewndinitialupdateframe"></a><a name="initialupdateframe"></a>フレーム化::初期更新フレーム

を`IntitialUpdateFrame`使用して新しいフレームを`Create`作成した後に呼び出す。

```cpp
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>パラメーター

*pDoc*<br/>
フレーム ウィンドウが関連付けられているドキュメントへのポイント。 NULL にすることができます。

*ビクジブル*<br/>
TRUE の場合、フレームが表示されアクティブになることを示します。 FALSE の場合、子孫は表示されません。

### <a name="remarks"></a>解説

これにより、そのフレーム ウィンドウのすべてのビューが呼び`OnInitialUpdate`出しを受信します。

また、以前アクティブなビューが存在しない場合は、フレーム ウィンドウのプライマリ ビューがアクティブになります。 プライマリ ビューは、AFX_IDW_PANE_FIRSTの子 ID を持つビューです。 最後に *、bMakeVisible*が 0 以外の場合、フレーム ウィンドウが表示されます。 *bMakeVisible*が 0 の場合、フレーム ウィンドウの現在のフォーカスと表示状態は変更されません。 フレームワークの File New および File Open の実装を使用する場合は、この関数を呼び出す必要はありません。

## <a name="cframewndinmodalstate"></a><a name="inmodalstate"></a>フレームオンド::インモーダルステート

フレーム ウィンドウがモーダルかモードレスかを確認します。

```
BOOL InModalState() const;
```

### <a name="return-value"></a>戻り値

はい場合は 0 以外の値。それ以外の場合は 0。

## <a name="cframewndistracking"></a><a name="istracking"></a>フレームウンド::イズトラッキング

ウィンドウ内の分割バーが現在移動中かどうかを調べます。

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>戻り値

分割操作が進行中の場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cframewndloadacceltable"></a><a name="loadacceltable"></a>フレームウンド::ロードアクセルテーブル

指定したアクセラレータ テーブルを読み込むための呼び出し。

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>パラメーター

*リソース名*<br/>
アクセラレータ リソースの名前を識別します。 リソースが整数 ID で識別される場合は、MAKEINTRESOURCE を使用します。

### <a name="return-value"></a>戻り値

アクセラレータ テーブルが正常に読み込まれた場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

一度にロードできるテーブルは 1 つだけです。

リソースから読み込まれたアクセラレータ テーブルは、アプリケーションの終了時に自動的に解放されます。

フレーム ウィンドウ`LoadFrame`を作成するために呼び出すと、フレームワークはメニューリソースとアイコン リソースとともにアクセラレータ テーブルを読み込み、このメンバー関数の後続の呼び出しは不要になります。

## <a name="cframewndloadbarstate"></a><a name="loadbarstate"></a>フレーム化::ロードバーステート

フレーム ウィンドウが所有する各コントロール バーの設定を復元します。

```cpp
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
初期化 (INI) ファイル内のセクションの名前、または状態情報が格納されている Windows レジストリのキー。

### <a name="remarks"></a>解説

復元される情報には、表示、水平/垂直、ドッキング状態、コントロールバーの位置が含まれます。

復元する設定は、 を呼び出す`LoadBarState`前にレジストリに書き込まれていなければなりません。 を呼び出すことによってレジストリに情報を書き込[む::セットレジストリキー](../../mfc/reference/cwinapp-class.md#setregistrykey)を呼び出します。 情報を INI ファイルに書き込むには[、SaveBarState](#savebarstate)を呼び出します。

## <a name="cframewndloadframe"></a><a name="loadframe"></a>フレーム化::ロードフレーム

リソース情報からフレーム ウィンドウを動的に作成する呼び出し。

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
フレーム ウィンドウに関連付けられている共有リソースの ID。

*デフォルトスタイル*<br/>
フレームの[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)。 ウィンドウに表示されるドキュメントの名前をタイトル バーに自動的に表示する場合は、FWS_ADDTOTITLE スタイルを含めます。

*pParentWnd*<br/>
フレームの親へのポインター。

*pContext*<br/>
[構造体](../../mfc/reference/ccreatecontext-structure.md)へのポインター。 このパラメーターは NULL にすることができます。

### <a name="remarks"></a>解説

2`CFrameWnd`つの手順でオブジェクトを作成します。 まず、オブジェクトを構築するコンストラクターを`CFrameWnd`呼び出し、次に`LoadFrame``CFrameWnd`を呼び出します。 *nIDResource*パラメーターは、フレーム ウィンドウのタイトルのメニュー、アクセラレータ テーブル、アイコン、および文字列リソースを指定します。

フレーム`Create`ウィンドウの作成パラメータ`LoadFrame`をすべて指定する場合ではなく、メンバー関数を使用します。

フレームワークは、`LoadFrame`ドキュメント テンプレート オブジェクトを使用してフレーム ウィンドウを作成するときに呼び出します。

フレームワークは、フレーム ウィンドウに接続するオブジェクト (含まれているビュー オブジェクトを含む) を指定するために *、pContext*引数を使用します。 を呼び出`LoadFrame`すときに *、pContext*引数を NULL に設定できます。

## <a name="cframewndm_bautomenuenable"></a><a name="m_bautomenuenable"></a>フレームウンド::m_bAutoMenuEnable

このデータ メンバーが有効 (既定) の場合、ON_UPDATE_COMMAND_UI またはON_COMMAND ハンドラーを持たないメニュー項目は、ユーザーがメニューをプル ダウンしたときに自動的に無効になります。

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>解説

ON_COMMAND ハンドラーを持つメニュー項目は、ON_UPDATE_COMMAND_UI ハンドラーは自動的に有効になりません。

このデータ メンバが設定されている場合、ツール バー ボタンを有効にするのと同じ方法で、メニュー項目が自動的に有効になります。

> [!NOTE]
> `m_bAutoMenuEnable`は、トップレベルのメニュー項目には影響しません。

このデータ メンバーは、現在の選択に基づいてオプション コマンドの実装を簡略化し、メニュー項目を有効または無効にするためのON_UPDATE_COMMAND_UI ハンドラーを記述する必要性を減らします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

## <a name="cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a>フレーム化::ネゴシエートボーダースペース

OLE インプレース アクティブ化時にフレーム ウィンドウの境界領域をネゴシエートします。

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>パラメーター

*ボーダーコマンド*<br/>
に次のいずれかの値が`enum BorderCmd`含まれています。

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*国境を越える*<br/>
[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター、または境界線の座標を指定する[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、OLE 境界領域のネゴシエーションの`CFrameWnd`実装です。

## <a name="cframewndonbarcheck"></a><a name="onbarcheck"></a>フレームオンド::オンバーチェック

指定されたコントロール バーでアクションが実行されるたびに呼び出されます。

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
表示されているコントロール バーの ID。

### <a name="return-value"></a>戻り値

コントロール バーが存在する場合は 0 以外。それ以外の場合は 0。

## <a name="cframewndoncontexthelp"></a><a name="oncontexthelp"></a>フレーム化::オンコンテキストヘルプ

インプレース項目の Shift + F1 ヘルプを処理します。

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>解説

状況依存ヘルプを有効にするには、

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

ステートメントを`CFrameWnd`クラス メッセージ マップに追加し、アクセラレータ テーブルエントリ (通常は SHIFT + F1) を追加して、このメンバー関数を有効にします。

アプリケーションが OLE コンテナの場合`OnContextHelp`は、フレーム ウィンドウ オブジェクトに含まれるすべての埋め込みアイテムをヘルプ モードにします。 カーソルが矢印と疑問符に変わり、マウス ポインタを移動してマウスの左ボタンを押すと、ダイアログ ボックス、ウィンドウ、メニュー、またはコマンド ボタンを選択できます。 このメンバー関数は、カーソルの`WinHelp`下にあるオブジェクトのヘルプ コンテキストを使用して Windows 関数を呼び出します。

## <a name="cframewndoncreateclient"></a><a name="oncreateclient"></a>フレームオンド::オンCreateクライアント

の実行中にフレームワークによって呼び出`OnCreate`されます。

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>パラメーター

*lpcs*<br/>
[構造体への](/windows/win32/api/winuser/ns-winuser-createstructw)ポインター。

*pContext*<br/>
[構造体](../../mfc/reference/ccreatecontext-structure.md)へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数を呼び出すことはありません。

この関数の既定の実装では、`CView`可能な場合は、 *pContext*で提供される情報からオブジェクトを作成します。

`CCreateContext`オブジェクトで渡された値をオーバーライドしたり、フレーム ウィンドウのメイン クライアント領域のコントロールの作成方法を変更したりするには、この関数をオーバーライドします。 オーバーライド`CCreateContext`できるメンバーについては[、CCreateContext](../../mfc/reference/ccreatecontext-structure.md)クラスで説明します。

> [!NOTE]
> 構造体に渡された値を`CREATESTRUCT`置き換えないでください。 これらは情報提供のみを目的とします。 たとえば、初期ウィンドウの四角形をオーバーライドする場合は、`CWnd`メンバー関数[PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow)をオーバーライドします。

## <a name="cframewndonhidemenubar"></a><a name="onhidemenubar"></a>フレーム化::オンハイドメニューバー

この関数は、現在の MFC アプリケーションでメニュー バーを非表示にするときに呼び出されます。

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>解説

このイベント ハンドラーを使用すると、システムがメニューを非表示にするときに、アプリケーションでカスタム アクションを実行できます。 メニューが非表示にならないようにすることはできませんが、たとえば、他のメソッドを呼び出してメニュースタイルや状態を取得することはできます。

## <a name="cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a>フレームウィンドウ::オンセットプレビューモード

印刷プレビュー モードの内外にアプリケーションのメイン フレーム ウィンドウを設定するには、このメンバー関数を呼び出します。

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>パラメーター

*bプレビュー*<br/>
アプリケーションを印刷プレビュー モードにするかどうかを指定します。 印刷プレビューに配置する場合は TRUE に設定し、プレビュー モードをキャンセルするには FALSE に設定します。

*pステート*<br/>
`CPrintPreviewState`構造体へのポインター。

### <a name="remarks"></a>解説

既定の実装では、すべての標準ツールバーが無効になり、メイン メニューとメイン クライアント ウィンドウが非表示になります。 これにより、MDI フレーム ウィンドウが一時的な SDI フレーム ウィンドウになります。

印刷プレビュー中にコントロール バーやその他のフレーム ウィンドウパーツの非表示と表示をカスタマイズするには、このメンバー関数をオーバーライドします。 オーバーライドされたバージョン内から基本クラスの実装を呼び出します。

## <a name="cframewndonshowmenubar"></a><a name="onshowmenubar"></a>フレームオンド::オンショーメニューバー

この関数は、現在の MFC アプリケーションでメニュー バーを表示するときに呼び出されます。

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>解説

このイベント ハンドラーを使用すると、メニューが表示されるときにアプリケーションでカスタム アクションを実行できます。 メニューが表示されないようにすることはできませんが、たとえば、他のメソッドを呼び出してメニュースタイルや状態を取得することはできます。

## <a name="cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a>次の項目を使用します。

関連付けられたメニューが更新されたときに、フレームワークによって呼び出されます。

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
更新コマンドを生成したメニューを表す[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトへのポインター。 更新ハンドラーは、ユーザー インターフェイスを更新する`CCmdUI` *pCmdUI*を使用してオブジェクトの[有効メンバー](../../mfc/reference/ccmdui-class.md#enable)関数を呼び出します。

## <a name="cframewndrecalclayout"></a><a name="recalclayout"></a>フレーム化::レカルクレイアウト

標準のコントロール バーのオンとオフを切り替えるとき、またはフレーム ウィンドウのサイズが変更されたときに、フレームワークによって呼び出されます。

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*通知する*<br/>
フレーム ウィンドウのアクティブなインプレイス アイテムがレイアウト変更の通知を受け取るかどうかを判断します。 TRUE の場合、アイテムに通知されます。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメンバー関数の既定の実装では、`CWnd`メンバー関数`RepositionBars`を呼び出して、フレーム内のすべてのコントロール バーとメイン クライアント ウィンドウ (通常`CView`は MDICLIENT) を再配置します。

フレーム ウィンドウのレイアウトが変更された後のコントロール バーの外観と動作を制御するには、このメンバー関数をオーバーライドします。 たとえば、コントロール バーのオンとオフを切り離したり、別のコントロール バーを追加したりする場合に呼び出します。

## <a name="cframewndrectdefault"></a><a name="rectdefault"></a>フレームの種類::既定

ウィンドウを作成`CRect`するときにこの静的変数をパラメーターとして渡して、ウィンドウの初期サイズと位置を Windows が選択できるようにします。

```
static AFX_DATA const CRect rectDefault;
```

## <a name="cframewndsavebarstate"></a><a name="savebarstate"></a>フレーム化::セーブバーステート

フレーム ウィンドウが所有する各コントロール バーに関する情報を格納します。

```cpp
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
初期化ファイル内のセクションの名前、または状態情報が格納されている Windows レジストリのキー。

### <a name="remarks"></a>解説

この情報は[、LoadBarState](#loadbarstate)を使用して初期化ファイルから読み取ることができます。 格納される情報には、表示設定、水平/垂直の向き、ドッキング状態、コントロール バーの位置が含まれます。

## <a name="cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a>フレームウィンドウ::アクティブプレビュービュー

リッチ プレビューのアクティブ ビューとして指定したビューを指定します。

```cpp
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>パラメーター

*新しいビュー*<br/>
アクティブ化するビューへのポインター。

### <a name="remarks"></a>解説

## <a name="cframewndsetactiveview"></a><a name="setactiveview"></a>フレーム化::アクティブビュー

アクティブ なビューを設定するには、このメンバー関数を呼び出します。

```cpp
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*新しいビュー*<br/>
[CView](../../mfc/reference/cview-class.md)オブジェクトへのポインターを指定します。

*通知する*<br/>
ビューにアクティブ化の通知を受け取るかどうかを指定します。 TRUE の`OnActivateView`場合は、新しいビューに対して呼び出されます。FALSE の場合は、そうではありません。

### <a name="remarks"></a>解説

フレームワークは、ユーザーがフレーム ウィンドウ内のビューにフォーカスを変更すると、自動的にこの関数を呼び出します。 明示的に呼び出`SetActiveView`して、指定したビューにフォーカスを変更できます。

## <a name="cframewndsetdockstate"></a><a name="setdockstate"></a>フレームウンド::セットドックステート

オブジェクトに格納されている状態情報を`CDockState`フレーム ウィンドウのコントロール バーに適用します。

```cpp
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>パラメーター

*state*<br/>
保存された状態をフレーム ウィンドウのコントロール バーに適用します。

### <a name="remarks"></a>解説

コントロール バーの以前の状態を復元するには、 または`CDockState::LoadState``Serialize`を使用`SetDockState`して保存された状態をフレーム ウィンドウのコントロール バーに適用します。 前の状態は、オブジェクトに`CDockState`格納されます。`GetDockState`

## <a name="cframewndsetmenubarstate"></a><a name="setmenubarstate"></a>フレーム化::セットメニューバーステート

現在の MFC アプリケーションのメニューの表示状態を非表示または表示に設定します。

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nステート*|[in]メニューを表示するか非表示にするかを指定します。 *nState*パラメーターには、次の値を指定できます。<br /><br />- AFX_MBS_VISIBLE (0x01) - 非表示のメニューが表示されますが、表示されている場合は効果はありません。<br />- AFX_MBS_HIDDEN (0x02) - メニューが表示されている場合は非表示になりますが、非表示の場合は効果はありません。|

### <a name="return-value"></a>戻り値

このメソッドがメニューの状態を正常に変更した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ランタイム エラーが発生した場合、このメソッドはデバッグ モードでアサートし[、CException](../../mfc/reference/cexception-class.md)クラスから派生した例外を発生させます。

## <a name="cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a>フレーム化::セットメニューバーの可視性

現在の MFC アプリケーションのメニューの既定の動作を、非表示または表示に設定します。

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nStyle*|[in]メニューが既定で非表示にするか、または表示されてフォーカスを持つかを指定します。 *nStyle*パラメーターには、次の値を指定できます。<br /><br />- AFX_MBV_KEEPVISIBLE (0x01) -<br />     メニューは常に表示され、デフォルトではフォーカスはありません。<br />- AFX_MBV_DISPLAYONFOCUS (0x02) -<br />     メニューはデフォルトで非表示になっています。 メニューが非表示になっている場合は、Alt キーを押してメニューを表示し、フォーカスを移動します。 メニューが表示されている場合は、Alt キーまたは Esc キーを押してメニューを非表示にします。<br />- AFX_MBV_ディスプレイオンフォーカス (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (ビットごとの組み合わせ (OR) - メニューはデフォルトで非表示になっています。 メニューが非表示の場合は、F10 キーを押してメニューを表示し、フォーカスを移動します。 メニューが表示されている場合は、F10 キーを押して、フォーカスをメニューのオンまたはオフに切り替えます。 メニューは、Alt キーまたは Esc キーを押して非表示にするまで表示されます。|

### <a name="remarks"></a>解説

*nStyle*パラメーターの値が無効な場合、このメソッドはデバッグ モードでアサートし、リリース モードで[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)を発生させます。 他のランタイム エラーの場合、このメソッドはデバッグ モードでアサートし[、CException](../../mfc/reference/cexception-class.md)クラスから派生した例外を発生させます。

このメソッドは、Windows Vista 以降のために作成されたアプリケーションのメニューの状態に影響します。

## <a name="cframewndsetmessagetext"></a><a name="setmessagetext"></a>フレームテキスト::メッセージテキスト

ID が 0 のステータス バー ペインに文字列を配置します。

```cpp
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
ステータス バーに配置する文字列へのポイント。

*nID*<br/>
ステータス バーに配置する文字列のリソース ID を文字列で指定します。

### <a name="remarks"></a>解説

通常、これはステータス バーの左端の最も長いペインです。

## <a name="cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a>フレームの割り込み:::設定プログレスバーポジション

タスク バーに表示される Windows 7 プログレス バーの現在位置を設定します。

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>パラメーター

*経過中のポス*<br/>
設定する位置を指定します。 で設定した範囲内になければなりません`SetProgressBarRange`。

### <a name="remarks"></a>解説

## <a name="cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a>フレームの種類::設定プログレスバーレンジ

タスク バーに表示される Windows 7 プログレス バーの範囲を設定します。

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>パラメーター

*nレンジミン*<br/>
最小の値。

*nレンジマックス*<br/>
最大値。

### <a name="remarks"></a>解説

## <a name="cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a>フレーム化::設定プログレスバーステート

タスク バー ボタンに表示される進行状況インジケーターの種類と状態を設定します。

```cpp
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>パラメーター

*tbpフラグ*<br/>
進行状況ボタンの現在の状態を制御するフラグ。 すべての状態が相互に排他的であるため、TBPF_NOPROGRESS、TBPF_INDETERMINATE、TBPF_NORMAL、TBPF_ERROR、TBPF_PAUSEDのフラグを 1 つだけ指定します。

### <a name="remarks"></a>解説

## <a name="cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a>フレームアイコン::タスクバーオーバーレイアイコン

オーバーロードされます。 アプリケーションの状態を示す、またはユーザーに通知するタスク バー ボタンにオーバーレイを適用します。

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);

BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
オーバーレイとして使用するアイコンのリソース ID を指定します。 詳細については *、hIcon*の説明を参照してください。

*lpcszDescr*<br/>
アクセシビリティを目的として、オーバーレイによって伝達される情報の代替テキストバージョンを提供する文字列へのポインター。

*Hicon*<br/>
オーバーレイとして使用するアイコンのハンドル。 これは、16 x 16 ピクセルを 96 ドット/インチ (dpi) で測定する小さなアイコンにする必要があります。 タスク バー ボタンに既にオーバーレイ アイコンが適用されている場合、その既存のオーバーレイは置き換えられます。 この値は NULL にできます。 NULL 値の処理方法は、タスク バー ボタンが 1 つのウィンドウを表すか、ウィンドウのグループを表すかによって異なります。 必要がなくなったときに、呼び出し側アプリケーションは*hIcon*を解放する必要があります。

### <a name="return-value"></a>戻り値

成功した場合は TRUE。OS のバージョンが Windows 7 より小さい場合、またはアイコンの設定でエラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cframewndsettitle"></a><a name="settitle"></a>フレームを組み合わせた::セットタイトル

ウィンドウ オブジェクトのタイトルを設定します。

```cpp
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>パラメーター

*lpszタイトル*<br/>
ウィンドウ オブジェクトのタイトルを含む文字列へのポインター。

## <a name="cframewndshowcontrolbar"></a><a name="showcontrolbar"></a>フレーム化::ショーコントロールバー

コントロール バーの表示と非表示を切り替える場合は、このメンバー関数を呼び出します。

```cpp
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
表示または非表示にするコントロール バーへのポインター。

*bショー*<br/>
TRUE の場合、コントロール バーが表示されることを指定します。 FALSE の場合、コントロール バーを非表示にすることを指定します。

*bディレイ*<br/>
TRUE の場合は、コントロール バーの表示を遅らせる。 FALSE の場合は、コントロール バーをすぐに表示します。

## <a name="cframewndshowownedwindows"></a><a name="showownedwindows"></a>フレームウンド::ショー所有のウィンドウズ

`CFrameWnd`オブジェクトの子孫であるすべてのウィンドウを表示します。

```cpp
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
所有するウィンドウを表示するか非表示にするかを指定します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[クラス](../../mfc/reference/cdoctemplate-class.md)<br/>
[構造体](../../mfc/reference/cruntimeclass-structure.md)
