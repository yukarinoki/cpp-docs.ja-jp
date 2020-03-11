---
title: CWinThread クラス
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
ms.openlocfilehash: 43154e1ec4c6b856ad203a4b9ac49e4f4bcf9576
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866564"
---
# <a name="cwinthread-class"></a>CWinThread クラス

アプリケーション内の実行中のスレッドを表します。

## <a name="syntax"></a>構文

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CWinThread:: CWinThread](#cwinthread)|`CWinThread` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CWinThread:: CreateThread](#createthread)|`CWinThread` オブジェクトの実行を開始します。|
|[CWinThread:: ExitInstance](#exitinstance)|スレッドが終了したときにクリーンアップするようにオーバーライドします。|
|[CWinThread:: GetMainWnd](#getmainwnd)|スレッドのメインウィンドウへのポインターを取得します。|
|[CWinThread:: GetThreadPriority](#getthreadpriority)|現在のスレッドの優先順位を取得します。|
|[CWinThread:: InitInstance](#initinstance)|スレッドインスタンスの初期化を実行するには、をオーバーライドします。|
|[CWinThread:: IsIdleMessage](#isidlemessage)|特別なメッセージを確認します。|
|[CWinThread:: OnIdle](#onidle)|をオーバーライドして、スレッド固有のアイドル時処理を実行します。|
|[CWinThread::P ostThreadMessage](#postthreadmessage)|別の `CWinThread` オブジェクトにメッセージをポストします。|
|[CWinThread::P reTranslateMessage](#pretranslatemessage)|Windows 関数[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)および[DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)にディスパッチされる前に、メッセージをフィルター処理します。|
|[CWinThread::P Roて Messagefilter](#processmessagefilter)|アプリケーションに到着する前に、特定のメッセージをインターセプトします。|
|[CWinThread::P rocessWndProcException](#processwndprocexception)|スレッドのメッセージおよびコマンドハンドラーによってスローされた未処理の例外をすべてインターセプトします。|
|[CWinThread::P umpMessage](#pumpmessage)|スレッドのメッセージループを格納します。|
|[CWinThread:: ResumeThread](#resumethread)|スレッドの中断カウントをデクリメントします。|
|[CWinThread:: Run](#run)|メッセージポンプを持つスレッドの関数を制御します。 既定のメッセージループをカスタマイズするには、をオーバーライドします。|
|[CWinThread:: SetThreadPriority](#setthreadpriority)|現在のスレッドの優先順位を設定します。|
|[CWinThread:: SuspendThread](#suspendthread)|スレッドの中断カウントをインクリメントします。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[CWinThread:: operator ハンドル](#operator_handle)|`CWinThread` オブジェクトのハンドルを取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|説明|
|----------|-----------------|
|[CWinThread:: m_bAutoDelete](#m_bautodelete)|スレッドの終了時にオブジェクトを破棄するかどうかを指定します。|
|[CWinThread:: m_hThread](#m_hthread)|現在のスレッドへのハンドル。|
|[CWinThread:: m_nThreadID](#m_nthreadid)|現在のスレッドの ID。|
|[CWinThread:: m_pActiveWnd](#m_pactivewnd)|OLE サーバーがアクティブになっている場合の、コンテナーアプリケーションのメインウィンドウへのポインター。|
|[CWinThread:: m_pMainWnd](#m_pmainwnd)|アプリケーションのメインウィンドウへのポインターを保持します。|

## <a name="remarks"></a>コメント

通常、実行のメインスレッドは、`CWinApp`から派生したオブジェクトによって提供されます。`CWinApp` は `CWinThread`から派生します。 追加の `CWinThread` オブジェクトは、特定のアプリケーション内の複数のスレッドを許可します。

`CWinThread` がサポートするスレッドには、ワーカースレッドとユーザーインターフェイススレッドという2種類の一般的な種類があります。 ワーカースレッドには、メッセージポンプがありません。たとえば、スプレッドシートアプリケーションでバックグラウンド計算を実行するスレッドなどです。 ユーザーインターフェイススレッドには、メッセージポンプがあり、システムから受信したメッセージを処理します。 [CWinApp](../../mfc/reference/cwinapp-class.md)およびそれから派生したクラスは、ユーザーインターフェイススレッドの例です。 その他のユーザーインターフェイススレッドは、`CWinThread`から直接派生させることもできます。

クラス `CWinThread` のオブジェクトは、通常、スレッドの実行中に存在します。 この動作を変更する場合は、 [m_bAutoDelete](#m_bautodelete)を FALSE に設定します。

`CWinThread` クラスは、コードと MFC を完全にスレッドセーフにするために必要です。 スレッド固有の情報を維持するためにフレームワークによって使用されるスレッドローカルデータは、`CWinThread` オブジェクトによって管理されます。 スレッドローカルデータを処理するために `CWinThread` に依存しているため、mfc を使用するすべてのスレッドは MFC によって作成される必要があります。 たとえば、ランタイム関数によって作成されたスレッド[_beginthread、_BEGINTHREADEX](../../c-runtime-library/reference/beginthread-beginthreadex.md) MFC api を使用することはできません。

スレッドを作成するには、 [AfxBeginThread](application-information-and-management.md#afxbeginthread)を呼び出します。 ワーカースレッドとユーザーインターフェイススレッドのどちらを使用するかに応じて、2つの形式があります。 ユーザーインターフェイススレッドが必要な場合は、`CWinThread`派生クラスの `CRuntimeClass` へのポインターを `AfxBeginThread` に渡します。 ワーカースレッドを作成する場合は、制御関数へのポインターと制御関数へのパラメーターを `AfxBeginThread` に渡します。 ワーカースレッドとユーザーインターフェイススレッドの両方について、優先順位、スタックサイズ、作成フラグ、およびセキュリティ属性を変更するオプションのパラメーターを指定できます。 `AfxBeginThread` は、新しい `CWinThread` オブジェクトへのポインターを返します。

`AfxBeginThread`を呼び出す代わりに、`CWinThread`派生オブジェクトを構築し、`CreateThread`を呼び出すことができます。 この2段階の構築方法は、スレッドの実行の連続作成と終了の間で `CWinThread` オブジェクトを再利用する場合に便利です。

`CWinThread`の詳細については、「[マルチスレッドC++と MFC](../../parallel/multithreading-with-cpp-and-mfc.md)」、「マルチスレッド:[ユーザーインターフェイススレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)」、「マルチスレッド[: ワーカースレッドの作成](../../parallel/multithreading-creating-worker-threads.md)」、および「[マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

##  <a name="createthread"></a>CWinThread:: CreateThread

呼び出し元プロセスのアドレス空間内で実行するスレッドを作成します。

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>パラメーター

*dwCreateFlags*<br/>
スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。

- 中断カウントが1のスレッドを開始 CREATE_SUSPENDED ます。 スレッドが実行を開始する前に、 [m_bAutoDelete](#m_bautodelete)や派生クラスのメンバーなど、`CWinThread` オブジェクトのメンバーデータを初期化する場合は、CREATE_SUSPENDED を使用します。 初期化が完了したら、 [CWinThread:: ResumeThread](#resumethread)を使用して、実行中のスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。

- **0**作成直後にスレッドを開始します。

*nStackSize*<br/>
新しいスレッドへのスタックのバイト サイズを指定します。 **0**の場合、スタックサイズの既定値は、プロセスのプライマリスレッドのサイズと同じになります。

*lpSecurityAttrs*<br/>
スレッドのセキュリティ属性を指定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体を指します。

### <a name="return-value"></a>戻り値

スレッドが正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

`AfxBeginThread` を使用してスレッドオブジェクトを作成し、1回の手順で実行します。 スレッド実行の連続した作成と終了の間でスレッドオブジェクトを再利用する場合は、`CreateThread` を使用します。

##  <a name="cwinthread"></a>CWinThread:: CWinThread

`CWinThread` オブジェクトを構築します。

```
CWinThread();
```

### <a name="remarks"></a>コメント

スレッドの実行を開始するには、 [CreateThread](#createthread)メンバー関数を呼び出します。 通常は、 [AfxBeginThread](application-information-and-management.md#afxbeginthread)を呼び出してスレッドを作成します。これにより、このコンストラクターと `CreateThread`が呼び出されます。

##  <a name="exitinstance"></a>CWinThread:: ExitInstance

オーバーライドされる前の[実行](#run)メンバー関数内からフレームワークによって呼び出され、スレッドのこのインスタンスを終了します。または、 [InitInstance](#initinstance)の呼び出しが失敗した場合は、を呼び出します。

```
virtual int ExitInstance();
```

### <a name="return-value"></a>戻り値

スレッドの終了コード。0はエラーがないことを示し、0より大きい値はエラーを示します。 この値は、 [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)を呼び出すことによって取得できます。

### <a name="remarks"></a>コメント

このメンバー関数は、`Run` メンバー関数内のどこからでも呼び出すことはできません。 このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。

この関数の既定の実装では、 [m_bAutoDelete](#m_bautodelete)が TRUE の場合、`CWinThread` オブジェクトが削除されます。 スレッドが終了したときに追加のクリーンアップを実行する場合は、この関数をオーバーライドします。 `ExitInstance` の実装では、コードの実行後に基本クラスのバージョンを呼び出す必要があります。

##  <a name="getmainwnd"></a>CWinThread:: GetMainWnd

アプリケーションが OLE サーバーである場合は、この関数を呼び出して、アプリケーションオブジェクトの `m_pMainWnd` メンバーを直接参照するのではなく、アプリケーションのアクティブなメインウィンドウへのポインターを取得します。

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>戻り値

この関数は、2種類のウィンドウのいずれかへのポインターを返します。 スレッドが OLE サーバーに含まれていて、アクティブなコンテナー内でアクティブな状態にあるオブジェクトがある場合、この関数は、`CWinThread` オブジェクトの[CWinApp:: m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd)データメンバーを返します。

コンテナー内でアクティブなオブジェクトが存在しない場合、またはアプリケーションが OLE サーバーではない場合、この関数はスレッドオブジェクトの[m_pMainWnd](#m_pmainwnd)データメンバーを返します。

### <a name="remarks"></a>コメント

ユーザーインターフェイススレッドの場合、これはアプリケーションオブジェクトの `m_pActiveWnd` メンバーを直接参照することと同じです。

開発中のアプリケーションが OLE サーバーではない場合は、この関数を呼び出すことは、アプリケーション オブジェクトの `m_pMainWnd` メンバーを直接参照することと同じです。

既定の動作を変更するには、この関数をオーバーライドします。

##  <a name="getthreadpriority"></a>CWinThread:: GetThreadPriority

このスレッドの現在のスレッドの優先度レベルを取得します。

```
int GetThreadPriority();
```

### <a name="return-value"></a>戻り値

優先度クラス内の現在のスレッドの優先度レベル。 返される値は次のいずれかになり、優先度が最も高いものから順に表示されます。

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

これらの優先順位の詳細については、Windows SDK の「 [Setthreadpriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 」を参照してください。

##  <a name="initinstance"></a>CWinThread:: InitInstance

ユーザーインターフェイススレッドの新しいインスタンスを初期化するには、`InitInstance` をオーバーライドする必要があります。

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>戻り値

初期化が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

通常は、`InitInstance` をオーバーライドして、スレッドが最初に作成されたときに完了する必要があるタスクを実行します。

このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。 [AfxBeginThread](application-information-and-management.md#afxbeginthread)に渡される制御関数でワーカースレッドの初期化を実行します。

##  <a name="isidlemessage"></a>CWinThread:: IsIdleMessage

特定のメッセージが生成された後も `OnIdle` が呼び出されないようにするには、この関数をオーバーライドします。

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*pMsg*<br/>
処理中の現在のメッセージを指します。

### <a name="return-value"></a>戻り値

メッセージの処理後に `OnIdle` を呼び出す必要がある場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

既定の実装では、冗長なマウスメッセージや、キャレットによって生成されたメッセージの後に `OnIdle` は呼び出されません。

アプリケーションで短時間タイマーが作成された場合、`OnIdle` が頻繁に呼び出され、パフォーマンスの問題が発生します。 このようなアプリケーションのパフォーマンスを向上させるには、アプリケーションの `CWinApp`派生クラスの `IsIdleMessage` をオーバーライドして、次のように WM_TIMER メッセージを確認します。

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

この方法で WM_TIMER を処理することで、短いタイマーを使用するアプリケーションのパフォーマンスが向上します。

##  <a name="m_bautodelete"></a>CWinThread:: m_bAutoDelete

スレッドの終了時に `CWinThread` オブジェクトを自動的に削除するかどうかを指定します。

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>コメント

`m_bAutoDelete` データメンバーは、BOOL 型のパブリック変数です。

`m_bAutoDelete` の値は、基になるスレッドハンドルを閉じる方法には影響しませんが、ハンドルを閉じるタイミングに影響します。 スレッド ハンドルは、`CWinThread` オブジェクトが破棄されるときに必ず閉じられます。

##  <a name="m_hthread"></a>CWinThread:: m_hThread

この `CWinThread`にアタッチされているスレッドへのハンドル。

```
HANDLE m_hThread;
```

### <a name="remarks"></a>コメント

`m_hThread` データメンバーは、型 HANDLE のパブリック変数です。 これは、基になるカーネルスレッドオブジェクトが現在存在していて、ハンドルがまだ閉じられていない場合にのみ有効です。

CWinThread デストラクターは `m_hThread`で CloseHandle を呼び出します。 スレッドが終了したときに[m_bAutoDelete](#m_bautodelete)が TRUE の場合、cwinthread オブジェクトが破棄され、cwinthread オブジェクトとそのメンバー変数へのポインターが無効になります。 スレッドの終了値を確認したり、シグナルを待機したりするには、`m_hThread` メンバーが必要になることがあります。 スレッドの実行中に CWinThread オブジェクトとその `m_hThread` メンバーを保持し、終了後に、スレッドの実行を続行できるようにするには、`m_bAutoDelete` を FALSE に設定します。 それ以外の場合は、スレッドが終了し、CWinThread オブジェクトが破棄され、ハンドルを閉じてから使用を試みることができます。 この手法を使用する場合は、CWinThread オブジェクトを削除する必要があります。

##  <a name="m_nthreadid"></a>CWinThread:: m_nThreadID

この `CWinThread`にアタッチされているスレッドの ID。

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>コメント

`m_nThreadID` データメンバーは、DWORD 型のパブリック変数です。 これは、基になるカーネルスレッドオブジェクトが現在存在する場合にのみ有効です。
[M_hThread](#m_hthread)の有効期間については、「解説」も参照してください。

### <a name="example"></a>例

  [AfxGetThread](application-information-and-management.md#afxgetthread)の例を参照してください。

##  <a name="m_pactivewnd"></a>CWinThread:: m_pActiveWnd

スレッドのアクティブウィンドウオブジェクトへのポインターを格納するには、このデータメンバーを使用します。

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>コメント

`m_pActiveWnd` によって参照されているウィンドウが閉じている場合、Microsoft Foundation Class ライブラリはスレッドを自動的に終了します。 このスレッドがアプリケーションのプライマリスレッドの場合は、アプリケーションも終了します。 このデータメンバーが NULL の場合、アプリケーションの `CWinApp` オブジェクトのアクティブなウィンドウが継承されます。 `m_pActiveWnd` は `CWnd*`型のパブリック変数です。

通常、このメンバー変数は、`InitInstance`をオーバーライドするときに設定します。 ワーカースレッドでは、このデータメンバーの値は親スレッドから継承されます。

##  <a name="m_pmainwnd"></a>CWinThread:: m_pMainWnd

このデータメンバーを使用して、スレッドのメインウィンドウオブジェクトへのポインターを格納します。

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>コメント

`m_pMainWnd` によって参照されているウィンドウが閉じている場合、Microsoft Foundation Class ライブラリはスレッドを自動的に終了します。 このスレッドがアプリケーションのプライマリスレッドの場合は、アプリケーションも終了します。 このデータメンバーが NULL の場合、アプリケーションの `CWinApp` オブジェクトのメインウィンドウが、スレッドを終了するタイミングを決定するために使用されます。 `m_pMainWnd` は `CWnd*`型のパブリック変数です。

通常、このメンバー変数は、`InitInstance`をオーバーライドするときに設定します。 ワーカースレッドでは、このデータメンバーの値は親スレッドから継承されます。

##  <a name="onidle"></a>CWinThread:: OnIdle

アイドル時間の処理を実行するには、このメンバー関数をオーバーライドします。

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>パラメーター

*lCount*<br/>
スレッドのメッセージキューが空のときに `OnIdle` が呼び出されるたびにインクリメントされるカウンター。 このカウントは、新しいメッセージが処理されるたびに0にリセットされます。 *LCount*パラメーターを使用すると、メッセージを処理せずにスレッドがアイドル状態になった相対的な時間を調べることができます。

### <a name="return-value"></a>戻り値

アイドル状態の処理時間を増やすには0以外。アイドル処理時間がそれ以上必要ない場合は0。

### <a name="remarks"></a>コメント

`OnIdle` は、スレッドのメッセージキューが空のときに、既定のメッセージループで呼び出されます。 オーバーライドを使用して、独自のバックグラウンドアイドルハンドラータスクを呼び出します。

`OnIdle` は、追加のアイドル処理時間が不要であることを示すために0を返す必要があります。 *LCount*パラメーターは、メッセージキューが空のときに `OnIdle` が呼び出されるたびに増分され、新しいメッセージが処理されるたびに0にリセットされます。 この数に基づいて、異なるアイドルルーチンを呼び出すことができます。

このメンバー関数の既定の実装では、一時オブジェクトと未使用のダイナミックリンクライブラリがメモリから解放されます。

このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。

`OnIdle` が返されるまでアプリケーションはメッセージを処理できないため、この関数では長いタスクを実行しないようにしてください。

##  <a name="operator_handle"></a>CWinThread:: operator ハンドル

`CWinThread` オブジェクトのハンドルを取得します。

```
operator HANDLE() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、スレッドオブジェクトのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>コメント

ハンドルを使用して、Windows Api を直接呼び出します。

##  <a name="postthreadmessage"></a>CWinThread::P ostThreadMessage

ユーザー定義メッセージを別の `CWinThread` オブジェクトにポストするために呼び出されます。

```
BOOL PostThreadMessage(
    UINT message,
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*message*<br/>
ユーザー定義メッセージの ID。

*wParam*<br/>
最初のメッセージパラメーター。

*lParam*<br/>
2番目のメッセージパラメーター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

ポストされたメッセージは、メッセージマップマクロ ON_THREAD_MESSAGE によって適切なメッセージハンドラーにマップされます。

> [!NOTE]
> [Postthreadmessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)を呼び出すと、メッセージはスレッドのメッセージキューに配置されます。 ただし、このように投稿されたメッセージはウィンドウに関連付けられていないため、MFC では、メッセージまたはコマンドハンドラーにそれらをディスパッチしません。 これらのメッセージを処理するには、CWinApp 派生クラスの `PreTranslateMessage()` 関数をオーバーライドし、メッセージを手動で処理します。

##  <a name="pretranslatemessage"></a>CWinThread::P reTranslateMessage

Windows 関数[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)および[DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)にディスパッチされる前に、ウィンドウメッセージをフィルター処理するには、この関数をオーバーライドします。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*pMsg*<br/>
処理するメッセージを含む[MSG 構造体](/windows/win32/api/winuser/ns-winuser-msg)を指します。

### <a name="return-value"></a>戻り値

メッセージが `PreTranslateMessage` で完全に処理され、それ以上処理されない場合は0以外の。 メッセージを通常の方法で処理する必要がある場合は0。

### <a name="remarks"></a>コメント

このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。

##  <a name="processmessagefilter"></a>CWinThread::P Roて Messagefilter

フレームワークのフック関数は、このメンバー関数を呼び出して、特定の Windows メッセージをフィルター処理して応答します。

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*code*<br/>
フックコードを指定します。 このメンバー関数は、コードを使用して、 *Lpmsg*の処理方法を決定します。

*lpMsg*<br/>
Windows[メッセージ構造](/windows/win32/api/winuser/ns-winuser-msg)へのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

フック関数は、アプリケーションの通常のメッセージ処理に送信される前に、イベントを処理します。

この高度な機能をオーバーライドする場合は、フレームワークのフック処理を維持するために、基本クラスのバージョンを必ず呼び出してください。

##  <a name="processwndprocexception"></a>CWinThread::P rocessWndProcException

このメンバー関数は、スレッドのメッセージハンドラーまたはコマンドハンドラーの1つでスローされた例外をハンドラーがキャッチしない場合は常に、フレームワークによって呼び出されます。

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*e*<br/>
ハンドルされない例外を指しています。

*pMsg*<br/>
フレームワークが例外をスローする原因となった windows メッセージに関する情報を含む[MSG 構造体](/windows/win32/api/winuser/ns-winuser-msg)を指します。

### <a name="return-value"></a>戻り値

WM_CREATE 例外が生成された場合は-1。それ以外の場合は0です。

### <a name="remarks"></a>コメント

このメンバー関数を直接呼び出さないでください。

このメンバー関数の既定の実装では、次のメッセージから生成された例外のみを処理します。

|コマンド|操作|
|-------------|------------|
|WM_CREATE|オーバー.|
|WM_PAINT|影響を受けるウィンドウを検証して、別の WM_PAINT メッセージが生成されないようにします。|

このメンバー関数をオーバーライドして、例外のグローバルな処理を提供します。 既定の動作を表示する場合にのみ、基本機能を呼び出します。

このメンバー関数は、メッセージポンプを持つスレッドでのみ使用されます。

##  <a name="pumpmessage"></a>CWinThread::P umpMessage

スレッドのメッセージループを格納します。

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>コメント

`PumpMessage` には、スレッドのメッセージループが含まれています。 `PumpMessage` は、スレッドのメッセージをポンプするために `CWinThread` によって呼び出されます。 `PumpMessage` を直接呼び出してメッセージを強制的に処理することも、`PumpMessage` をオーバーライドして既定の動作を変更することもできます。

上級ユーザーのみが、`PumpMessage` を直接呼び出し、既定の動作をオーバーライドすることをお勧めします。

##  <a name="resumethread"></a>CWinThread:: ResumeThread

[SuspendThread](#suspendthread)メンバー関数によって中断されたスレッド、または CREATE_SUSPENDED フラグを使用して作成されたスレッドの実行を再開するために呼び出されます。

```
DWORD ResumeThread();
```

### <a name="return-value"></a>戻り値

成功した場合は、スレッドの前の中断回数。それ以外の場合は `0xFFFFFFFF`。 戻り値が0の場合、現在のスレッドは中断されませんでした。 戻り値が1の場合、スレッドは中断されましたが、現在は再起動されています。 戻り値が1より大きい場合は、スレッドが中断されたままになります。

### <a name="remarks"></a>コメント

現在のスレッドの中断回数が1つ減少します。 中断回数が0に減ると、スレッドは実行を再開します。それ以外の場合、スレッドは中断されたままになります。

##  <a name="run"></a>CWinThread:: Run

ユーザーインターフェイススレッドの既定のメッセージループを提供します。

```
virtual int Run();
```

### <a name="return-value"></a>戻り値

スレッドによって返される**int**値。 この値は、 [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)を呼び出すことによって取得できます。

### <a name="remarks"></a>コメント

`Run` は、アプリケーションが[WM_QUIT](/windows/win32/winmsg/wm-quit)メッセージを受信するまで Windows メッセージを取得してディスパッチします。 スレッドのメッセージキューに現在メッセージが含まれていない場合、`Run` は `OnIdle` を呼び出してアイドル時の処理を実行します。 受信メッセージは、特別な処理のために[PreTranslateMessage](#pretranslatemessage)メンバー関数に移動し、標準キーボード翻訳の Windows 関数[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)に移動します。 最後に、 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 関数が呼び出されます。

`Run` はオーバーライドされることはほとんどありませんが、これをオーバーライドして特殊な動作を実装することができます。

このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。

##  <a name="setthreadpriority"></a>CWinThread:: SetThreadPriority

この関数は、優先度クラス内の現在のスレッドの優先度レベルを設定します。

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>パラメーター

*nPriority*<br/>
優先度クラス内の新しいスレッド優先度レベルを指定します。 このパラメーターには、次のいずれかの値を指定する必要があります。優先度の高い順に表示されます。

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

これらの優先順位の詳細については、Windows SDK の「 [Setthreadpriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 」を参照してください。

### <a name="return-value"></a>戻り値

関数が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>コメント

[CreateThread](#createthread)が正常に返された後にのみ呼び出すことができます。

##  <a name="suspendthread"></a>CWinThread:: SuspendThread

現在のスレッドの中断カウントをインクリメントします。

```
DWORD SuspendThread();
```

### <a name="return-value"></a>戻り値

成功した場合は、スレッドの前の中断回数。それ以外の場合は `0xFFFFFFFF`。

### <a name="remarks"></a>コメント

いずれかのスレッドが0を超える中断カウントを持っている場合、そのスレッドは実行されません。 スレッドは、 [ResumeThread](#resumethread)メンバー関数を呼び出すことによって再開できます。

## <a name="see-also"></a>参照

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
