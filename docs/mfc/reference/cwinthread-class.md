---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
helpviewer_keywords:
- CWinThread [MFC], CWinThread
- CWinThread [MFC], CreateThread
- CWinThread [MFC], ExitInstance
- CWinThread [MFC], GetMainWnd
- CWinThread [MFC], GetThreadPriority
- CWinThread [MFC], InitInstance
- CWinThread [MFC], IsIdleMessage
- CWinThread [MFC], OnIdle
- CWinThread [MFC], PostThreadMessage
- CWinThread [MFC], PreTranslateMessage
- CWinThread [MFC], ProcessMessageFilter
- CWinThread [MFC], ProcessWndProcException
- CWinThread [MFC], PumpMessage
- CWinThread [MFC], ResumeThread
- CWinThread [MFC], Run
- CWinThread [MFC], SetThreadPriority
- CWinThread [MFC], SuspendThread
- CWinThread [MFC], m_bAutoDelete
- CWinThread [MFC], m_hThread
- CWinThread [MFC], m_nThreadID
- CWinThread [MFC], m_pActiveWnd
- CWinThread [MFC], m_pMainWnd
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
ms.openlocfilehash: f2e95dd3ba8be31633590e37d95dedc8749ebdd8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367420"
---
# <a name="cwinthread-class"></a>クラス

アプリケーション内の実行中のスレッドを表します。

