---
description: ': CWinThread クラスに関する詳細情報'
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
ms.openlocfilehash: f9f89aa6397f44c95e8958d077fe18258e3c17f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342609"
---
# <a name="cwinthread-class"></a>CWinThread クラス

アプリケーション内の実行中のスレッドを表します。

## <a name="syntax"></a>構文

```
class CWinThread : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWinThread:: CWinThread](#cwinthread)|`CWinThread` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CWinThread:: CreateThread](#createthread)|オブジェクトの実行を開始 `CWinThread` します。|
|[CWinThread:: ExitInstance](#exitinstance)|スレッドが終了したときにクリーンアップするようにオーバーライドします。|
|[CWinThread:: GetMainWnd](#getmainwnd)|スレッドのメインウィンドウへのポインターを取得します。|
|[CWinThread:: GetThreadPriority](#getthreadpriority)|現在のスレッドの優先順位を取得します。|
|[CWinThread:: InitInstance](#initinstance)|スレッドインスタンスの初期化を実行するには、をオーバーライドします。|
|[CWinThread:: IsIdleMessage](#isidlemessage)|特別なメッセージを確認します。|
|[CWinThread:: OnIdle](#onidle)|をオーバーライドして、スレッド固有のアイドル時処理を実行します。|
|[CWinThread::P ostThreadMessage](#postthreadmessage)|メッセージを別のオブジェクトにポスト `CWinThread` します。|
|[CWinThread::P reTranslateMessage](#pretranslatemessage)|Windows 関数 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) および [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)にディスパッチされる前に、メッセージをフィルター処理します。|
|[CWinThread::P Roて Messagefilter](#processmessagefilter)|アプリケーションに到着する前に、特定のメッセージをインターセプトします。|
|[CWinThread::P rocessWndProcException](#processwndprocexception)|スレッドのメッセージおよびコマンドハンドラーによってスローされた未処理の例外をすべてインターセプトします。|
|[CWinThread::P umpMessage](#pumpmessage)|スレッドのメッセージループを格納します。|
|[CWinThread:: ResumeThread](#resumethread)|スレッドの中断カウントをデクリメントします。|
|[CWinThread:: Run](#run)|メッセージポンプを持つスレッドの関数を制御します。 既定のメッセージループをカスタマイズするには、をオーバーライドします。|
|[CWinThread:: SetThreadPriority](#setthreadpriority)|現在のスレッドの優先順位を設定します。|
|[CWinThread:: SuspendThread](#suspendthread)|スレッドの中断カウントをインクリメントします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CWinThread:: operator ハンドル](#operator_handle)|オブジェクトのハンドルを取得し `CWinThread` ます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CWinThread:: m_bAutoDelete](#m_bautodelete)|スレッドの終了時にオブジェクトを破棄するかどうかを指定します。|
|[CWinThread:: m_hThread](#m_hthread)|現在のスレッドへのハンドル。|
|[CWinThread:: m_nThreadID](#m_nthreadid)|現在のスレッドの ID。|
|[CWinThread:: m_pActiveWnd](#m_pactivewnd)|OLE サーバーがアクティブになっている場合の、コンテナーアプリケーションのメインウィンドウへのポインター。|
|[CWinThread:: m_pMainWnd](#m_pmainwnd)|アプリケーションのメインウィンドウへのポインターを保持します。|

## <a name="remarks"></a>解説

通常、実行のメインスレッドは、から派生したオブジェクトによって提供されます。 `CWinApp` `CWinApp` はから派生 `CWinThread` します。 追加 `CWinThread` のオブジェクトを使用すると、特定のアプリケーション内で複数のスレッドを使用できます。

をサポートするスレッドには `CWinThread` 、ワーカースレッドとユーザーインターフェイススレッドという2つの一般的な種類があります。 ワーカースレッドには、メッセージポンプがありません。たとえば、スプレッドシートアプリケーションでバックグラウンド計算を実行するスレッドなどです。 ユーザーインターフェイススレッドには、メッセージポンプがあり、システムから受信したメッセージを処理します。 [CWinApp](../../mfc/reference/cwinapp-class.md) およびそれから派生したクラスは、ユーザーインターフェイススレッドの例です。 他のユーザーインターフェイススレッドは、から直接派生させることもでき `CWinThread` ます。

クラスのオブジェクト `CWinThread` は、通常、スレッドの実行中に存在します。 この動作を変更する場合は、 [m_bAutoDelete](#m_bautodelete) を FALSE に設定します。

クラスは、 `CWinThread` コードと MFC を完全にスレッドセーフにするために必要です。 スレッド固有の情報を保持するためにフレームワークによって使用されるスレッドローカルデータは、オブジェクトによって管理され `CWinThread` ます。 この依存 `CWinThread` 関係によってスレッドローカルデータが処理されるため、mfc を使用するすべてのスレッドは mfc によって作成される必要があります。 たとえば、ランタイム関数によって作成されたスレッド [_beginthread、_BEGINTHREADEX](../../c-runtime-library/reference/beginthread-beginthreadex.md) MFC api を使用することはできません。

スレッドを作成するには、 [AfxBeginThread](application-information-and-management.md#afxbeginthread)を呼び出します。 ワーカースレッドとユーザーインターフェイススレッドのどちらを使用するかに応じて、2つの形式があります。 ユーザーインターフェイススレッドが必要な場合は、 `AfxBeginThread` 派生クラスのへのポインターをに渡し `CRuntimeClass` `CWinThread` ます。 ワーカースレッドを作成する場合は、制御 `AfxBeginThread` 関数へのポインターと、制御関数へのパラメーターを渡します。 ワーカースレッドとユーザーインターフェイススレッドの両方について、優先順位、スタックサイズ、作成フラグ、およびセキュリティ属性を変更するオプションのパラメーターを指定できます。 `AfxBeginThread` は、新しいオブジェクトへのポインターを返し `CWinThread` ます。

を呼び出す代わりに、 `AfxBeginThread` から派生したオブジェクトを構築 `CWinThread` してを呼び出すことができ `CreateThread` ます。 この2段階の構築方法は、 `CWinThread` スレッドの実行の連続した作成と終了の間でオブジェクトを再利用する場合に便利です。

の詳細につい `CWinThread` ては、「 [C++ および MFC でのマルチスレッド](../../parallel/multithreading-with-cpp-and-mfc.md)」、「マルチスレッド: [User-Interface スレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)」、「マルチスレッド: [ワーカースレッドの作成](../../parallel/multithreading-creating-worker-threads.md)」、および「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cwinthreadcreatethread"></a><a name="createthread"></a> CWinThread:: CreateThread

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

- 中断カウントが1のスレッドを開始 CREATE_SUSPENDED ます。 `CWinThread`スレッドが実行を開始する前に、 [m_bAutoDelete](#m_bautodelete)や派生クラスのメンバーなど、オブジェクトのメンバーデータを初期化する場合は、CREATE_SUSPENDED を使用します。 初期化が完了したら、 [CWinThread:: ResumeThread](#resumethread) を使用して、実行中のスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。

- **0** 作成直後にスレッドを開始します。

*nStackSize*<br/>
新しいスレッドへのスタックのバイト サイズを指定します。 **0** の場合、スタックサイズの既定値は、プロセスのプライマリスレッドのサイズと同じになります。

*lpSecurityAttrs*<br/>
スレッドのセキュリティ属性を指定する [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 構造体を指します。

### <a name="return-value"></a>戻り値

スレッドが正常に作成された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

`AfxBeginThread`スレッドオブジェクトを作成し、1回の手順で実行するには、を使用します。 スレッド `CreateThread` 実行の連続した作成と終了の間でスレッドオブジェクトを再利用する場合は、を使用します。

## <a name="cwinthreadcwinthread"></a><a name="cwinthread"></a> CWinThread:: CWinThread

`CWinThread` オブジェクトを構築します。

```
CWinThread();
```

### <a name="remarks"></a>解説

スレッドの実行を開始するには、 [CreateThread](#createthread) メンバー関数を呼び出します。 通常は、 [AfxBeginThread](application-information-and-management.md#afxbeginthread)を呼び出してスレッドを作成します。このコンストラクターは、このコンストラクターとを呼び出します `CreateThread` 。

## <a name="cwinthreadexitinstance"></a><a name="exitinstance"></a> CWinThread:: ExitInstance

オーバーライドされる前の [実行](#run) メンバー関数内からフレームワークによって呼び出され、スレッドのこのインスタンスを終了します。または、 [InitInstance](#initinstance) の呼び出しが失敗した場合は、を呼び出します。

```
virtual int ExitInstance();
```

### <a name="return-value"></a>戻り値

スレッドの終了コード。0はエラーがないことを示し、0より大きい値はエラーを示します。 この値は、 [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)を呼び出すことによって取得できます。

### <a name="remarks"></a>解説

このメンバー関数は、メンバー関数内のどこからでも呼び出すことはできません `Run` 。 このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。

M_bAutoDelete が TRUE の場合、この関数の既定の実装では、オブジェクトが削除 `CWinThread` されます。 [](#m_bautodelete) スレッドが終了したときに追加のクリーンアップを実行する場合は、この関数をオーバーライドします。 の実装では、 `ExitInstance` コードの実行後に基本クラスのバージョンを呼び出す必要があります。

## <a name="cwinthreadgetmainwnd"></a><a name="getmainwnd"></a> CWinThread:: GetMainWnd

アプリケーションが OLE サーバーである場合は、この関数を呼び出して、アプリケーションオブジェクトのメンバーを直接参照するのではなく、アプリケーションのアクティブなメインウィンドウへのポインターを取得し `m_pMainWnd` ます。

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>戻り値

この関数は、2種類のウィンドウのいずれかへのポインターを返します。 スレッドが OLE サーバーに含まれていて、アクティブなコンテナー内でアクティブな状態にあるオブジェクトがある場合、この関数はオブジェクトの [CWinApp:: m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) データメンバーを返し `CWinThread` ます。

コンテナー内でアクティブなオブジェクトが存在しない場合、またはアプリケーションが OLE サーバーではない場合、この関数はスレッドオブジェクトの [m_pMainWnd](#m_pmainwnd) データメンバーを返します。

### <a name="remarks"></a>解説

ユーザーインターフェイススレッドの場合、これは `m_pActiveWnd` アプリケーションオブジェクトのメンバーを直接参照することと同じです。

開発中のアプリケーションが OLE サーバーではない場合は、この関数を呼び出すことは、アプリケーション オブジェクトの `m_pMainWnd` メンバーを直接参照することと同じです。

既定の動作を変更するには、この関数をオーバーライドします。

## <a name="cwinthreadgetthreadpriority"></a><a name="getthreadpriority"></a> CWinThread:: GetThreadPriority

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

## <a name="cwinthreadinitinstance"></a><a name="initinstance"></a> CWinThread:: InitInstance

`InitInstance` ユーザーインターフェイススレッドの新しいインスタンスを初期化するには、オーバーライドする必要があります。

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>戻り値

初期化が成功した場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

通常は、をオーバーライドし `InitInstance` て、スレッドが最初に作成されたときに完了する必要があるタスクを実行します。

このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。 [AfxBeginThread](application-information-and-management.md#afxbeginthread)に渡される制御関数でワーカースレッドの初期化を実行します。

## <a name="cwinthreadisidlemessage"></a><a name="isidlemessage"></a> CWinThread:: IsIdleMessage

`OnIdle`特定のメッセージが生成された後も呼び出されないようにするには、この関数をオーバーライドします。

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*pMsg*<br/>
処理中の現在のメッセージを指します。

### <a name="return-value"></a>戻り値

メッセージの `OnIdle` 処理後にを呼び出す必要がある場合は0以外の場合は。それ以外の場合は0。

### <a name="remarks"></a>解説

既定の実装では、 `OnIdle` 冗長なマウスメッセージや、キャレットの点滅によって生成されたメッセージは呼び出されません。

アプリケーションが短時間タイマーを作成した場合は、 `OnIdle` が頻繁に呼び出され、パフォーマンスの問題が発生します。 このようなアプリケーションのパフォーマンスを向上させるには、 `IsIdleMessage` アプリケーションの派生クラスでをオーバーライドし `CWinApp` て、次のように WM_TIMER メッセージを確認します。

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

この方法で WM_TIMER を処理することで、短いタイマーを使用するアプリケーションのパフォーマンスが向上します。

## <a name="cwinthreadm_bautodelete"></a><a name="m_bautodelete"></a> CWinThread:: m_bAutoDelete

スレッドの終了時に `CWinThread` オブジェクトを自動的に削除するかどうかを指定します。

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>解説

`m_bAutoDelete`データメンバーは、BOOL 型のパブリック変数です。

の値は、 `m_bAutoDelete` 基になるスレッドハンドルを閉じる方法には影響しませんが、ハンドルを閉じるタイミングに影響します。 スレッド ハンドルは、`CWinThread` オブジェクトが破棄されるときに必ず閉じられます。

## <a name="cwinthreadm_hthread"></a><a name="m_hthread"></a> CWinThread:: m_hThread

このにアタッチされているスレッドへのハンドル `CWinThread` 。

```
HANDLE m_hThread;
```

### <a name="remarks"></a>解説

`m_hThread`データメンバーは、型 HANDLE のパブリック変数です。 これは、基になるカーネルスレッドオブジェクトが現在存在していて、ハンドルがまだ閉じられていない場合にのみ有効です。

CWinThread デストラクターは、の CloseHandle を呼び出し `m_hThread` ます。 スレッドが終了したときに [m_bAutoDelete](#m_bautodelete) が TRUE の場合、cwinthread オブジェクトが破棄され、cwinthread オブジェクトとそのメンバー変数へのポインターが無効になります。 `m_hThread`スレッドの終了値を確認したり、シグナルを待機したりするには、メンバーが必要になることがあります。 スレッドの実行中に CWinThread オブジェクトとそのメンバーを保持 `m_hThread` し、終了した後で、 `m_bAutoDelete` スレッドの実行を継続できるようにするには、を FALSE に設定します。 それ以外の場合は、スレッドが終了し、CWinThread オブジェクトが破棄され、ハンドルを閉じてから使用を試みることができます。 この手法を使用する場合は、CWinThread オブジェクトを削除する必要があります。

## <a name="cwinthreadm_nthreadid"></a><a name="m_nthreadid"></a> CWinThread:: m_nThreadID

このにアタッチされているスレッドの ID `CWinThread` 。

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>解説

`m_nThreadID`データメンバーは、DWORD 型のパブリック変数です。 これは、基になるカーネルスレッドオブジェクトが現在存在する場合にのみ有効です。
[M_hThread](#m_hthread)の有効期間については、「解説」も参照してください。

### <a name="example"></a>例

  [AfxGetThread](application-information-and-management.md#afxgetthread)の例を参照してください。

## <a name="cwinthreadm_pactivewnd"></a><a name="m_pactivewnd"></a> CWinThread:: m_pActiveWnd

スレッドのアクティブウィンドウオブジェクトへのポインターを格納するには、このデータメンバーを使用します。

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>解説

によって参照されるウィンドウが閉じられると、Microsoft Foundation Class ライブラリによってスレッドが自動的に終了 `m_pActiveWnd` します。 このスレッドがアプリケーションのプライマリスレッドの場合は、アプリケーションも終了します。 このデータメンバーが NULL の場合、アプリケーションのオブジェクトのアクティブなウィンドウ `CWinApp` が継承されます。 `m_pActiveWnd` は型のパブリック変数です `CWnd*` 。

通常、このメンバー変数は、をオーバーライドするときに設定し `InitInstance` ます。 ワーカースレッドでは、このデータメンバーの値は親スレッドから継承されます。

## <a name="cwinthreadm_pmainwnd"></a><a name="m_pmainwnd"></a> CWinThread:: m_pMainWnd

このデータメンバーを使用して、スレッドのメインウィンドウオブジェクトへのポインターを格納します。

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>解説

によって参照されるウィンドウが閉じられると、Microsoft Foundation Class ライブラリによってスレッドが自動的に終了 `m_pMainWnd` します。 このスレッドがアプリケーションのプライマリスレッドの場合は、アプリケーションも終了します。 このデータメンバーが NULL の場合、アプリケーションのオブジェクトのメインウィンドウが、 `CWinApp` スレッドを終了するタイミングを決定するために使用されます。 `m_pMainWnd` は型のパブリック変数です `CWnd*` 。

通常、このメンバー変数は、をオーバーライドするときに設定し `InitInstance` ます。 ワーカースレッドでは、このデータメンバーの値は親スレッドから継承されます。

## <a name="cwinthreadonidle"></a><a name="onidle"></a> CWinThread:: OnIdle

アイドル時間の処理を実行するには、このメンバー関数をオーバーライドします。

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>パラメーター

*lCount*<br/>
`OnIdle`スレッドのメッセージキューが空のときにが呼び出されるたびに、カウンターがインクリメントされます。 このカウントは、新しいメッセージが処理されるたびに0にリセットされます。 *LCount* パラメーターを使用すると、メッセージを処理せずにスレッドがアイドル状態になった相対的な時間を調べることができます。

### <a name="return-value"></a>戻り値

アイドル状態の処理時間を増やすには0以外。アイドル処理時間がそれ以上必要ない場合は0。

### <a name="remarks"></a>解説

`OnIdle` は、スレッドのメッセージキューが空のときに、既定のメッセージループで呼び出されます。 オーバーライドを使用して、独自のバックグラウンドアイドルハンドラータスクを呼び出します。

`OnIdle` は、追加のアイドル処理時間が不要であることを示すために0を返します。 *LCount* パラメーターは、 `OnIdle` メッセージキューが空のときにが呼び出されるたびに増分され、新しいメッセージが処理されるたびに0にリセットされます。 この数に基づいて、異なるアイドルルーチンを呼び出すことができます。

このメンバー関数の既定の実装では、一時オブジェクトと未使用のダイナミックリンクライブラリがメモリから解放されます。

このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。

アプリケーションではが返されるまでメッセージを処理できないため `OnIdle` 、この関数では時間のかかるタスクを実行しないでください。

## <a name="cwinthreadoperator-handle"></a><a name="operator_handle"></a> CWinThread:: operator ハンドル

オブジェクトのハンドルを取得し `CWinThread` ます。

```
operator HANDLE() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、スレッドオブジェクトのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

