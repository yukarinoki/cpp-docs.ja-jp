---
title: アプリケーションの情報と管理
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 9d5216cd399943cda67bc9387ea37c938e5cab48
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694336"
---
# <a name="application-information-and-management"></a>アプリケーションの情報と管理

1 つを作成するアプリケーションを作成するときに[CWinApp](../../mfc/reference/cwinapp-class.md)の派生オブジェクト。 外部からは、このオブジェクトに関する情報を取得する可能性がありますが、 `CWinApp`-派生オブジェクト。 または、他のグローバル「マネージャー」オブジェクトにアクセスする必要があります。

Microsoft Foundation Class ライブラリでは、これらのタスクを達成するために、次のグローバル関数を提供します。

### <a name="application-information-and-management-functions"></a>アプリケーションの情報と管理機能

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|新しいスレッドを作成します。|
|[AfxContextMenuManager](#afxcontextmenumanager)|グローバルへのポインター[コンテキスト メニュー マネージャー](ccontextmenumanager-class.md)します。|
|[AfxEndThread](#afxendthread)|現在のスレッドを終了します。|
|[AfxFindResourceHandle](#afxfindresourcehandle)|リソース チェーンを説明し、特定のリソースのリソース ID とリソースの種類を見つけます。 |
|[AfxFreeLibrary](#afxfreelibrary)|ダイナミック リンク ライブラリ (DLL) が読み込まれたモジュールの参照カウントをデクリメント参照カウントがゼロに達すると、モジュールはマップではありません。|
|[AfxGetApp](#afxgetapp)|アプリケーションへのポインターの 1 つを返します`CWinApp`オブジェクト。|
|[AfxGetAppName](#afxgetappname)|アプリケーションの名前を含む文字列を返します。|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|アプリケーションのこのインスタンスを表す HINSTANCE を返します。|
|[AfxGetMainWnd](#afxgetmainwnd)|非 OLE アプリケーションの現在の"main"ウィンドウまたはサーバー アプリケーションの埋め込み先フレーム ウィンドウへのポインターを返します。|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|この関数を使用して、アプリケーションがレジストリ アクセスにリダイレクトするかどうかを判断する、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。|
|[AfxGetResourceHandle](#afxgetresourcehandle)|アプリケーションの既定のリソースのソースに HINSTANCE を返します。 アプリケーションのリソースに直接アクセスするのにには、これを使用します。|
|[AfxGetThread](#afxgetthread)|現在のポインターを取得[CWinThread](../../mfc/reference/cwinthread-class.md)オブジェクト。|
|[AfxInitRichEdit](#afxinitrichedit)|1.0 リッチ エディット コントロール、アプリケーションのバージョンを初期化します。|
|[AfxInitRichEdit2](#afxinitrichedit2)|バージョン 2.0 以降の豊富な編集アプリケーションのコントロールを初期化します。|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。|
|[AfxIsMFCToolBar](#afxismfctoolbar)|指定されたウィンドウがツール バー オブジェクトであるかどうかを判断します。|
|[AfxKeyboardManager](#afxkeyboardmanager)|グローバルへのポインター[キーボード manager](ckeyboardmanager-class.md)します。|
|[AfxLoadLibrary](#afxloadlibrary)|DLL モジュールをマップし、DLL 関数のアドレスを取得するために使用できるハンドルを返します。|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|グローバルへのポインター[ティアオフ メニュー マネージャー](cmenutearoffmanager-class.md)します。|
|[AfxMouseManager](#afxmousemanager)|グローバルへのポインター[マウス manager](cmousemanager-class.md)します。|
|[AfxRegisterClass](#afxregisterclass)|MFC を使用する DLL には、ウィンドウ クラスを登録します。|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC によって自動的に登録されている設定を補足する Windows のウィンドウ クラスを登録します。|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|アプリケーションにレジストリのアクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。|
|[AfxSetResourceHandle](#afxsetresourcehandle)|アプリケーションの既定のリソースが読み込まれる HINSTANCE ハンドルを設定します。|
|[AfxShellManager](#afxshellmanager)|グローバルへのポインター[シェル マネージャー](cshellmanager-class.md)します。 |
|[AfxSocketInit](#afxsocketinit)|呼び出される、 `CWinApp::InitInstance` Windows Sockets を初期化するためにオーバーライドします。|
|[AfxUserToolsManager](#afxusertoolsmanager)|グローバルへのポインター[ユーザー ツール マネージャー](cusertoolsmanager-class.md)します。|
|[AfxWinInit](#afxwininit)|MFC が指定したメソッドを呼び出して`WinMain`の一部として、関数、 [CWinApp](../../mfc/reference/cwinapp-class.md) MFC を初期化するために、GUI ベースのアプリケーションの初期化。 MFC を使用するコンソール アプリケーションを直接呼び出す必要があります。|

##  <a name="afxbeginthread"></a>  AfxBeginThread

この関数を呼び出して、新しいスレッドを作成します。

```
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,
    LPVOID pParam,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,
    int nPriority = THREAD_PRIORITY_NORMAL,
    UINT nStackSize = 0,
    DWORD dwCreateFlags = 0,
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```

### <a name="parameters"></a>パラメーター

*pfnThreadProc*<br/>
ワーカー スレッドの制御関数をポイントします。 Nll は指定できません。 この関数は次のように宣言する必要があります。

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*<br/>
派生したオブジェクトの RUNTIME_CLASS [CWinThread](../../mfc/reference/cwinthread-class.md)します。

*pParam*<br/>
内の関数宣言のパラメーターで示すように、制御関数に渡されるパラメーター *pfnThreadProc*します。

*nPriority*<br/>
スレッドの優先順位。 完全な一覧と使用可能な優先順位の説明では、次を参照してください。 [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK に含まれています。

*nStackSize*<br/>
新しいスレッドへのスタックのバイト サイズを指定します。 0 である場合、スタック サイズの既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。

*dwCreateFlags*<br/>
スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。

- CREATE_SUSPENDED 中断カウントが 1 つのスレッドを開始します。 メンバー データの初期化に使用する場合は、CREATE_SUSPENDED を使用して、`CWinThread`などオブジェクト[m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete)またはスレッドが実行を開始する前に、派生クラスのメンバー。 初期化が完了すると使用[cwinthread::resumethread](../../mfc/reference/cwinthread-class.md#resumethread)を実行しているスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。

- **0**作成後すぐにスレッドを開始します。

*lpSecurityAttrs*<br/>
指す、 [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560)スレッドのセキュリティ属性を指定する構造体。 NULL の場合、スレッドの作成と同じセキュリティ属性が使用されます。 この構造体の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

新しく作成されたスレッド オブジェクト、または障害が発生した場合は NULL へのポインター。

### <a name="remarks"></a>Remarks

`AfxBeginThread` の最初のフォームはワーカー スレッドを作成します。 2 番目のフォームは、ユーザー インターフェイス スレッドまたはワーカー スレッドとして機能可能なスレッドを作成します。

`AfxBeginThread` 新たに作成`CWinThread`オブジェクトを呼び出し、 [CreateThread](../../mfc/reference/cwinthread-class.md#createthread)関数のスレッドの実行を開始して、スレッドへのポインターを返します。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。 スレッドを終了するには、呼び出す[AfxEndThread](#afxendthread)からスレッドまたはワーカー スレッドの制御関数からの戻り値内で。

マルチスレッドは、アプリケーションによって有効化される必要があります。それ以外の場合、この関数は失敗します。 マルチ スレッドの有効化の詳細についてを参照してください[/MD、/MT、/LD (ランタイム ライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)  *Visual C コンパイラ オプション*します。

詳細については`AfxBeginThread`、記事を参照して[マルチ スレッド: ワーカー スレッドの作成](../../parallel/multithreading-creating-worker-threads.md)と[マルチ スレッド: ユーザー インターフェイス スレッドの生成](../../parallel/multithreading-creating-user-interface-threads.md)します。

### <a name="example"></a>例

例をご覧ください[csocket::attach](../../mfc/reference/csocket-class.md#attach)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxcontextmenumanager"></a> AfxContextMenuManager

グローバルへのポインター[コンテキスト メニュー マネージャー](ccontextmenumanager-class.md)します。

### <a name="syntax"></a>構文

```
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxcontextmenumanager.h

### <a name="see-also"></a>関連項目

[CContextMenuManager クラス](ccontextmenumanager-class.md)

##  <a name="afxendthread"></a>  AfxEndThread

現在実行中のスレッドを終了するには、この関数を呼び出します。

```
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>パラメーター

*nExitCode*<br/>
スレッドの終了コードを指定します。

*bDelete*<br/>
メモリからスレッド オブジェクトを削除します。

### <a name="remarks"></a>Remarks

終了するスレッド内からを呼び出す必要があります。

詳細については`AfxEndThread`、記事をご覧ください[マルチ スレッド: スレッドの終了](../../parallel/multithreading-terminating-threads.md)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
使用`AfxFindResourceHandle`リソース チェーンをウォークして特定のリソースでリソース ID とリソースの種類を見つけます。

### <a name="syntax"></a>構文

```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
リソース ID を含む文字列へのポインター
*lpszType*<br/>
リソースの種類へのポインター。 リソースの種類の一覧は、次を参照してください。 [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

リソースを含むモジュールへのハンドル。

### <a name="remarks"></a>Remarks

`AfxFindResourceHandle` 特定のリソースを検索してリソースを格納しているモジュールへのハンドルを返します。 リソースの MFC 拡張 DLL が読み込まれました可能性があります。 `AfxFindResourceHandle` どれがリソースを示します。

この順序で、モジュールが検索されます。

1. (MFC 拡張 DLL の場合) は、メイン モジュールです。

1. 非システム モジュールです。

1. 言語固有のモジュール。

1. (システム DLL の場合) は、メイン モジュールです。

1. システム モジュールです。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

### <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)

##  <a name="afxfreelibrary"></a>  AfxFreeLibrary

両方`AfxFreeLibrary`と`AfxLoadLibrary`ライブラリが読み込まれたモジュールごとに参照カウントを維持します。

```
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>パラメーター

*hInstLib*<br/>
ライブラリが読み込まれたモジュールのハンドル。 [AfxLoadLibrary](#afxloadlibrary)このハンドルを返します。

### <a name="return-value"></a>戻り値

関数が成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

`AfxFreeLibrary` ダイナミック リンク ライブラリ (DLL) が読み込まれたモジュールの参照カウントをデクリメントします。 参照カウントがゼロに達するし、モジュールは、呼び出し元プロセスのアドレス空間からマップされたが、ハンドルが無効になった。 この参照カウントは毎回`AfxLoadLibrary`が呼び出されます。

ライブラリ モジュールを解除する前に、システムは、これを使用するプロセスからデタッチする DLL を使用できます。 DLL を現在のプロセスに割り当てられたリソースをクリーンアップする機会が与えられますそうです。 エントリ ポイント関数を返した後、ライブラリ モジュールは、現在のプロセスのアドレス空間から削除されます。

使用`AfxLoadLibrary`DLL モジュールをマップします。

使用して、必ず`AfxFreeLibrary`と`AfxLoadLibrary`(Win32 関数ではなく`FreeLibrary`と`LoadLibrary`) アプリケーションが複数のスレッドを使用する場合。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`スタートアップとシャット ダウン コード MFC 拡張 DLL が読み込まれ、アンロードが MFC のグローバル状態を破損しないときに実行されることを確認します。

### <a name="example"></a>例

例をご覧ください[AfxLoadLibrary](#afxloadlibrary)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_.h

##  <a name="afxgetapp"></a>  AfxGetApp

この関数によって返されるポインターを使用して、メッセージのディスパッチのメイン コードや最上位ウィンドウなどのアプリケーションの情報にアクセスすることができます。

```
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>戻り値

1 つへのポインター`CWinApp`アプリケーションのオブジェクト。

### <a name="remarks"></a>Remarks

このメソッドは、NULL を返す場合、アプリケーションのメイン ウィンドウが完全にまだ初期化されていないことを示す場合します。 また、問題を示す場合もあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetappname"></a>  AfxGetAppName

この関数によって返される文字列は、一時文字列の名前の診断メッセージ、またはルートとして使用できます。

```
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>戻り値

アプリケーションの名前を表す、null で終わる文字列。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetinstancehandle"></a>  AfxGetInstanceHandle

この関数では、現在のアプリケーションのインスタンス ハンドルを取得できます。

```
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>戻り値

アプリケーションの現在のインスタンスの HINSTANCE。 MFC の USRDLL バージョンとリンクされた DLL 内から呼び出されると、DLL に HINSTANCE が返されます。

### <a name="remarks"></a>Remarks

`AfxGetInstanceHandle` 実行可能ファイルの HINSTANCE を常に返します (します。EXE) DLL が MFC の USRDLL バージョンとリンク内から呼び出された場合を除き、します。 この場合、DLL に HINSTANCE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetmainwnd"></a>  AfxGetMainWnd

アプリケーションが OLE サーバーである場合は、直接参照するのではなく、アプリケーションのアクティブなメイン ウィンドウへのポインターを取得するには、この関数を呼び出し、 [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd)アプリケーション オブジェクトのメンバー。

```
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>戻り値

サーバーが、コンテナー内に埋め込まれているアクティブなオブジェクトを持ち、そのコンテナーがアクティブである場合は、この関数は、埋め込まれているアクティブな文書を含むフレーム ウィンドウ オブジェクトへのポインターを返します。

この関数は単に返します、コンテナー内の場所で有効になっているオブジェクトが存在しないか、アプリケーションが OLE サーバーではない、 *m_pMainWnd*アプリケーション オブジェクト。

`AfxGetMainWnd` をアプリケーションのプライマリ スレッドから呼び出した場合は、上記の規則に従ってアプリケーションのメイン ウィンドウを返します。 アプリケーションのセカンダリ スレッドからこの関数を呼び出した場合は、関数は呼び出しを行ったスレッドに関連付けられているメイン ウィンドウを返します。

### <a name="remarks"></a>Remarks

アプリケーションが OLE サーバーではないかどうかは、直接参照するにはこの関数を呼び出す、 *m_pMainWnd*アプリケーション オブジェクトのメンバー。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetperuserregistration"></a>  AfxGetPerUserRegistration

この関数を使用して、アプリケーションがレジストリ アクセスにリダイレクトするかどうかを判断する、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。

```
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>戻り値

TRUE は、HKCU ノードにレジストリ情報が送られることを示しますFALSE は、アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードが**HKEY_CLASSES_ROOT** ( **HKCR**)。

### <a name="remarks"></a>Remarks

レジストリのリダイレクトを有効にすると、フレームワークはからのアクセスをリダイレクト**HKCR**に**する**します。 MFC と ATL のフレームワークは、リダイレクトの影響を受けます。

アプリケーションは、レジストリへのアクセスをリダイレクトするかどうかを変更する[AfxSetPerUserRegistration](#afxsetperuserregistration)します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxstat_.h

##  <a name="afxgetresourcehandle"></a>  AfxGetResourceHandle

Windows の呼び出しで関数の例を使用して、HINSTANCE 処理アプリケーションのリソースに直接アクセスするには、この関数によって返される`FindResource`します。

```
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>戻り値

アプリケーションの既定のリソースが読み込まれる HINSTANCE ハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetthread"></a>  AfxGetThread

ポインターを取得するには、この関数を呼び出して、 [CWinThread](../../mfc/reference/cwinthread-class.md)現在実行中のスレッドを表すオブジェクト。

```
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>戻り値

実行中のスレッドへのポインターそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

目的のスレッド内からを呼び出す必要があります。

> [!NOTE]
>  MFC プロジェクトの呼び出し元を移植する場合`AfxGetThread`4.2、5.0、または 6.0 では、Visual C バージョンから`AfxGetThread`呼び出し[AfxGetApp](#afxgetapp)スレッドが存在しない場合。 新しいバージョンのコンパイラで`AfxGetThread`スレッドが見つからなかった場合は NULL を返します。 呼び出す必要があるアプリケーションのスレッドを実行する場合に、`AfxGetApp`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxinitrichedit"></a>  AfxInitRichEdit

アプリケーションのリッチ エディット コントロール (バージョン 1.0) を初期化するには、この関数を呼び出します。

```
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Remarks

この関数は、旧バージョンとの互換性のために提供されます。 新しいアプリケーションを使用する必要があります[AfxInitRichEdit2](#afxinitrichedit2)します。

`AfxInitRichEdit` RICHED32 を読み込みます。リッチ エディット コントロールのバージョン 1.0 を初期化する DLL です。 バージョン 2.0 と 3.0 のリッチ エディット コントロール、RICHED20 を使用します。DLL を読み込む必要があります。 呼び出しでこれを行う[AfxInitRichEdit2](#afxinitrichedit2)します。

既存の Visual C アプリケーションをバージョン 2.0 でリッチ エディット コントロールを更新するを開き、します。RC ファイル、テキストとしてでは、"RichEdit20a"を"RICHEDIT"から各リッチ エディット コントロールのクラス名を変更します。 呼び出しを置き換える`AfxInitRichEdit`で`AfxInitRichEdit2`します。

この関数は、ライブラリは、プロセスにまだ初期化されていない場合にも、一般的なコントロール ライブラリを初期化します。 リッチ エディット コントロールを MFC アプリケーションから直接使用する場合は、MFC がリッチ エディット コントロールのランタイムを正しく初期化されるようにするのには、この関数を呼び出す必要があります。 Create メソッドを呼び出す場合[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)、する通常、この関数を呼び出す必要はありませんが、場合によってはでがありますいる。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxinitrichedit2"></a>  AfxInitRichEdit2

アプリケーションのリッチ エディット コントロール (バージョン 2.0 以降) を初期化するには、この関数を呼び出します。

```
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Remarks

RICHED20 を読み込むには、この関数を呼び出します。DLL と初期化バージョン 2.0 の豊富なコントロールを編集します。 Create メソッドを呼び出す場合[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)、する通常、この関数を呼び出す必要はありませんが、場合によってはでがありますいる。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

  ## <a name="afxisextendedframeclass"></a>  AfxIsExtendedFrameClass
指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]派生したオブジェクトへのポインター`CWnd`します。

### <a name="return-value"></a>戻り値

指定されたウィンドウが拡張フレーム オブジェクトは、TRUE を返します。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、場合に TRUE を返します*我が物*クラスを次のいずれかから派生します。

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

このメソッドは、関数またはメソッドのパラメーターが拡張フレーム ウィンドウであるかどうかを検証する必要があるときに役立ちます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

### <a name="see-also"></a>関連項目

[CWnd クラス](cwnd-class.md)<br/>
[CFrameWndEx クラス](cframewndex-class.md)

## <a name="afxismfctoolbar"></a> AfxIsMFCToolBar

指定されたウィンドウがツール バー オブジェクトであるかどうかを判断します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]派生したオブジェクトへのポインター`CWnd`します。

### <a name="return-value"></a>戻り値

指定されたウィンドウは、ツールバーのオブジェクトは、TRUE を返します。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

このメソッドが戻る`TRUE`場合*我が物*から派生した`CMFCToolBar`します。 このメソッドは関数またはメソッドのパラメーターがあることを検証するときに、`CMFCToolBar`オブジェクト。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

### <a name="see-also"></a>関連項目

[CWnd クラス](cwnd-class.md)<br/>
[CMFCToolBar クラス](cmfctoolbar-class.md)

## <a name="afxkeyboardmanager"></a> AfxKeyboardManager

グローバルへのポインター[キーボード manager](ckeyboardmanager-class.md)します。

### <a name="syntax"></a>構文

```
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxkeyboardmanager.h

### <a name="see-also"></a>関連項目

[マクロ、グローバル関数、およびグローバル変数](mfc-macros-and-globals.md)<br/>
[CKeyboardManager クラス](ckeyboardmanager-class.md)

##  <a name="afxloadlibrary"></a>  AfxLoadLibrary

使用`AfxLoadLibrary`DLL モジュールをマップします。

```
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>パラメーター

*lpszModuleName*<br/>
モジュールの名前を含む null で終わる文字列の指す (いずれかをします。DLL またはします。EXE ファイルの場合)。 指定した名前は、モジュールのファイル名です。

文字列のパスを指定するファイルが指定されたディレクトリに存在しない場合は、関数は失敗します。

パスが指定されていないと、ファイル名拡張子を省略した場合、既定の拡張機能。DLL が追加されます。 ただし、ファイル名の文字列では、モジュール名に拡張機能がないことを示す後続のポイント文字 (.) を含めることができます。 パスが指定されていない場合、関数は、次の順序でファイルを検索します。

- アプリケーションの読み込み元のディレクトリ。

- 現在のフォルダー。

- **Windows 95/98:** Windows システム ディレクトリ。 **Windows NT:** 32 ビット Windows システム ディレクトリ。 このディレクトリの名前は、SYSTEM32 です。

- **Windows NT のみ:** 16 ビット Windows システム ディレクトリ。 このディレクトリのパスを取得する Win32 関数はありませんが、これが検索されます。 このディレクトリの名前は、システムです。

- Windows ディレクトリ。

- PATH 環境変数に記載されているディレクトリ。

### <a name="return-value"></a>戻り値

関数が成功した場合は、モジュールへのハンドルを返します。 関数が失敗した場合、戻り値は NULL です。

### <a name="remarks"></a>Remarks

使用できるハンドルを返します[GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL 関数のアドレスを取得します。 `AfxLoadLibrary` その他の実行可能モジュールにマップすることも使用できます。

各プロセスは、各ライブラリが読み込まれたモジュールの参照カウントを保持します。 この参照カウントは毎回`AfxLoadLibrary`と呼びます。 毎回デクリメントされる`AfxFreeLibrary`が呼び出されます。 参照カウントがゼロに達するし、モジュールは、呼び出し元プロセスのアドレス空間からマップされたが、ハンドルが無効になった。

使用して、必ず`AfxLoadLibrary`と`AfxFreeLibrary`(Win32 関数ではなく`LoadLibrary`と`FreeLibrary`) MFC 拡張 DLL を動的に読み込む場合と、アプリケーションが複数のスレッドを使用している場合。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`MFC 拡張 DLL が読み込まれ、アンロードされたときに実行されるスタートアップとシャット ダウン コードが MFC のグローバル状態を破損しないことを保証します。

使用して`AfxLoadLibrary`アプリケーションでは MFC の DLL バージョンに動的にリンクすることが必要です。 のヘッダー ファイル`AfxLoadLibrary`、Afxdll_.h、は、MFC が DLL としてのアプリケーションにリンクされている場合に含まれます。 これは、使用または MFC 拡張 Dll を作成する MFC の DLL バージョンにリンクする必要があるため、設計します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_.h

## <a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager

グローバルへのポインター[ティアオフ メニュー マネージャー](cmenutearoffmanager-class.md)します。

### <a name="syntax"></a>構文

```
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmenutearoffmanager.h

### <a name="see-also"></a>関連項目

[CMenuTearOffManager クラス](cmenutearoffmanager-class.md)

## <a name="afxmousemanager"></a>  AfxMouseManager

グローバルへのポインター[マウス manager](cmousemanager-class.md)します。

### <a name="syntax"></a>構文

```
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmousemanager.h

### <a name="see-also"></a>関連項目

[CMouseManager クラス](cmousemanager-class.md)

##  <a name="afxregisterclass"></a>  AfxRegisterClass

この関数を使用して、MFC を使用する DLL にウィンドウ クラスを登録します。

```
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>パラメーター

*lpWndClass*<br/>
ポインターを[WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa)登録されるウィンドウ クラスに関する情報を含む構造体。 この構造体の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

TRUE の場合、クラスが正常に登録します。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

この関数を使用する場合、クラスは自動的に登録された DLL がアンロードされるときです。

非 DLL のビルドでは、`AfxRegisterClass`識別子が Windows 関数にマップするマクロとして定義されている`RegisterClass`アプリケーションに登録されているクラスは、自動的に登録されているため、します。 使用する場合`AfxRegisterClass`の代わりに`RegisterClass`アプリケーションと DLL の両方を変更せずに、コードを使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxregisterwndclass"></a>  AfxRegisterWndClass

独自のウィンドウ クラスを登録することができます。

```
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>パラメーター

*nClassStyle*<br/>
Windows クラスのスタイルまたはビットごとの OR を使用して作成されたスタイルの組み合わせを指定します ( **&#124;**) ウィンドウ クラスの演算子。 クラスのスタイルの一覧は、次を参照してください。、 [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) Windows SDK の構造体。 NULL の場合、既定値としては、次のように設定されます。

- CS_DBLCLKS、送信メッセージをダブルクリックしてウィンドウ プロシージャ、ユーザーがマウスをダブルクリックしたときにマウスのスタイルを設定します。

- Windows 標準 IDC_ARROW 矢印カーソル スタイルに設定します。

- ウィンドウはその背景を消去されませんので、NULL に背景ブラシを設定します。

- 標準的な手を振るフラグの Windows ロゴのアイコン、アイコンに設定します。

*hCursor*<br/>
ウィンドウ クラスから作成された各ウィンドウにインストールする、カーソルのリソースを識別するハンドルを指定します。 既定値を使用する場合**0**、標準の IDC_ARROW カーソルが表示されます。

*hbrBackground*<br/>
ウィンドウ クラスから作成された各ウィンドウにインストールする、ブラシ リソースを識別するハンドルを指定します。 既定値を使用する場合**0**NULL 背景のブラシを必要があります、ウィンドウは、既定では消去されません、バック グラウンド処理中に、 [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd)します。

*hIcon*<br/>
ウィンドウ クラスから作成された各ウィンドウにインストールする、アイコン リソースを識別するハンドルを指定します。 既定値を使用する場合**0**、標準的な手を振るフラグの Windows ロゴのアイコンが表示されます。

### <a name="return-value"></a>戻り値

クラス名を含む null で終わる文字列。 このクラス名を渡すことができます、`Create`メンバー関数で`CWnd`またはその他の**CWnd-** ウィンドウを作成するクラスを派生します。 名前は、Microsoft Foundation Class ライブラリによって生成されます。

> [!NOTE]
>  戻り値は、静的バッファーへのポインターです。 この文字列を保存するには、それを割り当てる、`CString`変数。

### <a name="remarks"></a>Remarks

Microsoft Foundation Class ライブラリでは、いくつかの標準のウィンドウ クラスが自動的に登録します。 独自のウィンドウ クラスを登録する場合は、この関数を呼び出します。

クラスの名前が登録されている`AfxRegisterWndClass`パラメーターにのみ依存します。 呼び出す場合`AfxRegisterWndClass`複数回と同じパラメーターを持つことのみクラスを登録する最初の呼び出しで。 後続の呼び出し`AfxRegisterWndClass`と同じパラメーターを持つ登録済みのクラス名を返すだけです。

呼び出す場合`AfxRegisterWndClass`クラスごとに別のウィンドウ クラスを取得する代わりに、同じパラメーターを持つ複数の CWnd から派生したクラスの各クラスは、同じウィンドウ クラスを共有します。 これは CS_CLASSDC クラスのスタイルを使用する場合、問題が発生することができます。 複数の CS_CLASSDC ウィンドウ クラスではなく最終的に CS_CLASSDC ウィンドウ クラスの 1 つ、さらにそのクラスの共有と同じドメイン コント ローラーを使用して、すべての C++ windows。 この問題を回避するには、呼び出す[AfxRegisterClass](#afxregisterclass)クラスを登録します。

テクニカル ノートを参照してください[TN001: ウィンドウ クラスの登録](../../mfc/tn001-window-class-registration.md)ウィンドウ クラスの登録の詳細については、`AfxRegisterWndClass`関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxsetperuserregistration"></a>  AfxSetPerUserRegistration

アプリケーションにレジストリのアクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** ( **HKCU**) ノードです。

```
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
[in]TRUE は、HKCU ノードにレジストリ情報が送られることを示しますFALSE は、アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードが**HKEY_CLASSES_ROOT** ( **HKCR**)。

### <a name="remarks"></a>Remarks

Windows Vista では、通常使用されるレジストリにアクセスするアプリケーションの前に、 **HKEY_CLASSES_ROOT**ノード。 ただし、Windows Vista またはそれ以降のオペレーティング システムでは、HKCR への書き込みに管理者特権モードでアプリケーションを実行する必要があります。

このメソッドは、読み取りし、書き込みを HKCU、HKCR からレジストリ アクセスをリダイレクトすることにより、管理者特権モードで実行することがなく、レジストリにアプリケーションを使用します。 詳細については、「 [Linker Property Pages](../../ide/linker-property-pages.md)」を参照してください。

フレームワークが HKCR へのアクセスをリダイレクトするレジストリのリダイレクトを有効にした場合**する**します。 MFC と ATL のフレームワークは、リダイレクトの影響を受けます。

既定の実装では、HKCR の下のレジストリにアクセスします。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxstat_.h

##  <a name="afxsetresourcehandle"></a>  AfxSetResourceHandle

この関数を使用すると、アプリケーションの既定のリソースが読み込まれるを決定する HINSTANCE ハンドルを設定できます。

```
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>パラメーター

*hInstResource*<br/>
インスタンスまたはモジュールを識別するハンドルをします。アプリケーションのリソースの読み込み元の EXE または DLL ファイルです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxshellmanager"></a>  AfxShellManager

グローバルへのポインター[シェル マネージャー](cshellmanager-class.md)します。

### <a name="syntax"></a>構文

```
CShellManager* afxShellManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxshellmanager.h

### <a name="see-also"></a>関連項目

[CShellManager クラス](cshellmanager-class.md)

##  <a name="afxsocketinit"></a>  AfxSocketInit

この関数を呼び出して、 `CWinApp::InitInstance` Windows Sockets を初期化するためにオーバーライドします。

```
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>パラメーター

*lpwsaData*<br/>
ポインターを[WSADATA](../../mfc/reference/wsadata-structure.md)構造体。 場合*lpwsaData*が null の場合、次のアドレスと等しく、`WSADATA`構造はへの呼び出しで塗りつぶされます`WSAStartup`します。 この関数も確実に`WSACleanup`アプリケーションが終了する前が呼び出されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

静的にリンクされた MFC アプリケーションでセカンダリ スレッドで MFC ソケットを使用する場合を呼び出す必要があります`AfxSocketInit`ソケット ライブラリを初期化するためにソケットを使用する各スレッドにします。 既定では、`AfxSocketInit`は、プライマリ スレッドでのみ呼び出されます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxsock.h

## <a name="afxusertoolsmanager"></a>  AfxUserToolsManager

グローバルへのポインター[ユーザー ツール マネージャー](cusertoolsmanager-class.md)します。

### <a name="syntax"></a>構文

```
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxusertoolsmanager.h

### <a name="see-also"></a>関連項目

[CUserToolsManager クラス](cusertoolsmanager-class.md)

##  <a name="afxwininit"></a>  AfxWinInit

この関数は MFC 指定によって呼び出されます`WinMain`の一部として、関数、 [CWinApp](../../mfc/reference/cwinapp-class.md) MFC を初期化するために、GUI ベースのアプリケーションの初期化。

```
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>パラメーター

*hInstance*<br/>
現在実行中のモジュールのハンドル。

*hPrevInstance*<br/>
アプリケーションの以前のインスタンスへのハンドル。 Win32 ベースのアプリケーションでは、このパラメーターは常に**NULL**します。

*lpCmdLine*<br/>
アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。

*nCmdShow*<br/>
GUI アプリケーションのメイン ウィンドウの表示方法を指定します。

### <a name="remarks"></a>Remarks

コンソール アプリケーションでは、これを使用しません MFC が指定した`WinMain`関数を呼び出す必要があります`AfxWinInit`MFC を初期化するために直接します。

呼び出す場合`AfxWinInit`のインスタンスを宣言、自分で、`CWinApp`クラス。 コンソール アプリケーションの場合からクラスを派生が選択した可能性があります`CWinApp`のインスタンスを使用して、代わりに、`CWinApp`直接します。 この手法は、アプリケーションのすべての機能の実装のままにする場合に適切な**メイン**します。

> [!NOTE]
>  アセンブリのアクティベーション コンテキストを作成するとき、MFC はユーザー モジュールによって得られるマニフェスト リソースを使用します。 アクティブ化コンテキストが作成された`AfxWinInit`します。 詳細については、次を参照してください。[の MFC モジュール状態でアクティブ化コンテキストのサポート](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CWinApp クラス](../../mfc/reference/cwinapp-class.md)