## <a name="syntax"></a>構文

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::CWinスレッド](#cwinthread)|`CWinThread` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[::スレッドの作成](#createthread)|オブジェクトの実行を`CWinThread`開始します。|
|[を使用します。](#exitinstance)|スレッドが終了したときにクリーンアップするようにオーバーライドします。|
|[::ゲットメインウンド](#getmainwnd)|スレッドのメイン ウィンドウへのポインターを取得します。|
|[スレッドの優先順位を取得します。](#getthreadpriority)|現在のスレッドの優先順位を取得します。|
|[::イニトインスタンス](#initinstance)|スレッド インスタンスの初期化を実行する場合にオーバーライドします。|
|[メッセージを見る](#isidlemessage)|特別なメッセージをチェックします。|
|[::オンアイドル](#onidle)|スレッド固有のアイドル時間処理を実行するためにオーバーライドします。|
|[:Pソストスレッドメッセージ](#postthreadmessage)|メッセージを別`CWinThread`のオブジェクトに投稿します。|
|[メッセージを再変換:P](#pretranslatemessage)|メッセージが Windows[関数に](/windows/win32/api/winuser/nf-winuser-translatemessage)ディスパッチされる前にフィルター処理されます[。](/windows/win32/api/winuser/nf-winuser-dispatchmessage)|
|[:Pロセスメッセージフィルタ](#processmessagefilter)|特定のメッセージがアプリケーションに到達する前にインターセプトします。|
|[:Pロセスウンドプロセス例外](#processwndprocexception)|スレッドのメッセージおよびコマンド ハンドラーによってスローされた、未処理の例外をすべてインターセプトします。|
|[:Pウンプメッセージ](#pumpmessage)|スレッドのメッセージ ループを格納します。|
|[スレッドを再開します。](#resumethread)|スレッドの中断カウントを減らします。|
|[実行](#run)|メッセージ ポンプを使用したスレッドの制御機能。 既定のメッセージ ループをカスタマイズする場合にオーバーライドします。|
|[スレッドの優先順位を設定します。](#setthreadpriority)|現在のスレッドの優先順位を設定します。|
|[スレッドを中断します。](#suspendthread)|スレッドの中断カウントをインクリメントします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ハンドルを操作します。](#operator_handle)|オブジェクトのハンドルを`CWinThread`取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CWinThread::m_bAutoDelete](#m_bautodelete)|スレッド終了時にオブジェクトを破棄するかどうかを指定します。|
|[スウィンスレッド::m_hThread](#m_hthread)|現在のスレッドへのハンドル。|
|[スウィンスレッド::m_nThreadID](#m_nthreadid)|現在のスレッドの ID。|
|[スウィンスレッド::m_pActiveWnd](#m_pactivewnd)|OLE サーバーが埋め込み場所でアクティブな場合のコンテナー アプリケーションのメイン ウィンドウへのポインター。|
|[次のスレッド::m_pMainWnd](#m_pmainwnd)|アプリケーションのメイン ウィンドウへのポインターを保持します。|

## <a name="remarks"></a>解説

実行のメイン スレッドは通常、 から`CWinApp`派生したオブジェクトによって提供されます。`CWinApp`は から`CWinThread`派生します。 追加`CWinThread`のオブジェクトは、特定のアプリケーション内で複数のスレッドを許可します。

`CWinThread`サポートするスレッドには、ワーカー スレッドとユーザー インターフェイス スレッドの 2 種類があります。 ワーカー スレッドにはメッセージ ポンプがありません。 ユーザー インターフェイス スレッドには、メッセージ ポンプがあり、システムから受信したメッセージを処理します。 [CWinApp](../../mfc/reference/cwinapp-class.md)とそこから派生したクラスは、ユーザー インターフェイス スレッドの例です。 その他のユーザー インターフェイス スレッドも`CWinThread`から直接派生できます。

クラス`CWinThread`のオブジェクトは、通常、スレッドの存続期間中に存在します。 この動作を変更する場合は[、m_bAutoDelete](#m_bautodelete)を FALSE に設定します。

この`CWinThread`クラスは、コードと MFC を完全にスレッド セーフにするために必要です。 スレッド固有の情報を維持するためにフレームワークで使用されるスレッドローカルデータは、オブジェクト`CWinThread`によって管理されます。 スレッド ローカル データ`CWinThread`を処理するにはこの依存性があるため、MFC を使用するスレッドは MFC で作成する必要があります。 たとえば、ランタイム関数によって作成されたスレッド[_beginthread、_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md)は、任意の MFC API を使用できません。

スレッドを作成するには[、AfxBeginThread](application-information-and-management.md#afxbeginthread)を呼び出します。 ワーカー スレッドとユーザー インターフェイス スレッドのどちらを使用するかによって、2 つの形式があります。 ユーザー インターフェイス スレッドが必要な場合は、`AfxBeginThread``CRuntimeClass``CWinThread`派生クラスの へのポインターを渡します。 ワーカー スレッドを作成する場合は、制御関数`AfxBeginThread`へのポインターと、制御関数へのパラメーターに渡します。 ワーカー スレッドとユーザー インターフェイス スレッドの両方に対して、優先順位、スタック サイズ、作成フラグ、およびセキュリティ属性を変更するオプションのパラメーターを指定できます。 `AfxBeginThread`新しい`CWinThread`オブジェクトへのポインタを返します。

を呼び`AfxBeginThread`出す代わりに、-derived オブジェクトを`CWinThread`構築`CreateThread`してから を呼び出すことができます。 この 2 段階の構築方法は、連続したスレッド実行の`CWinThread`作成と終了の間にオブジェクトを再利用する場合に便利です。

`CWinThread`詳細については、「 [C++ および MFC を使用したマルチスレッド](../../parallel/multithreading-with-cpp-and-mfc.md)化[、マルチスレッド : ユーザー インターフェイス スレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)、[マルチスレッド : ワーカー スレッドの作成](../../parallel/multithreading-creating-worker-threads.md)、[マルチスレッド : 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cwinthreadcreatethread"></a><a name="createthread"></a>::スレッドの作成

呼び出し元プロセスのアドレス空間内で実行するスレッドを作成します。

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>パラメーター

*フラグを作成します。*<br/>
スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。

- CREATE_SUSPENDED 中断カウント 1 でスレッドを開始します。 m_bAutoDeleteや派生クラスのメンバーなど、`CWinThread`オブジェクトのメンバー データを初期化する[m_bAutoDelete](#m_bautodelete)場合は、CREATE_SUSPENDEDを使用して、スレッドの実行を開始します。 初期化が完了したら[、CWinThread::ResumeThread](#resumethread)を使用してスレッドの実行を開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。

- **0**作成後すぐにスレッドを開始します。

*スタックサイズ*<br/>
新しいスレッドへのスタックのバイト サイズを指定します。 **0**の場合、スタック サイズは、プロセスのプライマリ スレッドと同じサイズになります。

*セキュリティアトルス*<br/>
スレッドのセキュリティ属性を指定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポイント。

### <a name="return-value"></a>戻り値

スレッドが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

スレッド`AfxBeginThread`オブジェクトを作成し、1 ステップで実行するために使用します。 スレッド`CreateThread`の実行の連続的な作成と終了の間にスレッド オブジェクトを再利用する場合に使用します。

## <a name="cwinthreadcwinthread"></a><a name="cwinthread"></a>::CWinスレッド

`CWinThread` オブジェクトを構築します。

```
CWinThread();
```

### <a name="remarks"></a>解説

スレッドの実行を開始するには[、CreateThread](#createthread)メンバー関数を呼び出します。 通常は、このコンストラクターと を呼び出す[AfxBeginThread](application-information-and-management.md#afxbeginthread)`CreateThread`を呼び出してスレッドを作成します。

## <a name="cwinthreadexitinstance"></a><a name="exitinstance"></a>を使用します。

スレッドのこのインスタンスを終了する場合、または[InitInstance](#initinstance)の呼び出しが失敗した場合に、めったにオーバーライドされない[Run](#run)メンバー関数内からフレームワークによって呼び出されます。

```
virtual int ExitInstance();
```

### <a name="return-value"></a>戻り値

スレッドの終了コード。0 はエラーがないことを示し、0 より大きい値はエラーを示します。 この値は、[呼](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)び出すことによって取得できます。

### <a name="remarks"></a>解説

このメンバー関数は、`Run`メンバー関数以外の場所から呼び出す必要があります。 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。

この関数の既定の実装では`CWinThread`[、m_bAutoDelete](#m_bautodelete)が TRUE の場合、オブジェクトが削除されます。 スレッドが終了したときに追加のクリーンアップを実行する場合は、この関数をオーバーライドします。 コードの実行`ExitInstance`後に、 の実装で基本クラスのバージョンを呼び出す必要があります。

## <a name="cwinthreadgetmainwnd"></a><a name="getmainwnd"></a>::ゲットメインウンド

アプリケーションが OLE サーバーの場合は、アプリケーション オブジェクトの`m_pMainWnd`メンバーを直接参照するのではなく、アプリケーションのアクティブなメイン ウィンドウへのポインターを取得するには、この関数を呼び出します。

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>戻り値

この関数は、2 種類のウィンドウのうち 1 つを指すポインターを返します。 スレッドが OLE サーバーの一部であり、アクティブなコンテナー内でインプレース アクティブなオブジェクトを持つ場合、この関数は、オブジェクトの[CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd)データ メンバーを`CWinThread`返します。

コンテナー内で埋め込みオブジェクトがアクティブでない場合、またはアプリケーションが OLE サーバーでない場合、この関数はスレッド オブジェクトの[m_pMainWnd](#m_pmainwnd)データ メンバーを返します。

### <a name="remarks"></a>解説

ユーザー インターフェイス スレッドの場合、これはアプリケーション オブジェクトのメンバー`m_pActiveWnd`を直接参照することと同じです。

開発中のアプリケーションが OLE サーバーではない場合は、この関数を呼び出すことは、アプリケーション オブジェクトの `m_pMainWnd` メンバーを直接参照することと同じです。

既定の動作を変更するには、この関数をオーバーライドします。

## <a name="cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a>スレッドの優先順位を取得します。

このスレッドの現在のスレッドの優先順位レベルを取得します。

```
int GetThreadPriority();
```

### <a name="return-value"></a>戻り値

その優先順位クラス内の現在のスレッドの優先順位レベル。 返される値は、優先順位が最も高いものから最低にリストされている次のいずれかになります。

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

これらの優先順位の詳細については、Windows SDK[の「SetThreadPriority」](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority)を参照してください。

## <a name="cwinthreadinitinstance"></a><a name="initinstance"></a>::イニトインスタンス

`InitInstance`ユーザー インターフェイス スレッドの新しいインスタンスを初期化するには、オーバーライドする必要があります。

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

通常、スレッドが`InitInstance`最初に作成されたときに完了する必要があるタスクを実行するためにオーバーライドします。

このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。 [AfxBeginThread](application-information-and-management.md#afxbeginthread)に渡された制御関数で、ワーカー スレッドの初期化を実行します。

## <a name="cwinthreadisidlemessage"></a><a name="isidlemessage"></a>メッセージを見る

特定のメッセージが生成`OnIdle`された後に呼び出されないようにするには、この関数をオーバーライドします。

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*Pmsg*<br/>
処理中の現在のメッセージを指します。

### <a name="return-value"></a>戻り値

メッセージの処理`OnIdle`後に呼び出す必要がある場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

デフォルトの実装では、カ`OnIdle`レットの点滅によって生成された冗長なマウス メッセージおよびメッセージの後には呼び出されません。

アプリケーションが短いタイマーを作成した場合`OnIdle`、頻繁に呼び出され、パフォーマンスの問題が発生します。 このようなアプリケーションのパフォーマンスを向上させるには、アプリケーションの`IsIdleMessage``CWinApp`派生クラスでオーバーライドして、次のようにWM_TIMERメッセージをチェックします。

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

この方法でWM_TIMERを処理すると、短いタイマーを使用するアプリケーションのパフォーマンスが向上します。

## <a name="cwinthreadm_bautodelete"></a><a name="m_bautodelete"></a>CWinThread::m_bAutoDelete

スレッドの終了時に `CWinThread` オブジェクトを自動的に削除するかどうかを指定します。

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>解説

データ`m_bAutoDelete`メンバーは、BOOL 型のパブリック変数です。

の値は`m_bAutoDelete`、基になるスレッド ハンドルの閉じ方には影響しませんが、ハンドルを閉じるタイミングには影響を与えます。 スレッド ハンドルは、`CWinThread` オブジェクトが破棄されるときに必ず閉じられます。

## <a name="cwinthreadm_hthread"></a><a name="m_hthread"></a>スウィンスレッド::m_hThread

この`CWinThread`にアタッチされたスレッドへのハンドル。

```
HANDLE m_hThread;
```

### <a name="remarks"></a>解説

データ`m_hThread`メンバーは、HANDLE 型のパブリック変数です。 この値は、基になるカーネル スレッド オブジェクトが現在存在し、ハンドルがまだ閉じていない場合にのみ有効です。

CWinThread デストラクターは、 を`m_hThread`呼び出します。 スレッドが終了したときに[m_bAutoDelete](#m_bautodelete)が TRUE の場合、CWinThread オブジェクトは破棄され、CWinThread オブジェクトとそのメンバー変数へのポインターは無効になります。 メンバーは、スレッド`m_hThread`終了値をチェックするか、シグナルを待機する必要があります。 CWinThread オブジェクトとその`m_hThread`メンバーをスレッドの実行中および終了後に保持するには、スレッドの`m_bAutoDelete`実行を続行する前に FALSE に設定します。 そうしないと、スレッドが終了し、CWinThread オブジェクトを破棄し、ハンドルを閉じてから使用を試みることができます。 この方法を使用する場合は、CWinThread オブジェクトの削除を担当します。

## <a name="cwinthreadm_nthreadid"></a><a name="m_nthreadid"></a>スウィンスレッド::m_nThreadID

この`CWinThread`にアタッチされたスレッドの ID。

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>解説

データ`m_nThreadID`メンバーは、DWORD 型のパブリック変数です。 基になるカーネル スレッド オブジェクトが現在存在する場合にのみ有効です。
m_hThread[の有効期間](#m_hthread)に関する解説も参照してください。

### <a name="example"></a>例

  [AfxGetThread](application-information-and-management.md#afxgetthread)の例を参照してください。

## <a name="cwinthreadm_pactivewnd"></a><a name="m_pactivewnd"></a>スウィンスレッド::m_pActiveWnd

このデータ メンバーを使用して、スレッドのアクティブ ウィンドウ オブジェクトへのポインターを格納します。

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>解説

参照先のウィンドウが閉じられると、Microsoft Foundation クラス ライブラリ`m_pActiveWnd`は自動的にスレッドを終了します。 このスレッドがアプリケーションのプライマリ スレッドである場合、アプリケーションも終了します。 このデータ メンバーが NULL の場合、アプリケーションのオブジェクトの`CWinApp`アクティブ ウィンドウが継承されます。 `m_pActiveWnd`型のパブリック変数です`CWnd*`。

通常、このメンバー変数は、 をオーバーライド`InitInstance`するときに設定します。 ワーカー スレッドでは、このデータ メンバーの値は親スレッドから継承されます。

## <a name="cwinthreadm_pmainwnd"></a><a name="m_pmainwnd"></a>次のスレッド::m_pMainWnd

このデータ メンバーを使用して、スレッドのメイン ウィンドウ オブジェクトへのポインターを格納します。

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>解説

参照先のウィンドウが閉じられると、Microsoft Foundation クラス ライブラリ`m_pMainWnd`は自動的にスレッドを終了します。 このスレッドがアプリケーションのプライマリ スレッドである場合、アプリケーションも終了します。 このデータ メンバーが NULL の場合、アプリケーションのオブジェクトの`CWinApp`メイン ウィンドウを使用して、スレッドを終了するタイミングが決定されます。 `m_pMainWnd`型のパブリック変数です`CWnd*`。

通常、このメンバー変数は、 をオーバーライド`InitInstance`するときに設定します。 ワーカー スレッドでは、このデータ メンバーの値は親スレッドから継承されます。

## <a name="cwinthreadonidle"></a><a name="onidle"></a>::オンアイドル

アイドル時間処理を実行するには、このメンバー関数をオーバーライドします。

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>パラメーター

*Lcount*<br/>
スレッドのメッセージ キューが`OnIdle`空の場合は、毎回インクリメントされたカウンタが呼び出されます。 このカウントは、新しいメッセージが処理されるたびに 0 にリセットされます。 *lCount*パラメーターを使用して、メッセージを処理せずにスレッドがアイドル状態になった時間の相対的な長さを決定できます。

### <a name="return-value"></a>戻り値

より多くのアイドル処理時間を受け取る場合は 0 以外の値を指定します。アイドル処理時間がこれ以上必要ない場合は 0。

### <a name="remarks"></a>解説

`OnIdle`は、スレッドのメッセージ キューが空の場合に、既定のメッセージ ループで呼び出されます。 オーバーライドを使用して、独自のバックグラウンド アイドル ハンドラ タスクを呼び出します。

`OnIdle`追加のアイドル処理時間が必要な場合は 0 を返す必要があります。 *lCount*パラメーターは、メッセージ`OnIdle`・キューが空のときに呼び出されるたびにインクリメントされ、新しいメッセージが処理されるたびに 0 にリセットされます。 このカウントに基づいて、さまざまなアイドル ルーチンを呼び出すことができます。

このメンバー関数の既定の実装では、一時オブジェクトと未使用のダイナミック リンク ライブラリがメモリから解放されます。

このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。

アプリケーションは戻るまで`OnIdle`メッセージを処理できないため、この関数では時間のかかるタスクを実行しないでください。

## <a name="cwinthreadoperator-handle"></a><a name="operator_handle"></a>ハンドルを操作します。

オブジェクトのハンドルを`CWinThread`取得します。

```
operator HANDLE() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、スレッド オブジェクトのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

ハンドルを使用して、Windows API を直接呼び出します。

## <a name="cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a>:Pソストスレッドメッセージ

ユーザー定義メッセージを別`CWinThread`のオブジェクトにポストするために呼び出されます。

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*メッセージ*<br/>
ユーザー定義メッセージの ID。

*wParam*<br/>
最初のメッセージ パラメータ。

*lParam*<br/>
2 番目のメッセージ パラメーター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ポストされたメッセージは、メッセージ マップ マクロ ON_THREAD_MESSAGEによって適切なメッセージ ハンドラーにマップされます。

> [!NOTE]
> [を](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)呼び出すと、メッセージはスレッドのメッセージ キューに配置されます。 ただし、この方法でポストされたメッセージはウィンドウに関連付けられていないため、MFC はメッセージやコマンド ハンドラーにディスパッチしません。 これらのメッセージを処理するには、CWinApp`PreTranslateMessage()`派生クラスの関数をオーバーライドし、メッセージを手動で処理します。

## <a name="cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a>メッセージを再変換:P

ウィンドウ メッセージが Windows 関数にディスパッチされる前に、ウィンドウ[メッセージ](/windows/win32/api/winuser/nf-winuser-translatemessage)をフィルター[DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)処理するには、この関数をオーバーライドします。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*Pmsg*<br/>
処理するメッセージを含む[MSG 構造体](/windows/win32/api/winuser/ns-winuser-msg)へのポイント。

### <a name="return-value"></a>戻り値

メッセージが完全に`PreTranslateMessage`処理され、それ以上処理されない場合は、0 以外の値を指定します。 メッセージを通常の方法で処理する場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。

## <a name="cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a>:Pロセスメッセージフィルタ

フレームワークのフック関数は、特定の Windows メッセージをフィルター処理して応答するために、このメンバー関数を呼び出します。

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
フック コードを指定します。 このメンバー関数は、コードを使用して *、lpMsg*の処理方法を決定します。

*をクリックします。*<br/>
Windows [MSG 構造体](/windows/win32/api/winuser/ns-winuser-msg)へのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

フック関数は、イベントをアプリケーションの通常のメッセージ処理に送信する前に処理します。

この高度な機能をオーバーライドする場合は、フレームワークのフック処理を維持するために、必ず基本クラスバージョンを呼び出してください。

## <a name="cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a>:Pロセスウンドプロセス例外

スレッドのメッセージまたはコマンド ハンドラーのいずれかでスローされた例外をハンドラーがキャッチしない場合は、フレームワークがこのメンバー関数を呼び出します。

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*E*<br/>
ハンドルされない例外へのポイント。

*Pmsg*<br/>
フレームワークが例外をスローする原因となったウィンドウ メッセージに関する情報を含む[MSG 構造体](/windows/win32/api/winuser/ns-winuser-msg)へのポイント。

### <a name="return-value"></a>戻り値

WM_CREATE例外が生成された場合は -1。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数を直接呼び出さないでください。

このメンバー関数の既定の実装では、次のメッセージから生成された例外のみを処理します。

|command|アクション|
|-------------|------------|
|Wm_create|失敗。|
|Wm_paint|影響を受けるウィンドウを検証し、別のWM_PAINTメッセージが生成されないようにします。|

例外のグローバル処理を提供するには、このメンバー関数をオーバーライドします。 既定の動作を表示する場合にのみ、基本機能を呼び出します。

このメンバー関数は、メッセージ ポンプを持つスレッドでのみ使用されます。

## <a name="cwinthreadpumpmessage"></a><a name="pumpmessage"></a>:Pウンプメッセージ

スレッドのメッセージ ループを格納します。

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>解説

`PumpMessage`にはスレッドのメッセージ ループが含まれています。 `PumpMessage`は、スレッド`CWinThread`のメッセージを送り出すために呼び出されます。 メッセージを強制的`PumpMessage`に処理するために直接呼び出すか、またはオーバーライド`PumpMessage`してデフォルトの動作を変更できます。

直接`PumpMessage`呼び出しを行い、既定の動作をオーバーライドすることは、上級ユーザーにのみ推奨されます。

## <a name="cwinthreadresumethread"></a><a name="resumethread"></a>スレッドを再開します。

[SuspendThread](#suspendthread)メンバー関数によって中断されたスレッド、またはCREATE_SUSPENDED フラグで作成されたスレッドの実行を再開するために呼び出されます。

```
DWORD ResumeThread();
```

### <a name="return-value"></a>戻り値

成功した場合はスレッドの以前の中断カウント。`0xFFFFFFFF`それ以外の場合。 戻り値が 0 の場合、現在のスレッドは中断されていません。 戻り値が 1 の場合、スレッドは中断されましたが、現在は再開されます。 1 より大きい戻り値は、スレッドが中断されたままであることを意味します。

### <a name="remarks"></a>解説

現在のスレッドの中断カウントは 1 つ減らされます。 中断カウントがゼロに減少した場合、スレッドは実行を再開します。それ以外の場合、スレッドは中断されたままです。

## <a name="cwinthreadrun"></a><a name="run"></a>実行

ユーザー インターフェイス スレッドの既定のメッセージ ループを提供します。

```
virtual int Run();
```

### <a name="return-value"></a>戻り値

スレッドによって返される**int**値。 この値は、[呼](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)び出すことによって取得できます。

### <a name="remarks"></a>解説

`Run`アプリケーションが[WM_QUIT](/windows/win32/winmsg/wm-quit)メッセージを受信するまで、Windows メッセージを取得してディスパッチします。 スレッドのメッセージ キューに現在メッセージが含まれている場合`Run`は`OnIdle`、アイドル時間処理を実行する呼び出し。 受信メッセージは、特別な処理のために[PreTranslateMessage](#pretranslatemessage)メンバー関数に移動し、標準のキーボード変換の Windows 関数[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)に移動します。 最後に、[ディスパッチ メッセージ](/windows/win32/api/winuser/nf-winuser-dispatchmessage)の Windows 関数が呼び出されます。

`Run`めったにオーバーライドされませんが、特別な動作を実装するためにオーバーライドできます。

このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。

## <a name="cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a>スレッドの優先順位を設定します。

この関数は、その優先順位クラス内の現在のスレッドの優先順位を設定します。

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>パラメーター

*n優先順位*<br/>
その優先順位クラス内の新しいスレッドの優先順位レベルを指定します。 このパラメーターは、優先順位が最も高いものから最低の値にリストされている次のいずれかの値である必要があります。

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

これらの優先順位の詳細については、Windows SDK[の「SetThreadPriority」](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority)を参照してください。

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは[、CreateThread](#createthread)が正常に戻った後にのみ呼び出すことができます。

## <a name="cwinthreadsuspendthread"></a><a name="suspendthread"></a>スレッドを中断します。

現在のスレッドの中断カウントをインクリメントします。

```
DWORD SuspendThread();
```

### <a name="return-value"></a>戻り値

成功した場合はスレッドの以前の中断カウント。`0xFFFFFFFF`それ以外の場合。

### <a name="remarks"></a>解説

いずれかのスレッドの中断カウントがゼロより大きい場合、そのスレッドは実行されません。 スレッドは[、ResumeThread](#resumethread)メンバー関数を呼び出すことによって再開できます。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