ハンドルを使用して、Windows Api を直接呼び出します。

## <a name="cwinthreadpostthreadmessage"></a><a name="postthreadmessage"></a> CWinThread::P ostThreadMessage

ユーザー定義メッセージを別のオブジェクトにポストするために呼び出され `CWinThread` ます。

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

### <a name="remarks"></a>解説

ポストされたメッセージは、メッセージマップマクロ ON_THREAD_MESSAGE によって適切なメッセージハンドラーにマップされます。

> [!NOTE]
> [Postthreadmessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)を呼び出すと、メッセージはスレッドのメッセージキューに配置されます。 ただし、このように投稿されたメッセージはウィンドウに関連付けられていないため、MFC では、メッセージまたはコマンドハンドラーにそれらをディスパッチしません。 これらのメッセージを処理するには、 `PreTranslateMessage()` CWinApp 派生クラスの関数をオーバーライドし、メッセージを手動で処理します。

## <a name="cwinthreadpretranslatemessage"></a><a name="pretranslatemessage"></a> CWinThread::P reTranslateMessage

Windows 関数 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) および [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)にディスパッチされる前に、ウィンドウメッセージをフィルター処理するには、この関数をオーバーライドします。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*pMsg*<br/>
処理するメッセージを含む [MSG 構造体](/windows/win32/api/winuser/ns-winuser-msg) を指します。

