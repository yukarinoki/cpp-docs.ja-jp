---
title: CWinThread クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2c01336094077cc1f451f2e7b479ca4acf9fb77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441357"
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
|[CWinThread::CWinThread](#cwinthread)|`CWinThread` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[:Createthread](#createthread)|実行を開始、`CWinThread`オブジェクト。|
|[CWinThread::ExitInstance](#exitinstance)|スレッドの終了時にクリーンアップをオーバーライドします。|
|[CWinThread::GetMainWnd](#getmainwnd)|スレッドのメイン ウィンドウへのポインターを取得します。|
|[CWinThread::GetThreadPriority](#getthreadpriority)|現在のスレッドの優先順位を取得します。|
|[CWinThread::InitInstance](#initinstance)|オーバーライドすると、実行スレッドのインスタンスを初期化します。|
|[CWinThread::IsIdleMessage](#isidlemessage)|特別なメッセージを確認します。|
|[CWinThread::OnIdle](#onidle)|オーバーライドすると、スレッド固有のアイドル時間の処理を実行します。|
|[CWinThread::PostThreadMessage](#postthreadmessage)|別のメッセージを投稿`CWinThread`オブジェクト。|
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Windows 関数にディスパッチされる前に、メッセージをフィルター処理[TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage)します。|
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|アプリケーションに到達する前に、特定のメッセージを受け取ります。|
|[CWinThread::ProcessWndProcException](#processwndprocexception)|スレッドのメッセージとコマンド ハンドラーによってスローされたすべてのハンドルされない例外を受け取ります。|
|[CWinThread::PumpMessage](#pumpmessage)|スレッドのメッセージ ループが含まれています。|
|[Cwinthread::resumethread](#resumethread)|スレッドのデクリメントは、カウントを中断します。|
|[CWinThread::Run](#run)|スレッドのメッセージ ポンプの制御関数。 既定のメッセージ ループのカスタマイズをオーバーライドします。|
|[CWinThread::SetThreadPriority](#setthreadpriority)|現在のスレッドの優先順位を設定します。|
|[CWinThread::SuspendThread](#suspendthread)|スレッドの増分数を中断します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CWinThread::operator ハンドル](#operator_handle)|ハンドルを取得、`CWinThread`オブジェクト。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CWinThread::m_bAutoDelete](#m_bautodelete)|スレッドの終了時のオブジェクトを破棄するかどうかを指定します。|
|[CWinThread::m_hThread](#m_hthread)|現在のスレッドへのハンドルします。|
|[CWinThread::m_nThreadID](#m_nthreadid)|現在のスレッドの ID。|
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE サーバーがアクティブである場合は、コンテナー アプリケーションのメイン ウィンドウへのポインター。|
|[ため](#m_pmainwnd)|アプリケーションのメイン ウィンドウへのポインターを保持します。|

## <a name="remarks"></a>Remarks

実行のメイン スレッドがから派生したオブジェクトによって提供される通常`CWinApp`;`CWinApp`から派生`CWinThread`します。 追加`CWinThread`オブジェクトは、特定のアプリケーション内で複数のスレッドを使用します。

スレッドの 2 つの一般的な種類がありますを`CWinThread`をサポートしています: ワーカー スレッドとユーザー インターフェイス スレッド。 ワーカー スレッドがメッセージ ポンプあるありません: たとえば、スプレッドシート アプリケーションでバック グラウンド計算を実行するスレッド。 ユーザー インターフェイス スレッドでは、メッセージ ポンプし、システムから受信したメッセージを処理します。 [CWinApp](../../mfc/reference/cwinapp-class.md)およびそれから派生したクラスは、ユーザー インターフェイス スレッドの例を示します。 他のユーザー インターフェイス スレッドから直接派生させることも`CWinThread`します。

クラスのオブジェクト`CWinThread`通常のスレッドの期間存続します。 この動作を変更する場合は、設定[m_bAutoDelete](#m_bautodelete)を FALSE にします。

`CWinThread`クラスはスレッド セーフなコードと MFC を実現するために必要です。 スレッド固有の情報を維持するためにフレームワークによって使用されるスレッド ローカル データが自主`CWinThread`オブジェクト。 この依存のため`CWinThread`MFC でスレッド ローカル データを処理するために MFC を使用する任意のスレッドを作成する必要があります。 実行時の関数によって作成されたスレッドなど[_beginthread、_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) MFC の Api を使用することはできません。

スレッドを作成するには[AfxBeginThread](application-information-and-management.md#afxbeginthread)します。 ワーカー ロールまたはユーザー インターフェイス スレッドをするかどうかに応じて、2 つの形式があります。 ユーザー インターフェイス スレッドにする場合は、渡す`AfxBeginThread`へのポインター、`CRuntimeClass`の`CWinThread`-クラスを派生します。 ワーカー スレッドを作成する場合に渡す`AfxBeginThread`制御関数とパラメーターを制御する関数へのポインター。 ワーカー スレッドとユーザー インターフェイス スレッドの両方で、優先度、スタックのサイズ、作成フラグ、およびセキュリティ属性を変更する省略可能なパラメーターを指定できます。 `AfxBeginThread` 新しいへのポインターを返しますが`CWinThread`オブジェクト。

呼び出す代わりに`AfxBeginThread`、構築することができます、 `CWinThread`- オブジェクトを派生`CreateThread`します。 この 2 段階の構築方法を再利用する場合に便利ですが、`CWinThread`連続の作成とスレッド実行の終了間のオブジェクト。

詳細については`CWinThread`、記事を参照して[C++ と MFC を使用するマルチ スレッド](../../parallel/multithreading-with-cpp-and-mfc.md)、[マルチ スレッド: ユーザー インターフェイス スレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)、[マルチ スレッド: ワーカーの作成スレッド](../../parallel/multithreading-creating-worker-threads.md)、および[マルチ スレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CWinThread`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

##  <a name="createthread"></a>  :Createthread

呼び出し元のプロセスのアドレス空間内で実行するスレッドを作成します。

```
BOOL CreateThread(
    DWORD dwCreateFlags = 0,
    UINT nStackSize = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>パラメーター

*dwCreateFlags*<br/>
スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。

- CREATE_SUSPENDED 中断カウントが 1 つのスレッドを開始します。 メンバー データの初期化に使用する場合は、CREATE_SUSPENDED を使用して、`CWinThread`などオブジェクト[m_bAutoDelete](#m_bautodelete)またはスレッドが実行を開始する前に、派生クラスのメンバー。 使用して、初期化が完了すると、 [cwinthread::resumethread](#resumethread)を実行しているスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。

- **0**作成後すぐにスレッドを開始します。

*nStackSize*<br/>
新しいスレッドへのスタックのバイト サイズを指定します。 場合**0**プロセスのプライマリ スレッドの場合と同じサイズに既定のスタック サイズ。

*lpSecurityAttrs*<br/>
指す、 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)スレッドのセキュリティ属性を指定する構造体。

### <a name="return-value"></a>戻り値

スレッドが正常に作成された場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

使用`AfxBeginThread`スレッド オブジェクトを作成し、1 つの手順で実行します。 使用`CreateThread`作成とスレッド実行の終了の間でスレッド オブジェクトを再利用する場合。

##  <a name="cwinthread"></a>  CWinThread::CWinThread

`CWinThread` オブジェクトを構築します。

```
CWinThread();
```

### <a name="remarks"></a>Remarks

スレッドの実行を開始する、 [CreateThread](#createthread)メンバー関数。 呼び出してスレッドを作成することは、通常は[AfxBeginThread](application-information-and-management.md#afxbeginthread)は、このコンス トラクターを呼び出します`CreateThread`します。

##  <a name="exitinstance"></a>  CWinThread::ExitInstance

ほとんどオーバーライド内からフレームワークによって呼び出されます[実行](#run)、スレッドのこのインスタンスを終了するメンバー関数への呼び出しまたは[InitInstance](#initinstance)が失敗しました。

```
virtual int ExitInstance();
```

### <a name="return-value"></a>戻り値

スレッドの終了コード。0 は、エラーを 、エラーを示す 0 より大きい値です。 この値は、呼び出すことによって取得できる[GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)します。

### <a name="remarks"></a>Remarks

このメンバー関数から呼び出さないで任意の場所内では、`Run`メンバー関数。 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。

この関数の既定の実装を削除、`CWinThread`オブジェクトの場合[m_bAutoDelete](#m_bautodelete)は TRUE です。 スレッドの終了時に、追加のクリーンアップを実行する場合は、この関数をオーバーライドします。 実装`ExitInstance`コードが実行された後に、基本クラスのバージョンを呼び出す必要があります。

##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd

アプリケーションが OLE サーバーである場合は、直接参照するのではなく、アプリケーションのアクティブなメイン ウィンドウへのポインターを取得するには、この関数を呼び出し、`m_pMainWnd`アプリケーション オブジェクトのメンバー。

```
virtual CWnd* GetMainWnd();
```

### <a name="return-value"></a>戻り値

この関数は、windows の 2 種類のいずれかにポインターを返します。 かどうか、スレッドが OLE サーバーの一部であるし、作業中のコンテナー内で、インプレース アクティブであるオブジェクトが、この関数を返します、[先](../../mfc/reference/cwinapp-class.md#m_pactivewnd)のデータ メンバー、`CWinThread`オブジェクト。

この関数が返すかどうかは、コンテナー内の場所で有効になっているオブジェクトがないか、アプリケーションが OLE サーバーではない、 [m_pMainWnd](#m_pmainwnd)スレッド オブジェクトのデータ メンバー。

### <a name="remarks"></a>Remarks

ユーザー インターフェイス スレッドでは、これを直接参照するのと同じですが、`m_pActiveWnd`アプリケーション オブジェクトのメンバー。

開発中のアプリケーションが OLE サーバーではない場合は、この関数を呼び出すことは、アプリケーション オブジェクトの `m_pMainWnd` メンバーを直接参照することと同じです。

既定の動作を変更するには、この関数をオーバーライドします。

##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority

このスレッドの現在のスレッド優先度レベルを取得します。

```
int GetThreadPriority();
```

### <a name="return-value"></a>戻り値

優先度クラス内で現在のスレッド優先度レベル。 返される値は、次のいずれかを指定が優先度の高い順に一覧表示。

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

これらの優先順位の詳細については、次を参照してください。 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK に含まれています。

##  <a name="initinstance"></a>  CWinThread::InitInstance

`InitInstance` ユーザー インターフェイス スレッドの新しいインスタンスを初期化するためにオーバーライドする必要があります。

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>戻り値

初期化が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

通常、オーバーライドする`InitInstance`スレッドが最初に作成したときに完了する必要がありますのあるタスクを実行します。

このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。 制御関数に渡されるでワーカー スレッドの初期化を実行[AfxBeginThread](application-information-and-management.md#afxbeginthread)します。

##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage

保持するには、この関数をオーバーライド`OnIdle`特定のメッセージが生成された後に呼び出されるからです。

```
virtual BOOL IsIdleMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*pMsg*<br/>
処理されている現在のメッセージを指します。

### <a name="return-value"></a>戻り値

0 以外の値`OnIdle`処理後に呼び出す必要があるメッセージ。 それ以外の場合、0。

### <a name="remarks"></a>Remarks

既定の実装は呼び出しません`OnIdle`冗長なマウス メッセージとメッセージのキャレットの点滅によって生成された後にします。

アプリケーションが短い時間のタイマーを作成した場合`OnIdle`が呼び出される多くの場合、パフォーマンスの問題が発生します。 このようなアプリケーションのパフォーマンスを向上させるのには、オーバーライド`IsIdleMessage`アプリケーションの`CWinApp`-WM_TIMER メッセージを次のようにチェックするクラスを派生します。

[!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]

この方法で WM_TIMER を処理すると、短いタイマーを使用するアプリケーションのパフォーマンスが向上します。

##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete

スレッドの終了時に `CWinThread` オブジェクトを自動的に削除するかどうかを指定します。

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Remarks

`m_bAutoDelete`データ メンバーは、BOOL 型のパブリック変数です。

`m_bAutoDelete` の値は、基になるスレッド ハンドルを閉じる方法に影響しません。 スレッド ハンドルは、`CWinThread` オブジェクトが破棄されるときに必ず閉じられます。

##  <a name="m_hthread"></a>  CWinThread::m_hThread

これに接続されているスレッドへのハンドル`CWinThread`します。

```
HANDLE m_hThread;
```

### <a name="remarks"></a>Remarks

`m_hThread`データ メンバーが型ハンドルのパブリック変数です。 存在する現在のスレッドを基になる場合にのみ有効です。

##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID

スレッドの ID は、これに接続されている`CWinThread`します。

```
DWORD m_nThreadID;
```

### <a name="remarks"></a>Remarks

`m_nThreadID`データ メンバーは DWORD 型のパブリック変数です。 存在する現在のスレッドを基になる場合にのみ有効です。

### <a name="example"></a>例

  例をご覧ください[AfxGetThread](application-information-and-management.md#afxgetthread)します。

##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd

このデータ メンバーを使用すると、スレッドのアクティブなウィンドウのオブジェクトへのポインターを格納できます。

```
CWnd* m_pActiveWnd;
```

### <a name="remarks"></a>Remarks

Microsoft Foundation Class ライブラリは自動的に終了スレッドによって参照されるウィンドウと`m_pActiveWnd`が閉じられました。 このスレッドは、アプリケーションのプライマリ スレッドは、アプリケーションも終了します。 このデータ メンバーが null の場合、アプリケーションのアクティブなウィンドウの場合`CWinApp`オブジェクトは継承されます。 `m_pActiveWnd` 型のパブリック変数`CWnd*`します。

オーバーライドする場合にこのメンバー変数を設定する通常、`InitInstance`します。 ワーカー スレッドでは、このデータ メンバーの値は親スレッドから継承されます。

##  <a name="m_pmainwnd"></a>  ため

このデータ メンバーを使用すると、スレッドのメイン ウィンドウのオブジェクトへのポインターを格納できます。

```
CWnd* m_pMainWnd;
```

### <a name="remarks"></a>Remarks

Microsoft Foundation Class ライブラリは自動的に終了スレッドによって参照されるウィンドウと`m_pMainWnd`が閉じられました。 このスレッドは、アプリケーションのプライマリ スレッドは、アプリケーションも終了します。 このデータ メンバーが null の場合、アプリケーションのメイン ウィンドウの場合`CWinApp`オブジェクトは、スレッドを終了するタイミングを決定するために使用されます。 `m_pMainWnd` 型のパブリック変数`CWnd*`します。

オーバーライドする場合にこのメンバー変数を設定する通常、`InitInstance`します。 ワーカー スレッドでは、このデータ メンバーの値は親スレッドから継承されます。

##  <a name="onidle"></a>  CWinThread::OnIdle

アイドル状態時の処理を実行するには、このメンバー関数をオーバーライドします。

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>パラメーター

*lCount*<br/>
カウンターは毎回増加`OnIdle`スレッドのメッセージ キューが空のときに呼び出されます。 この数は、新しいメッセージが処理されるたびに 0 にリセットされます。 使用することができます、 *lCount*相対スレッドがアイドル状態メッセージを処理することがなく時間の長さを決定するパラメーター。

### <a name="return-value"></a>戻り値

0 以外の場合よりアイドル処理時間を受信するにはこれ以上アイドル状態の処理時間が必要な場合は 0 を返します。

### <a name="remarks"></a>Remarks

`OnIdle` スレッドのメッセージ キューが空の場合、既定のメッセージ ループで呼びます。 オーバーライドを使用して、独自の背景のアイドル処理を呼び出します。

`OnIdle` アイドル状態の追加の処理時間が必要ないことを示すために 0 を返す必要があります。 *LCount*パラメーターはたびに増分`OnIdle`メッセージ キューが空で、新しいメッセージが処理されるたびに 0 にリセットするときに呼び出されます。 この数に基づく、別のアイドル処理ルーチンを呼び出すことができます。

このメンバー関数の既定の実装では、一時オブジェクトとメモリから未使用のダイナミック リンク ライブラリを解放します。

このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。

までのメッセージを処理できないため、`OnIdle`戻り値は、この関数で時間のかかるタスクは行いません。

##  <a name="operator_handle"></a>  CWinThread::operator ハンドル

ハンドルを取得、`CWinThread`オブジェクト。

```
operator HANDLE() const;
```

### <a name="return-value"></a>戻り値

成功した場合、スレッド オブジェクトのハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

Windows Api を直接呼び出すには、ハンドルを使用します。

##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage

別のユーザー定義メッセージを投稿すると呼ばれる`CWinThread`オブジェクト。

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
最初のメッセージ パラメーター。

*lParam*<br/>
2 番目のメッセージ パラメーター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

投稿されたメッセージは、メッセージ マップ マクロによって、適切なメッセージ ハンドラーにマップされます。

> [!NOTE]
>  Windows を呼び出すときに[次](https://msdn.microsoft.com/library/windows/desktop/ms644946)MFC メッセージ ハンドラーは呼び出されません、MFC アプリケーション内の関数。 詳細については、サポート技術情報の記事、"PRB:: MFC メッセージ ハンドラーしないというで PostThreadMessage()"(Q142415) を参照してください。

##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage

Windows 関数にディスパッチされる前に、ウィンドウ メッセージをフィルター処理するには、この関数をオーバーライド[TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage)します。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*pMsg*<br/>
指す、 [MSG 構造体](../../mfc/reference/msg-structure1.md)処理するメッセージを格納しています。

### <a name="return-value"></a>戻り値

メッセージで完全に処理された場合は 0 以外`PreTranslateMessage`さらに処理する必要があります。 通常の方法で、メッセージを処理する必要がありますがある場合は 0 します。

### <a name="remarks"></a>Remarks

このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。

##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter

フレームワークのフック関数は、特定の Windows メッセージに応答をフィルター処理には、このメンバー関数を呼び出します。

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
フック コードを指定します。 このメンバー関数では、コードを使用して、処理する方法を決定*lpMsg します。*

*lpMsg*<br/>
Windows へのポインター [MSG 構造体](../../mfc/reference/msg-structure1.md)します。

### <a name="return-value"></a>戻り値

メッセージが処理された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションの通常のメッセージを送信する前に、イベントを処理するフック関数を処理します。

この高度な機能をオーバーライドする場合は、フレームワークを維持するために基本クラスのバージョンを呼び出すことを確認する処理をフックします。

##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException

フレームワークは、ハンドラーは、スレッドのメッセージまたはコマンド ハンドラーのいずれかでスローされる例外をキャッチしませんたびに、このメンバー関数を呼び出します。

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*e*<br/>
未処理の例外を指します。

*pMsg*<br/>
指す、 [MSG 構造体](../../mfc/reference/msg-structure1.md)フレームワークが例外をスローする原因となった windows メッセージに関する情報を格納します。

### <a name="return-value"></a>戻り値

WM_CREATE 例外が生成される場合は-1それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数を直接呼び出さないでください。

このメンバー関数の既定の実装では、次のメッセージから生成される例外のみを処理します。

|コマンド|アクション|
|-------------|------------|
|WM_CREATE|失敗します。|
|WM_PAINT|別の WM_PAINT メッセージから生成されるように、影響を受けるウィンドウを検証します。|

グローバルに、例外の処理を提供するには、このメンバー関数をオーバーライドします。 既定の動作を表示しようとする場合にのみ、基本機能を呼び出します。

このメンバー関数は、メッセージ ポンプ スレッドでのみ使用されます。

##  <a name="pumpmessage"></a>  CWinThread::PumpMessage

スレッドのメッセージ ループが含まれています。

```
virtual BOOL PumpMessage();
```

### <a name="remarks"></a>Remarks

`PumpMessage` スレッドのメッセージ ループが含まれています。 `PumpMessage` によって呼び出される`CWinThread`スレッドのメッセージをポンプします。 呼び出すことができます`PumpMessage`強制的に処理されるメッセージを上書きするか直接`PumpMessage`をその既定の動作を変更します。

呼び出す`PumpMessage`直接あり高度なユーザーのみ、既定の動作のオーバーライドはお勧めします。

##  <a name="resumethread"></a>  Cwinthread::resumethread

によって中断されたスレッドの実行を再開すると呼ばれる、 [SuspendThread](#suspendthread)メンバー関数、または CREATE_SUSPENDED フラグで作成されたスレッド。

```
DWORD ResumeThread();
```

### <a name="return-value"></a>戻り値

スレッドが前のカウントが成功した場合の中断`0xFFFFFFFF`それ以外の場合。 戻り値が 0 の場合、現在のスレッドが中断されません。 戻り値が 1 つの場合は、スレッドが中断されたが再起動されます。 戻り値より大きい値を 1 つは、スレッドが中断しています。

### <a name="remarks"></a>Remarks

現在のスレッドの中断カウントが 1 つ減少します。 中断カウントが短縮された場合、スレッドを対 0 の場合に、実行を再開しますそれ以外の場合、スレッドが中断しています。

##  <a name="run"></a>  CWinThread::Run

ユーザー インターフェイス スレッドの既定のメッセージ ループを提供します。

```
virtual int Run();
```

### <a name="return-value"></a>戻り値

**Int**スレッドによって返される値。 この値は、呼び出すことによって取得できる[GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)します。

### <a name="remarks"></a>Remarks

`Run` 取得し、アプリケーションが受信するまで、Windows メッセージをディスパッチする[WM_QUIT](/windows/desktop/winmsg/wm-quit)メッセージ。 スレッドのメッセージ キューにメッセージがない場合`Run`呼び出し`OnIdle`アイドル処理を実行します。 受信メッセージに移動、 [PreTranslateMessage](#pretranslatemessage)メンバー関数の特別な処理と、Windows 関数に[TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)標準キーボード変換をします。 最後に、 [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows 関数が呼び出されます。

`Run` オーバーライドされることはほとんどありませんが、特別な動作を実装するためにオーバーライドできます。

このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。

##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority

この関数は、現在のスレッドの優先度クラス内での優先度レベルを設定します。

```
BOOL SetThreadPriority(int nPriority);
```

### <a name="parameters"></a>パラメーター

*nPriority*<br/>
優先度クラス内で新しいスレッドの優先順位を指定します。 このパラメーターは、最も高い優先順位の降順で表示される、次の値のいずれかを指定する必要があります。

- THREAD_PRIORITY_TIME_CRITICAL

- THREAD_PRIORITY_HIGHEST

- THREAD_PRIORITY_ABOVE_NORMAL

- THREAD_PRIORITY_NORMAL

- THREAD_PRIORITY_BELOW_NORMAL

- THREAD_PRIORITY_LOWEST

- THREAD_PRIORITY_IDLE

これらの優先順位の詳細については、次を参照してください。 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

関数が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

後にのみ呼び出すことができます[CreateThread](#createthread)が正常に終了します。

##  <a name="suspendthread"></a>  CWinThread::SuspendThread

インクリメントの現在のスレッドの数を一時停止します。

```
DWORD SuspendThread();
```

### <a name="return-value"></a>戻り値

スレッドが前のカウントが成功した場合の中断`0xFFFFFFFF`それ以外の場合。

### <a name="remarks"></a>Remarks

任意のスレッドにゼロよりも中断カウントがある場合は、そのスレッドは実行されません。 スレッドを再開することができます、 [ResumeThread](#resumethread)メンバー関数。

## <a name="see-also"></a>関連項目

[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
