---
title: CFrameWnd クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0be95b0092db315dd3af7086770411b93eb2ae23
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955213"
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
|[CFrameWnd::ActivateFrame](#activateframe)|ユーザーへ表示され、使用可能なフレームを作成します。|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|フレーム ウィンドウをモーダルに設定します。|  
|[CFrameWnd::Create](#create)|作成し、初期化に関連付けられている Windows フレーム ウィンドウへの呼び出し、`CFrameWnd`オブジェクト。|  
|[CFrameWnd::CreateView](#createview)|派生していないフレーム内でビューを作成`CView`です。|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|コントロール バーをドッキングします。|  
|[CFrameWnd::EnableDocking](#enabledocking)|ドッキング コントロール バーを使用できます。|  
|[CFrameWnd::EndModalState](#endmodalstate)|フレーム ウィンドウのモーダル状態を終了します。 により、すべてのウィンドウでによって無効になっている`BeginModalState`です。|  
|[切り離すには](#floatcontrolbar)|コントロール バーを寄せて配置します。|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|返します、アクティブな`CDocument`オブジェクト。|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|返します、アクティブな`CFrameWnd`オブジェクト。|  
|[CFrameWnd::GetActiveView](#getactiveview)|返します、アクティブな`CView`オブジェクト。|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|コントロール バーを取得します。|  
|[CFrameWnd::GetDockState](#getdockstate)|フレーム ウィンドウのドッキング状態を取得します。|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|現在の MFC アプリケーション メニューの表示状態を取得します。|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|現在の MFC アプリケーション メニューの既定の動作を表示または非表示のいずれかにするかどうかを示します。|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|ステータス バーのフレーム ウィンドウに属するへのポインターを返します。|  
|[CFrameWnd::GetMessageString](#getmessagestring)|コマンド ID に対応するメッセージを取得します|  
|[CFrameWnd::GetTitle](#gettitle)|関連するコントロール バーのタイトルを取得します。|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|により、`OnInitialUpdate`メンバー関数が呼び出されるフレーム ウィンドウのすべてのビューに属しています。|  
|[CFrameWnd::InModalState](#inmodalstate)|フレーム ウィンドウがモーダルの状態であるかどうかどうかを示す値を返します。|  
|[CFrameWnd::IsTracking](#istracking)|分割バーが移動されて現在かどうかを判断します。|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|アクセラレータ テーブルを読み込むへの呼び出し。|  
|[CFrameWnd::LoadBarState](#loadbarstate)|コントロール バーの設定を復元する呼び出しです。|  
|[CFrameWnd::LoadFrame](#loadframe)|リソースの情報からフレーム ウィンドウを動的に作成する呼び出しです。|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|フレーム ウィンドウの境界領域をネゴシエートします。|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|指定されたコントロール バーで、アクションが実行されるたびに呼び出されます。|  
|[受信](#oncontexthelp)|埋め込み先アイテムについては、shift キーを押しながら f1 キーを処理します。|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|印刷プレビュー モードに出入りするアプリケーションのメイン フレーム ウィンドウを設定します。|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|関連のメニューが更新されたときに、フレームワークによって呼び出されます。|  
|[表示](#recalclayout)|コントロール バーの位置を変更、`CFrameWnd`オブジェクト。|  
|[CFrameWnd::SaveBarState](#savebarstate)|コントロール バーの設定を保存する呼び出しです。|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|リッチ プレビュー用のアクティブなビューを指定されたビューを指定します。|  
|[CFrameWnd::SetActiveView](#setactiveview)|アクティブな設定`CView`オブジェクト。|  
|[CFrameWnd::SetDockState](#setdockstate)|メイン ウィンドウで、フレーム ウィンドウのドッキングを呼び出します。|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|非表示または表示する現在の MFC アプリケーションで、メニューの表示状態を設定します。|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|非表示または非表示には、現在の MFC アプリケーションで、メニューの既定の動作を設定します。|  
|[CFrameWnd::SetMessageText](#setmessagetext)|標準的なステータス バーのテキストを設定します。|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|タスク バーに表示される Windows 7 の進行状況バーの現在位置を設定します。|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|タスク バーに表示される Windows 7 の進行状況バーの範囲を設定します。|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|タスク バー ボタンに表示される進行状況インジケーターの状態と型を設定します。|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|オーバーロードされます。 アプリケーションの状態や、ユーザーに通知を示すためにタスク バー ボタンにオーバーレイを適用します。|  
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
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|自動コントロールは、有効にして、メニュー項目の機能を無効にします。|  
|[CFrameWnd::rectDefault](#rectdefault)|静的に渡す`CRect`を作成する際に、パラメーターとして、`CFrameWnd`ウィンドウの初期サイズと位置を選択するウィンドウを許可するオブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 アプリケーション用に役立ちますフレーム ウィンドウを作成するには、派生クラスを`CFrameWnd`です。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 これには、フレーム ウィンドウを構築するために 3 つの方法があります。  
  
-   使用して直接構築[作成](#create)です。  
  
-   使用して直接構築[LoadFrame](#loadframe)です。  
  
-   間接的に構築ドキュメント テンプレートを使用します。  
  
 いずれかを呼び出す前に`Create`または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウ オブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に`Create`、ウィンドウ クラスを登録することも、 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。  
  
 使用して、`Create`引数を渡す、フレームの作成パラメーターとして直接のメンバー関数。  
  
 `LoadFrame` も少ない引数を必要と`Create`、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースからほとんどの既定値を取得します。 によってアクセスされる`LoadFrame`、これらすべてのリソースが同じリソース ID を持つ必要があります (たとえば、 **IDR_MAINFRAME**)。  
  
 ときに、`CFrameWnd`オブジェクトには、ビューやドキュメントが含まれています、によって作成されるない直接の代わりに、プログラマが直接のフレームワークです。 `CDocTemplate`オブジェクトは、フレームの作成、コンテナーのビューの作成と適切なドキュメント ビューの接続を統制します。 パラメーター、`CDocTemplate`コンス トラクターを指定して、 `CRuntimeClass` 3 つのクラスの関係 (ドキュメント、フレーム、および表示)。 A`CRuntimeClass`オブジェクトを動的に (たとえば、ファイルの新規作成 コマンドまたは複数ドキュメント インターフェイス (MDI) の新しいウィンドウ コマンドを使用して) を指定すると、ユーザーが新しいフレームを作成する、フレームワークによって使用されます。  
  
 フレーム ウィンドウ クラスから派生`CFrameWnd`で宣言する必要があります`DECLARE_DYNCREATE`上記の順序で`RUNTIME_CLASS`正常に動作するためのメカニズムです。  
  
 A `CFrameWnd` Windows の一般的なアプリケーションのメイン ウィンドウの次の関数を実行する既定の実装が含まれます。  
  
-   A`CFrameWnd`フレーム ウィンドウの追跡、Windows のアクティブなウィンドウまたは現在の入力フォーカスの独立した現在アクティブなビューです。 アクティブなビューを呼び出すことによって通知、フレームが再アクティブ化された`CView::OnActivateView`です。  
  
-   コマンド メッセージおよびによって処理されるものなど、多くの一般的なフレーム通知メッセージ、 `OnSetFocus`、 `OnHScroll`、および`OnVScroll`関数の`CWnd`で委任され、`CFrameWnd`現在アクティブなビューをフレーム ウィンドウです。  
  
-   現在アクティブなビュー (またはの場合は、MDI フレームの現在アクティブな MDI 子フレーム ウィンドウ) には、フレーム ウィンドウのキャプションを決定できます。 無効にして、この機能を無効にすることができます、 **FWS_ADDTOTITLE**フレーム ウィンドウのスタイル ビットです。  
  
-   A`CFrameWnd`フレーム ウィンドウは、コントロール バー、ビュー、およびその他の子ウィンドウ フレーム ウィンドウのクライアント領域内の位置を管理します。 フレーム ウィンドウは、ツールバーとその他のコントロール バーのボタンのアイドル時間の更新も行います。 A`CFrameWnd`フレーム ウィンドウは上と、ツールバーとステータス バーがオフの切り替え用のコマンドの既定の実装もあります。  
  
-   A`CFrameWnd`フレーム ウィンドウは、メイン メニュー バーを管理します。 フレーム ウィンドウを使用して、ポップアップ メニューが表示されたら、 **UPDATE_COMMAND_UI**有効、無効になっている、またはチェックするメニュー項目を決定するメカニズムです。 ユーザーがメニュー項目を選択すると、フレーム ウィンドウは、そのコマンドのメッセージ文字列でステータス バーを更新します。  
  
-   A`CFrameWnd`フレーム ウィンドウがキーボード アクセラレータを自動的に変換する省略可能なアクセラレータ テーブル。  
  
-   A`CFrameWnd`フレーム ウィンドウで設定されたオプションのヘルプ ID を持つ`LoadFrame`状況依存のヘルプで使用されます。 フレーム ウィンドウは、セミモーダル状態 (shift キーを押しながら f1 キー) の状況依存のヘルプと印刷プレビュー モードなどの主要な orchestrator です。  
  
-   A`CFrameWnd`フレーム ウィンドウがフレーム ウィンドウにファイル マネージャーからのドラッグ アンド ドロップ ファイルを開きます。 ファイル拡張子が登録されている、アプリケーションに関連付けられている場合は、フレーム ウィンドウ要求に応答するダイナミック データ エクス (チェンジ DDE) 開くまたはユーザーがファイル マネージャーで、データ ファイルを開いたときに発生する、 **ShellExecute**Windows の関数が呼び出されます。  
  
-   フレーム ウィンドウがアプリケーションのメイン ウィンドウの場合 (つまり、 `CWinThread::m_pMainWnd`)、ユーザーが、アプリケーションを閉じるときに、フレーム ウィンドウには、変更後のすべてのドキュメントを保存するように求める (の`OnClose`と`OnQueryEndSession`)。  
  
-   フレーム ウィンドウがアプリケーションのメイン ウィンドウの場合は、フレーム ウィンドウの WinHelp の実行コンテキストです。 WINHELP をシャット ダウンは、フレーム ウィンドウを終了します。このアプリケーションのヘルプが起動された場合は EXE です。  
  
 C++ を使用しないでください**削除**フレーム ウィンドウを破棄する演算子です。 代わりに、`CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ オブジェクトが削除されます。 ユーザーが既定値であるフレーム ウィンドウを閉じたとき`OnClose`ハンドラーを呼び出す`DestroyWindow`です。  
  
 詳細については`CFrameWnd`を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="activateframe"></a>  CFrameWnd::ActivateFrame  
 アクティブ化し、が表示され、使用可能なユーザーにできるように、フレーム ウィンドウを復元するには、このメンバー関数を呼び出します。  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 *nCmdShow*  
 渡すパラメーターを指定します[また](../../mfc/reference/cwnd-class.md#showwindow)です。 既定では、フレームが表示され、正常に復元します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は通常、DDE、OLE、またはその他のイベントをユーザーに、フレーム ウィンドウまたはその内容を表示することがありますなどの非ユーザー インターフェイス イベント後に呼び出されます。  
  
 既定の実装、フレームをアクティブに Z オーダーの最上位に表示および、必要に応じて、アプリケーションのメイン フレーム ウィンドウと同じ手順を実行します。  
  
 フレームをアクティブにする方法を変更するには、このメンバー関数をオーバーライドします。 たとえば、MDI 子ウィンドウを最大化を強制することができます。 適切な機能を追加し、明示的な基底クラスのバージョンを呼び出す*nCmdShow*です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="beginmodalstate"></a>  CFrameWnd::BeginModalState  
 フレーム ウィンドウをモーダルにします。  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="cframewnd"></a>  CFrameWnd::CFrameWnd  
 構築、`CFrameWnd`オブジェクトは、表示されるフレーム ウィンドウを作成しません。  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す**作成**表示ウィンドウを作成します。  
  
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
 *lpszClassName*  
 Windows クラスの名前を null で終わる文字列へのポインター。 クラス名に登録されている任意の名前を指定できます、`AfxRegisterWndClass`グローバル関数または**RegisterClass** Windows の機能です。 場合**NULL**、定義済みの既定値を使用して`CFrameWnd`属性。  
  
 *したとき*  
 ウィンドウの名前を表す文字の null で終わる文字列へのポインター。 タイトル バーのテキストとして使用します。  
  
 *dwStyle*  
 ウィンドウを指定[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)属性。 含める、 **FWS_ADDTOTITLE**  ウィンドウで表されるドキュメントの名前を自動的に表示するタイトル バーをする場合のスタイルを設定します。  
  
 *rect*  
 ウィンドウの位置とサイズを指定します。 *RectDefault*値により、Windows を新しいウィンドウの位置とサイズを指定します。  
  
 *pParentWnd*  
 このフレーム ウィンドウの親ウィンドウを指定します。 このパラメーターを指定する必要があります**NULL**トップレベルのフレーム ウィンドウです。  
  
 *lpszMenuName*  
 ウィンドウで使用するメニュー リソースの名前を識別します。 使用して**されるときは**メニューに、文字列の代わりに整数の ID がある場合。 このパラメーターを指定できます**NULL**です。  
  
 *dwExStyle*  
 ウィンドウの拡張[スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)属性。  
  
 *pContext*  
 ポインターを指定します、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターを指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 構築、 `CFrameWnd` 2 つのステップ内のオブジェクト。 最初に、構築コンス トラクターを呼び出し、`CFrameWnd`オブジェクト、およびを呼び出す`Create`、ウィンドウ フレームを作成およびにアタッチする、`CFrameWnd`オブジェクト。 `Create` ウィンドウのクラス名とウィンドウの名前を初期化し、既定値、スタイル、親、および関連メニューを登録します。  
  
 使用して`LoadFrame`なく`Create`引数を指定する代わりに、そのリソースからフレーム ウィンドウを読み込めません。  
  
##  <a name="createview"></a>  CFrameWnd::CreateView  
 呼び出す`CreateView`フレーム内でビューを作成します。  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>パラメーター  
 *pContext*  
 ビューとドキュメントの種類を指定します。  
  
 *nID*  
 ビューの ID 番号。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CWnd`それ以外の成功した場合は、オブジェクト**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 「ビュー」を作成するこのはないメンバー関数を使用して`CView`-フレーム内で派生します。 呼び出した後`CreateView`、手動でアクティブにビューを設定し、表示されるように設定する必要があります以外の場合はこれらのタスクが自動的に実行されない`CreateView`です。  
  
##  <a name="dockcontrolbar"></a>  CFrameWnd::DockControlBar  
 フレーム ウィンドウにドッキングするコントロール バーが発生します。  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pBar*  
 ドッキング コントロール バーへのポインター。  
  
 *辺*  
 フレーム ウィンドウにドッキングのどの辺を決定します。 0 または 1 つ以上の次を指定できます。  
  
- `AFX_IDW_DOCKBAR_TOP` フレーム ウィンドウの最上位の側にドッキングします。  
  
- `AFX_IDW_DOCKBAR_BOTTOM` フレーム ウィンドウの下の辺にドッキングします。  
  
- `AFX_IDW_DOCKBAR_LEFT` フレーム ウィンドウの左側にドッキングします。  
  
- `AFX_IDW_DOCKBAR_RIGHT` フレーム ウィンドウの右側にドッキングします。  
  
 0 の場合、移行先フレーム ウィンドウのドッキングできる任意の辺に、コントロール バーをドッキングできます。  
  
 *lpRect*  
 コントロール バーをドッキングする、移行先フレーム ウィンドウの非クライアント領域で、画面座標を判断します。  
  
### <a name="remarks"></a>Remarks  
 両方への呼び出しで指定したフレーム ウィンドウの辺のいずれかにドッキングするコントロール バー [CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)と[CFrameWnd::EnableDocking](#enabledocking)です。 面選択はによって決まります*辺*です。  
  
##  <a name="enabledocking"></a>  CFrameWnd::EnableDocking  
 フレーム ウィンドウのドッキング可能なコントロール バーを有効にするには、この関数を呼び出します。  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDockStyle*  
 フレーム ウィンドウのどの辺がドッキング コントロール バー用のサイトとして使用できるように指定します。 次の 1 つ以上を指定できます。  
  
- `CBRS_ALIGN_TOP` クライアント領域の上部にドッキングできます。  
  
- `CBRS_ALIGN_BOTTOM` クライアント領域の下部にドッキングできます。  
  
- `CBRS_ALIGN_LEFT` クライアント領域の左側にドッキングできます。  
  
- `CBRS_ALIGN_RIGHT` クライアント領域の右側にドッキングできます。  
  
- `CBRS_ALIGN_ANY` クライアント領域の任意の辺にドッキングできます。  
  
### <a name="remarks"></a>Remarks  
 既定では、コントロール バーを次の順序でフレーム ウィンドウの一辺にドッキングされます: top、bottom、left、right です。  
  
### <a name="example"></a>例  
  例を参照して[用意されて](../../mfc/reference/ctoolbar-class.md#create)です。  
  
##  <a name="endmodalstate"></a>  CFrameWnd::EndModalState  
 フレーム ウィンドウをモーダルからモードレスに変更します。  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>Remarks  
 `EndModalState` により、すべてのウィンドウでによって無効になっている[BeginModalState](#beginmodalstate)です。  
  
##  <a name="floatcontrolbar"></a>  切り離すには  
 この関数ではないフレーム ウィンドウにドッキングするコントロール バーです。  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>パラメーター  
 *pBar*  
 フローティングするコントロール バーへのポインター。  
  
 *ポイント*  
 内の位置を画面座標では、コントロール バーの左上隅を配置する場所。  
  
 *dwStyle*  
 新しいフレーム ウィンドウ内で、コントロール バーを水平方向または垂直方向に整列するかどうかを指定します。 次のいずれかを指定できます。  
  
- `CBRS_ALIGN_TOP` コントロール バーを垂直方向します。  
  
- `CBRS_ALIGN_BOTTOM` コントロール バーを垂直方向します。  
  
- `CBRS_ALIGN_LEFT` コントロール バーが横向きにします。  
  
- `CBRS_ALIGN_RIGHT` コントロール バーが横向きにします。  
  
 水平および垂直方向の両方の方向を指定するスタイルが渡された場合、ツールバーなります指向水平方向にします。  
  
### <a name="remarks"></a>Remarks  
 通常、これは、アプリケーションの起動時にプログラムが前回の実行から設定を復元するときにします。  
  
 この関数は、ユーザーがドッキングが利用できない場所経由でのコントロール バーをドラッグするときにマウスの左ボタンを離すのドロップ操作の原因と、フレームワークによって呼び出されます。  
  
##  <a name="getactivedocument"></a>  CFrameWnd::GetActiveDocument  
 現在へのポインターを取得するには、このメンバー関数を呼び出す**CDocument**現在アクティブなビューにアタッチします。  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>戻り値  
 現在へのポインター [CDocument](../../mfc/reference/cdocument-class.md)です。 現在のドキュメントがない場合を返します**NULL**です。  
  
##  <a name="getactiveframe"></a>  CFrameWnd::GetActiveFrame  
 マルチ ドキュメント インターフェイス (MDI) 子ウィンドウの MDI フレーム ウィンドウのアクティブなへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>戻り値  
 アクティブな MDI 子ウィンドウへのポインター。 かどうか、アプリケーションは、SDI アプリケーション、または MDI フレーム ウィンドウがアクティブなドキュメント、暗黙的なを持たない**この**ポインターが返されます。  
  
### <a name="remarks"></a>Remarks  
 アクティブな MDI 子がないか、アプリケーションは、暗黙的なシングル ドキュメント インターフェイス (SDI)、**この**ポインターが返されます。  
  
##  <a name="getactiveview"></a>  CFrameWnd::GetActiveView  
 フレーム ウィンドウにアタッチされているアクティブなビュー (存在する場合) へのポインターを取得するには、このメンバー関数を呼び出します ( `CFrameWnd`)。  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在へのポインター [CView](../../mfc/reference/cview-class.md)です。 現在のビューがない場合を返します**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 この関数を返します**NULL** MDI メイン フレーム ウィンドウに対して呼び出されると ( `CMDIFrameWnd`)。 MDI アプリケーションでは、MDI メイン フレーム ウィンドウに関連付けられているビューはありません。 代わりに、それぞれ個別の子ウィンドウ ( `CMDIChildWnd`) は 1 つまたは複数の関連するビューがあります。 MDI アプリケーションでアクティブなビューは、まずアクティブな MDI 子ウィンドウの検索とその子ウィンドウのアクティブなビューを検索して取得できます。 関数を呼び出すことによってアクティブな MDI 子ウィンドウが見つかりません`MDIGetActive`または`GetActiveFrame`次に示すようにします。  
  
 [!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="getcontrolbar"></a>  CFrameWnd::GetControlBar  
 呼び出す`GetControlBar`ID に関連付けられているコントロール バーへのアクセスを取得するには  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 コントロール バーの ID 番号。  
  
### <a name="return-value"></a>戻り値  
 ID に関連付けられているコントロール バーへのポインター  
  
### <a name="remarks"></a>Remarks  
 *NID*パラメーターに渡される一意の識別子を参照、`Create`コントロール バーのメソッドです。 コントロール バーの詳細については、のトピックを参照してください[コントロール バー](../../mfc/control-bars.md)です。  
  
 `GetControlBar` 浮動およびしたがってされていない子ウィンドウ フレームの場合でも、コントロール バーを返します。  
  
##  <a name="getdockstate"></a>  CFrameWnd::GetDockState  
 フレーム ウィンドウのコントロール バーの状態情報を格納するには、このメンバー関数を呼び出す、`CDockState`オブジェクト。  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *state*  
 関数が戻るとき、フレーム ウィンドウのコントロール バーの現在の状態が含まれています。  
  
### <a name="remarks"></a>Remarks  
 内容を記述することができますし、`CDockState`記憶域を使用する`CDockState::SaveState`または`Serialize`です。 後でコントロール バーを以前の状態に復元する場合での状態を読み込む`CDockState::LoadState`または`Serialize`、まず`SetDockState`フレーム ウィンドウのコントロール バーに以前の状態を適用します。  
  
##  <a name="getmenubarstate"></a>  CFrameWnd::GetMenuBarState  
 現在の MFC アプリケーション メニューの表示状態を取得します。  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値は、次の値を持つことができます。  
  
-   AFX_MBS_VISIBLE (0x01) で、メニューは表示されます。  
  
-   AFX_MBS_HIDDEN (0x02) で、メニューを非表示にします。  
  
### <a name="remarks"></a>Remarks  
 このメソッドはデバッグ モードでアサートし、派生する例外を発生させます。 ランタイム エラーが発生した場合、 [CException](../../mfc/reference/cexception-class.md)クラスです。  
  
##  <a name="getmenubarvisibility"></a>  CFrameWnd::GetMenuBarVisibility  
 現在の MFC アプリケーション メニューの既定の状態が表示または非表示かどうかを示します。  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、次の値のいずれかを返します。  
  
-   AFX_MBV_KEEPVISIBLE (0x01) で、メニューが表示されるすべての時刻、および既定値は、フォーカスを持っていません。  
  
-   AFX_MBV_DISPLAYONFOCUS (0x02) - 既定では、メニューは表示されません。 メニューが表示されていない場合は、メニューを表示して、フォーカスに ALT キーを押します。 メニューが表示される場合は、非表示に alt キーまたは ESC キーを押します。  
  
-   AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (ビットごとの組み合わせ (OR)) - 既定では、メニューは表示されません。 メニューが表示されていない場合は、メニューを表示して、フォーカスを F10 キーを押します。 メニューが表示される場合をオンまたはオフ、メニュー、フォーカスを切り替える F10 キーを押します。 非表示にする、alt キーまたは ESC キーを押すまで、メニューが表示されます。  
  
### <a name="remarks"></a>Remarks  
 このメソッドはデバッグ モードでアサートし、派生する例外を発生させます。 ランタイム エラーが発生した場合、 [CException](../../mfc/reference/cexception-class.md)クラスです。  
  
##  <a name="getmessagebar"></a>  CFrameWnd::GetMessageBar  
 ステータス バーへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>戻り値  
 ステータス バー ウィンドウへのポインター。  
  
##  <a name="getmessagestring"></a>  CFrameWnd::GetMessageString  
 コマンド Id のカスタム文字列を指定するには、この関数をオーバーライドします。  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 目的のメッセージのリソース ID です。  
  
 *rMessage*  
 `CString` メッセージを格納するオブジェクトです。  
  
### <a name="remarks"></a>Remarks  
 既定の実装がで指定された文字列を単に読み込みます*nID*リソース ファイルからです。 この関数はステータス バーにメッセージ文字列の更新が必要なときにフレームワークによって呼び出されます。  
  
##  <a name="gettitle"></a>  CFrameWnd::GetTitle  
 ウィンドウ オブジェクトのタイトルを取得します。  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ウィンドウ オブジェクトの現在のタイトルを含むオブジェクト。  
  
##  <a name="initialupdateframe"></a>  CFrameWnd::InitialUpdateFrame  
 呼び出す**IntitialUpdateFrame**で新しいフレームを作成した後**作成**です。  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDoc*  
 フレーム ウィンドウが関連付けられているドキュメントへのポインター。 指定できます**NULL**です。  
  
 *bMakeVisible*  
 場合**TRUE**、フレームが表示され、アクティブになることを示します。 場合**FALSE**子孫が作成されていない表示します。  
  
### <a name="remarks"></a>Remarks  
 これにより、受信するには、そのフレーム ウィンドウ内のすべてのビュー、`OnInitialUpdate`呼び出しです。  
  
 また、存在していなかった以前、アクティブなビュー、フレーム ウィンドウの主要なビューがアクティブなが作成されます。 プライマリ ビューの子の ID を持つビュー **AFX_IDW_PANE_FIRST**です。 フレーム ウィンドウが表示されます。 最後に、場合*bMakeVisible*は 0 以外。 場合*bMakeVisible*が 0 の場合、現在フォーカスをフレーム ウィンドウの表示の状態は変更されません。 新しいファイルとファイルを開くのフレームワークの実装を使用する場合は、この関数を呼び出す必要はありません。  
  
##  <a name="inmodalstate"></a>  CFrameWnd::InModalState  
 フレーム ウィンドウをモーダルまたはモードレス チェックするには、このメンバー関数を呼び出します。  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は yes です。それ以外の場合 0 を返します。  
  
##  <a name="istracking"></a>  CFrameWnd::IsTracking  
 かどうかは、ウィンドウの分割バーが移動されている現在を決定するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>戻り値  
 分割操作の実行中である場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="loadacceltable"></a>  CFrameWnd::LoadAccelTable  
 指定されたアクセラレータ テーブルを読み込むに呼び出します。  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszResourceName*  
 アクセラレータ リソースの名前を識別します。 使用して**されるときは**リソースが整数の ID で識別された場合  
  
### <a name="return-value"></a>戻り値  
 アクセラレータ テーブル読み込みが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 1 つのテーブルは、同時に読み込むことができます。  
  
 アクセラレータ テーブル リソースから読み込まれますが、アプリケーションの終了時に自動的に解放されます。  
  
 呼び出す場合`LoadFrame`フレーム ウィンドウを作成するために、フレームワークがメニューおよびアイコンのリソースと一緒にアクセラレータ テーブルを読み込むし、以降このメンバー関数を呼び出す必要はありません。  
  
##  <a name="loadbarstate"></a>  CFrameWnd::LoadBarState  
 フレーム ウィンドウが所有する各コントロール バーの設定を復元するには、この関数を呼び出します。  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszProfileName*  
 初期化 (INI) ファイルのセクションまたは状態情報が格納されている Windows レジストリのキーの名前。  
  
### <a name="remarks"></a>Remarks  
 復元情報には、可視性、水平、垂直方向、ドッキング状態、およびコントロール バーの位置が含まれます。  
  
 呼び出す前に、レジストリに書き込まれる、設定を復元する`LoadBarState`です。 呼び出して情報をレジストリに書き込む[書き込むに](../../mfc/reference/cwinapp-class.md#setregistrykey)です。 呼び出して、INI ファイルに情報を書き込む[に](#savebarstate)です。  
  
##  <a name="loadframe"></a>  CFrameWnd::LoadFrame  
 リソースの情報からフレーム ウィンドウを動的に作成する呼び出しです。  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *可能*  
 フレーム ウィンドウに関連付けられている共有リソースの ID。  
  
 *dwDefaultStyle*  
 フレームの[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。 含める、 **FWS_ADDTOTITLE**  ウィンドウで表されるドキュメントの名前を自動的に表示するタイトル バーをする場合のスタイルを設定します。  
  
 *pParentWnd*  
 フレームの親へのポインター。  
  
 *pContext*  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターを指定できます**NULL**です。  
  
### <a name="remarks"></a>Remarks  
 構築、 `CFrameWnd` 2 つのステップ内のオブジェクト。 最初に、構築コンス トラクターを呼び出し、`CFrameWnd`オブジェクト、およびを呼び出す`LoadFrame`、Windows フレーム ウィンドウと関連付けられているリソースを読み込むし、フレーム ウィンドウのアタッチ、`CFrameWnd`オブジェクト。 *可能*パラメーターは、メニューのアクセラレータ テーブル、アイコン、および、フレーム ウィンドウのタイトルの文字列リソースを指定します。  
  
 使用して、`Create`メンバー関数ではなく`LoadFrame`すべてのフレーム ウィンドウの作成パラメーターを指定する場合。  
  
 フレームワークによって`LoadFrame`ドキュメント テンプレート オブジェクトを使用してフレーム ウィンドウを作成するとします。  
  
 フレームワークを使用して、 *pContext*も含めて、フレーム ウィンドウに接続しているオブジェクトを指定する引数には、オブジェクト表示にはが含まれています。 設定することができます、 *pContext*引数**NULL**を呼び出すと`LoadFrame`です。  
  
##  <a name="m_bautomenuenable"></a>  CFrameWnd::m_bAutoMenuEnable  
 このデータ メンバーが有効の場合 (既定である) 場合は、メニュー項目がない`ON_UPDATE_COMMAND_UI`または`ON_COMMAND`ハンドラーは、ユーザーがメニューを取り出すときに自動的に無効です。  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>Remarks  
 メニュー項目を持つ、`ON_COMMAND`ハンドラーがない`ON_UPDATE_COMMAND_UI`ハンドラーが自動的に有効にします。  
  
 このデータ メンバーを設定すると、メニュー項目はツールバーのボタンが有効になっている同じ方法で自動的に有効にします。  
  
> [!NOTE]
> `m_bAutoMenuEnable` トップレベルのメニュー項目に影響を与えません。  
  
 このデータ メンバーが現在の選択に基づく省略可能なコマンドの実装を簡略化し、必要が減り、書き込む`ON_UPDATE_COMMAND_UI`のハンドラーを有効にして、メニュー項目を無効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="negotiateborderspace"></a>  CFrameWnd::NegotiateBorderSpace  
 OLE インプレース アクティブ化時にフレーム ウィンドウの境界領域をネゴシエートする場合は、このメンバー関数を呼び出します。  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBorderCmd*  
 次の値のいずれかが含まれています、 **enum BorderCmd**:  
  
- **borderGet** = 1  
  
- **borderRequest** = 2  
  
- **borderSet** 3 を =  
  
 *lpRectBorder*  
 ポインター、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)罫線の座標を指定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、 **CFrameWnd** OLE 境界領域の調整の実装です。  
  
##  <a name="onbarcheck"></a>  CFrameWnd::OnBarCheck  
 指定されたコントロール バーで、アクションが実行されるたびに呼び出されます。  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 バーの表示されているコントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 コントロール バーが存在する場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="oncontexthelp"></a>  受信  
 埋め込み先アイテムについては、shift キーを押しながら f1 キーを処理します。  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>Remarks  
 状況依存のヘルプを有効にするを追加する必要があります、  
  
 [!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 ステートメントを`CFrameWnd`メッセージ マップのクラスし、も通常 shift キーを押しながら F1、このメンバー関数を有効にする、アクセラレータ テーブル エントリを追加します。  
  
 アプリケーションが OLE コンテナー、`OnContextHelp`ヘルプ モードにフレーム ウィンドウ オブジェクト内に含まれるすべての埋め込み先アイテムを格納します。 カーソルが矢印と疑問符 () と、ユーザーに変わりますはマウス ポインターを移動し、 ダイアログ ボックス、ウィンドウ、メニューのまたはコマンド ボタンを選択する左マウス ボタンをクリックします。 このメンバー関数は、Windows の関数を呼び出す`WinHelp`カーソルの下にあるオブジェクトのヘルプ コンテキストを使用します。  
  
##  <a name="oncreateclient"></a>  CFrameWnd::OnCreateClient  
 実行中に、フレームワークによって呼び出されます`OnCreate`です。  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpc*  
 Windows へのポインター [CREATESTRUCT](../../mfc/reference/createstruct-structure.md)構造体。  
  
 *pContext*  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数を呼び出すことはありません。  
  
 この関数の既定の実装を作成、`CView`で提供された情報からオブジェクト*pContext*可能であれば、します。  
  
 渡された値を上書きするには、この関数をオーバーライド、`CCreateContext`オブジェクト、または変更するフレーム ウィンドウのメインのクライアント領域内を制御する方法が作成されます。 `CCreateContext`メンバーをオーバーライドすることができますに記載されて、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)クラスです。  
  
> [!NOTE]
>  渡された値を置き換えないで、`CREATESTRUCT`構造体。 これらは情報提供のみを使用します。 最初のウィンドウの四角形をオーバーライドする場合は、たとえば、オーバーライド、`CWnd`メンバー関数は、 [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow)です。  
  
##  <a name="onhidemenubar"></a>  CFrameWnd::OnHideMenuBar  
 この関数は、システムが現在の MFC アプリケーションのメニュー バーを非表示にすると呼び出されます。  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>Remarks  
 このイベント ハンドラーは、システムは、メニューを非表示にするときに、カスタム アクションを実行するアプリケーションを使用します。 隠ぺいされているから、メニューを防ぐことはできませんが、たとえば、メニュー スタイルまたは状態を取得するには、その他のメソッドを呼び出すことができます。  
  
##  <a name="onsetpreviewmode"></a>  CFrameWnd::OnSetPreviewMode  
 印刷プレビュー モードの内外にアプリケーションのメイン フレーム ウィンドウを設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 *bPreview*  
 印刷プレビュー モードでアプリケーションを配置するかどうかを指定します。 設定**TRUE**印刷プレビューで配置する**FALSE**プレビュー モードをキャンセルします。  
  
 *pState*  
 ポインター、 **CPrintPreviewState**構造体。  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、すべての標準ツールバーを無効になり、メイン メニューと、メイン クライアント ウィンドウを非表示になります。 これには、一時的な SDI フレーム ウィンドウに MDI フレーム ウィンドウがオンにします。  
  
 印刷プレビュー時にコントロール バーやその他のフレーム ウィンドウの一部の表示や非表示をカスタマイズするには、このメンバー関数をオーバーライドします。 オーバーライドのバージョン内から基本クラス実装を呼び出します。  
  
##  <a name="onshowmenubar"></a>  CFrameWnd::OnShowMenuBar  
 この関数は、システムがときに、現在の MFC アプリケーションでメニュー バーを表示します。  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>Remarks  
 このイベント ハンドラーは、メニューが表示されるときに、カスタム アクションを実行するアプリケーションを使用します。 表示されてから、メニューを防ぐことはできませんが、たとえば、メニューのスタイルまたは状態を取得するには、その他のメソッドを呼び出すことができます。  
  
##  <a name="onupdatecontrolbarmenu"></a>  CFrameWnd::OnUpdateControlBarMenu  
 関連のメニューが更新されたときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 *対応付けられました。*  
 ポインター、 [CCmdUI](../../mfc/reference/ccmdui-class.md)更新コマンドを作成するメニューを表すオブジェクト。 更新ハンドラーは、[を有効にする](../../mfc/reference/ccmdui-class.md#enable)のメンバー関数、`CCmdUI`オブジェクト*対応付けられた*ユーザー インターフェイスを更新します。  
  
##  <a name="recalclayout"></a>  表示  
 標準コントロール バーは、オンまたはオフに切り替えられるとは、またはフレーム ウィンドウのサイズが変更されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bNotify*  
 フレーム ウィンドウのアクティブなインプレースで項目がレイアウトの変更の通知を受け取るかどうかを判断します。 場合**TRUE**、したアイテムが通知された**FALSE**です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数の既定の実装、`CWnd`メンバー関数は、`RepositionBars`フレームも、メイン クライアント ウィンドウと同様に、すべてのコントロール バーの位置を変更する (通常、`CView`または**MDICLIENT**).  
  
 フレーム ウィンドウのレイアウトが変更された後に、コントロール バーの動作と外観を制御するには、このメンバー関数をオーバーライドします。 などのコントロール バーを有効または無効にするか、別のコントロール バーを追加するときに、それを呼び出します。  
  
##  <a name="rectdefault"></a>  CFrameWnd::rectDefault  
 静的に渡す`CRect`ウィンドウの初期サイズと位置を選択するウィンドウを許可するウィンドウを作成する際に、パラメーターとして。  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="savebarstate"></a>  CFrameWnd::SaveBarState  
 フレーム ウィンドウが所有する各コントロール バーの情報を格納するには、この関数を呼び出します。  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszProfileName*  
 初期化ファイルのセクションまたは状態情報が格納されている Windows レジストリのキーの名前。  
  
### <a name="remarks"></a>Remarks  
 この情報は、初期化を使用してファイルから読み取ることができます[戻す](#loadbarstate)です。 格納されている情報には、可視性、水平、垂直方向、ドッキング状態、およびコントロール バーの位置が含まれています。  
  
##  <a name="setactivepreviewview"></a>  CFrameWnd::SetActivePreviewView  
 リッチ プレビュー用のアクティブなビューを指定されたビューを指定します。  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>パラメーター  
 *pViewNew*  
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
 *pViewNew*  
 ポインターを指定します、 [CView](../../mfc/reference/cview-class.md)オブジェクト、または**NULL**のアクティブなビューがありません。  
  
 *bNotify*  
 ビューがアクティブ化の通知を受け取るかどうかを指定します。 場合**TRUE**、 `OnActivateView` ; 新しいビューの場合は呼び出さ**FALSE**はありません。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、この関数のフレーム ウィンドウ内のビューにフォーカスを変更すると自動的に呼び出します。 明示的に呼び出すことができます`SetActiveView`を指定されたビューにフォーカスを変更します。  
  
##  <a name="setdockstate"></a>  CFrameWnd::SetDockState  
 格納されている状態情報を適用するには、このメンバー関数を呼び出して、`CDockState`フレーム ウィンドウのコントロール バー オブジェクト。  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>パラメーター  
 *state*  
 フレーム ウィンドウのコントロール バーに格納されている状態を適用します。  
  
### <a name="remarks"></a>Remarks  
 コントロール バーの以前の状態を復元するに格納されている状態を読み込むことができます`CDockState::LoadState`または`Serialize`を使用して`SetDockState`フレーム ウィンドウのコントロール バーに適用します。 以前の状態が格納されている、`CDockState`でオブジェクトです。 `GetDockState`  
  
##  <a name="setmenubarstate"></a>  CFrameWnd::SetMenuBarState  
 非表示または表示する現在の MFC アプリケーションで、メニューの表示状態を設定します。  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*%n 状態*|メニューを表示または非表示するかどうかを指定します。 *%N 状態*パラメーターは、次の値を持つことができます。<br /><br /> AFX_MBS_VISIBLE (0x01) では、非表示にされていても意味を持ちませんが表示されている場合に、メニューを表示します。<br />AFX_MBS_HIDDEN (0x02) - には、メニューが非表示が表示されていてもが表示されない場合は、効果がありません。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドは、メニューの状態を正常に変更された場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドはデバッグ モードでアサートし、派生する例外を発生させます。 ランタイム エラーが発生した場合、 [CException](../../mfc/reference/cexception-class.md)クラスです。  
  
##  <a name="setmenubarvisibility"></a>  CFrameWnd::SetMenuBarVisibility  
 非表示または非表示には、現在の MFC アプリケーションで、メニューの既定の動作を設定します。  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[in]*nStyle*|かどうか、メニューは表示されず、既定では表示やフォーカスがあるを指定します。 *NStyle*パラメーターは、次の値を持つことができます。<br /><br /> AFX_MBV_KEEPVISIBLE (0X01)-<br />     メニューは、常に表示され、既定ではありませんが、フォーカス。<br />AFX_MBV_DISPLAYONFOCUS (0X02)-<br />     既定では、メニューが表示されません。 メニューが表示されていない場合は、メニューを表示して、フォーカスに ALT キーを押します。 メニューが表示される場合は、メニューを非表示に alt キーまたは ESC キーを押します。<br />-AFX_MBV_ DISPLAYONFOCUS (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04)<br />     (ビットごとの組み合わせ (OR)) - 既定では、メニューは表示されません。 メニューが表示されていない場合は、メニューを表示して、フォーカスを F10 キーを押します。 メニューが表示される場合をオンまたはオフ、メニュー、フォーカスを切り替える F10 キーを押します。 非表示にする、alt キーまたは ESC キーを押すまで、メニューが表示されます。|  
  
### <a name="remarks"></a>Remarks  
 場合の値、 *nStyle*が発生し、デバッグ モードでこのメソッドはアサート パラメーターが有効でない[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)リリース モードでします。 その他のランタイム エラーが発生した場合、このメソッドはデバッグ モードでアサートし、派生した例外が発生、 [CException](../../mfc/reference/cexception-class.md)クラスです。  
  
 このメソッドに記述されたアプリケーションでメニューの状態に影響[!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]およびそれ以降。  
  
##  <a name="setmessagetext"></a>  CFrameWnd::SetMessageText  
 0 の ID がステータス バー ペインに文字列を配置するには、この関数を呼び出します。  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszText*  
 ステータス バーに配置される文字列を指します。  
  
 *nID*  
 文字列、ステータス バーに配置される文字列のリソース ID です。  
  
### <a name="remarks"></a>Remarks  
 これは、通常、ステータス バーの左端と、最も長いウィンドウです。  
  
##  <a name="setprogressbarposition"></a>  CFrameWnd::SetProgressBarPosition  
 タスク バーに表示される Windows 7 の進行状況バーの現在位置を設定します。  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>パラメーター  
 *nProgressPos*  
 設定する位置を指定します。 設定されている範囲でなければなりません`SetProgressBarRange`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setprogressbarrange"></a>  CFrameWnd::SetProgressBarRange  
 タスク バーに表示される Windows 7 の進行状況バーの範囲を設定します。  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>パラメーター  
 *nRangeMin*  
 最小値。  
  
 *nRangeMax*  
 最大値。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setprogressbarstate"></a>  CFrameWnd::SetProgressBarState  
 タスク バー ボタンに表示される進行状況インジケーターの状態と型を設定します。  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *tbpFlags*  
 進行状況 ボタンの現在の状態を制御するフラグ。 すべての状態は相互に排他的であるため、次のいずれかのみフラグを指定します。 TBPF_NOPROGRESS、TBPF_INDETERMINATE、TBPF_NORMAL、TBPF_ERROR、TBPF_PAUSED です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settaskbaroverlayicon"></a>  CFrameWnd::SetTaskbarOverlayIcon  
 オーバーロードされます。 アプリケーションの状態を示すために、またはユーザーに通知するのには、タスク バー ボタンにオーバーレイを適用します。  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>パラメーター  
 *可能*  
 オーバーレイを使用するアイコンのリソース ID を指定します。 説明を参照してください*hIcon*詳細についてはします。  
  
 *lpcszDescr*  
 Alt テキスト バージョンのアクセシビリティのために、オーバーレイで伝達される情報を提供する文字列へのポインター。  
  
 *hIcon*  
 オーバーレイを使用するアイコンのハンドル。 これは、96 ドット/インチ (dpi) に 16 x 16 ピクセルの測定、小さいアイコンでなければなりません。 タスク バー ボタンには、オーバーレイ アイコンが既に適用されて、既存のオーバーレイが置き換えられます。 この値は、`NULL` の場合もあります。 方法、`NULL`値は、タスク バー ボタンが 1 つのウィンドウまたは windows のグループを表すかどうかによって異なります。 解放する呼び出し元のアプリケーションの責任である*hIcon*が不要になったときにします。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 成功した場合`FALSE`アイコンの設定にエラーが発生した場合またはオペレーティング システムのバージョンが Windows 7 より小さい場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="settitle"></a>  CFrameWnd::SetTitle  
 ウィンドウ オブジェクトのタイトルを設定します。  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszTitle*  
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
 *pBar*  
 コントロール バーを表示するか非表示へのポインター。  
  
 *bShow*  
 場合**TRUE**、コントロール バーが表示されることを指定します。 場合**FALSE**、コントロール バーを非表示にすることを指定します。  
  
 *bDelay*  
 場合**TRUE**、遅延のコントロール バーを表示します。 場合**FALSE**、バーのすぐにコントロールを表示します。  
  
##  <a name="showownedwindows"></a>  CFrameWnd::ShowOwnedWindows  
 子孫であるすべてのウィンドウを表示するには、このメンバー関数を呼び出して、`CFrameWnd`オブジェクト。  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShow*  
 所有しているウィンドウを表示するか非表示にするかどうかを指定します。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CRuntimeClass 構造体](../../mfc/reference/cruntimeclass-structure.md)