### <a name="return-value"></a>戻り値

メッセージがで完全に処理され、 `PreTranslateMessage` それ以上処理されない場合は0以外の。 メッセージを通常の方法で処理する必要がある場合は0。

### <a name="remarks"></a>解説

このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。

## <a name="cwinthreadprocessmessagefilter"></a><a name="processmessagefilter"></a> CWinThread::P Roて Messagefilter

フレームワークのフック関数は、このメンバー関数を呼び出して、特定の Windows メッセージをフィルター処理して応答します。

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*code*<br/>
フックコードを指定します。 このメンバー関数は、コードを使用して、 *Lpmsg* の処理方法を決定します。

*lpMsg*<br/>
Windows [メッセージ構造](/windows/win32/api/winuser/ns-winuser-msg)へのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

フック関数は、アプリケーションの通常のメッセージ処理に送信される前に、イベントを処理します。

この高度な機能をオーバーライドする場合は、フレームワークのフック処理を維持するために、基本クラスのバージョンを必ず呼び出してください。

## <a name="cwinthreadprocesswndprocexception"></a><a name="processwndprocexception"></a> CWinThread::P rocessWndProcException

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
フレームワークが例外をスローする原因となった windows メッセージに関する情報を含む [MSG 構造体](/windows/win32/api/winuser/ns-winuser-msg) を指します。

