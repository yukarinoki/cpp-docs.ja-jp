---
title: アプリケーションの情報と管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41b6aa602956c6dcdeda8f6b8c24c1be48c58ce2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358483"
---
# <a name="application-information-and-management"></a>アプリケーションの情報と管理
1 つを作成するアプリケーションを作成するときに[CWinApp](../../mfc/reference/cwinapp-class.md)-派生オブジェクト。 ときに、外部からこのオブジェクトに関する情報を取得することがあります、 `CWinApp`-派生オブジェクト。 または、他のグローバル「マネージャー」のオブジェクトにアクセスする必要があります。
  
 Microsoft Foundation Class ライブラリでは、これらのタスクを達成するために、次のグローバル関数を提供します。  
  
### <a name="application-information-and-management-functions"></a>アプリケーションの情報と管理機能  
  
|||  
|-|-|  
|[AfxBeginThread](#afxbeginthread)|新しいスレッドを作成します。|  
|[AfxContextMenuManager](#afxcontextmenumanager)|グローバルへのポインター[コンテキスト メニュー マネージャー](ccontextmenumanager-class.md)です。|
|[AfxEndThread](#afxendthread)|現在のスレッドを終了します。|  
|[AfxFindResourceHandle](#afxfindresourcehandle)|リソース チェーンについて説明し、特定のリソースのリソース ID とリソースの種類を探します。 |
|[AfxFreeLibrary](#afxfreelibrary)|読み込まれたダイナミック リンク ライブラリ (DLL) モジュールの参照カウントをデクリメント参照カウントが 0 になったときに、モジュールはマップされています。|  
|[AfxGetApp](#afxgetapp)|アプリケーションへのポインターの 1 つを返します`CWinApp`オブジェクト。|  
|[AfxGetAppName](#afxgetappname)|アプリケーションの名前を含む文字列を返します。|  
|[AfxGetInstanceHandle](#afxgetinstancehandle)|返します、`HINSTANCE`アプリケーションのこのインスタンスを表すです。|  
|[AfxGetMainWnd](#afxgetmainwnd)|非 OLE アプリケーションの現在の"main"ウィンドウまたはサーバー アプリケーションの埋め込み先フレーム ウィンドウへのポインターを返します。|  
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|この関数を使用して、アプリケーションがレジストリ アクセスをリダイレクトするかどうかを判断、 **HKEY_CURRENT_USER** ( **HKCU**) ノード。|  
|[AfxGetResourceHandle](#afxgetresourcehandle)|返します、`HINSTANCE`アプリケーションの既定のリソースのソースにします。 アプリケーションのリソースに直接アクセスするのにには、これを使用します。|  
|[AfxGetThread](#afxgetthread)|現在のポインターを取得[CWinThread](../../mfc/reference/cwinthread-class.md)オブジェクト。|  
|[AfxInitRichEdit](#afxinitrichedit)|Version 1.0 のリッチ エディット コントロール、アプリケーションを初期化します。|  
|[AfxInitRichEdit2](#afxinitrichedit2)|Version 2.0 以降のリッチ エディット コントロール、アプリケーションを初期化します。| 
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。|
|[AfxIsMFCToolBar](#afxismfctoolbar)|指定されたウィンドウがツール バー オブジェクトであるかどうかを判断します。|
|[AfxKeyboardManager](#afxkeyboardmanager)|グローバルへのポインター[キーボード マネージャー](ckeyboardmanager-class.md)です。|
|[AfxLoadLibrary](#afxloadlibrary)|DLL モジュールをマップし、DLL 関数のアドレスを取得するために使用できるハンドルを返します。|  
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|グローバルへのポインター[ティアオフ メニュー マネージャー](cmenutearoffmanager-class.md)です。|
|[AfxMouseManager](#afxmousemanager)|グローバルへのポインター[マウス マネージャー](cmousemanager-class.md)です。|
|[AfxRegisterClass](#afxregisterclass)|MFC を使用する DLL には、ウィンドウ クラスを登録します。|  
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC によって自動的に登録されているものを補足する Windows のウィンドウ クラスを登録します。|  
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|アプリケーションがレジストリ アクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** ( **HKCU**) ノード。|  
|[AfxSetResourceHandle](#afxsetresourcehandle)|セット、`HINSTANCE`読み込まれるアプリケーションの既定のリソース ハンドル。|  
|[AfxShellManager](#afxshellmanager)|グローバルへのポインター[シェル マネージャー](cshellmanager-class.md)です。 |
|[AfxSocketInit](#afxsocketinit)|呼び出される、 `CWinApp::InitInstance` Windows Sockets を初期化するためにオーバーライドします。|  
|[AfxUserToolsManager](#afxusertoolsmanager)|グローバルへのポインター[ユーザー ツール マネージャー](cusertoolsmanager-class.md)です。|
|[AfxWinInit](#afxwininit)|MFC が指定したによって呼び出されます`WinMain`の一部として、関数、 [CWinApp](../../mfc/reference/cwinapp-class.md) MFC を初期化するために、GUI ベースのアプリケーションの初期化します。 MFC を使用するコンソール アプリケーションを直接呼び出す必要があります。|  
  

  
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
 `pfnThreadProc`  
 ワーカー スレッドの制御関数をポイントします。 ことはできません**NULL**です。 この関数は次のように宣言する必要があります。  
  
 `UINT __cdecl MyControllingFunction( LPVOID pParam );`  
  
 *pThreadClass*  
 派生したオブジェクトの RUNTIME_CLASS [CWinThread](../../mfc/reference/cwinthread-class.md)です。  
  
 *pParam*  
 `pfnThreadProc` の関数の宣言へのパラメーターに示されるように、制御関数に渡すパラメーター。  
  
 `nPriority`  
 スレッドの優先順位。 完全な一覧と使用可能な優先事項の説明では、次を参照してください。 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) Windows SDK に含まれています。  
  
 `nStackSize`  
 新しいスレッドへのスタックのバイト サイズを指定します。 0 である場合、スタック サイズの既定値は、このスレッドを生成するスレッドのスタックと同じサイズです。  
  
 `dwCreateFlags`  
 スレッドの作成を制御する追加のフラグを指定します。 このフラグは、2 つの値の 1 つを含めることができます。  
  
- **CREATE_SUSPENDED**中断カウントが 1 つのスレッドを開始します。 使用して**CREATE_SUSPENDED**のメンバー データを初期化する場合、`CWinThread`などのオブジェクト[m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete)またはスレッドが実行を開始する前に、派生クラスのメンバーです。 初期化が完了したらを使用して[cwinthread::resumethread](../../mfc/reference/cwinthread-class.md#resumethread)を実行しているスレッドを開始します。 `CWinThread::ResumeThread` が呼び出されるまでは、スレッドは実行されません。  
  
- **0**作成後すぐにスレッドを開始します。  
  
 `lpSecurityAttrs`  
 指す、 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)構造体のスレッドのセキュリティ属性を指定します。 場合**NULL**スレッドの作成が使用すると、同じセキュリティ属性します。 この構造体の詳細については、Windows SDK を参照してください。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたスレッド オブジェクトへのポインターまたは**NULL**障害が発生した場合。  
  
### <a name="remarks"></a>コメント  
 `AfxBeginThread` の最初のフォームはワーカー スレッドを作成します。 2 番目のフォームは、ユーザー インターフェイス スレッドまたはワーカー スレッドとして機能可能なスレッドを作成します。  
  
 `AfxBeginThread` 新たに作成`CWinThread`オブジェクトを呼び出してその[CreateThread](../../mfc/reference/cwinthread-class.md#createthread)関数のスレッドの実行を開始して、スレッドへのポインターを返します。 なんらかの原因でスレッド生成に失敗すると、スレッド生成処理全体をチェックし、すべてのオブジェクトを確実に解放します。 スレッドを終了するには、呼び出す[AfxEndThread](#afxendthread)から内のスレッドまたはワーカー スレッドの制御関数からの戻り値。  
  
 マルチスレッドは、アプリケーションによって有効化される必要があります。それ以外の場合、この関数は失敗します。 マルチ スレッド処理を有効にする方法の詳細についてを参照してください[/MD、/MT、/LD (ランタイム ライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)  *Visual C コンパイラ オプション*です。  
  
 詳細については`AfxBeginThread`、記事を参照して[マルチ スレッド: ワーカー スレッドの生成](../../parallel/multithreading-creating-worker-threads.md)と[マルチ スレッド: ユーザー インターフェイス スレッドの生成](../../parallel/multithreading-creating-user-interface-threads.md)です。  
  
### <a name="example"></a>例  
 例を参照して[csocket::attach](../../mfc/reference/csocket-class.md#attach)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  

## <a name="afxcontextmenumanager"></a> AfxContextMenuManager
グローバルへのポインター[コンテキスト メニュー マネージャー](ccontextmenumanager-class.md)です。  
   
### <a name="syntax"></a>構文    
```  
CContextMenuManager* afxContextMenuManager;  
```     
### <a name="requirements"></a>要件  
 **ヘッダー:** afxcontextmenumanager.h     

### <a name="see-also"></a>関連項目   
 [CContextMenuManager クラス](ccontextmenumanager-class.md)

  
##  <a name="afxendthread"></a>  AfxEndThread  
 この関数では、現在実行中のスレッドを終了します。  
  
```   
void AFXAPI AfxEndThread(
    UINT nExitCode,  
    BOOL bDelete  = TRUE); 
```  
  
### <a name="parameters"></a>パラメーター  
 *nExitCode*  
 スレッドの終了コードを指定します。  
  
 *bDelete*  
 メモリからスレッド オブジェクトを削除します。  
  
### <a name="remarks"></a>コメント  
 終了するスレッド内からを呼び出す必要があります。  
  
 詳細については`AfxEndThread`、記事を参照して[マルチ スレッド: スレッドの終了](../../parallel/multithreading-terminating-threads.md)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
使用して`AfxFindResourceHandle`をリソース チェーンについて説明し、特定のリソースでリソース ID とリソースの種類を探します。  
   
### <a name="syntax"></a>構文    
```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );  
```
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 リソース ID を含む文字列へのポインター    
 *lpszType*  
 リソースの種類へのポインター。 リソースの種類の一覧は、次を参照してください。 [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) Windows SDK に含まれています。  
   
### <a name="return-value"></a>戻り値  
 リソースを含むモジュールへのハンドル。  
   
### <a name="remarks"></a>コメント  
 `AfxFindResourceHandle` 特定のリソースを検索して、リソースを含むモジュールへのハンドルを返します。 すべての MFC 拡張 DLL が読み込まリソース可能性があります。 `AfxFindResourceHandle` どれがリソースを示します。  
  
 モジュールは、この順序で検索されます。  
  
1.  (MFC 拡張 DLL の場合) は、メイン モジュールです。  
  
2.  非システム モジュールです。  
  
3.  言語固有のモジュールです。  
  
4.  (システム DLL の場合) は、メイン モジュールです。  
  
5.  システム モジュールです。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)   
  
##  <a name="afxfreelibrary"></a>  AfxFreeLibrary  
 両方`AfxFreeLibrary`と`AfxLoadLibrary`ライブラリが読み込まれたモジュールごとに参照カウントを保持します。  
  
```   
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib); 
```  
  
### <a name="parameters"></a>パラメーター  
 *hInstLib*  
 ライブラリが読み込まれたモジュールのハンドル。 [AfxLoadLibrary](#afxloadlibrary)このハンドルを返します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE** 、関数が成功した場合は、それ以外の場合、 **FALSE**です。  
  
### <a name="remarks"></a>コメント  
 `AfxFreeLibrary` 読み込まれたダイナミック リンク ライブラリ (DLL) モジュールの参照カウントをデクリメントします。 参照カウントには、ゼロに達するとモジュールは、呼び出し元プロセスのアドレス空間からマップされたハンドルは無効になりました。 この参照カウントは毎回`AfxLoadLibrary`と呼びます。  
  
 ライブラリ モジュールをマップ解除する前に、システムは、これを使用して、プロセスからデタッチする DLL を使用できます。 これが、DLL、現在のプロセスに割り当てられているリソースをクリーンアップできます。 エントリ ポイント関数が返されると、ライブラリ モジュールが現在のプロセスのアドレス空間から削除されます。  
  
 使用して`AfxLoadLibrary`DLL モジュールをマップします。  
  
 使用してください`AfxFreeLibrary`と`AfxLoadLibrary`(Win32 関数ではなく**FreeLibrary**と**LoadLibrary**) 場合は、アプリケーションが複数のスレッドを使用します。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`スタートアップおよびシャット ダウン コード MFC 拡張 DLL の読み込みし、アンロードに MFC のグローバル状態が破損していないときに実行されることを確認します。  
  
### <a name="example"></a>例  
 例を参照して[AfxLoadLibrary](#afxloadlibrary)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdll_.h  
  
##  <a name="afxgetapp"></a>  AfxGetApp  
 この関数によって返されるポインターは、メイン メッセージのディスパッチ コードまたは最上位ウィンドウなどのアプリケーションの情報にアクセスを使用できます。  
  
```   
CWinApp* AFXAPI AfxGetApp(); 
```  
  
### <a name="return-value"></a>戻り値  
 1 つへのポインター`CWinApp`アプリケーションのオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、NULL を返す場合、アプリケーションのメイン ウィンドウが完全にまだ初期化されていないその可能性があります。 これは、も発生している可能性があります。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxgetappname"></a>  AfxGetAppName  
 この関数によって返される文字列は、一時的な文字列名診断メッセージ、またはルートとして使用できます。  
  
```   
LPCTSTR AFXAPI AfxGetAppName(); 
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションの名前を表す、null で終わる文字列。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxgetinstancehandle"></a>  AfxGetInstanceHandle  
 この関数では、現在のアプリケーションのインスタンス ハンドルを取得することができます。  
  
```   
HINSTANCE  AFXAPI AfxGetInstanceHandle(); 
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`アプリケーションの現在のインスタンスにします。 MFC の USRDLL バージョンとリンクされた DLL 内から呼び出された場合、 `HINSTANCE` DLL が返されます。  
  
### <a name="remarks"></a>コメント  
 `AfxGetInstanceHandle` 常に返します、`HINSTANCE`実行可能ファイルの (です。EXE) DLL が MFC の USRDLL バージョンとリンクされた内から呼び出された場合を除き、します。 この例を返します、 `HINSTANCE` DLL にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxgetmainwnd"></a>  AfxGetMainWnd  
 アプリケーションが OLE サーバーの場合は、直接参照することではなく、アプリケーションのアクティブなメイン ウィンドウへのポインターを取得するには、この関数を呼び出して、 [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd)アプリケーション オブジェクトのメンバーです。  
  
```   
CWnd* AFXAPI AfxGetMainWnd(); 
```  
  
### <a name="return-value"></a>戻り値  
 サーバーが、コンテナー内に埋め込まれているアクティブなオブジェクトを持ち、そのコンテナーがアクティブである場合は、この関数は、埋め込まれているアクティブな文書を含むフレーム ウィンドウ オブジェクトへのポインターを返します。  
  
 コンテナー内に埋め込まれているアクティブなオブジェクトが存在しない場合や、開発中のアプリケーションが OLE サーバーではない場合は、この関数は単純に、開発中のアプリケーション オブジェクトの `m_pMainWnd` を返します。  
  
 `AfxGetMainWnd` をアプリケーションのプライマリ スレッドから呼び出した場合は、上記の規則に従ってアプリケーションのメイン ウィンドウを返します。 アプリケーションのセカンダリ スレッドからこの関数を呼び出した場合は、関数は呼び出しを行ったスレッドに関連付けられているメイン ウィンドウを返します。  
  
### <a name="remarks"></a>コメント  
 開発中のアプリケーションが OLE サーバーではない場合は、この関数を呼び出すことは、アプリケーション オブジェクトの `m_pMainWnd` メンバーを直接参照することと同じです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxgetperuserregistration"></a>  AfxGetPerUserRegistration  
 この関数を使用して、アプリケーションがレジストリ アクセスをリダイレクトするかどうかを判断、 **HKEY_CURRENT_USER** ( **HKCU**) ノード。  
  
```  
BOOL AFXAPI AfxGetPerUserRegistration();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` レジストリ情報に送られることを示す、 **HKCU**ノードです。`FALSE`アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードは**HKEY_CLASSES_ROOT** ( **HKCR**)。  
  
### <a name="remarks"></a>コメント  
 フレームワークからのアクセスにリダイレクト レジストリのリダイレクトを有効にした場合**HKCR**に**する**です。 MFC と ATL のフレームワークは、リダイレクトの影響を受けます。  
  
 アプリケーションがレジストリ アクセスをリダイレクトするかどうかを変更するには、使用[AfxSetPerUserRegistration](#afxsetperuserregistration)です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxstat_.h    
  
##  <a name="afxgetresourcehandle"></a>  AfxGetResourceHandle  
 使用して、`HINSTANCE`直接アクセスするアプリケーションのリソース、たとえば、Windows の関数の呼び出しでは、この関数によって返されたハンドル**FindResource**です。  
  
```   
extern HINSTANCE  AfxGetResourceHandle(); 
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`読み込まれるアプリケーションの既定のリソース ハンドル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxgetthread"></a>  AfxGetThread  
 ポインターを取得するには、この関数を呼び出して、 [CWinThread](../../mfc/reference/cwinthread-class.md)実行中のスレッドを表すオブジェクト。  
  
```   
CWinThread* AfxGetThread(); 
```  
  
### <a name="return-value"></a>戻り値  
 実行中のスレッドへのポインターそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 目的のスレッド内からを呼び出す必要があります。  
  
> [!NOTE]
>  MFC プロジェクト通話を移植する場合`AfxGetThread`4.2、5.0 または 6.0 では、Visual C バージョンから`AfxGetThread`呼び出し[AfxGetApp](#afxgetapp)スレッドが存在しない場合。 新しいバージョンのコンパイラで`AfxGetThread`返します**NULL**スレッドが見つからなかった場合です。 アプリケーション スレッドを実行する場合に、呼び出す必要があります`AfxGetApp`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxinitrichedit"></a>  AfxInitRichEdit  
 この関数では、アプリケーションのリッチ エディット コントロール (version 1.0) を初期化します。  
  
```   
BOOL AFXAPI AfxInitRichEdit(); 
```  
  
### <a name="remarks"></a>コメント  
 この関数は旧バージョンとの互換性のために提供されます。 新しいアプリケーションを使用する必要があります[AfxInitRichEdit2](#afxinitrichedit2)です。  
  
 `AfxInitRichEdit` RICHED32 を読み込みます。リッチ エディット コントロールのバージョン 1.0 を初期化するために DLL です。 2.0 および 3.0 RICHED20、リッチ エディット コントロールのバージョンを使用します。DLL を読み込む必要があります。 呼び出しでこの情報は[AfxInitRichEdit2](#afxinitrichedit2)です。  
  
 バージョン 2.0 に既存の Visual C アプリケーションでのリッチ エディット コントロールを更新するを開き、します。RC ファイルをテキスト、としては、"RichEdit20a"を"RICHEDIT"から各リッチ エディット コントロールのクラス名を変更します。 呼び出しを置き換える`AfxInitRichEdit`で`AfxInitRichEdit2`です。  
  
 この関数は、ライブラリは、プロセスの既に初期化されていない場合にも、共通のコントロール ライブラリを初期化します。 リッチ エディット コントロールを MFC アプリケーションから直接使用する場合は、MFC でリッチ エディット コントロールのランタイムが正しく初期化されているこの関数を呼び出す必要があります。 Create メソッドを呼び出す場合[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)、通常必要はありません、この関数を呼び出すが、いくつかの場合がありますいる。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxinitrichedit2"></a>  AfxInitRichEdit2  
 この関数では、アプリケーションのリッチ エディット コントロール (バージョン 2.0 以降) を初期化します。  
  
```   
BOOL AFXAPI AfxInitRichEdit2(); 
```  
  
### <a name="remarks"></a>コメント  
 RICHED20 を読み込むには、この関数を呼び出します。DLL と初期化のバージョン 2.0 の豊富なコントロールを編集します。 Create メソッドを呼び出す場合[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)、 [CRichEditView](../../mfc/reference/cricheditview-class.md)、または[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)、通常必要はありません、この関数を呼び出すが、いくつかの場合がありますいる。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  

  ## <a name="afxisextendedframeclass"></a>  AfxIsExtendedFrameClass
指定されたウィンドウが拡張フレーム オブジェクトかどうかを確認します。  
   
### <a name="syntax"></a>構文    
```  
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );  
```
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 `CWnd`から派生したオブジェクトへのポインター。  
   
### <a name="return-value"></a>戻り値  
 `TRUE` 指定されたウィンドウが拡張フレーム オブジェクトの場合それ以外の場合`FALSE`です。  
   
### <a name="remarks"></a>コメント  
 `TRUE` が次のいずれかのクラスから派生している場合、このメソッドは `pWnd` を返します。  
  
-   `CFrameWndEx`  
  
-   `CMDIFrameWndEx`  
  
-   `COleIPFrameWndEx`  
  
-   `COleDocIPFrameWndEx`  
  
-   `CMDIChildWndEx`  
  
 このメソッドは、関数またはメソッドのパラメーターが拡張フレーム ウィンドウであるかどうかを検証する必要があるときに役立ちます。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxpriv.h  
   
### <a name="see-also"></a>関連項目  
 [CWnd クラス](cwnd-class.md)   
 [CFrameWndEx クラス](cframewndex-class.md)   

## <a name="afxismfctoolbar"></a> AfxIsMFCToolBar
指定されたウィンドウがツール バー オブジェクトであるかどうかを判断します。  
   
### <a name="syntax"></a>構文    
```  
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);  
```
### <a name="parameters"></a>パラメーター  
 [入力] `pWnd`  
 `CWnd`から派生したオブジェクトへのポインター。  
   
### <a name="return-value"></a>戻り値  
 `TRUE` 指定されたウィンドウがオブジェクトの場合、ツールバーです。それ以外の場合`FALSE`です。  
   
### <a name="remarks"></a>コメント  
 このメソッドが戻る`TRUE`場合`pWnd`から派生した`CMFCToolBar`です。 このメソッドは、関数またはメソッドのパラメーターがあることを検証する必要がある場合に便利です、`CMFCToolBar`オブジェクト。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxpriv.h  
   
### <a name="see-also"></a>関連項目  
 [CWnd クラス](cwnd-class.md)   
 [CMFCToolBar クラス](cmfctoolbar-class.md)

 
## <a name="afxkeyboardmanager"></a> AfxKeyboardManager
グローバルへのポインター[キーボード マネージャー](ckeyboardmanager-class.md)です。  
   
### <a name="syntax"></a>構文    
```  
CKeyboardManager* afxKeyboardManager;  
```  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxkeyboardmanager.h  
   
### <a name="see-also"></a>関連項目  

 [マクロ、グローバル関数、およびグローバル変数](mfc-macros-and-globals.md)   
 [CKeyboardManager クラス](ckeyboardmanager-class.md)


##  <a name="afxloadlibrary"></a>  AfxLoadLibrary  
 使用して`AfxLoadLibrary`DLL モジュールをマップします。  
  
```   
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName); 
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszModuleName*  
 モジュールの名前を表す null で終わる文字列へのポインター (どちらか、します。DLL またはします。EXE ファイルの場合)。 指定された名前は、モジュールのファイル名です。  
  
 文字列のパスを指定しますが、指定したディレクトリにファイルが存在しません、関数が失敗します。  
  
 パスが指定されていないと、ファイル名拡張子を省略すると、既定の拡張機能です。DLL が追加されます。 ただし、ファイル名の文字列は、ピリオド文字 (.)、モジュール名に拡張子がないことを表しますを含めることができます。 パスが指定されていない場合、関数は次の順序でファイルを検索します。  
  
-   アプリケーションの読み込み元のディレクトリです。  
  
-   現在のフォルダー。  
  
- **Windows 95/98:** Windows システム ディレクトリ。 **Windows NT:** 32 ビット Windows のシステム ディレクトリ。 このディレクトリの名前は、SYSTEM32 です。  
  
- **Windows NT のみ:** 16 ビットの Windows システム ディレクトリ。 このディレクトリのパスを取得する Win32 関数はありませんが検索されます。 このディレクトリの名前は、システムです。  
  
-   Windows ディレクトリ。  
  
-   PATH 環境変数に記載されているディレクトリ。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は、モジュールへのハンドルです。 関数が失敗した場合、戻り値は NULL です。  
  
### <a name="remarks"></a>コメント  
 使用できるハンドルを返します[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) DLL 関数のアドレスを取得します。 `AfxLoadLibrary` その他の実行可能モジュールにマップするも使用できます。  
  
 各プロセスは、各ライブラリが読み込まれたモジュールの参照カウントを維持できます。 この参照カウントは毎回`AfxLoadLibrary`が呼び出され、減少するたびに`AfxFreeLibrary`と呼びます。 参照カウントには、ゼロに達するとモジュールは、呼び出し元プロセスのアドレス空間からマップされたハンドルは無効になりました。  
  
 使用してください`AfxLoadLibrary`と`AfxFreeLibrary`(Win32 関数ではなく**LoadLibrary**と**FreeLibrary**)、MFC を動的に読み込む場合と、アプリケーションは、複数のスレッドを使用している場合拡張 DLL です。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`MFC 拡張 DLL が読み込まれ、アンロードされるときに実行されるスタートアップおよびシャット ダウン コードに MFC のグローバル状態が破損していないことを保証します。  
  
 使用して`AfxLoadLibrary`アプリケーション内に、MFC の DLL バージョンは動的にリンクする必要があります。 用のヘッダー ファイル`AfxLoadLibrary`、Afxdll_.h、はのみ MFC が DLL としてアプリケーションにリンクされている場合に含まれます。 これは仕様使用または MFC 拡張 Dll を作成する MFC の DLL バージョンにリンクする必要があるためです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]  
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]  
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdll_.h  
   
## <a name="afxmenutearoffmanager"></a> AfxMenuTearOffManager
グローバルへのポインター[ティアオフ メニュー マネージャー](cmenutearoffmanager-class.md)です。  
   
### <a name="syntax"></a>構文    
```  
CMenuTearOffManager* g_pTearOffMenuManager;  
```  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmenutearoffmanager.h  
   
### <a name="see-also"></a>関連項目     
 [CMenuTearOffManager クラス](cmenutearoffmanager-class.md)
 
## <a name="afxmousemanager"></a>  AfxMouseManager
グローバルへのポインター[マウス マネージャー](cmousemanager-class.md)です。  
   
### <a name="syntax"></a>構文  
  ```  
CMouseManager* afxMouseManager;  
```  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmousemanager.h  
   
### <a name="see-also"></a>関連項目  
 [CMouseManager クラス](cmousemanager-class.md)
 

  
##  <a name="afxregisterclass"></a>  AfxRegisterClass  
 この関数を使用すると、MFC を使用する DLL のウィンドウ クラスを登録できます。  
  
```   
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass); 
```  
  
### <a name="parameters"></a>パラメーター  
 *lpWndClass*  
 ポインター、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)登録する、ウィンドウ クラスに関する情報を含む構造体。 この構造体の詳細については、Windows SDK を参照してください。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**クラスが正常に登録されているそれ以外の場合**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 この関数を使用する場合、クラスは、自動的に登録された DLL がアンロードされるときです。  
  
 非 DLL のビルドでは、`AfxRegisterClass`識別子が Windows 関数にマップするマクロとして定義されている**RegisterClass**アプリケーションで登録されたクラスが自動的に登録ではないため、します。 使用する場合`AfxRegisterClass`の代わりに**RegisterClass**アプリケーションと DLL の両方を変更せずに、コードを使用できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxregisterwndclass"></a>  AfxRegisterWndClass  
 独自のウィンドウ クラスを登録できます。  
  
```  
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,  
    HCURSOR hCursor = 0,  
    HBRUSH hbrBackground = 0,  
    HICON hIcon = 0);  
```  
  
### <a name="parameters"></a>パラメーター  
 *nClassStyle*  
 Windows クラス スタイル、またはビットごとの OR を使用して作成されたスタイルの組み合わせを指定します ( **&#124;**) ウィンドウ クラスの演算子。 クラスのスタイルの一覧は、次を参照してください。、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Windows SDK 内の構造。 場合**NULL**、既定値は次のように設定されます。  
  
-   マウスのスタイルを設定**CS_DBLCLKS**、送信し、ユーザーがマウスをダブルクリックすると、ウィンドウ プロシージャへのメッセージ をダブルクリックします。  
  
-   Windows 標準に矢印カーソルのスタイルを設定**IDC_ARROW**です。  
  
-   背景ブラシが設定**NULL**ウィンドウは、背景は消去されません。  
  
-   標準 (たなびく旗) の Windows ロゴ アイコンにアイコンを設定します。  
  
 `hCursor`  
 ウィンドウ クラスから作成された各ウィンドウにインストールする、カーソル リソースへのハンドルを指定します。 既定値を使用する場合**0**、標準が表示される**IDC_ARROW**カーソル。  
  
 *hbrBackground*  
 ウィンドウ クラスから作成された各ウィンドウにインストールするブラシ リソースへのハンドルを指定します。 既定値を使用する場合**0**、する必要が、 **NULL**背景のブラシ、および、ウィンドウには、既定では、消去の処理中に、バック グラウンド[WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)です。  
  
 `hIcon`  
 ウィンドウ クラスから作成された各ウィンドウにインストールするアイコンのリソースへのハンドルを指定します。 既定値を使用する場合**0**、標準的な (たなびく旗) の Windows ロゴ アイコンが表示されます。  
  
### <a name="return-value"></a>戻り値  
 クラス名を含む null で終わる文字列。 このクラス名を渡すことができます、**作成**メンバー関数内`CWnd`またはその他の**CWnd-** ウィンドウを作成するクラスを派生します。 名前は、Microsoft Foundation Class ライブラリによって生成されます。  
  
> [!NOTE]
>  戻り値は、静的バッファーへのポインターです。 この文字列を保存するには、それを割り当てる、`CString`変数。  
  
### <a name="remarks"></a>コメント  
 Microsoft Foundation Class ライブラリでは、いくつかの標準のウィンドウ クラスが自動的に登録します。 独自のウィンドウ クラスを登録する場合は、この関数を呼び出します。  
  
 クラスの名前が登録されている`AfxRegisterWndClass`パラメーターにのみ依存します。 呼び出す場合`AfxRegisterWndClass`複数回と同じパラメーターを持つことのみクラスを登録する最初の呼び出しで。 後続の呼び出し`AfxRegisterWndClass`と同じパラメーターを使用して登録済みのクラス名に返されるだけです。  
  
 呼び出す場合`AfxRegisterWndClass`クラスごとに別のウィンドウ クラスを取得する代わりに、同じパラメーターを持つ複数の CWnd から派生したクラスの各クラスは、同じウィンドウ クラスを共有します。 これは、問題となる場合、 **CS_CLASSDC**クラス スタイルを使用します。 複数の代わりに**CS_CLASSDC** 、ウィンドウ クラスいずれかで終わる**CS_CLASSDC**ウィンドウ クラス、およびクラスが同じドメイン コント ローラーを共有することを使用するすべての C++ windows です。 この問題を避けるためには、呼び出す[AfxRegisterClass](#afxregisterclass)クラスを登録します。  
  
 テクニカル ノートを参照してください[TN001: ウィンドウ クラスの登録](../../mfc/tn001-window-class-registration.md)ウィンドウ クラスの登録の詳細について、`AfxRegisterWndClass`関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxsetperuserregistration"></a>  AfxSetPerUserRegistration  
 アプリケーションがレジストリ アクセスをリダイレクトするかどうかを設定、 **HKEY_CURRENT_USER** ( **HKCU**) ノード。  
  
```  
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE` レジストリ情報に送られることを示す、 **HKCU**ノードです。`FALSE`アプリケーションが既定のノードにレジストリ情報を書き出すことを示します。 既定のノードは**HKEY_CLASSES_ROOT** ( **HKCR**)。  
  
### <a name="remarks"></a>コメント  

Windows Vista では、通常使用されるレジストリにアクセスしたアプリケーションの前に、 **HKEY_CLASSES_ROOT**ノード。 ただし、Windows Vista またはそれ以降のオペレーティング システムでは、使用する必要がありますアプリケーションを実行するへの書き込みを管理者特権モードで**HKCR**です。  
  
 このメソッドにより、アプリケーションからレジストリへのアクセスをリダイレクトすることで、管理者特権モードで実行せずに、レジストリに読み書きを**HKCR**に**HKCU**です。 詳細については、次を参照してください。[リンカー プロパティ ページ](../../ide/linker-property-pages.md)です。  
  
 フレームワークからのアクセスにリダイレクト レジストリのリダイレクトを有効にした場合**HKCR**に**する**です。 MFC と ATL のフレームワークは、リダイレクトの影響を受けます。  
  
 既定の実装の下のレジストリにアクセスする**HKCR**です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxstat_.h    
  
##  <a name="afxsetresourcehandle"></a>  AfxSetResourceHandle  
 この関数を使って設定、`HINSTANCE`読み込まれるアプリケーションの既定のリソースを決定するハンドル。  
  
```  
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstResource`  
 インスタンスまたはモジュールを識別するハンドル、します。アプリケーションのリソースの読み込み元の EXE または DLL ファイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  

## <a name="afxshellmanager"></a>  AfxShellManager
グローバルへのポインター[シェル マネージャー](cshellmanager-class.md)です。  
   
### <a name="syntax"></a>構文    
```  
CShellManager* afxShellManager;  
```  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxshellmanager.h  
   
### <a name="see-also"></a>関連項目  
 [CShellManager クラス](cshellmanager-class.md)
  
##  <a name="afxsocketinit"></a>  AfxSocketInit  
 この関数を呼び出して、 `CWinApp::InitInstance` Windows Sockets を初期化するためにオーバーライドします。  
  
```  
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpwsaData`  
 ポインター、 [WSADATA](../../mfc/reference/wsadata-structure.md)構造体。 場合`lpwsaData`は等しくありません`NULL`のアドレス、`WSADATA`構造がへの呼び出しで埋められた`WSAStartup`です。 この関数によりも`WSACleanup`は、アプリケーションが終了する前の呼び出されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 静的にリンクされた MFC アプリケーションのセカンダリ スレッドで MFC ソケットを使用して、呼び出す必要があります`AfxSocketInit`ソケット ライブラリを初期化するためにソケットを使用する各スレッドにします。 既定では、`AfxSocketInit`プライマリ スレッドでのみ呼び出すことができます。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxsock.h  

## <a name="afxusertoolsmanager"></a>  AfxUserToolsManager
グローバルへのポインター[ユーザー ツール マネージャー](cusertoolsmanager-class.md)です。  
   
### <a name="syntax"></a>構文    
```  
CUserToolsManager* afxUserToolsManager;  
```  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxusertoolsmanager.h  
   
### <a name="see-also"></a>関連項目  
 [CUserToolsManager クラス](cusertoolsmanager-class.md)
 
  
##  <a name="afxwininit"></a>  AfxWinInit  
 この関数は、MFC に提供されている`WinMain`の一部として、関数、 [CWinApp](../../mfc/reference/cwinapp-class.md) MFC を初期化するために、GUI ベースのアプリケーションの初期化します。  
  
```  
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,  
    HINSTANCE hPrevInstance,  
    LPTSTR lpCmdLine,  
    int nCmdShow);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hInstance`  
 現在実行中のモジュールのハンドル。  
  
 *hPrevInstance*  
 アプリケーションの以前のインスタンスへのハンドル。 Win32 ベースのアプリケーションでは、このパラメーターは常に**NULL**です。  
  
 `lpCmdLine`  
 アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。  
  
 `nCmdShow`  
 GUI アプリケーションのメイン ウィンドウの表示方法を指定します。  
  
### <a name="remarks"></a>コメント  
 コンソール アプリケーションでは、これを使用しません、MFC に提供されている`WinMain`関数を呼び出す必要があります`AfxWinInit`MFC を初期化するために直接できます。  
  
 呼び出す場合`AfxWinInit`、自分でする必要がありますのインスタンスを宣言、`CWinApp`クラスです。 コンソール アプリケーションの場合がありますをしないように選択から独自のクラスを派生させる`CWinApp`のインスタンスを代わりに使用して`CWinApp`直接です。 この手法は、アプリケーションのすべての機能の実装のままにする場合に適切な**メイン**です。  
  
> [!NOTE]
>  アセンブリのアクティベーション コンテキストを作成するときに、MFC は、ユーザー モジュールによって指定されたマニフェスト リソースを使用します。 アクティブ化コンテキストは`AfxWinInit`します。 詳細については、次を参照してください。 [MFC モジュール状態でのアクティベーション コンテキスト サポート](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]  

### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)
