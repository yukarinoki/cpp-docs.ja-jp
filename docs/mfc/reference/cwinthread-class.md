---
title: CWinThread クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 115b351ccbaf9c8c5cbccb0004d04c53e54351ba
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123065"
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
|[Cwinthread::createthread](#createthread)|実行を開始、`CWinThread`オブジェクト。|  
|[CWinThread::ExitInstance](#exitinstance)|スレッドの終了時にクリーンアップするためにオーバーライドします。|  
|[CWinThread::GetMainWnd](#getmainwnd)|スレッドのメイン ウィンドウへのポインターを取得します。|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|現在のスレッドの優先度を取得します。|  
|[CWinThread::InitInstance](#initinstance)|オーバーライドすると、実行スレッドのインスタンスを初期化します。|  
|[CWinThread::IsIdleMessage](#isidlemessage)|特別なメッセージを確認します。|  
|[CWinThread::OnIdle](#onidle)|スレッド固有のアイドル時間の処理を実行するためにオーバーライドします。|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|別のメッセージをポスト`CWinThread`オブジェクト。|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Windows 関数にディスパッチされる前にメッセージをフィルター [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)です。|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|アプリケーションに到達する前に、特定のメッセージを受け取ります。|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|スレッドのメッセージとコマンド ハンドラーによってスローされたすべてのハンドルされない例外を受け取ります。|  
|[CWinThread::PumpMessage](#pumpmessage)|スレッドのメッセージ ループが含まれています。|  
|[Cwinthread::resumethread](#resumethread)|スレッドの減分は、カウントを中断します。|  
|[CWinThread::Run](#run)|メッセージ ポンプを持つスレッドの制御関数です。 既定のメッセージ ループをカスタマイズするをオーバーライドします。|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|現在のスレッドの優先順位を設定します。|  
|[CWinThread::SuspendThread](#suspendthread)|スレッドのインクリメントでは、カウントを中断します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CWinThread::operator ハンドル](#operator_handle)|ハンドルを取得、`CWinThread`オブジェクト。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|スレッドの終了位置にあるオブジェクトを破棄するかどうかを指定します。|  
|[CWinThread::m_hThread](#m_hthread)|現在のスレッドへのハンドルします。|  
|[CWinThread::m_nThreadID](#m_nthreadid)|現在のスレッドの ID です。|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE サーバーが、インプレース アクティブである場合は、コンテナー アプリケーションのメイン ウィンドウへのポインター。|  
|[ため](#m_pmainwnd)|アプリケーションのメイン ウィンドウへのポインターを保持します。|  
  
## <a name="remarks"></a>Remarks  
 実行のメイン スレッドがから派生したオブジェクトによって提供される通常`CWinApp`です。`CWinApp`から派生した`CWinThread`です。 追加`CWinThread`オブジェクトは、特定のアプリケーションで複数のスレッドを使用します。  
  
 スレッドの 2 つの一般的な種類がありますを`CWinThread`をサポートしています。 ワーカー スレッドとユーザー インターフェイス スレッドです。 ワーカー スレッドがメッセージ ポンプを持っていません: たとえば、スプレッドシート アプリケーションでバック グラウンド計算を実行するスレッド。 ユーザー インターフェイス スレッドでは、メッセージ ポンプし、システムから受信したメッセージを処理します。 [CWinApp](../../mfc/reference/cwinapp-class.md)し、そこから派生したクラスは、ユーザー インターフェイス スレッドの例を示します。 他のユーザー インターフェイス スレッドから直接派生させることも`CWinThread`します。  
  
 クラスのオブジェクト`CWinThread`通常、スレッドの期間に存在します。 この動作を変更する場合は、設定[m_bAutoDelete](#m_bautodelete)を FALSE にします。  
  
 `CWinThread`クラスはスレッド セーフなコードと MFC を実現するために必要です。 スレッド固有の情報を維持するためにフレームワークによって使用されるスレッド ローカル データがによって管理されている`CWinThread`オブジェクト。 この依存のため`CWinThread`、スレッド ローカル データを処理するには、MFC で MFC を使用する任意のスレッドを作成します。 ランタイム関数によって作成されたスレッドなど、 [_beginthread、_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) MFC Api を使用することはできません。  
  
 スレッドを作成するには[AfxBeginThread](application-information-and-management.md#afxbeginthread)です。 ワーカー ロールまたはユーザー インターフェイス スレッドをするかどうかに応じて、次の 2 つの形式があります。 ユーザー インターフェイス スレッドを実行する場合に、渡す`AfxBeginThread`へのポインター、`CRuntimeClass`の`CWinThread`-クラスを派生します。 ワーカー スレッドを作成する場合に渡す`AfxBeginThread`制御関数と、制御関数にパラメーターへのポインター。 ワーカー スレッドとユーザー インターフェイス スレッドの両方では、優先度、スタックのサイズ、作成フラグ、およびセキュリティ属性を変更する省略可能なパラメーターを指定できます。 `AfxBeginThread` 新しいへのポインターを返しますが`CWinThread`オブジェクト。  
  
 呼び出し元ではなく`AfxBeginThread`、構築することができます、 `CWinThread`-派生オブジェクトとを呼び出します`CreateThread`です。 この 2 段階の構築方法を再利用する場合に便利ですが、`CWinThread`スレッド実行の後続の作成と終了の間のオブジェクト。  
  
 詳細については`CWinThread`、記事を参照して[C++ と MFC を使用するマルチ スレッド](../../parallel/multithreading-with-cpp-and-mfc.md)、[マルチ スレッド: ユーザー インターフェイス スレッドの生成](../../parallel/multithreading-creating-user-interface-threads.md)、[マルチ スレッド: ワーカーの作成スレッド](../../parallel/multithreading-creating-worker-threads.md)、および[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="createthread"></a>  Cwinthread::createthread  
 呼び出し元のプロセスのアドレス空間内で実行するスレッドを作成します。  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwCreateFlags*  
 スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。  
  
- CREATE_SUSPENDED は、中断カウントが 1 つのスレッドを開始します。 メンバー データを初期化する場合は、CREATE_SUSPENDED を使用して、`CWinThread`などのオブジェクト[m_bAutoDelete](#m_bautodelete)またはスレッドが実行を開始する前に、派生クラスのメンバーです。 初期化が完了したらを使用して、 [cwinthread::resumethread](#resumethread)を実行しているスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。  
  
- **0**作成後すぐにスレッドを開始します。  
  
 *nStackSize*  
 新しいスレッドへのスタックのバイト サイズを指定します。 場合**0**、スタック サイズの既定値は、プロセスのプライマリ スレッドのものと同じサイズです。  
  
 *lpSecurityAttrs*  
 指す、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造体のスレッドのセキュリティ属性を指定します。  
  
### <a name="return-value"></a>戻り値  
 スレッドが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 使用して`AfxBeginThread`スレッド オブジェクトを作成し、1 つのステップで実行します。 使用して`CreateThread`作成とスレッド実行の終了の間のスレッド オブジェクトを再利用する場合。  
  
##  <a name="cwinthread"></a>  CWinThread::CWinThread  
 `CWinThread` オブジェクトを構築します。  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>Remarks  
 スレッドの実行を開始する、 [CreateThread](#createthread)メンバー関数。 呼び出してスレッドを作成したは通常[AfxBeginThread](application-information-and-management.md#afxbeginthread)は、このコンス トラクターを呼び出します`CreateThread`です。  
  
##  <a name="exitinstance"></a>  CWinThread::ExitInstance  
 ほとんどオーバーライド内からフレームワークによって呼び出されます[実行](#run)、スレッドのこのインスタンスを終了するメンバー関数への呼び出しまたは[InitInstance](#initinstance)は失敗します。  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>戻り値  
 スレッドの終了コードです。0 は、エラーを 、エラーを示す 0 より大きい値です。 この値を呼び出すことによって取得できる[GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数から呼び出さないで任意の場所が内、`Run`メンバー関数。 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。  
  
 この関数の既定の実装の削除、`CWinThread`オブジェクトの場合[m_bAutoDelete](#m_bautodelete) true を指定します。 スレッドの終了時にその他のクリーンアップを実行する場合は、この関数をオーバーライドします。 実装`ExitInstance`コードが実行された後に、基本クラスのバージョンを呼び出す必要があります。  
  
##  <a name="getmainwnd"></a>  CWinThread::GetMainWnd  
 アプリケーションが OLE サーバーの場合は、直接参照することではなく、アプリケーションのアクティブなメイン ウィンドウへのポインターを取得するには、この関数を呼び出して、`m_pMainWnd`アプリケーション オブジェクトのメンバーです。  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>戻り値  
 この関数は、windows の 2 種類のいずれかにポインターを返します。 この関数が返すかどうか、スレッドは OLE サーバーの一部であるし、アクティブなコンテナー内の場所で有効になっているオブジェクトが存在し、[先](../../mfc/reference/cwinapp-class.md#m_pactivewnd)のデータ メンバー、`CWinThread`オブジェクト。  
  
 この関数を返します、コンテナー内の場所で有効になっているオブジェクトが存在しないか、アプリケーションが OLE サーバーではない、 [m_pMainWnd](#m_pmainwnd)スレッド オブジェクトのデータ メンバーです。  
  
### <a name="remarks"></a>Remarks  
 ユーザー インターフェイス スレッドでは、これは、直接参照することに相当します`m_pActiveWnd`アプリケーション オブジェクトのメンバーです。  
  
 開発中のアプリケーションが OLE サーバーではない場合は、この関数を呼び出すことは、アプリケーション オブジェクトの `m_pMainWnd` メンバーを直接参照することと同じです。  
  
 既定の動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="getthreadpriority"></a>  CWinThread::GetThreadPriority  
 このスレッドの現在のスレッド優先度レベルを取得します。  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>戻り値  
 優先度クラス内で現在のスレッド優先度レベル。 返される値は、次のいずれかを指定が最も高い優先順位の降順で表示されます。  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- THREAD_PRIORITY_LOWEST  
  
- THREAD_PRIORITY_IDLE  
  
 これらの優先順位の詳細については、次を参照してください。 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) Windows SDK に含まれています。  
  
##  <a name="initinstance"></a>  CWinThread::InitInstance  
 `InitInstance` ユーザー インターフェイス スレッドの新しいインスタンスを初期化するためにオーバーライドする必要があります。  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 通常、オーバーライドする`InitInstance`スレッドが最初に作成したときに完了する必要がありますのあるタスクを実行します。  
  
 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。 制御関数に渡されるでワーカー スレッドの初期化を実行[AfxBeginThread](application-information-and-management.md#afxbeginthread)です。  
  
##  <a name="isidlemessage"></a>  CWinThread::IsIdleMessage  
 保持するには、この関数をオーバーライド`OnIdle`特定のメッセージが生成された後に呼び出されているからです。  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pMsg*  
 処理されている現在のメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`OnIdle`処理後に呼び出す必要がありますメッセージ以外の場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 既定の実装は呼び出しません`OnIdle`冗長なマウス メッセージおよびメッセージのキャレットの点滅によって生成された後にします。  
  
 アプリケーションが短いタイマーを作成した場合`OnIdle`が呼び出される多くの場合、パフォーマンスの問題が発生します。 このようなアプリケーションのパフォーマンスを向上させるのには、オーバーライド`IsIdleMessage`アプリケーションの`CWinApp`-WM_TIMER メッセージを次のようにチェックするクラスを派生します。  
  
 [!code-cpp[NVC_MFCDocView#189](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 この方法で WM_TIMER を処理すると、短いタイマーを使用するアプリケーションのパフォーマンスが向上します。  
  
##  <a name="m_bautodelete"></a>  CWinThread::m_bAutoDelete  
 スレッドの終了時に `CWinThread` オブジェクトを自動的に削除するかどうかを指定します。  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>Remarks  
 `m_bAutoDelete`データ メンバーは BOOL 型のパブリック変数です。  
  
 `m_bAutoDelete` の値は、基になるスレッド ハンドルを閉じる方法に影響しません。 スレッド ハンドルは、`CWinThread` オブジェクトが破棄されるときに必ず閉じられます。  
  
##  <a name="m_hthread"></a>  CWinThread::m_hThread  
 これに接続されているスレッドへのハンドル`CWinThread`です。  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>Remarks  
 `m_hThread`データ メンバーは型ハンドルのパブリック変数です。 基になるスレッドを現在存在する場合にのみ有効です。  
  
##  <a name="m_nthreadid"></a>  CWinThread::m_nThreadID  
 これに接続されているスレッドの ID`CWinThread`です。  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>Remarks  
 `m_nThreadID`データ メンバーは、DWORD 型のパブリック変数です。 基になるスレッドを現在存在する場合にのみ有効です。  
  
### <a name="example"></a>例  
  例を参照して[AfxGetThread](application-information-and-management.md#afxgetthread)です。  
  
##  <a name="m_pactivewnd"></a>  CWinThread::m_pActiveWnd  
 このデータ メンバーを使用すると、スレッドのアクティブなウィンドウのオブジェクトへのポインターを格納できます。  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>Remarks  
 Microsoft Foundation Class ライブラリは自動的に終了スレッドによって参照されるウィンドウ`m_pActiveWnd`が閉じられます。 このスレッドが、プライマリ スレッド アプリケーションのアプリケーションも終了します。 このデータ メンバーが NULL の場合、アプリケーションのアクティブなウィンドウ`CWinApp`オブジェクトが継承されます。 `m_pActiveWnd` 型のパブリック変数`CWnd*`です。  
  
 オーバーライドする場合にこのメンバー変数を設定する通常、`InitInstance`です。 ワーカー スレッドでは、このデータ メンバーの値は親スレッドから継承されます。  
  
##  <a name="m_pmainwnd"></a>  ため  
 このデータ メンバーを使用すると、スレッドのメイン ウィンドウのオブジェクトへのポインターを格納できます。  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>Remarks  
 Microsoft Foundation Class ライブラリは自動的に終了スレッドによって参照されるウィンドウ`m_pMainWnd`が閉じられます。 このスレッドが、プライマリ スレッド アプリケーションのアプリケーションも終了します。 このデータ メンバーが NULL の場合、アプリケーションのメイン ウィンドウ`CWinApp`オブジェクトは、スレッドを終了する場合の判別に使用されます。 `m_pMainWnd` 型のパブリック変数`CWnd*`です。  
  
 オーバーライドする場合にこのメンバー変数を設定する通常、`InitInstance`です。 ワーカー スレッドでは、このデータ メンバーの値は親スレッドから継承されます。  
  
##  <a name="onidle"></a>  CWinThread::OnIdle  
 アイドル処理を実行するには、このメンバー関数をオーバーライドします。  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>パラメーター  
 *lCount*  
 カウンターたびに増分されます`OnIdle`は、スレッドのメッセージ キューが空のときに呼び出されます。 この数は、新しいメッセージが処理されるたびに 0 にリセットされます。 使用することができます、 *lCount*パラメーターをスレッドがアイドル状態になったメッセージを処理することがなく時間の相対的な長さを決定します。  
  
### <a name="return-value"></a>戻り値  
 さらにアイドル処理時間の受信には 0 以外。これ以上アイドル状態の処理時間が必要な場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `OnIdle` スレッドのメッセージ キューが空とき、既定のメッセージ ループで呼び出されます。 これらに上書きを使用して、独自の背景のアイドル処理を呼び出します。  
  
 `OnIdle` 追加のアイドル処理時間が必要ないことを示すために 0 を返す必要があります。 *LCount*パラメーターはたびに増分`OnIdle`は、メッセージ キューが空で、新しいメッセージが処理されるたびに 0 にリセットされるときに呼び出されます。 この数に基づく、別のアイドル処理ルーチンを呼び出すことができます。  
  
 このメンバー関数の既定の実装では、一時オブジェクトやメモリから未使用のダイナミック リンク ライブラリを解放します。  
  
 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。  
  
 アプリケーションがまでメッセージを処理できないため`OnIdle`戻り値は、この関数で時間のかかるタスクを実行しません。  
  
##  <a name="operator_handle"></a>  CWinThread::operator ハンドル  
 ハンドルを取得、`CWinThread`オブジェクト。  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、スレッド オブジェクトのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 Windows Api を直接呼び出すために、ハンドルを使用します。  
  
##  <a name="postthreadmessage"></a>  CWinThread::PostThreadMessage  
 別のユーザー定義メッセージを投稿すると呼ばれる`CWinThread`オブジェクト。  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 *message*  
 ユーザー定義メッセージの ID。  
  
 *wParam*  
 最初のメッセージのパラメーター。  
  
 *lParam*  
 2 番目のメッセージのパラメーター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 投稿されたメッセージは、メッセージ マップ マクロによって適切なメッセージ ハンドラーにマップされます。  
  
> [!NOTE]
>  Windows を呼び出すときに[次](http://msdn.microsoft.com/library/windows/desktop/ms644946)MFC メッセージ ハンドラーが呼び出されないと、MFC アプリケーション内の関数。 詳細については、サポート技術情報の記事「"PRB:: MFC メッセージ ハンドラーされませんと呼ばれるで PostThreadMessage()"(Q142415) を参照してください。  
  
##  <a name="pretranslatemessage"></a>  CWinThread::PreTranslateMessage  
 Windows 関数にディスパッチされる前に、ウィンドウ メッセージをフィルター処理するには、この関数をオーバーライド[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)です。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pMsg*  
 指す、 [MSG 構造体](../../mfc/reference/msg-structure1.md)を処理するメッセージを含むです。  
  
### <a name="return-value"></a>戻り値  
 メッセージで完全に処理された場合は 0 以外`PreTranslateMessage`さらに処理する必要がないとします。 通常の方法で、メッセージを処理する必要がある場合は 0 します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。  
  
##  <a name="processmessagefilter"></a>  CWinThread::ProcessMessageFilter  
 フレームワークのフック関数は、フィルター処理し、特定の Windows メッセージに応答するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *コード*  
 フック コードを指定します。 このメンバー関数では、コードを使用して、処理方法を決定*lpMsg です。*  
  
 *lpMsg*  
 Windows へのポインター [MSG 構造体](../../mfc/reference/msg-structure1.md)です。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 フック関数の処理、アプリケーションの通常のメッセージを送信する前に、イベントを処理します。  
  
 この高度な機能をオーバーライドする場合は、フレームワークを維持するために基本クラスのバージョンを呼び出すことを確認する処理をフックします。  
  
##  <a name="processwndprocexception"></a>  CWinThread::ProcessWndProcException  
 ハンドラーがのスレッドのメッセージまたはコマンド ハンドラーでスローされる例外をキャッチしていないときに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *e*  
 未処理の例外へのポインター。  
  
 *pMsg*  
 指す、 [MSG 構造体](../../mfc/reference/msg-structure1.md)フレームワークが例外をスローする原因となった windows メッセージに関する情報を格納します。  
  
### <a name="return-value"></a>戻り値  
 WM_CREATE 例外が生成される場合は-1それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数を直接呼び出さないでください。  
  
 このメンバー関数の既定の実装では、次のメッセージから生成された例外だけを処理します。  
  
|コマンド|アクション|  
|-------------|------------|  
|WM_CREATE|失敗します。|  
|WM_PAINT|影響を受けるウィンドウで、別の WM_PAINT メッセージが生成されるようにを検証します。|  
  
 グローバルに、例外の処理を提供するには、このメンバー関数をオーバーライドします。 既定の動作を表示する場合にのみ、基本機能を呼び出します。  
  
 このメンバー関数は、メッセージ ポンプが含まれるスレッドでのみ使用されます。  
  
##  <a name="pumpmessage"></a>  CWinThread::PumpMessage  
 スレッドのメッセージ ループが含まれています。  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>Remarks  
 `PumpMessage` スレッドのメッセージ ループが含まれています。 `PumpMessage` によって呼び出される`CWinThread`スレッドのメッセージ ポンプにします。 呼び出すことができます`PumpMessage`を強制的に処理されるメッセージを上書きするか直接`PumpMessage`既定の動作を変更します。  
  
 呼び出す`PumpMessage`直接と高度なユーザーのみに推奨される、既定の動作をオーバーライドします。  
  
##  <a name="resumethread"></a>  Cwinthread::resumethread  
 によって中断されたスレッドの実行を再開すると呼ばれる、 [SuspendThread](#suspendthread)メンバー関数、またはスレッド CREATE_SUSPENDED フラグを作成します。  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>戻り値  
 スレッドが以前の中断カウントが成功した場合`0xFFFFFFFF`それ以外の場合。 戻り値が 0 の場合は、現在のスレッドは中断されません。 戻り値は、1 つは、スレッドが中断されますが、再起動されます。 1 つは、スレッドを超える戻り値は、中断されたままです。  
  
### <a name="remarks"></a>Remarks  
 現在のスレッドの中断カウントは 1 つを減少します。 中断カウントが減少している場合、スレッドが実行を再開には、0それ以外の場合、スレッドは中断されたままです。  
  
##  <a name="run"></a>  CWinThread::Run  
 ユーザー インターフェイス スレッドの既定のメッセージ ループを提供します。  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>戻り値  
 **Int**スレッドによって返される値。 この値を呼び出すことによって取得できる[GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)です。  
  
### <a name="remarks"></a>Remarks  
 `Run` 取得し、アプリケーションが受信するまでは、Windows メッセージをディスパッチする[WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641)メッセージ。 スレッドのメッセージ キューにメッセージがない場合`Run`呼び出し`OnIdle`アイドル処理を実行します。 受信メッセージに移動、 [PreTranslateMessage](#pretranslatemessage)メンバー関数は、特別な処理し、Windows 関数に[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)標準キーボード変換用。 最後に、 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数が呼び出されます。  
  
 `Run` オーバーライドされることはほとんどありませんが、特別な動作を実装するメソッドをオーバーライドすることができます。  
  
 このメンバー関数は、ユーザー インターフェイス スレッドでのみ使用されます。  
  
##  <a name="setthreadpriority"></a>  CWinThread::SetThreadPriority  
 この関数は、現在のスレッドの優先度クラス内での優先度レベルを設定します。  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>パラメーター  
 *nPriority*  
 優先度クラス内で新しいスレッドの優先順位を指定します。 このパラメーターは、最高の優先順位の降順で表示される、次の値のいずれかを指定する必要があります。  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- THREAD_PRIORITY_LOWEST  
  
- THREAD_PRIORITY_IDLE  
  
 これらの優先順位の詳細については、次を参照してください。 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 後にのみ呼び出すことができます[CreateThread](#createthread)が正常に返されます。  
  
##  <a name="suspendthread"></a>  CWinThread::SuspendThread  
 インクリメントを現在のスレッドの数を一時停止します。  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>戻り値  
 スレッドが以前の中断カウントが成功した場合`0xFFFFFFFF`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 任意のスレッドにゼロよりも中断カウントがある場合は、そのスレッドは実行されません。 呼び出してスレッドを再開できる、 [ResumeThread](#resumethread)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)