### <a name="return-value"></a>戻り値

WM_CREATE 例外が生成された場合は-1。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数を直接呼び出さないでください。

このメンバー関数の既定の実装では、次のメッセージから生成された例外のみを処理します。

|コマンド|アクション|
|-------------|------------|
|WM_CREATE|オーバー.|
|WM_PAINT|影響を受けるウィンドウを検証して、別の WM_PAINT メッセージが生成されないようにします。|

このメンバー関数をオーバーライドして、例外のグローバルな処理を提供します。 既定の動作を表示する場合にのみ、基本機能を呼び出します。

このメンバー関数は、メッセージポンプを持つスレッドでのみ使用されます。

## <a name="cwinthreadpumpmessage"></a><a name="pumpmessage"></a> CWinThread::P umpMessage

スレッドのメッセージループを格納します。

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>解説

`PumpMessage` スレッドのメッセージループを格納します。 `PumpMessage` は `CWinThread` 、スレッドのメッセージをポンプするためにによって呼び出されます。 `PumpMessage`を直接呼び出して、メッセージを強制的に処理することも、をオーバーライドして既定の動作を変更することもでき `PumpMessage` ます。

`PumpMessage`上級ユーザーのみが、を直接呼び出し、既定の動作をオーバーライドすることをお勧めします。

