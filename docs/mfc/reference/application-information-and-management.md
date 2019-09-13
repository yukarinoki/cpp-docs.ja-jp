---
title: アプリケーションの情報と管理
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 52e6dbaa07fa8343a07533f071d538d9f76b0f61
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741160"
---
# <a name="application-information-and-management"></a>アプリケーションの情報と管理

アプリケーションを作成するときは、1つの[CWinApp](../../mfc/reference/cwinapp-class.md)派生オブジェクトを作成します。 場合によっては、から派生したオブジェクトの`CWinApp`外部から、このオブジェクトに関する情報を取得する必要があります。 または、他のグローバル "mananger" オブジェクトへのアクセスが必要になる場合があります。

Microsoft Foundation Class ライブラリには、これらのタスクを実行するための次のグローバル関数が用意されています。

### <a name="application-information-and-management-functions"></a>アプリケーションの情報と管理の機能

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|新しいスレッドを作成します。|
|[AfxContextMenuManager](#afxcontextmenumanager)|グローバル[コンテキストメニューマネージャー](ccontextmenumanager-class.md)へのポインター。|
|[AfxEndThread](#afxendthread)|現在のスレッドを終了します。|
|[AfxFindResourceHandle](#afxfindresourcehandle)|リソースチェーンを調べ、リソース ID とリソースの種類を指定して特定のリソースを検索します。 |
|[AfxFreeLibrary](#afxfreelibrary)|読み込まれたダイナミックリンクライブラリ (DLL) モジュールの参照カウントをデクリメントします。参照カウントが0になると、モジュールはマップ解除されます。|
|[AfxGetApp](#afxgetapp)|アプリケーションの1つ`CWinApp`のオブジェクトへのポインターを返します。|
|[AfxGetAppName](#afxgetappname)|アプリケーションの名前を含む文字列を返します。|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|アプリケーションのこのインスタンスを表す HINSTANCE を返します。|
|[AfxGetMainWnd](#afxgetmainwnd)|非 OLE アプリケーションの現在の "main" ウィンドウ、またはサーバーアプリケーションの埋め込み先フレームウィンドウへのポインターを返します。|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|アプリケーションが**HKEY_CURRENT_USER** ( **HKCU**) ノードへのレジストリアクセスをリダイレクトするかどうかを判断するには、この関数を使用します。|
|[AfxGetResourceHandle](#afxgetresourcehandle)|アプリケーションの既定のリソースのソースに HINSTANCE を返します。 アプリケーションのリソースに直接アクセスするには、これを使用します。|
|[AfxGetThread](#afxgetthread)|現在の[CWinThread](../../mfc/reference/cwinthread-class.md)オブジェクトへのポインターを取得します。|
|[AfxInitRichEdit](#afxinitrichedit)|アプリケーションのバージョン1.0 リッチエディットコントロールを初期化します。|
|[AfxInitRichEdit2](#afxinitrichedit2)|アプリケーションのバージョン2.0 以降のリッチエディットコントロールを初期化します。|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。|
|[AfxIsMFCToolBar](#afxismfctoolbar)|指定されたウィンドウがツールバーオブジェクトであるかどうかを判断します。|
|[AfxKeyboardManager](#afxkeyboardmanager)|グローバル[キーボードマネージャー](ckeyboardmanager-class.md)へのポインター。|
|[AfxLoadLibrary](#afxloadlibrary)|DLL モジュールをマップし、DLL 関数のアドレスを取得するために使用できるハンドルを返します。|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|グローバル[ティアオフメニューマネージャー](cmenutearoffmanager-class.md)へのポインター。|
|[AfxMouseManager](#afxmousemanager)|グローバル[マウスマネージャー](cmousemanager-class.md)へのポインター。|
|[AfxRegisterClass](#afxregisterclass)|MFC を使用する DLL にウィンドウクラスを登録します。|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC によって自動的に登録されたものを補うために、Windows のウィンドウクラスを登録します。|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|アプリケーションが**HKEY_CURRENT_USER** ( **HKCU**) ノードへのレジストリアクセスをリダイレクトするかどうかを設定します。|
|[AfxSetResourceHandle](#afxsetresourcehandle)|アプリケーションの既定のリソースが読み込まれる HINSTANCE ハンドルを設定します。|
|[AfxShellManager](#afxshellmanager)|グローバル[シェルマネージャー](cshellmanager-class.md)へのポインター。 |
|[AfxSocketInit](#afxsocketinit)|Windows ソケットを`CWinApp::InitInstance`初期化するために、オーバーライドで呼び出されます。|
|[AfxUserToolsManager](#afxusertoolsmanager)|グローバル[ユーザーツールマネージャー](cusertoolsmanager-class.md)へのポインター。|
|[AfxWinInit](#afxwininit)|Mfc を初期化するために`WinMain` 、GUI ベースのアプリケーションの[CWinApp](../../mfc/reference/cwinapp-class.md)初期化の一部として、mfc が提供する関数によって呼び出されます。 MFC を使用するコンソールアプリケーションでは、を直接呼び出す必要があります。|

##  <a name="afxbeginthread"></a>AfxBeginThread

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
[CWinThread](../../mfc/reference/cwinthread-class.md)から派生したオブジェクトの RUNTIME_CLASS。

*pParam*<br/>
*PfnThreadProc*の関数宣言のパラメーターに示されているように、制御関数に渡されるパラメーター。

*nPriority*<br/>
スレッドの優先順位。 使用可能な優先順位の完全な一覧と説明については、Windows SDK の「 [Setthreadpriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 」を参照してください。

*nStackSize*<br/>
新しいスレッドへのスタックのバイト サイズを指定します。 0 である場合、スタック サイズの既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。

*dwCreateFlags*<br/>
スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。

- CREATE_SUSPENDED は、中断回数が1のスレッドを開始します。 スレッドが実行を開始する前に、 [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete)や派生`CWinThread`クラスのメンバーなど、オブジェクトのメンバーデータを初期化する場合は、CREATE_SUSPENDED を使用します。 初期化が完了したら、 [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread)を使用して、実行中のスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。

- **0**作成直後にスレッドを開始します。

*lpSecurityAttrs*<br/>
スレッドのセキュリティ属性を指定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体を指します。 NULL の場合は、作成するスレッドと同じセキュリティ属性が使用されます。 この構造の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

新しく作成されたスレッドオブジェクトへのポインター、またはエラーが発生した場合は NULL。

### <a name="remarks"></a>Remarks

`AfxBeginThread` の最初のフォームはワーカー スレッドを作成します。 2 番目のフォームは、ユーザー インターフェイス スレッドまたはワーカー スレッドとして機能可能なスレッドを作成します。

`AfxBeginThread`新しい`CWinThread`オブジェクトを作成し、その[CreateThread](../../mfc/reference/cwinthread-class.md#createthread)関数を呼び出してスレッドの実行を開始し、そのスレッドへのポインターを返します。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。 スレッドを終了するには、スレッド内から[AfxEndThread](#afxendthread)を呼び出すか、ワーカースレッドの制御関数から制御を戻します。

マルチスレッドは、アプリケーションによって有効化される必要があります。それ以外の場合、この関数は失敗します。 マルチスレッドを有効にする方法の詳細については、「 *Visual C++コンパイラオプション*」の「 [/md、/Mt、/Ld (ランタイムライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md) 」を参照してください。

の`AfxBeginThread`詳細については、マルチ[スレッドに関する記事を参照してください。ワーカースレッド](../../parallel/multithreading-creating-worker-threads.md)とマルチ[スレッドの作成:ユーザーインターフェイススレッド](../../parallel/multithreading-creating-user-interface-threads.md)を作成しています。

### <a name="example"></a>例

「 [CSocket:: Attach](../../mfc/reference/csocket-class.md#attach)」の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxcontextmenumanager"></a>AfxContextMenuManager

グローバル[コンテキストメニューマネージャー](ccontextmenumanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxcontextmenumanager

##  <a name="afxendthread"></a>AfxEndThread

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
メモリからスレッドオブジェクトを削除します。

### <a name="remarks"></a>Remarks

は、終了するスレッド内から呼び出す必要があります。

の`AfxEndThread`詳細については、マルチ[スレッドに関する記事を参照してください。スレッド](../../parallel/multithreading-terminating-threads.md)を終了しています。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
リソース`AfxFindResourceHandle`チェーンをウォークし、リソース ID とリソースの種類を指定して特定のリソースを検索するには、を使用します。

### <a name="syntax"></a>構文

```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
リソース ID を格納している文字列へのポインター。
*lpszType*<br/>
リソースの種類へのポインター。 リソースの種類の一覧については、「Windows SDK の[Findresource](/windows/win32/api/winbase/nf-winbase-findresourcea) 」を参照してください。

### <a name="return-value"></a>戻り値

リソースを格納しているモジュールへのハンドル。

### <a name="remarks"></a>Remarks

`AfxFindResourceHandle`特定のリソースを検索し、そのリソースを含むモジュールへのハンドルを返します。 リソースは、読み込まれたすべての MFC 拡張 DLL に存在する可能性があります。 `AfxFindResourceHandle`リソースがあるユーザーを示します。

モジュールは、次の順序で検索されます。

1. メインモジュール (MFC 拡張 DLL の場合)。

1. 非システムモジュール。

1. 言語固有のモジュール。

1. メインモジュール (システム DLL の場合)。

1. システムモジュール。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="afxfreelibrary"></a>AfxFreeLibrary

と`AfxFreeLibrary`は`AfxLoadLibrary`どちらも、読み込まれた各ライブラリモジュールの参照カウントを保持します。

```
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>パラメーター

*hInstLib*<br/>
読み込まれたライブラリモジュールのハンドル。 [AfxLoadLibrary](#afxloadlibrary)は、このハンドルを返します。

### <a name="return-value"></a>戻り値

関数が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

`AfxFreeLibrary`読み込まれたダイナミックリンクライブラリ (DLL) モジュールの参照カウントをデクリメントします。 参照カウントがゼロになると、モジュールは呼び出し元プロセスのアドレス空間からマップ解除され、ハンドルは無効になります。 この参照カウントは、 `AfxLoadLibrary`が呼び出されるたびに増分されます。

ライブラリモジュールをマップ解除する前に、システムによって、DLL を使用しているプロセスから DLL をデタッチできます。 これにより、DLL は、現在のプロセスの代わりに割り当てられたリソースをクリーンアップすることができます。 エントリポイント関数が戻ると、現在のプロセスのアドレス空間からライブラリモジュールが削除されます。

DLL `AfxLoadLibrary`モジュールをマップするために使用します。

アプリケーションで複数の`AfxFreeLibrary`スレッド`AfxLoadLibrary`を使用する場合は、 `FreeLibrary` ( `LoadLibrary`Win32 関数およびの代わりに) およびを使用してください。 および`AfxLoadLibrary`を`AfxFreeLibrary`使用すると、mfc 拡張 DLL が読み込まれてアンロードされたときに実行される起動コードとシャットダウンコードが、mfc のグローバル状態を破壊することがなくなります。

### <a name="example"></a>例

[AfxLoadLibrary](#afxloadlibrary)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_

##  <a name="afxgetapp"></a>  AfxGetApp

この関数によって返されるポインターは、メインのメッセージディスパッチコードや最上位のウィンドウなどのアプリケーション情報にアクセスするために使用できます。

```
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>戻り値

アプリケーションの単一`CWinApp`のオブジェクトへのポインター。

### <a name="remarks"></a>Remarks

このメソッドが NULL を返す場合、アプリケーションのメインウィンドウがまだ完全に初期化されていないことを示している可能性があります。 また、問題がある可能性もあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetappname"></a>  AfxGetAppName

この関数によって返される文字列は、診断メッセージに使用することも、一時文字列名のルートとして使用することもできます。

```
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>戻り値

アプリケーションの名前を格納している null で終わる文字列。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetinstancehandle"></a>  AfxGetInstanceHandle

この関数を使用すると、現在のアプリケーションのインスタンスハンドルを取得できます。

```
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>戻り値

アプリケーションの現在のインスタンスへの HINSTANCE。 USRDLL バージョンの MFC とリンクされている DLL 内から呼び出された場合、DLL の HINSTANCE が返されます。

### <a name="remarks"></a>Remarks

`AfxGetInstanceHandle`常に実行可能ファイルの HINSTANCE () を返します。EXE) を呼び出します。ただし、USRDLL バージョンの MFC にリンクされている DLL 内から呼び出された場合を除きます。 この場合、HINSTANCE が DLL に返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetmainwnd"></a>AfxGetMainWnd

アプリケーションが OLE サーバーである場合は、この関数を呼び出して、アプリケーションオブジェクトの[m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd)メンバーを直接参照するのではなく、アプリケーションのアクティブなメインウィンドウへのポインターを取得します。

```
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>戻り値

サーバーが、コンテナー内に埋め込まれているアクティブなオブジェクトを持ち、そのコンテナーがアクティブである場合は、この関数は、埋め込まれているアクティブな文書を含むフレーム ウィンドウ オブジェクトへのポインターを返します。

コンテナー内でアクティブなオブジェクトが存在しない場合、またはアプリケーションが OLE サーバーではない場合、この関数は単にアプリケーションオブジェクトの*m_pMainWnd*を返します。

`AfxGetMainWnd` をアプリケーションのプライマリ スレッドから呼び出した場合は、上記の規則に従ってアプリケーションのメイン ウィンドウを返します。 アプリケーションのセカンダリ スレッドからこの関数を呼び出した場合は、関数は呼び出しを行ったスレッドに関連付けられているメイン ウィンドウを返します。

### <a name="remarks"></a>Remarks

アプリケーションが OLE サーバーではない場合、この関数を呼び出すことは、アプリケーションオブジェクトの*m_pMainWnd*メンバーを直接参照することと同じです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxgetperuserregistration"></a>  AfxGetPerUserRegistration

アプリケーションが**HKEY_CURRENT_USER** ( **HKCU**) ノードへのレジストリアクセスをリダイレクトするかどうかを判断するには、この関数を使用します。

```
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>戻り値

TRUE は、レジストリ情報が HKCU ノードに送られることを示します。FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込むことを示します。 既定のノードは**HKEY_CLASSES_ROOT** ( **HKCR**) です。

### <a name="remarks"></a>Remarks

レジストリリダイレクトを有効にすると、フレームワークは**HKCR**から**HKEY_CURRENT_USER\Software\Classes**へのアクセスをリダイレクトします。 リダイレクトによって影響を受けるのは、MFC フレームワークと ATL フレームワークだけです。

アプリケーションがレジストリアクセスをリダイレクトするかどうかを変更するには、 [AfxSetPerUserRegistration](#afxsetperuserregistration)を使用します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxstat_

##  <a name="afxgetresourcehandle"></a>  AfxGetResourceHandle

この関数によって返される HINSTANCE ハンドルを使用して、Windows の関数`FindResource`の呼び出しなど、アプリケーションのリソースに直接アクセスします。

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

現在実行中のスレッドを表す[CWinThread](../../mfc/reference/cwinthread-class.md)オブジェクトへのポインターを取得するには、この関数を呼び出します。

```
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>戻り値

現在実行中のスレッドへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>Remarks

は、目的のスレッド内から呼び出す必要があります。

> [!NOTE]
>  Visual C++バージョン4.2、5.0、または`AfxGetThread` 6.0 からを呼び出す MFC プロジェクトを移植する場合`AfxGetThread`は、スレッドが見つからない場合は[AfxGetApp](#afxgetapp)を呼び出します。 新しいバージョンのコンパイラでは、 `AfxGetThread`スレッドが見つからなかった場合は NULL を返します。 アプリケーションスレッドが必要な場合は、を呼び`AfxGetApp`出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxinitrichedit"></a>  AfxInitRichEdit

この関数を呼び出して、アプリケーションのリッチエディットコントロール (バージョン 1.0) を初期化します。

```
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>Remarks

この関数は、旧バージョンとの互換性のために用意されています。 新しいアプリケーションでは[AfxInitRichEdit2](#afxinitrichedit2)を使用する必要があります。

`AfxInitRichEdit`RICHED32 を読み込みます。リッチエディットコントロールのバージョン1.0 を初期化する DLL。 リッチエディットコントロールのバージョン2.0 および3.0 を使用するには、RICHED20.DLL を使用します。DLL を読み込む必要があります。 これは、 [AfxInitRichEdit2](#afxinitrichedit2)を呼び出すことで実現されます。

既存のビジュアルC++アプリケーションのリッチエディットコントロールをバージョン2.0 に更新するには、を開きます。RC ファイルをテキストとして指定し、各リッチエディットコントロールのクラス名を "RICHEDIT" から "RichEdit20a" に変更します。 次に、の呼び出し`AfxInitRichEdit`を`AfxInitRichEdit2`に置き換えます。

この関数は、ライブラリがまだプロセス用に初期化されていない場合にも、コモンコントロールライブラリを初期化します。 MFC アプリケーションからリッチエディットコントロールを直接使用する場合は、MFC がリッチエディットコントロールランタイムを正しく初期化していることを確認するために、この関数を呼び出す必要があります。 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)の Create メソッドを呼び出す場合は、通常、この関数を呼び出す必要はありませんが、場合によっては必要になることがあります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxinitrichedit2"></a>  AfxInitRichEdit2

この関数を呼び出して、アプリケーションのリッチエディットコントロール (バージョン2.0 以降) を初期化します。

```
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>Remarks

RICHED20.DLL を読み込むには、この関数を呼び出します。リッチエディットコントロールのバージョン2.0 を DLL および初期化します。 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)の Create メソッドを呼び出す場合は、通常、この関数を呼び出す必要はありませんが、場合によっては必要になることがあります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

  ## <a name="afxisextendedframeclass"></a>AfxIsExtendedFrameClass
指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
からから`CWnd`派生したオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

指定されたウィンドウが拡張フレームオブジェクトである場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

このメソッドは、次のいずれかのクラスから*pWnd*が派生している場合に TRUE を返します。

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

このメソッドは、関数またはメソッドのパラメーターが拡張フレーム ウィンドウであるかどうかを検証する必要があるときに役立ちます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxismfctoolbar"></a>AfxIsMFCToolBar

指定されたウィンドウがツールバーオブジェクトであるかどうかを判断します。

### <a name="syntax"></a>構文

```
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
からから`CWnd`派生したオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

指定されたウィンドウがツールバーオブジェクトである場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

このメソッドは`TRUE` 、がから`CMFCToolBar`派生している場合、を返します。 このメソッドは、関数またはメソッドのパラメーターがオブジェクトで`CMFCToolBar`あることを検証する必要がある場合に便利です。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxkeyboardmanager"></a>AfxKeyboardManager

グローバル[キーボードマネージャー](ckeyboardmanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxkeyboardmanager

##  <a name="afxloadlibrary"></a>AfxLoadLibrary

DLL `AfxLoadLibrary`モジュールをマップするために使用します。

```
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>パラメーター

*lpszModuleName*<br/>
モジュールの名前 () を含む null で終わる文字列を指します。DLL または。EXE ファイル) を実行します。 指定された名前は、モジュールのファイル名です。

文字列にパスが指定されていても、指定したディレクトリにファイルが存在しない場合、関数は失敗します。

パスが指定されておらず、ファイル名拡張子が省略されている場合は、既定の拡張子です。DLL が追加されます。 ただし、ファイル名の文字列には、モジュール名に拡張子が付いていないことを示すために、末尾のポイント文字 (.) を含めることができます。 パスが指定されていない場合、関数は次の順序でファイルを検索します。

- アプリケーションの読み込み元のディレクトリ。

- 現在のフォルダー。

- **Windows 95/98:** Windows システム フォルダー。 **Windows NT:** 32ビットの Windows システムディレクトリ。 このディレクトリの名前は SYSTEM32 です。

- **Windows NT のみ:** 16ビットの Windows システムディレクトリ。 このディレクトリのパスを取得する Win32 関数はありませんが、検索されます。 このディレクトリの名前は SYSTEM です。

- Windows ディレクトリ。

- PATH 環境変数に記載されているディレクトリ。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はモジュールへのハンドルになります。 関数が失敗した場合、戻り値は NULL になります。

### <a name="remarks"></a>Remarks

これは、 [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)で DLL 関数のアドレスを取得するために使用できるハンドルを返します。 `AfxLoadLibrary`は、他の実行可能モジュールをマップするためにも使用できます。

各プロセスは、読み込まれた各ライブラリモジュールの参照カウントを保持します。 が呼び出されるたびに、この`AfxLoadLibrary`参照カウントがインクリメントされ、 `AfxFreeLibrary`が呼び出されるたびにデクリメントされます。 参照カウントがゼロになると、モジュールは呼び出し元プロセスのアドレス空間からマップ解除され、ハンドルは無効になります。

アプリケーションで複数の`AfxLoadLibrary`スレッドを使用し、MFC 拡張 DLL `FreeLibrary`を動的に読み込む場合は、(Win32 関数`LoadLibrary`およびの代わりに) と`AfxFreeLibrary`を必ず使用してください。 および`AfxLoadLibrary`を`AfxFreeLibrary`使用すると、mfc 拡張 DLL が読み込まれてアンロードされるときに実行される起動コードとシャットダウンコードが、mfc のグローバル状態を破壊しないことが保証されます。

アプリケーション`AfxLoadLibrary`でを使用するには、mfc の dll バージョンに動的にリンクする必要があり`AfxLoadLibrary`ます。 Afxdll_ のヘッダーファイルは、mfc が dll としてアプリケーションにリンクされている場合にのみ含まれます。 これは仕様です。 MFC の拡張 Dll を使用または作成するには、MFC の DLL バージョンにリンクする必要があるためです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_

## <a name="afxmenutearoffmanager"></a>AfxMenuTearOffManager

グローバル[ティアオフメニューマネージャー](cmenutearoffmanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmenutearoffmanager

## <a name="afxmousemanager"></a>AfxMouseManager

グローバル[マウスマネージャー](cmousemanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmousemanager

##  <a name="afxregisterclass"></a>AfxRegisterClass

MFC を使用する DLL にウィンドウクラスを登録するには、この関数を使用します。

```
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>パラメーター

*lpWndClass*<br/>
登録するウィンドウクラスに関する情報を格納している[WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)構造体へのポインター。 この構造の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

クラスが正常に登録された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>Remarks

この関数を使用すると、DLL がアンロードされるときにクラスが自動的に登録解除されます。

DLL 以外のビルド`AfxRegisterClass`では、アプリケーションに登録されているクラスが自動的に登録解除されるため、識別子は Windows 関数`RegisterClass`にマップされるマクロとして定義されます。 `AfxRegisterClass` の`RegisterClass`代わりにを使用する場合は、アプリケーションと DLL の両方でコードを変更せずに使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxregisterwndclass"></a>AfxRegisterWndClass

独自のウィンドウクラスを登録できます。

```
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>パラメーター

*nClassStyle*<br/>
ウィンドウクラスに対して、ビットごとの OR ( **&#124;** ) 演算子を使用して作成された Windows クラススタイルまたはスタイルの組み合わせを指定します。 クラススタイルの一覧については、Windows SDK の[WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)構造体を参照してください。 NULL の場合、既定値は次のように設定されます。

- マウスのスタイルを CS_DBLCLKS に設定します。これは、ユーザーがマウスをダブルクリックすると、ダブルクリックメッセージをウィンドウプロシージャに送信します。

- 矢印カーソルのスタイルを Windows 標準 IDC_ARROW に設定します。

- 背景ブラシを NULL に設定します。これにより、ウィンドウの背景が消去されません。

- アイコンを標準の [フラグが設定された Windows ロゴ] アイコンに設定します。

*hCursor*<br/>
ウィンドウクラスから作成された各ウィンドウにインストールされるカーソルリソースへのハンドルを指定します。 既定値の**0**を使用すると、標準の IDC_ARROW カーソルが取得されます。

*hbrBackground*<br/>
ウィンドウクラスから作成された各ウィンドウにインストールされるブラシリソースへのハンドルを指定します。 既定値の**0**を使用すると、NULL の背景ブラシが作成され、ウィンドウは既定で[WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)の処理中にバックグラウンドを消去しません。

*hIcon*<br/>
ウィンドウクラスから作成された各ウィンドウにインストールされるアイコンリソースへのハンドルを指定します。 既定値の**0**を使用すると、標準のフラグが設定された Windows ロゴアイコンが表示されます。

### <a name="return-value"></a>戻り値

クラス名を格納している null で終わる文字列。 ウィンドウを作成するために、 `Create` `CWnd`または他の**CWnd**の派生クラスのメンバー関数にこのクラス名を渡すことができます。 名前は Microsoft Foundation Class ライブラリによって生成されます。

> [!NOTE]
>  戻り値は、静的バッファーへのポインターです。 この文字列を保存するには、 `CString`変数に割り当てます。

### <a name="remarks"></a>Remarks

Microsoft Foundation Class ライブラリによって、いくつかの標準ウィンドウクラスが自動的に登録されます。 独自のウィンドウクラスを登録する場合は、この関数を呼び出します。

によって`AfxRegisterWndClass`クラスに登録された名前は、パラメーターだけに依存します。 同じパラメーターを`AfxRegisterWndClass`使用してを複数回呼び出すと、最初の呼び出しでクラスが登録されるだけです。 同じパラメーター `AfxRegisterWndClass`を持つの後続の呼び出しでは、既に登録されている classname が返されます。

同じパラメーターを`AfxRegisterWndClass`持つ複数の CWnd 派生クラスに対してを呼び出すと、各クラスに対して個別のウィンドウクラスを取得するのではなく、各クラスが同じウィンドウクラスを共有します。 これにより、CS_CLASSDC クラススタイルが使用されている場合に問題が発生する可能性があります。 複数の CS_CLASSDC ウィンドウクラスの代わりに、CS_CLASSDC ウィンドウクラスが1つずつ作成さC++れ、そのクラスを使用するすべてのウィンドウが同じ DC を共有します。 この問題を回避するには、 [AfxRegisterClass](#afxregisterclass)を呼び出してクラスを登録します。

テクニカルノート[テクニカルノート1を参照してください。ウィンドウクラスの](../../mfc/tn001-window-class-registration.md)登録`AfxRegisterWndClass`と関数の詳細については、ウィンドウクラスの登録に関する情報を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration

アプリケーションが**HKEY_CURRENT_USER** ( **HKCU**) ノードへのレジストリアクセスをリダイレクトするかどうかを設定します。

```
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からTRUE は、レジストリ情報が HKCU ノードに送られることを示します。FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込むことを示します。 既定のノードは**HKEY_CLASSES_ROOT** ( **HKCR**) です。

### <a name="remarks"></a>Remarks

Windows Vista より前では、レジストリにアクセスしたアプリケーションでは通常、 **HKEY_CLASSES_ROOT**ノードが使用されていました。 ただし、Windows Vista 以降のオペレーティングシステムでは、HKCR に書き込むには、管理者特権モードでアプリケーションを実行する必要があります。

このメソッドを使用すると、レジストリアクセスを HKCR から HKCU にリダイレクトすることにより、アプリケーションでレジストリへの読み取りと書き込みを管理者特権モードで実行できます。 詳細については、「 [Linker Property Pages](../../build/reference/linker-property-pages.md)」を参照してください。

レジストリリダイレクトを有効にすると、フレームワークは HKCR から**HKEY_CURRENT_USER\Software\Classes**へのアクセスをリダイレクトします。 リダイレクトによって影響を受けるのは、MFC フレームワークと ATL フレームワークだけです。

既定の実装では、HKCR の下のレジストリにアクセスします。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxstat_

##  <a name="afxsetresourcehandle"></a>AfxSetResourceHandle

この関数を使用して、アプリケーションの既定のリソースが読み込まれる場所を決定する HINSTANCE handle を設定します。

```
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>パラメーター

*hInstResource*<br/>
のインスタンスまたはモジュールハンドル。アプリケーションのリソースの読み込み元となる EXE または DLL ファイル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxshellmanager"></a>AfxShellManager

グローバル[シェルマネージャー](cshellmanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```
CShellManager* afxShellManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxshellmanager

##  <a name="afxsocketinit"></a>AfxSocketInit

Windows ソケットを初期化する`CWinApp::InitInstance`には、オーバーライドでこの関数を呼び出します。

```
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>パラメーター

*lpwsaData*<br/>
[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata)構造体へのポインター。 *LpwsaData*が NULL でない場合は、の呼び出しに`WSADATA` `WSAStartup`よって構造体のアドレスが格納されます。 また、この関数は`WSACleanup` 、アプリケーションが終了する前にが呼び出されるようにします。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

静的にリンクされた mfc アプリケーションでセカンダリスレッドで mfc ソケットを使用`AfxSocketInit`する場合は、ソケットライブラリを初期化するためにソケットを使用する各スレッドでを呼び出す必要があります。 既定では`AfxSocketInit` 、はプライマリスレッドでのみ呼び出されます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxsock

## <a name="afxusertoolsmanager"></a>AfxUserToolsManager

グローバル[ユーザーツールマネージャー](cusertoolsmanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxusertoolsmanager

##  <a name="afxwininit"></a>AfxWinInit

この関数は、GUI ベースのアプリケーションの`WinMain` [CWinApp](../../mfc/reference/cwinapp-class.md)初期化の一部として、mfc が提供する関数によって呼び出され、mfc を初期化します。

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
アプリケーションの前のインスタンスを対象としたハンドル。 Win32 ベースのアプリケーションの場合、このパラメーターは常に**NULL**になります。

*lpCmdLine*<br/>
は、アプリケーションのコマンドラインを指定する null で終わる文字列を指します。

*nCmdShow*<br/>
GUI アプリケーションのメインウィンドウを表示する方法を指定します。

### <a name="remarks"></a>Remarks

Mfc によって提供`WinMain`される関数を使用しないコンソールアプリケーションの場合は、を直接呼び出し`AfxWinInit`て mfc を初期化する必要があります。

自分でを`AfxWinInit`呼び出す場合は、 `CWinApp`クラスのインスタンスを宣言する必要があります。 コンソールアプリケーションでは、から`CWinApp`独自のクラスを派生させずに、の`CWinApp`インスタンスを直接使用することもできます。 この手法は、アプリケーションのすべての機能を**main**の実装に残しておく場合に適しています。

> [!NOTE]
>  アセンブリのアクティベーションコンテキストを作成すると、MFC はユーザーモジュールによって提供されるマニフェストリソースを使用します。 アクティベーションコンテキストは、 `AfxWinInit`で作成されます。 詳細については、「 [MFC モジュール状態でのアクティベーションコンテキストのサポート](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)<br/>
[CWinApp クラス](cwinapp-class.md)<br/>
[CContextMenuManager クラス](ccontextmenumanager-class.md)<br/>
[CWnd クラス](cwnd-class.md)<br/>
[CFrameWndEx クラス](cframewndex-class.md)<br/>
[CMFCToolBar クラス](cmfctoolbar-class.md)<br/>
[CKeyboardManager クラス](ckeyboardmanager-class.md)<br/>
[CMenuTearOffManager クラス](cmenutearoffmanager-class.md)<br/>
[CMouseManager クラス](cmousemanager-class.md)<br/>
[CShellManager クラス](cshellmanager-class.md)<br/>
[CUserToolsManager クラス](cusertoolsmanager-class.md)
