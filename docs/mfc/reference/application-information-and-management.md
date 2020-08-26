---
title: アプリケーションの情報と管理
description: MFC (Microsoft Foundation Class ライブラリ) アプリケーションの情報と管理機能への参照。
ms.date: 01/27/2020
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: 3412ed3f02e93d3e8c947d4f730355c219493a77
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832308"
---
# <a name="application-information-and-management"></a>アプリケーションの情報と管理

アプリケーションを作成するときは、1つの [CWinApp](../../mfc/reference/cwinapp-class.md)派生オブジェクトを作成します。 場合によっては、から派生したオブジェクトの外部から、このオブジェクトに関する情報を取得する必要があり `CWinApp` ます。 または、他のグローバルな "マネージャー" オブジェクトへのアクセスが必要になる場合があります。

Microsoft Foundation Class ライブラリには、これらのタスクを実行するための次のグローバル関数が用意されています。

## <a name="application-information-and-management-functions"></a>アプリケーションの情報と管理の機能

| 名前 | 説明 |
|-|-|
|[AfxBeginThread](#afxbeginthread)|新しいスレッドを作成します。|
|[AfxContextMenuManager](#afxcontextmenumanager)|グローバル [コンテキストメニューマネージャー](ccontextmenumanager-class.md)へのポインター。|
|[AfxEndThread](#afxendthread)|現在のスレッドを終了します。|
|[AfxFindResourceHandle](#afxfindresourcehandle)|リソースチェーンを調べ、リソース ID とリソースの種類を指定して特定のリソースを検索します。 |
|[AfxFreeLibrary](#afxfreelibrary)|読み込まれたダイナミックリンクライブラリ (DLL) モジュールの参照カウントをデクリメントします。 参照カウントが0になると、モジュールはマップ解除されます。|
|[AfxGetApp](#afxgetapp)|アプリケーションの1つのオブジェクトへのポインターを返し `CWinApp` ます。|
|[AfxGetAppName](#afxgetappname)|アプリケーションの名前を含む文字列を返します。|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|アプリケーションのこのインスタンスを表す HINSTANCE を返します。|
|[AfxGetMainWnd](#afxgetmainwnd)|非 OLE アプリケーションの現在の "main" ウィンドウ、またはサーバーアプリケーションの埋め込み先フレームウィンドウへのポインターを返します。|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|アプリケーションがレジストリアクセスを **HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを判断するには、この関数を使用します。|
|[AfxGetResourceHandle](#afxgetresourcehandle)|アプリケーションの既定のリソースのソースに HINSTANCE を返します。 アプリケーションのリソースに直接アクセスするには、を使用します。|
|[AfxGetThread](#afxgetthread)|現在の [CWinThread](../../mfc/reference/cwinthread-class.md) オブジェクトへのポインターを取得します。|
|[AfxInitRichEdit](#afxinitrichedit)|アプリケーションのバージョン1.0 リッチエディットコントロールを初期化します。|
|[AfxInitRichEdit2](#afxinitrichedit2)|アプリケーションのバージョン2.0 以降のリッチエディットコントロールを初期化します。|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。|
|[AfxIsMFCToolBar](#afxismfctoolbar)|指定されたウィンドウがツールバーオブジェクトであるかどうかを判断します。|
|[AfxKeyboardManager](#afxkeyboardmanager)|グローバル [キーボードマネージャー](ckeyboardmanager-class.md)へのポインター。|
|[AfxLoadLibrary](#afxloadlibrary)|DLL モジュールをマップし、DLL 関数のアドレスを取得するために使用できるハンドルを返します。|
|[AfxLoadLibraryEx](#afxloadlibraryex)|指定されたオプションを使用して DLL モジュールをマップし、DLL 関数のアドレスを取得するために使用できるハンドルを返します。|
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|グローバル [ティアオフメニューマネージャー](cmenutearoffmanager-class.md)へのポインター。|
|[AfxMouseManager](#afxmousemanager)|グローバル [マウスマネージャー](cmousemanager-class.md)へのポインター。|
|[AfxRegisterClass](#afxregisterclass)|MFC を使用する DLL にウィンドウクラスを登録します。|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC によって自動的に登録されたものを補完するために、Windows のウィンドウクラスを登録します。|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|アプリケーションがレジストリアクセスを **HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを設定します。|
|[AfxSetResourceHandle](#afxsetresourcehandle)|アプリケーションの既定のリソースが読み込まれる HINSTANCE ハンドルを設定します。|
|[AfxShellManager](#afxshellmanager)|グローバル [シェルマネージャー](cshellmanager-class.md)へのポインター。 |
|[AfxSocketInit](#afxsocketinit)|`CWinApp::InitInstance`Windows ソケットを初期化するために、オーバーライドで呼び出されます。|
|[AfxUserToolsManager](#afxusertoolsmanager)|グローバル [ユーザーツールマネージャー](cusertoolsmanager-class.md)へのポインター。|
|[AfxWinInit](#afxwininit)|Mfc `WinMain` を初期化するために、GUI ベースのアプリケーションの [CWinApp](../../mfc/reference/cwinapp-class.md) 初期化の一部として、mfc が提供する関数によって呼び出されます。 MFC を使用するコンソールアプリケーションでは、を直接呼び出す必要があります。|

## <a name="afxbeginthread"></a><a name="afxbeginthread"></a> AfxBeginThread

この関数を呼び出して、新しいスレッドを作成します。

```cpp
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

*pfnThreadProc*\
ワーカー スレッドの制御関数をポイントします。 ポインターを NULL にすることはできません。 この関数は次のように宣言する必要があります。

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*pThreadClass*\
[CWinThread](../../mfc/reference/cwinthread-class.md)から派生したオブジェクトの RUNTIME_CLASS。

*pParam*\
制御関数に渡すパラメーター。

*nPriority*\
スレッドに設定する優先順位。 使用可能な優先順位の完全な一覧と説明については、Windows SDK の「 [Setthreadpriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) 」を参照してください。

*nStackSize*\
新しいスレッドへのスタックのバイト サイズを指定します。 0 である場合、スタック サイズの既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。

*dwCreateFlags*\
スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。

- 中断カウントが1のスレッドを開始 CREATE_SUSPENDED ます。 `CWinThread`スレッドが実行を開始する前に、 [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete)や派生クラスのメンバーなど、オブジェクトのメンバーデータを初期化する場合は、CREATE_SUSPENDED を使用します。 初期化が完了したら、 [CWinThread:: ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) を使用して、実行中のスレッドを開始します。 が呼び出されるまで、スレッドは実行されません `CWinThread::ResumeThread` 。

- **0** 作成直後にスレッドを開始します。

*lpSecurityAttrs*\
スレッドのセキュリティ属性を指定する [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 構造体を指します。 NULL の場合は、作成するスレッドと同じセキュリティ属性が使用されます。 この構造の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

エラーが発生した場合、新しく作成されたスレッドのオブジェクトまたは NULL をポイントします。

### <a name="remarks"></a>解説

`AfxBeginThread` の最初のフォームはワーカー スレッドを作成します。 2 番目のフォームは、ユーザー インターフェイス スレッドまたはワーカー スレッドとして機能可能なスレッドを作成します。

`AfxBeginThread` 新しいオブジェクトを作成し `CWinThread` 、その [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) 関数を呼び出してスレッドの実行を開始し、そのスレッドへのポインターを返します。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。 スレッドを終了するには、スレッド内から [AfxEndThread](#afxendthread) を呼び出すか、ワーカースレッドの制御関数から制御を戻します。

マルチスレッドは、アプリケーションによって有効化される必要があります。それ以外の場合、この関数は失敗します。 マルチスレッドを有効にする方法の詳細については、「 [/md、/mt、/ld (ランタイムライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。

の詳細につい `AfxBeginThread` ては、「 [マルチスレッド: ワーカースレッドの作成](../../parallel/multithreading-creating-worker-threads.md) 」および「 [マルチスレッド: ユーザーインターフェイススレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)」を参照してください。

### <a name="example"></a>例

「 [CSocket:: Attach](../../mfc/reference/csocket-class.md#attach)」の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxcontextmenumanager"></a><a name="afxcontextmenumanager"></a> AfxContextMenuManager

グローバル [コンテキストメニューマネージャー](ccontextmenumanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```cpp
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxcontextmenumanager

## <a name="afxendthread"></a><a name="afxendthread"></a> AfxEndThread

現在実行中のスレッドを終了するには、この関数を呼び出します。

```cpp
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>パラメーター

*nExitCode*\
スレッドの終了コードを指定します。

*bDelete*\
メモリからスレッドオブジェクトを削除します。

### <a name="remarks"></a>解説

は、終了するスレッド内から呼び出す必要があります。

の詳細につい `AfxEndThread` ては、「 [マルチスレッド: スレッドの終了](../../parallel/multithreading-terminating-threads.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxfindresourcehandle"></a><a name="afxfindresourcehandle"></a> AfxFindResourceHandle

リソース `AfxFindResourceHandle` チェーンをウォークし、リソース ID とリソースの種類を指定して特定のリソースを検索するには、を使用します。

### <a name="syntax"></a>構文

```cpp
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>パラメーター

*lpszName*\
リソース ID を格納している文字列へのポインター。
*lpszType*\
リソースの種類へのポインター。 リソースの種類の一覧については、「Windows SDK の [Findresource](/windows/win32/api/winbase/nf-winbase-findresourcea) 」を参照してください。

### <a name="return-value"></a>戻り値

リソースを格納しているモジュールへのハンドル。

### <a name="remarks"></a>解説

`AfxFindResourceHandle` 特定のリソースを検索し、そのリソースを含むモジュールへのハンドルを返します。 リソースは、読み込まれたすべての MFC 拡張 DLL に存在する可能性があります。 `AfxFindResourceHandle` リソースがあるユーザーを示します。

モジュールは、次の順序で検索されます。

1. Main モジュール (MFC 拡張 DLL の場合)。

1. 非システムモジュール。

1. 言語固有のモジュール。

1. メインモジュール (システム DLL の場合)。

1. システムモジュール。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxfreelibrary"></a><a name="afxfreelibrary"></a> AfxFreeLibrary

`AfxFreeLibrary`とはどちらも、 `AfxLoadLibrary` 読み込まれた各ライブラリモジュールの参照カウントを保持します。

```cpp
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>パラメーター

*hInstLib*\
読み込まれたライブラリモジュールのハンドル。 [AfxLoadLibrary](#afxloadlibrary) は、このハンドルを返します。

### <a name="return-value"></a>戻り値

関数が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

`AfxFreeLibrary` 読み込まれたダイナミックリンクライブラリ (DLL) モジュールの参照カウントをデクリメントします。 参照カウントがゼロになると、モジュールは呼び出し元プロセスのアドレス空間からマップ解除され、ハンドルは無効になります。 この参照カウントは、が呼び出されるたびに増分され `AfxLoadLibrary` ます。

ライブラリモジュールをマップ解除する前に、システムによって、DLL を使用しているプロセスから DLL をデタッチできます。 これにより、DLL は、現在のプロセスに割り当てられているリソースをクリーンアップすることができます。 エントリポイント関数が戻ると、現在のプロセスのアドレス空間からライブラリモジュールが削除されます。

`AfxLoadLibrary`DLL モジュールをマップするために使用します。

`AfxFreeLibrary` `AfxLoadLibrary` `FreeLibrary` アプリケーションで複数のスレッドを使用する場合は、(Win32 関数およびの代わりに) およびを使用してください `LoadLibrary` 。 およびを使用する `AfxLoadLibrary` と、 `AfxFreeLibrary` MFC 拡張 DLL が読み込まれてアンロードされたときに実行される起動コードとシャットダウンコードが、mfc のグローバル状態を破壊することがなくなります。

### <a name="example"></a>例

[AfxLoadLibrary](#afxloadlibrary)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_

## <a name="afxgetapp"></a><a name="afxgetapp"></a> AfxGetApp

この関数によって返されるポインターは、メインのメッセージディスパッチコードや最上位のウィンドウなどのアプリケーション情報にアクセスするために使用できます。

```cpp
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>戻り値

アプリケーションの単一のオブジェクトへのポインター `CWinApp` 。

### <a name="remarks"></a>解説

このメソッドが NULL を返す場合は、アプリケーションのメインウィンドウがまだ完全に初期化されていないことを示している可能性があります。 また、問題がある可能性もあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetappname"></a><a name="afxgetappname"></a> AfxGetAppName

返される文字列は、診断メッセージに使用することも、一時文字列名のルートとして使用することもできます。

```cpp
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>戻り値

アプリケーションの名前を格納している null で終わる文字列。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a> AfxGetInstanceHandle

この関数を使用すると、現在のアプリケーションのインスタンスハンドルを取得できます。

```cpp
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>戻り値

アプリケーションの現在のインスタンスへの HINSTANCE。 USRDLL バージョンの MFC とリンクされている DLL 内から呼び出された場合、DLL の HINSTANCE が返されます。

### <a name="remarks"></a>解説

`AfxGetInstanceHandle` 常に実行可能ファイルの HINSTANCE () を返します。EXE) を呼び出します。ただし、USRDLL バージョンの MFC にリンクされている DLL 内から呼び出された場合を除きます。 この場合、HINSTANCE が DLL に返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetmainwnd"></a><a name="afxgetmainwnd"></a> AfxGetMainWnd

アプリケーションが OLE サーバーである場合は、この関数を呼び出して、アプリケーションのアクティブなメインウィンドウへのポインターを取得します。 アプリケーションオブジェクトの [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) メンバーを直接参照するのではなく、この結果を使用します。

```cpp
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>戻り値

サーバーにアクティブなコンテナー内で埋め込み先のオブジェクトがある場合に、埋め込み先のアクティブなドキュメントを含むフレームウィンドウオブジェクトへのポインターを返します。

コンテナー内でアクティブなオブジェクトが存在しない場合、またはアプリケーションが OLE サーバーではない場合、この関数はアプリケーションオブジェクトの *m_pMainWnd* を返します。

`AfxGetMainWnd` をアプリケーションのプライマリ スレッドから呼び出した場合は、上記の規則に従ってアプリケーションのメイン ウィンドウを返します。 アプリケーションのセカンダリ スレッドからこの関数を呼び出した場合は、関数は呼び出しを行ったスレッドに関連付けられているメイン ウィンドウを返します。

### <a name="remarks"></a>解説

アプリケーションが OLE サーバーではない場合、この関数を呼び出すことは、アプリケーションオブジェクトの *m_pMainWnd* メンバーを直接参照することと同じです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a> AfxGetPerUserRegistration

アプリケーションがレジストリアクセスを **HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを判断するには、この関数を使用します。

```cpp
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>戻り値

TRUE は、レジストリ情報が HKCU ノードに送られることを示します。 FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込むことを示します。 既定のノードは **HKEY_CLASSES_ROOT** (**HKCR**) です。

### <a name="remarks"></a>解説

レジストリリダイレクトを有効にすると、フレームワークによって **HKCR** から **HKEY_CURRENT_USER**にアクセスできるようになります。 リダイレクトによって影響を受けるのは、MFC フレームワークと ATL フレームワークだけです。

アプリケーションがレジストリアクセスをリダイレクトするかどうかを変更するには、 [AfxSetPerUserRegistration](#afxsetperuserregistration)を使用します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxstat_

## <a name="afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a> AfxGetResourceHandle

この関数によって返される HINSTANCE ハンドルを使用して、Windows の関数の呼び出しなど、アプリケーションのリソースに直接アクセスし `FindResource` ます。

```cpp
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>戻り値

アプリケーションの既定のリソースが読み込まれる HINSTANCE ハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetthread"></a><a name="afxgetthread"></a> AfxGetThread

現在実行中のスレッドを表す [CWinThread](../../mfc/reference/cwinthread-class.md) オブジェクトへのポインターを取得するには、この関数を呼び出します。

```cpp
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>戻り値

現在実行中のスレッドへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

は、スレッド内から呼び出す必要があります。

> [!NOTE]
> `AfxGetThread`Visual C++ バージョン4.2、5.0、または6.0 からを呼び出す MFC プロジェクトを移植する場合は、 `AfxGetThread` スレッドが見つからない場合は[AfxGetApp](#afxgetapp)を呼び出します。 新しいバージョンのコンパイラでは、スレッドが見つからなかった `AfxGetThread` 場合は NULL を返します。 アプリケーションスレッドが必要な場合は、を呼び出す必要があり `AfxGetApp` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxinitrichedit"></a><a name="afxinitrichedit"></a> AfxInitRichEdit

この関数を呼び出して、アプリケーションのリッチエディットコントロール (バージョン 1.0) を初期化します。

```cpp
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>解説

この関数は、旧バージョンとの互換性のために用意されています。 新しいアプリケーションでは [AfxInitRichEdit2](#afxinitrichedit2)を使用する必要があります。

`AfxInitRichEdit` リッチエディットコントロールのバージョン1.0 を初期化するために RICHED32.DLL を読み込みます。 リッチエディットコントロールのバージョン2.0 および3.0 を使用するには、RICHED20.DLL を読み込む必要があります。 これは、 [AfxInitRichEdit2](#afxinitrichedit2)を呼び出すことによって読み込まれます。

既存の Visual C++ アプリケーションのリッチエディットコントロールをバージョン2.0 に更新するには、を開きます。RC ファイルをテキストとして指定し、各リッチエディットコントロールのクラス名を "RICHEDIT" から "RichEdit20a" に変更します。 次に、の呼び出しをに置き換え `AfxInitRichEdit` `AfxInitRichEdit2` ます。

この関数は、ライブラリがまだプロセス用に初期化されていない場合にも、コモンコントロールライブラリを初期化します。 MFC アプリケーションからリッチエディットコントロールを直接使用する場合は、この関数を呼び出して、MFC がリッチエディットコントロールランタイムを正しく初期化したことを確認します。 `Create` [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)のメソッドを呼び出す場合は、通常、この関数を呼び出す必要はありませんが、場合によっては必要になることがあります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxinitrichedit2"></a><a name="afxinitrichedit2"></a> AfxInitRichEdit2

この関数を呼び出して、アプリケーションのリッチエディットコントロール (バージョン2.0 以降) を初期化します。

```cpp
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>解説

この関数を呼び出して、リッチエディットコントロールの RICHED20.DLL を読み込み、バージョン2.0 を初期化します。 `Create` [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)のメソッドを呼び出す場合は、通常、この関数を呼び出す必要はありませんが、場合によっては必要になることがあります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxisextendedframeclass"></a><a name="afxisextendedframeclass"></a> AfxIsExtendedFrameClass

指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。

### <a name="syntax"></a>構文

```cpp
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>パラメーター

*pWnd*\
からから派生したオブジェクトへのポインター `CWnd` 。

### <a name="return-value"></a>戻り値

指定されたウィンドウが拡張フレームオブジェクトである場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、次のいずれかのクラスから *pWnd* が派生している場合に TRUE を返します。

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

このメソッドは、関数またはメソッドのパラメーターが拡張フレーム ウィンドウであるかどうかを検証する必要があるときに役立ちます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxismfctoolbar"></a><a name="afxismfctoolbar"></a> AfxIsMFCToolBar

指定されたウィンドウがツールバーオブジェクトであるかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*\
からから派生したオブジェクトへのポインター `CWnd` 。

### <a name="return-value"></a>戻り値

指定されたウィンドウがツールバーオブジェクトである場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッド `TRUE` は、 *pWnd*がから派生している場合、を返し `CMFCToolBar` ます。 このメソッドは、関数またはメソッドのパラメーターがオブジェクトであることを検証する必要がある場合に便利です `CMFCToolBar` 。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxkeyboardmanager"></a><a name="afxkeyboardmanager"></a> AfxKeyboardManager

グローバル [キーボードマネージャー](ckeyboardmanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```cpp
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxkeyboardmanager

## <a name="afxloadlibrary"></a><a name="afxloadlibrary"></a> AfxLoadLibrary

`AfxLoadLibrary`DLL モジュールをマップするために使用します。

```cpp
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>パラメーター

*lpszModuleName*\
モジュールの名前 () を含む null で終わる文字列を指します。DLL または。EXE ファイル) を実行します。 指定された名前は、モジュールのファイル名です。

文字列にパスが指定されていても、指定したディレクトリにファイルが存在しない場合、関数は失敗します。

パスが指定されておらず、ファイル名拡張子が省略されている場合は、既定の拡張子です。DLL が追加されます。 ただし、ファイル名の文字列には、モジュール名に拡張子が付いていないことを示すために、末尾のポイント文字 (.) を含めることができます。 パスが指定されていない場合、関数は [デスクトップアプリケーションの検索順序](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)を使用します。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はモジュールへのハンドルになります。 失敗した場合、戻り値は NULL になります。

### <a name="remarks"></a>解説

これは、 [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) で DLL 関数のアドレスを取得するために使用できるハンドルを返します。 `AfxLoadLibrary` は、他の実行可能モジュールをマップするためにも使用できます。

各プロセスは、読み込まれた各ライブラリモジュールの参照カウントを保持します。 が呼び出されるたびに、この参照カウントがインクリメントされ `AfxLoadLibrary` 、が呼び出されるたびにデクリメントされ `AfxFreeLibrary` ます。 参照カウントがゼロになると、モジュールは呼び出し元プロセスのアドレス空間からマップ解除され、ハンドルは無効になります。

`AfxLoadLibrary` `AfxFreeLibrary` `LoadLibrary` アプリケーションで `FreeLibrary` 複数のスレッドを使用し、MFC 拡張 DLL を動的に読み込む場合は、(Win32 関数とではなく) およびを使用してください。 およびを使用する `AfxLoadLibrary` と、 `AfxFreeLibrary` MFC 拡張 DLL が読み込まれてアンロードされるときに実行される起動コードとシャットダウンコードが、mfc のグローバル状態を破壊することはありません。

アプリケーションでを使用する `AfxLoadLibrary` には、MFC の DLL バージョンに動的にリンクする必要があります。 のヘッダーファイル `AfxLoadLibrary` (Afxdll_ .h) は、MFC が DLL としてアプリケーションにリンクされている場合にのみ含まれます。 Mfc の DLL バージョンにリンクして MFC 拡張 Dll を使用または作成する必要があるため、この要件は仕様によるものです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_

## <a name="afxloadlibraryex"></a><a name="afxloadlibraryex"></a> AfxLoadLibraryEx

`AfxLoadLibraryEx`DLL モジュールをマップするために使用します。

```cpp
HINSTANCE AFXAPI AfxLoadLibraryEx(LPCTSTR lpFileName, HANDLE hFile, DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*lpFileName*\
モジュールの名前 () を含む null で終わる文字列を指します。DLL または。EXE ファイル) を実行します。 指定された名前は、モジュールのファイル名です。

文字列にパスが指定されていても、指定したディレクトリにファイルが存在しない場合、関数は失敗します。

パスが指定されておらず、ファイル名拡張子が省略されている場合は、既定の拡張子です。DLL が追加されます。 ただし、ファイル名の文字列には、モジュール名に拡張子が付いていないことを示すために、末尾のポイント文字 (.) を含めることができます。 パスが指定されていない場合、関数は [デスクトップアプリケーションの検索順序](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)を使用します。

*hFile*\
このパラメーターは将来使用するために予約されています。 NULL にする必要があります。

*dwFlags*\
モジュールの読み込み時に実行されるアクション。 フラグが指定されていない場合、この関数の動作は関数と同じになり `AfxLoadLibrary` ます。 このパラメーターの有効な値については、 [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw) のドキュメントを参照してください。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はモジュールへのハンドルになります。 失敗した場合、戻り値は NULL になります。

### <a name="remarks"></a>解説

`AfxLoadLibraryEx` DLL 関数のアドレスを取得するために [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) で使用できるハンドルを返します。 `AfxLoadLibraryEx` は、他の実行可能モジュールをマップするためにも使用できます。

各プロセスは、読み込まれた各ライブラリモジュールの参照カウントを保持します。 が呼び出されるたびに、この参照カウントがインクリメントされ `AfxLoadLibraryEx` 、が呼び出されるたびにデクリメントされ `AfxFreeLibrary` ます。 参照カウントがゼロになると、モジュールは呼び出し元プロセスのアドレス空間からマップ解除され、ハンドルは無効になります。

`AfxLoadLibraryEx` `AfxFreeLibrary` `LoadLibraryEx` `FreeLibrary` アプリケーションで複数のスレッドを使用し、MFC 拡張 DLL を動的に読み込む場合は、(Win32 関数およびの代わりに) とを必ず使用してください。 およびを使用する `AfxLoadLibraryEx` と、 `AfxFreeLibrary` MFC 拡張 DLL が読み込まれてアンロードされたときに実行される起動コードとシャットダウンコードが、mfc のグローバル状態を破壊することがなくなります。

アプリケーションでを使用する `AfxLoadLibraryEx` には、MFC の DLL バージョンに動的にリンクする必要があります。 のヘッダーファイル `AfxLoadLibraryEx` (Afxdll_ .h) は、MFC が DLL としてアプリケーションにリンクされている場合にのみ含まれます。 Mfc の DLL バージョンにリンクして MFC 拡張 Dll を使用または作成する必要があるため、この要件は仕様によるものです。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_

## <a name="afxmenutearoffmanager"></a><a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager

グローバル [ティアオフメニューマネージャー](cmenutearoffmanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```cpp
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmenutearoffmanager

## <a name="afxmousemanager"></a><a name="afxmousemanager"></a> AfxMouseManager

グローバル [マウスマネージャー](cmousemanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```cpp
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmousemanager

## <a name="afxregisterclass"></a><a name="afxregisterclass"></a> AfxRegisterClass

MFC を使用する DLL にウィンドウクラスを登録するには、この関数を使用します。

```cpp
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>パラメーター

*lpWndClass*\
登録するウィンドウクラスに関する情報を格納している [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 構造体へのポインター。 この構造の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

クラスが正常に登録された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数を使用すると、DLL がアンロードされるときにクラスが自動的に登録解除されます。

DLL 以外のビルドでは、 `AfxRegisterClass` `RegisterClass` アプリケーションに登録されているクラスが自動的に登録解除されるため、識別子は Windows 関数にマップされるマクロとして定義されます。 の代わりにを使用する場合は `AfxRegisterClass` `RegisterClass` 、アプリケーションと DLL の両方でコードを変更せずに使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxregisterwndclass"></a><a name="afxregisterwndclass"></a> AfxRegisterWndClass

独自のウィンドウクラスを登録できます。

```cpp
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>パラメーター

*nClassStyle*\
ウィンドウクラスに対して、ビットごとの OR (**&#124;**) 演算子を使用して作成された Windows クラススタイルまたはスタイルの組み合わせを指定します。 クラススタイルの一覧については、Windows SDK の [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 構造体を参照してください。 NULL の場合、既定値は次のように設定されます。

- マウスのスタイルを CS_DBLCLKS に設定します。これにより、ユーザーがマウスをダブルクリックすると、ダブルクリックメッセージがウィンドウプロシージャに送信されます。

- 矢印カーソルのスタイルを Windows 標準 IDC_ARROW に設定します。

- 背景ブラシを NULL に設定します。これにより、ウィンドウは背景を消去しません。

- アイコンを標準の [フラグが設定された Windows ロゴ] アイコンに設定します。

*hCursor*\
ウィンドウクラスから作成された各ウィンドウにインストールされるカーソルリソースへのハンドルを指定します。 既定値の **0**を使用すると、標準 IDC_ARROW カーソルが取得されます。

*hbrBackground*\
ウィンドウクラスから作成された各ウィンドウにインストールされるブラシリソースへのハンドルを指定します。 既定値の **0**を使用すると、NULL の背景ブラシが作成されます。既定では、 [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)の処理中にウィンドウの背景が消去されることはありません。

*hIcon*\
ウィンドウクラスから作成された各ウィンドウにインストールされるアイコンリソースへのハンドルを指定します。 既定値の **0**を使用すると、標準のフラグが設定された Windows ロゴアイコンが表示されます。

### <a name="return-value"></a>戻り値

クラス名を格納している null で終わる文字列。 `Create` `CWnd` ウィンドウを作成するために、または他の**CWnd**の派生クラスのメンバー関数にこのクラス名を渡すことができます。 名前は Microsoft Foundation Class ライブラリによって生成されます。

> [!NOTE]
> 戻り値は、静的バッファーへのポインターです。 この文字列を保存するには、変数に割り当て `CString` ます。

### <a name="remarks"></a>解説

Microsoft Foundation Class ライブラリによって、いくつかの標準ウィンドウクラスが自動的に登録されます。 独自のウィンドウクラスを登録する場合は、この関数を呼び出します。

によってクラスに登録された名前は、 `AfxRegisterWndClass` パラメーターだけに依存します。 `AfxRegisterWndClass`同じパラメーターを使用してを複数回呼び出すと、最初の呼び出しでクラスが登録されるだけです。 後で `AfxRegisterWndClass` 同じパラメーターを使用してを呼び出すと、既に登録されている classname が返されます。

`AfxRegisterWndClass`同じパラメーターを持つ複数の CWnd 派生クラスに対してを呼び出すと、各クラスに対して個別のウィンドウクラスを取得するのではなく、各クラスが同じウィンドウクラスを共有します。 この共有によって、CS_CLASSDC クラスのスタイルが使用されている場合に問題が発生する可能性があります。 複数の CS_CLASSDC ウィンドウクラスではなく、CS_CLASSDC ウィンドウクラスが1つだけになります。 そのクラスを使用するすべての C++ ウィンドウは、同じ DC を共有します。 この問題を回避するには、 [AfxRegisterClass](#afxregisterclass) を呼び出してクラスを登録します。

ウィンドウクラスの登録と関数の詳細については、「テクニカルノート [テクニカルノート 1: ウィンドウクラスの登録」](../../mfc/tn001-window-class-registration.md) を参照してください `AfxRegisterWndClass` 。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a> AfxSetPerUserRegistration

アプリケーションがレジストリアクセスを **HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを設定します。

```cpp
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*bEnable*\
からTRUE は、レジストリ情報が HKCU ノードに送られることを示します。 FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込むことを示します。 既定のノードは **HKEY_CLASSES_ROOT** (**HKCR**) です。

### <a name="remarks"></a>解説

Windows Vista より前では、レジストリにアクセスしたアプリケーションでは、一般的に **HKEY_CLASSES_ROOT** ノードが使用されていました。 ただし、Windows Vista 以降のオペレーティングシステムでは、HKCR に書き込むには、管理者特権モードでアプリケーションを実行する必要があります。

このメソッドを使用すると、管理者特権モードで実行しなくても、アプリケーションでレジストリの読み取りと書き込みを行うことができます。 これは、レジストリアクセスを HKCR から HKCU にリダイレクトすることによって機能します。 詳細については、「 [Linker Property Pages](../../build/reference/linker-property-pages.md)」を参照してください。

レジストリリダイレクトを有効にすると、フレームワークによって HKCR から **HKEY_CURRENT_USER**にアクセスできるようになります。 リダイレクトによって影響を受けるのは、MFC フレームワークと ATL フレームワークだけです。

既定の実装では、HKCR の下のレジストリにアクセスします。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxstat_

## <a name="afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a> AfxSetResourceHandle

この関数を使用して、アプリケーションの既定のリソースが読み込まれる場所を決定する HINSTANCE handle を設定します。

```cpp
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>パラメーター

*hInstResource*\
のインスタンスまたはモジュールハンドル。アプリケーションのリソースの読み込み元となる EXE または DLL ファイル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxshellmanager"></a><a name="afxshellmanager"></a> AfxShellManager

グローバル [シェルマネージャー](cshellmanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```cpp
CShellManager* afxShellManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxshellmanager

## <a name="afxsocketinit"></a><a name="afxsocketinit"></a> AfxSocketInit

`CWinApp::InitInstance`Windows ソケットを初期化するには、オーバーライドでこの関数を呼び出します。

```cpp
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>パラメーター

*lpwsaData*\
[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata)構造体へのポインター。 *LpwsaData*が NULL と等しくない場合、構造体のアドレス `WSADATA` はの呼び出しによって入力され `WSAStartup` ます。 また、この関数 `WSACleanup` は、アプリケーションが終了する前にが呼び出されるようにします。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

静的にリンクされた MFC アプリケーションでセカンダリスレッドで MFC ソケットを使用する場合は、ソケット `AfxSocketInit` ライブラリを初期化するためにソケットを使用する各スレッドでを呼び出す必要があります。 既定で `AfxSocketInit` は、はプライマリスレッドでのみ呼び出されます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxsock

## <a name="afxusertoolsmanager"></a><a name="afxusertoolsmanager"></a> AfxUserToolsManager

グローバル [ユーザーツールマネージャー](cusertoolsmanager-class.md)へのポインター。

### <a name="syntax"></a>構文

```cpp
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxusertoolsmanager

## <a name="afxwininit"></a><a name="afxwininit"></a> AfxWinInit

この関数は、 `WinMain` GUI ベースのアプリケーションの [CWinApp](../../mfc/reference/cwinapp-class.md) 初期化の一部として、mfc が提供する関数によって呼び出され、mfc を初期化します。

```cpp
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>パラメーター

*hInstance*\
現在実行中のモジュールのハンドル。

*hPrevInstance*\
アプリケーションの前のインスタンスを対象としたハンドル。 Win32 ベースのアプリケーションの場合、このパラメーターは常に **NULL**になります。

*lpCmdLine*\
は、アプリケーションのコマンドラインを指定する null で終わる文字列を指します。

*nCmdShow*\
GUI アプリケーションのメインウィンドウを表示する方法を指定します。

### <a name="remarks"></a>解説

MFC によって提供される関数を使用しないコンソールアプリケーションの場合は、を `WinMain` 直接呼び出して mfc を初期化する必要があり `AfxWinInit` ます。

自分でを呼び出す場合は `AfxWinInit` 、クラスのインスタンスを宣言する必要があり `CWinApp` ます。 コンソールアプリケーションでは、から独自のクラスを派生させずに、のインスタンスを直接使用することもでき `CWinApp` `CWinApp` ます。 この手法は、アプリケーションのすべての機能を **main**の実装に残しておく場合に適しています。

> [!NOTE]
> アセンブリのアクティベーションコンテキストを作成すると、MFC はユーザーモジュールによって提供されるマニフェストリソースを使用します。 アクティベーションコンテキストは、で作成され `AfxWinInit` ます。 詳細については、「 [MFC モジュール状態でのアクティベーションコンテキストのサポート](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)\
[CWinApp クラス](cwinapp-class.md)\
[CContextMenuManager クラス](ccontextmenumanager-class.md)\
[CWnd クラス](cwnd-class.md)\
[CFrameWndEx クラス](cframewndex-class.md)\
[CMFCToolBar クラス](cmfctoolbar-class.md)\
[Cのマネージャークラス](ckeyboardmanager-class.md)\
[CMenuTearOffManager クラス](cmenutearoffmanager-class.md)\
[CMouseManager クラス](cmousemanager-class.md)\
[CShellManager クラス](cshellmanager-class.md)\
[Cuserツールマネージャークラス](cusertoolsmanager-class.md)