## <a name="cwinthreadresumethread"></a><a name="resumethread"></a> CWinThread:: ResumeThread

[SuspendThread](#suspendthread)メンバー関数によって中断されたスレッド、または CREATE_SUSPENDED フラグを使用して作成されたスレッドの実行を再開するために呼び出されます。

```
DWORD ResumeThread();
```

### <a name="return-value"></a>戻り値

成功した場合は、スレッドの前の中断回数。 `0xFFFFFFFF` それ以外の場合は。 戻り値が0の場合、現在のスレッドは中断されませんでした。 戻り値が1の場合、スレッドは中断されましたが、現在は再起動されています。 戻り値が1より大きい場合は、スレッドが中断されたままになります。

### <a name="remarks"></a>解説

現在のスレッドの中断回数が1つ減少します。 中断回数が0に減ると、スレッドは実行を再開します。それ以外の場合、スレッドは中断されたままになります。

## <a name="cwinthreadrun"></a><a name="run"></a> CWinThread:: Run

ユーザーインターフェイススレッドの既定のメッセージループを提供します。

```
virtual int Run();
```

### <a name="return-value"></a>戻り値

**`int`** スレッドによって返される値。 この値は、 [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)を呼び出すことによって取得できます。

### <a name="remarks"></a>解説

`Run` アプリケーションが [WM_QUIT](/windows/win32/winmsg/wm-quit) メッセージを受信するまで、Windows メッセージを取得してディスパッチします。 スレッドのメッセージキューに現在メッセージが含まれていない場合、は `Run` を呼び出して `OnIdle` アイドル時の処理を実行します。 受信メッセージは、特別な処理のために [PreTranslateMessage](#pretranslatemessage) メンバー関数に移動し、標準キーボード翻訳の Windows 関数 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) に移動します。 最後に、 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 関数が呼び出されます。

`Run` がオーバーライドされることはほとんどありませんが、これをオーバーライドして特殊な動作を実装することができます。

このメンバー関数は、ユーザーインターフェイススレッドでのみ使用されます。

## <a name="cwinthreadsetthreadpriority"></a><a name="setthreadpriority"></a> CWinThread:: SetThreadPriority

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

### <a name="remarks"></a>解説

[CreateThread](#createthread)が正常に返された後にのみ呼び出すことができます。

## <a name="cwinthreadsuspendthread"></a><a name="suspendthread"></a> CWinThread:: SuspendThread

現在のスレッドの中断カウントをインクリメントします。

```
DWORD SuspendThread();
```

### <a name="return-value"></a>戻り値

成功した場合は、スレッドの前の中断回数。 `0xFFFFFFFF` それ以外の場合は。

### <a name="remarks"></a>解説

いずれかのスレッドが0を超える中断カウントを持っている場合、そのスレッドは実行されません。 スレッドは、 [ResumeThread](#resumethread) メンバー関数を呼び出すことによって再開できます。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
