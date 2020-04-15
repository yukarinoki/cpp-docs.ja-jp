---
title: アプリケーションの情報と管理
description: MFC (MFC) アプリケーションの情報と管理機能への参照。
ms.date: 01/27/2020
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
ms.openlocfilehash: fc0b4b09f6c48da68bebe4a2825f49bcf6ab7e23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372498"
---
# <a name="application-information-and-management"></a>アプリケーションの情報と管理

アプリケーションを作成するときに、単一の[CWinApp](../../mfc/reference/cwinapp-class.md)派生オブジェクトを作成します。 派生オブジェクトの外部からこのオブジェクトに関する情報を`CWinApp`取得する場合があります。 または、他のグローバルな"マネージャ"オブジェクトへのアクセスが必要な場合もあります。

Microsoft Foundation クラス ライブラリには、これらのタスクを実行するのに役立つ次のグローバル関数が用意されています。

## <a name="application-information-and-management-functions"></a>アプリケーション情報と管理機能

|||
|-|-|
|[AfxBeginThread](#afxbeginthread)|新しいスレッドを作成します。|
|[メニューマネージャー](#afxcontextmenumanager)|グローバル コンテキスト[メニュー マネージャ](ccontextmenumanager-class.md)へのポインタ 。|
|[AfxEndThread](#afxendthread)|現在のスレッドを終了します。|
|[AfxFindResourceHandle](#afxfindresourcehandle)|リソース チェーンを走査し、リソース ID とリソースの種類別に特定のリソースを検索します。 |
|[AfxFreeLibrary](#afxfreelibrary)|読み込まれたダイナミック リンク ライブラリ (DLL) モジュールの参照カウントをデクリメントします。 参照カウントがゼロになると、モジュールはマップ解除されます。|
|[AfxGetApp](#afxgetapp)|アプリケーションの単一`CWinApp`オブジェクトへのポインターを返します。|
|[AfxGetAppName](#afxgetappname)|アプリケーション名を含む文字列を返します。|
|[AfxGetInstanceHandle](#afxgetinstancehandle)|アプリケーションのこのインスタンスを表す HINSTANCE を返します。|
|[AfxGetMainWnd](#afxgetmainwnd)|OLE アプリケーション以外の現在の "メイン" ウィンドウ、またはサーバー アプリケーションの埋め込みフレーム ウィンドウへのポインターを返します。|
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|この関数を使用して、アプリケーションがレジストリアクセスを**HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを決定します。|
|[AfxGetResourceHandle](#afxgetresourcehandle)|アプリケーションの既定のリソースのソースに HINSTANCE を返します。 アプリケーションのリソースに直接アクセスするために使用します。|
|[AfxGetThread](#afxgetthread)|現在の[CWinThread](../../mfc/reference/cwinthread-class.md)オブジェクトへのポインターを取得します。|
|[AfxInitRichEdit](#afxinitrichedit)|アプリケーションのバージョン 1.0 リッチ エディット コントロールを初期化します。|
|[AfxInitRichEdit2](#afxinitrichedit2)|アプリケーションのバージョン 2.0 以降のリッチ エディット コントロールを初期化します。|
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。|
|[AfxIsMFCToolBar](#afxismfctoolbar)|指定したウィンドウがツール バー オブジェクトかどうかを判断します。|
|[アfx キーボード マネージャー](#afxkeyboardmanager)|グローバル キーボード[マネージャー](ckeyboardmanager-class.md)へのポインター 。|
|[AfxLoadLibrary](#afxloadlibrary)|DLL モジュールを割り当て、DLL 関数のアドレスを取得するために使用できるハンドルを返します。|
|[アfx ロードライブラリ](#afxloadlibraryex)|指定されたオプションを使用して DLL モジュールを割り当て、DLL 関数のアドレスを取得するために使用できるハンドルを返します。|
|[アfxメニューティアオフマネージャー](#afxmenutearoffmanager)|グローバル[ティアオフ メニュー マネージャ](cmenutearoffmanager-class.md)へのポインタ 。|
|[アfxマウスマネージャー](#afxmousemanager)|グローバル マウス[マネージャ](cmousemanager-class.md)へのポインタ 。|
|[AfxRegisterClass](#afxregisterclass)|MFC を使用する DLL にウィンドウ クラスを登録します。|
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC によって自動的に登録されたウィンドウ クラスを補足する Windows ウィンドウ クラスを登録します。|
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|アプリケーションがレジストリへのアクセスを**HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを設定します。|
|[AfxSetResourceHandle](#afxsetresourcehandle)|アプリケーションの既定のリソースが読み込まれる場所の HINSTANCE ハンドルを設定します。|
|[アfxシェルマネージャー](#afxshellmanager)|グローバル シェル[マネージャ](cshellmanager-class.md)へのポインタ 。 |
|[AfxSocketInit](#afxsocketinit)|オーバーライドで呼`CWinApp::InitInstance`び出され、Windows ソケットを初期化します。|
|[アfxユーザーツールマネージャー](#afxusertoolsmanager)|グローバル ユーザー[ツール マネージャ](cusertoolsmanager-class.md)へのポインタ 。|
|[AfxWinInit](#afxwininit)|MFC を初期化するために、GUI ベースのアプリケーションの`WinMain`[CWinApp](../../mfc/reference/cwinapp-class.md)初期化の一部として、MFC 提供の関数によって呼び出されます。 MFC を使用するコンソール アプリケーションに対して直接呼び出す必要があります。|

## <a name="afxbeginthread"></a><a name="afxbeginthread"></a>を行う

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

*を実行します。*\
ワーカー スレッドの制御関数をポイントします。 ポインターを NULL にすることはできません。 この関数は次のように宣言する必要があります。

`UINT __cdecl MyControllingFunction( LPVOID pParam );`

*クラス*\
[から](../../mfc/reference/cwinthread-class.md)派生したオブジェクトのRUNTIME_CLASS。

*pパラム*\
制御関数に渡すパラメーター。

*n優先順位*\
スレッドに設定する優先順位。 利用可能な優先順位の完全な一覧と説明については、Windows SDK の[SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority)を参照してください。

*スタックサイズ*\
新しいスレッドへのスタックのバイト サイズを指定します。 0 である場合、スタック サイズの既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。

*フラグを作成します。*\
スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。

- CREATE_SUSPENDED 中断カウント 1 でスレッドを開始します。 m_bAutoDeleteや派生クラスのメンバーなど、`CWinThread`オブジェクトのメンバー データを初期化する[m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete)場合は、CREATE_SUSPENDEDを使用して、スレッドの実行を開始します。 初期化が完了したら[、CWinThread::ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread)を使用してスレッドの実行を開始します。 スレッドは呼び出されるまで`CWinThread::ResumeThread`実行されません。

- **0**作成後すぐにスレッドを開始します。

*セキュリティアトルス*\
スレッドのセキュリティ属性を指定する[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\))構造体へのポイント。 NULL の場合、作成スレッドと同じセキュリティー属性が使用されます。 この構造体の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

エラーが発生した場合、新しく作成されたスレッドのオブジェクトまたは NULL をポイントします。

### <a name="remarks"></a>解説

`AfxBeginThread` の最初のフォームはワーカー スレッドを作成します。 2 番目のフォームは、ユーザー インターフェイス スレッドまたはワーカー スレッドとして機能可能なスレッドを作成します。

`AfxBeginThread`新`CWinThread`しいオブジェクトを作成し、[その CreateThread](../../mfc/reference/cwinthread-class.md#createthread)関数を呼び出してスレッドの実行を開始し、スレッドへのポインターを返します。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。 スレッドを終了するには、スレッド内から[AfxEndThread](#afxendthread)を呼び出すか、ワーカー スレッドの制御関数から戻ります。

マルチスレッドは、アプリケーションによって有効化される必要があります。それ以外の場合、この関数は失敗します。 マルチスレッドを有効にする方法の詳細については、「 [/MD、 /MT、/LD (ランタイム ライブラリを使用する) 」](../../build/reference/md-mt-ld-use-run-time-library.md)を参照してください。

詳細については、「[マルチスレッド : ワーカー スレッドの作成](../../parallel/multithreading-creating-worker-threads.md)とマルチスレッド[: ユーザー インターフェイス スレッドの作成](../../parallel/multithreading-creating-user-interface-threads.md)」を参照してください。 `AfxBeginThread`

### <a name="example"></a>例

[CSocket::アタッチ](../../mfc/reference/csocket-class.md#attach)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxcontextmenumanager"></a><a name="afxcontextmenumanager"></a>メニューマネージャー

グローバル コンテキスト[メニュー マネージャ](ccontextmenumanager-class.md)へのポインタ 。

### <a name="syntax"></a>構文

```cpp
CContextMenuManager* afxContextMenuManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxcontextmenumanager.h

## <a name="afxendthread"></a><a name="afxendthread"></a>アfxエンドスレッド

現在実行中のスレッドを終了します。

```cpp
void AFXAPI AfxEndThread(
    UINT nExitCode,
    BOOL bDelete  = TRUE);
```

### <a name="parameters"></a>パラメーター

*コードを終了します。*\
スレッドの終了コードを指定します。

*b削除*\
スレッド オブジェクトをメモリから削除します。

### <a name="remarks"></a>解説

終了するスレッド内から呼び出す必要があります。

`AfxEndThread`の詳細については、「[マルチスレッド : スレッドの終了](../../parallel/multithreading-terminating-threads.md)」を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxfindresourcehandle"></a><a name="afxfindresourcehandle"></a>ハンドルを見つける

リソース`AfxFindResourceHandle`チェーンを走査し、リソース ID とリソースの種類によって特定のリソースを検索するために使用します。

### <a name="syntax"></a>構文

```cpp
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*\
リソース ID を含む文字列へのポインター。
*lpsz タイプ*\
リソースの種類へのポインター。 リソースの種類の一覧については、Windows SDK[の「リソースの検索](/windows/win32/api/winbase/nf-winbase-findresourcea)」を参照してください。

### <a name="return-value"></a>戻り値

リソースを含むモジュールへのハンドル。

### <a name="remarks"></a>解説

`AfxFindResourceHandle`特定のリソースを検索し、リソースを含むモジュールへのハンドルを返します。 リソースは、読み込まれている MFC 拡張 DLL に含まれている可能性があります。 `AfxFindResourceHandle`は、リソースを持っているユーザーを示します。

モジュールは次の順序で検索されます。

1. メイン モジュール (MFC 拡張 DLL の場合)。

1. システム モジュール以外。

1. 言語固有のモジュール。

1. メインモジュール (システム DLL の場合)。

1. システム モジュール。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="afxfreelibrary"></a><a name="afxfreelibrary"></a>アfxフリーライブラリ

また`AfxFreeLibrary`、`AfxLoadLibrary`ロードされた各ライブラリ モジュールの参照カウントを維持します。

```cpp
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib);
```

### <a name="parameters"></a>パラメーター

*再び*\
読み込まれたライブラリ モジュールのハンドル。 [このハンドルを](#afxloadlibrary)返します。

### <a name="return-value"></a>戻り値

関数が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

`AfxFreeLibrary`読み込まれたダイナミック リンク ライブラリ (DLL) モジュールの参照カウントをデクリメントします。 参照カウントがゼロになると、モジュールは呼び出し元プロセスのアドレス・スペースからマップ解除され、ハンドルは無効になります。 この参照カウントは、呼び出`AfxLoadLibrary`されるたびにインクリメントされます。

ライブラリ モジュールの割り当てを解除する前に、システムは DLL を使用するプロセスから DLL をデタッチできるようにします。 これにより、DLL は現在のプロセスに割り当てられたリソースをクリーンアップできます。 エントリポイント関数が戻ると、ライブラリ モジュールは現在のプロセスのアドレス空間から削除されます。

DLL`AfxLoadLibrary`モジュールをマップするために使用します。

アプリケーションで複数の`AfxFreeLibrary`スレッド`AfxLoadLibrary`を使用する場合は、必ず`FreeLibrary` `LoadLibrary`、Win32 関数と () の代わりに 、 を使用してください。 MFC `AfxLoadLibrary` `AfxFreeLibrary`拡張 DLL の読み込みとアンロード時に実行されるスタートアップ コードとシャットダウン コードを使用して、グローバルな MFC 状態を破損させないようにします。

### <a name="example"></a>例

[AfxLoad ライブラリ](#afxloadlibrary)の例を参照してください。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_.h

## <a name="afxgetapp"></a><a name="afxgetapp"></a>AfxGetApp

この関数によって返されるポインターを使用して、メイン メッセージ ディスパッチ コードや最上位ウィンドウなどのアプリケーション情報にアクセスできます。

```cpp
CWinApp* AFXAPI AfxGetApp();
```

### <a name="return-value"></a>戻り値

アプリケーションの単一`CWinApp`オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドが NULL を返す場合、アプリケーションのメイン ウィンドウがまだ完全に初期化されていないことを示している可能性があります。 また、問題を示している可能性もあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetappname"></a><a name="afxgetappname"></a>アfxゲットアプリ名

返される文字列は、診断メッセージに使用することも、一時文字列名のルートとして使用することもできます。

```cpp
LPCTSTR AFXAPI AfxGetAppName();
```

### <a name="return-value"></a>戻り値

アプリケーション名を含む null で終わる文字列。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetinstancehandle"></a><a name="afxgetinstancehandle"></a>ハンドル

この関数を使用すると、現在のアプリケーションのインスタンス ハンドルを取得できます。

```cpp
HINSTANCE  AFXAPI AfxGetInstanceHandle();
```

### <a name="return-value"></a>戻り値

アプリケーションの現在のインスタンスへの HINSTANCE。 USRDLL バージョンの MFC にリンクされている DLL 内から呼び出された場合は、DLL に対する HINSTANCE が返されます。

### <a name="remarks"></a>解説

`AfxGetInstanceHandle`常に実行可能ファイル (.EXE) は、MFC の USRDLL バージョンにリンクされている DLL 内から呼び出されていない限りです。 この場合、DLL に H インスタンスを返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetmainwnd"></a><a name="afxgetmainwnd"></a>アfxゲットメインウンド

アプリケーションが OLE サーバーの場合は、アプリケーションのアクティブなメイン ウィンドウへのポインターを取得するには、この関数を呼び出します。 アプリケーション オブジェクトの[m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd)メンバーを直接参照するのではなく、この結果を使用します。

```cpp
CWnd* AFXAPI AfxGetMainWnd();
```

### <a name="return-value"></a>戻り値

サーバーにアクティブなコンテナー内で埋め込みオブジェクトがアクティブな場合、埋め込みオブジェクトを含むフレーム ウィンドウ オブジェクトへのポインターを返します。

コンテナー内で埋め込みオブジェクトがアクティブでない場合、またはアプリケーションが OLE サーバーでない場合、この関数はアプリケーション オブジェクトの*m_pMainWnd*を返します。

`AfxGetMainWnd` をアプリケーションのプライマリ スレッドから呼び出した場合は、上記の規則に従ってアプリケーションのメイン ウィンドウを返します。 アプリケーションのセカンダリ スレッドからこの関数を呼び出した場合は、関数は呼び出しを行ったスレッドに関連付けられているメイン ウィンドウを返します。

### <a name="remarks"></a>解説

アプリケーションが OLE サーバーでない場合、この関数を呼び出すことは、アプリケーション オブジェクトの*m_pMainWnd*メンバーを直接参照することと同じです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetperuserregistration"></a><a name="afxgetperuserregistration"></a>ユーザー登録

この関数を使用して、アプリケーションがレジストリアクセスを**HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを決定します。

```cpp
BOOL AFXAPI AfxGetPerUserRegistration();
```

### <a name="return-value"></a>戻り値

TRUE は、レジストリ情報が HKCU ノードに送信されたことを示します。 FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込む場合に示します。 デフォルトのノードは**HKEY_CLASSES_ROOT** (**HKCR**) です。

### <a name="remarks"></a>解説

レジストリ リダイレクトを有効にすると、フレームワークは**HKCR**から**HKEY_CURRENT_USER\Software\Classes**にアクセスをリダイレクトします。 リダイレクトの影響を受けるのは、MFC フレームワークと ATL フレームワークだけです。

アプリケーションがレジストリ アクセスをリダイレクトするかどうかを変更するには[、AfxSetPerUserRegistration](#afxsetperuserregistration)を使用します。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxstat_.h

## <a name="afxgetresourcehandle"></a><a name="afxgetresourcehandle"></a>ハンドルを取得します。

この関数によって返される HINSTANCE ハンドルを使用して、たとえば Windows 関数の呼び出しなどでアプリケーション`FindResource`のリソースに直接アクセスします。

```cpp
extern HINSTANCE  AfxGetResourceHandle();
```

### <a name="return-value"></a>戻り値

アプリケーションの既定のリソースが読み込まれる HINSTANCE ハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxgetthread"></a><a name="afxgetthread"></a>を行う

現在実行中のスレッドを表す[CWinThread](../../mfc/reference/cwinthread-class.md)オブジェクトへのポインターを取得します。

```cpp
CWinThread* AfxGetThread();
```

### <a name="return-value"></a>戻り値

現在実行中のスレッドへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

スレッド内から呼び出す必要があります。

> [!NOTE]
> Visual C++ バージョン 4.2、5.0、または 6.0 から呼び出しを行う`AfxGetThread`MFC プロジェクトを移植する場合は、`AfxGetThread`スレッドが見つからない場合は[AfxGetApp](#afxgetapp)を呼び出します。 コンパイラの新しいバージョンでは、`AfxGetThread`スレッドが見つからなかった場合は NULL を返します。 アプリケーション スレッドが必要な場合は、`AfxGetApp`を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxinitrichedit"></a><a name="afxinitrichedit"></a>アfxイニトリリッチエディット

アプリケーションのリッチ エディット コントロール (バージョン 1.0) を初期化します。

```cpp
BOOL AFXAPI AfxInitRichEdit();
```

### <a name="remarks"></a>解説

この関数は、下位互換性を保つために用意されています。 新しいアプリケーションでは[AfxInitRichEdit2](#afxinitrichedit2)を使用する必要があります。

`AfxInitRichEdit`を読み込みます。DLL を使用して、リッチ エディット コントロールのバージョン 1.0 を初期化します。 リッチ エディット コントロールのバージョン 2.0 および 3.0 を使用するには、RICHED20 を使用します。DLL を読み込む必要があります。 これは[、AfxInitRichEdit2](#afxinitrichedit2)への呼び出しを行うことによって読み込まれます。

既存の Visual C++ アプリケーションのリッチ エディット コントロールをバージョン 2.0 に更新するには、 を開きます。RC ファイルをテキストとして、各リッチ エディット コントロールのクラス名を "RICHEDIT" から "RichEdit20a" に変更します。 次に、 の`AfxInitRichEdit`呼`AfxInitRichEdit2`び出しを に置き換えます。

この関数は、プロセスに対してライブラリがまだ初期化されていない場合は、コモン コントロール ライブラリも初期化します。 MFC アプリケーションからリッチ エディット コントロールを直接使用する場合は、この関数を呼び出して、MFC がリッチ エディット コントロール ランタイムを適切に初期化したことを確認します。 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)の`Create`メソッドを呼び出す場合は、通常、この関数を呼び出す必要はありませんが、場合によっては必要な場合があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxinitrichedit2"></a><a name="afxinitrichedit2"></a>アプシニトリトリエディット2

アプリケーションのリッチ エディット コントロール (バージョン 2.0 以降) を初期化します。

```cpp
BOOL AFXAPI AfxInitRichEdit2();
```

### <a name="remarks"></a>解説

RICHED20 を読み込むには、この関数を呼び出します。DLL を使用して、リッチ エディット コントロールのバージョン 2.0 を初期化します。 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)の`Create`メソッドを呼び出す場合は、通常、この関数を呼び出す必要はありませんが、場合によっては必要な場合があります。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxisextendedframeclass"></a><a name="afxisextendedframeclass"></a>拡張されたフレーム クラス

指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。

### <a name="syntax"></a>構文

```cpp
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );
```

### <a name="parameters"></a>パラメーター

*Pwnd*\
[in]から`CWnd`派生したオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

指定されたウィンドウが拡張フレーム オブジェクトである場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*pWnd*が次のいずれかのクラスから派生する場合、このメソッドは TRUE を返します。

- `CFrameWndEx`

- `CMDIFrameWndEx`

- `COleIPFrameWndEx`

- `COleDocIPFrameWndEx`

- `CMDIChildWndEx`

このメソッドは、関数またはメソッドのパラメーターが拡張フレーム ウィンドウであるかどうかを検証する必要があるときに役立ちます。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxismfctoolbar"></a><a name="afxismfctoolbar"></a>アビスMFCツールバー

指定したウィンドウがツール バー オブジェクトかどうかを判断します。

### <a name="syntax"></a>構文

```cpp
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*\
[in]から`CWnd`派生したオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

指定されたウィンドウがツール バー オブジェクトの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*pWnd*が から`CMFCToolBar`派生した場合、このメソッドは返します。 `TRUE` このメソッドは、関数またはメソッドのパラメーターがオブジェクトであることを検証する必要がある場合`CMFCToolBar`に便利です。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxpriv.h

## <a name="afxkeyboardmanager"></a><a name="afxkeyboardmanager"></a>アfx キーボード マネージャー

グローバル キーボード[マネージャー](ckeyboardmanager-class.md)へのポインター 。

### <a name="syntax"></a>構文

```cpp
CKeyboardManager* afxKeyboardManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxキーボードマネージャー.h

## <a name="afxloadlibrary"></a><a name="afxloadlibrary"></a>Afx ロードライブラリ

DLL`AfxLoadLibrary`モジュールをマップするために使用します。

```cpp
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName);
```

### <a name="parameters"></a>パラメーター

*モジュール名*\
モジュールの名前を含む null で終わる文字列を指します 。DLL または .EXE ファイル)。 指定された名前はモジュールのファイル名です。

文字列がパスを指定し、指定したディレクトリにファイルが存在しない場合、関数は失敗します。

パスが指定されておらず、ファイル名拡張子を省略した場合、既定の拡張子が .DLL が追加されます。 ただし、ファイル名文字列には、モジュール名に拡張子がないことを示す末尾の文字 (.) を含めることができます。 パスを指定しない場合、この関数は[デスクトップ アプリケーションの検索順序を使用します](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はモジュールへのハンドルになります。 失敗した場合、戻り値は NULL です。

### <a name="remarks"></a>解説

DLL 関数のアドレスを取得するために[GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)で使用できるハンドルを返します。 `AfxLoadLibrary`他の実行可能モジュールをマップするためにも使用できます。

各プロセスは、ロードされた各ライブラリ モジュールの参照カウントを保持します。 この参照カウントは、呼`AfxLoadLibrary`び出されるたびにインクリメントされ、呼び出されるたびに`AfxFreeLibrary`減分されます。 参照カウントがゼロになると、モジュールは呼び出し元プロセスのアドレス・スペースからマップ解除され、ハンドルは無効になります。

アプリケーションが複数の`AfxLoadLibrary`スレッド`AfxFreeLibrary`を使用し、MFC 拡張`LoadLibrary`DLL`FreeLibrary`を動的に読み込む場合は、必ず Win32 関数および () の代わりに 、 を使用してください。 MFC 拡張 DLL が読み込まれ、アンロードされたときに実行されるスタートアップ コードとシャットダウン コードを使用`AfxLoadLibrary`して保証します。 `AfxFreeLibrary`

アプリケーション`AfxLoadLibrary`で使用するには、DLL バージョンの MFC に動的にリンクする必要があります。 Afxdll_.h`AfxLoadLibrary`のヘッダー ファイルは、MFC が DLL としてアプリケーションにリンクされている場合にのみ含まれます。 この要件は、MFC の DLL バージョンにリンクして MFC 拡張 DLL を使用または作成する必要があるため、仕様です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_.h

## <a name="afxloadlibraryex"></a><a name="afxloadlibraryex"></a>アfx ロードライブラリ

DLL`AfxLoadLibraryEx`モジュールをマップするために使用します。

```cpp
HINSTANCE AFXAPI AfxLoadLibraryEx(LPCTSTR lpFileName, HANDLE hFile, DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*ファイル名*\
モジュールの名前を含む null で終わる文字列を指します 。DLL または .EXE ファイル)。 指定された名前はモジュールのファイル名です。

文字列がパスを指定し、指定したディレクトリにファイルが存在しない場合、関数は失敗します。

パスが指定されておらず、ファイル名拡張子を省略した場合、既定の拡張子が .DLL が追加されます。 ただし、ファイル名文字列には、モジュール名に拡張子がないことを示す末尾の文字 (.) を含めることができます。 パスを指定しない場合、この関数は[デスクトップ アプリケーションの検索順序を使用します](/windows/win32/dlls/dynamic-link-library-search-order#search-order-for-desktop-applications)。

*hファイル*\
このパラメーターは将来使用するために予約されています。 NULL である必要があります。

*Dwflags*\
モジュールの読み込み時に実行されるアクション。 フラグを指定しない場合、この関数の動作は`AfxLoadLibrary`関数と同じです。 このパラメーターの可能な値については[、LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)ドキュメントで説明します。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はモジュールへのハンドルになります。 失敗した場合、戻り値は NULL です。

### <a name="remarks"></a>解説

`AfxLoadLibraryEx`DLL 関数のアドレスを取得するために[GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)で使用できるハンドルを返します。 `AfxLoadLibraryEx`他の実行可能モジュールをマップするためにも使用できます。

各プロセスは、ロードされた各ライブラリ モジュールの参照カウントを保持します。 この参照カウントは、呼`AfxLoadLibraryEx`び出されるたびにインクリメントされ、呼び出されるたびに`AfxFreeLibrary`減分されます。 参照カウントがゼロになると、モジュールは呼び出し元プロセスのアドレス・スペースからマップ解除され、ハンドルは無効になります。

アプリケーションが複数の`AfxLoadLibraryEx`スレッド`AfxFreeLibrary`を使用し、MFC 拡張`LoadLibraryEx`DLL`FreeLibrary`を動的に読み込む場合は、必ず Win32 関数と () の代わりに、 と を使用してください。 MFC `AfxLoadLibraryEx` `AfxFreeLibrary`拡張 DLL の読み込みとアンロード時に実行されるスタートアップ コードとシャットダウン コードを使用して、グローバルな MFC 状態を破損させないようにします。

アプリケーション`AfxLoadLibraryEx`で使用するには、DLL バージョンの MFC に動的にリンクする必要があります。 Afxdll_.h`AfxLoadLibraryEx`のヘッダー ファイルは、MFC が DLL としてアプリケーションにリンクされている場合にのみ含まれます。 この要件は、MFC の DLL バージョンにリンクして MFC 拡張 DLL を使用または作成する必要があるため、仕様です。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxdll_.h

## <a name="afxmenutearoffmanager"></a><a name="afxmenutearoffmanager"></a>アfxメニューティアオフマネージャー

グローバル[ティアオフ メニュー マネージャ](cmenutearoffmanager-class.md)へのポインタ 。

### <a name="syntax"></a>構文

```cpp
CMenuTearOffManager* g_pTearOffMenuManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmenuティアオフマネージャー.h

## <a name="afxmousemanager"></a><a name="afxmousemanager"></a>アfxマウスマネージャー

グローバル マウス[マネージャ](cmousemanager-class.md)へのポインタ 。

### <a name="syntax"></a>構文

```cpp
CMouseManager* afxMouseManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmousemanager.h

## <a name="afxregisterclass"></a><a name="afxregisterclass"></a>クラス

この関数を使用して、MFC を使用する DLL にウィンドウ クラスを登録します。

```cpp
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass);
```

### <a name="parameters"></a>パラメーター

*クラスを選択します。*\
登録するウィンドウ クラスに関する情報を含む[WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)構造体へのポインター。 この構造体の詳細については、Windows SDK を参照してください。

### <a name="return-value"></a>戻り値

クラスが正常に登録された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数を使用すると、DLL がアンロードされるときにクラスが自動的に登録解除されます。

DLL 以外のビルドでは、`AfxRegisterClass`アプリケーションに登録されたクラスが自動的に登録解除されるため、`RegisterClass`識別子は Windows 関数にマップするマクロとして定義されます。 の代わりに`AfxRegisterClass``RegisterClass`を使用する場合、アプリケーションと DLL の両方で変更せずにコードを使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxregisterwndclass"></a><a name="afxregisterwndclass"></a>クラス

独自のウィンドウ クラスを登録できます。

```cpp
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,
    HCURSOR hCursor = 0,
    HBRUSH hbrBackground = 0,
    HICON hIcon = 0);
```

### <a name="parameters"></a>パラメーター

*nクラススタイル*\
ウィンドウ クラスのビットごとの OR (**&#124;**) 演算子を使用して作成される、Windows クラス のスタイルまたはスタイルの組み合わせを指定します。 クラス スタイルの一覧については、Windows SDK の[WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)構造体を参照してください。 NULL の場合、デフォルトは次のように設定されます。

- マウスのスタイルをCS_DBLCLKSに設定します。

- 矢印カーソルスタイルを Windows 標準IDC_ARROWに設定します。

- 背景ブラシを NULL に設定して、ウィンドウの背景を消去しません。

- アイコンを標準の波打ちフラグの Windows ロゴ アイコンに設定します。

*カーソル*\
ウィンドウ クラスから作成された各ウィンドウにインストールするカーソル リソースへのハンドルを指定します。 既定値の**0**を使用すると、標準のIDC_ARROW カーソルが表示されます。

*hbr背景*\
ウィンドウ クラスから作成された各ウィンドウにインストールするブラシ リソースへのハンドルを指定します。 既定値の**0**を使用すると、背景ブラシは NULL になり、既定では[、WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)の処理中にウィンドウの背景が消去されることはありません。

*Hicon*\
ウィンドウ クラスから作成された各ウィンドウにインストールするアイコン リソースへのハンドルを指定します。 既定値の**0**を使用すると、Windows ロゴ アイコンに対する標準のフラグが表示されます。

### <a name="return-value"></a>戻り値

クラス名を含む null で終わる文字列。 このクラス名をメンバー関数に渡`Create`すか、他`CWnd`の**CWnd-** 派生クラスに渡してウィンドウを作成できます。 名前は、Microsoft ファウンデーション クラス ライブラリによって生成されます。

> [!NOTE]
> 戻り値は、静的バッファーへのポインターです。 この文字列を保存するには、`CString`変数に代入します。

### <a name="remarks"></a>解説

Microsoft Foundation クラス ライブラリでは、いくつかの標準ウィンドウ クラスが自動的に登録されます。 独自のウィンドウ クラスを登録する場合は、この関数を呼び出します。

クラスに登録される名前は、`AfxRegisterWndClass`パラメータのみに依存します。 同一の`AfxRegisterWndClass`パラメータを使用して複数回呼び出すと、最初の呼び出しでクラスが登録されるだけです。 同じパラメーター`AfxRegisterWndClass`を使用して以降の呼び出しは、既に登録済みのクラス名を返します。

同じパラメーター`AfxRegisterWndClass`を持つ複数の CWnd 派生クラスを呼び出す場合、各クラスは同じウィンドウ クラスを共有します。 この共有は、CS_CLASSDCクラス スタイルを使用すると問題を引き起こす可能性があります。 複数のウィンドウ クラスCS_CLASSDCではなく、最終的に 1 つのCS_CLASSDCウィンドウ クラスが作成されます。 そのクラスを使用するすべての C++ ウィンドウは、同じ DC を共有します。 この問題を回避するには、[クラスを登録する AfxRegister クラス](#afxregisterclass)を呼び出します。

ウィンドウクラス登録と機能の詳細については、テクニカルノート[TN001: ウィンドウクラス登録](../../mfc/tn001-window-class-registration.md)を`AfxRegisterWndClass`参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxsetperuserregistration"></a><a name="afxsetperuserregistration"></a>ユーザー登録

アプリケーションがレジストリへのアクセスを**HKEY_CURRENT_USER** (**HKCU**) ノードにリダイレクトするかどうかを設定します。

```cpp
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*\
[in]TRUE は、レジストリ情報が HKCU ノードに送信されたことを示します。 FALSE は、アプリケーションがレジストリ情報を既定のノードに書き込む場合に示します。 デフォルトのノードは**HKEY_CLASSES_ROOT** (**HKCR**) です。

### <a name="remarks"></a>解説

Windows Vista より前は、レジストリにアクセスするアプリケーションでは **、HKEY_CLASSES_ROOT**ノードが一般的に使用されました。 ただし、Windows Vista 以降のオペレーティング システムでは、アプリケーションを昇格モードで実行して HKCR に書き込む必要があります。

このメソッドを使用すると、アプリケーションは、管理者特権モードで実行せずにレジストリの読み取りと書き込みを行うことができます。 これは、HKCR から HKCU にレジストリ アクセスをリダイレクトすることで動作します。 詳細については、「[リンカープロパティ ページ](../../build/reference/linker-property-pages.md)」を参照してください。

レジストリ リダイレクトを有効にすると、フレームワークは HKCR から**HKEY_CURRENT_USER\Software\Classes**にアクセスをリダイレクトします。 リダイレクトの影響を受けるのは、MFC フレームワークと ATL フレームワークだけです。

既定の実装は、HKCR の下のレジストリにアクセスします。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxstat_.h

## <a name="afxsetresourcehandle"></a><a name="afxsetresourcehandle"></a>リソースハンドル

この関数を使用して、アプリケーションの既定のリソースが読み込まれる場所を決定する HINSTANCE ハンドルを設定します。

```cpp
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);
```

### <a name="parameters"></a>パラメーター

*リソース*\
インスタンスまたはモジュール ハンドルを .アプリケーションのリソースが読み込まれる EXE ファイルまたは DLL ファイル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxshellmanager"></a><a name="afxshellmanager"></a>アfxシェルマネージャー

グローバル シェル[マネージャ](cshellmanager-class.md)へのポインタ 。

### <a name="syntax"></a>構文

```cpp
CShellManager* afxShellManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxshellmanager.h

## <a name="afxsocketinit"></a><a name="afxsocketinit"></a>Afxソケットイニット

オーバーライドでこの関数を`CWinApp::InitInstance`呼び出して、Windows ソケットを初期化します。

```cpp
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);
```

### <a name="parameters"></a>パラメーター

*データ*\
[WSADATA](/windows/win32/api/winsock2/ns-winsock2-wsadata)構造体へのポインター。 *lpwsaData*が NULL でない場合、`WSADATA`構造体のアドレスは 呼び出しによって埋められます`WSAStartup`。 この関数は、アプリケーション`WSACleanup`が終了する前に呼び出されるかどうかを確認します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用する`AfxSocketInit`場合は、ソケット ライブラリを初期化するためにソケットを使用する各スレッドで呼び出す必要があります。 デフォルトでは、`AfxSocketInit`プライマリ スレッドでのみ呼び出されます。

### <a name="requirements"></a>必要条件

  **ヘッダー** afxsock.h

## <a name="afxusertoolsmanager"></a><a name="afxusertoolsmanager"></a>アfxユーザーツールマネージャー

グローバル ユーザー[ツール マネージャ](cusertoolsmanager-class.md)へのポインタ 。

### <a name="syntax"></a>構文

```cpp
CUserToolsManager* afxUserToolsManager;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxuser ツールマネージャー.h

## <a name="afxwininit"></a><a name="afxwininit"></a>アfxWinInit

この関数は、MFC を初期化するために`WinMain`、GUI ベースのアプリケーションの[CWinApp](../../mfc/reference/cwinapp-class.md)初期化の一部として、MFC 提供の関数によって呼び出されます。

```cpp
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,
    HINSTANCE hPrevInstance,
    LPTSTR lpCmdLine,
    int nCmdShow);
```

### <a name="parameters"></a>パラメーター

*Hinstance*\
現在実行中のモジュールのハンドル。

*インスタンス*\
アプリケーションの前のインスタンスへのハンドル。 Win32 ベースのアプリケーションの場合、このパラメータは常に**NULL です**。

*ライン*\
アプリケーションのコマンド ラインを指定する null で終わる文字列を指します。

*をクリックします。*\
GUI アプリケーションのメインウィンドウの表示方法を指定します。

### <a name="remarks"></a>解説

MFC 提供`WinMain`の関数を使用しないコンソール アプリケーションの場合は、MFC を初期化`AfxWinInit`するために直接呼び出す必要があります。

自分自身を呼`AfxWinInit`び出す場合は、クラスのインスタンス`CWinApp`を宣言する必要があります。 コンソール アプリケーションの場合、独自のクラスを派生させず`CWinApp`、代わりに直接の`CWinApp`インスタンスを使用することもできます。 この方法は、main**の実装**でアプリケーションのすべての機能をそのままにする場合に適しています。

> [!NOTE]
> MFC は、アセンブリのアクティブ化コンテキストを作成するときに、ユーザー モジュールによって提供されるマニフェスト リソースを使用します。 アクティベーション コンテキストは で`AfxWinInit`作成されます。 詳細については、「 [MFC モジュールの状態でのアクティブ化コンテキストのサポート](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="see-also"></a>関連項目

[マクロとグローバル](mfc-macros-and-globals.md)\
[CWinAppクラス](cwinapp-class.md)\
[クラス](ccontextmenumanager-class.md)\
[CWndクラス](cwnd-class.md)\
[クラス](cframewndex-class.md)\
[クラス](cmfctoolbar-class.md)\
[クラス](ckeyboardmanager-class.md)\
[クラス](cmenutearoffmanager-class.md)\
[クラス](cmousemanager-class.md)\
[クラス](cshellmanager-class.md)\
[クラス](cusertoolsmanager-class.md)
