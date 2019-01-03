---
title: CWinApp クラス
ms.date: 11/04/2016
f1_keywords:
- CWinApp
- AFXWIN/CWinApp
- AFXWIN/CWinApp::CWinApp
- AFXWIN/CWinApp::AddDocTemplate
- AFXWIN/CWinApp::AddToRecentFileList
- AFXWIN/CWinApp::ApplicationRecoveryCallback
- AFXWIN/CWinApp::CloseAllDocuments
- AFXWIN/CWinApp::CreatePrinterDC
- AFXWIN/CWinApp::DelRegTree
- AFXWIN/CWinApp::DoMessageBox
- AFXWIN/CWinApp::DoWaitCursor
- AFXWIN/CWinApp::EnableD2DSupport
- AFXWIN/CWinApp::EnableHtmlHelp
- AFXWIN/CWinApp::EnableTaskbarInteraction
- AFXWIN/CWinApp::ExitInstance
- AFXWIN/CWinApp::GetApplicationRecoveryParameter
- AFXWIN/CWinApp::GetApplicationRecoveryPingInterval
- AFXWIN/CWinApp::GetApplicationRestartFlags
- AFXWIN/CWinApp::GetAppRegistryKey
- AFXWIN/CWinApp::GetDataRecoveryHandler
- AFXWIN/CWinApp::GetFirstDocTemplatePosition
- AFXWIN/CWinApp::GetHelpMode
- AFXWIN/CWinApp::GetNextDocTemplate
- AFXWIN/CWinApp::GetPrinterDeviceDefaults
- AFXWIN/CWinApp::GetProfileBinary
- AFXWIN/CWinApp::GetProfileInt
- AFXWIN/CWinApp::GetProfileString
- AFXWIN/CWinApp::GetSectionKey
- AFXWIN/CWinApp::HideApplication
- AFXWIN/CWinApp::HtmlHelp
- AFXWIN/CWinApp::InitInstance
- AFXWIN/CWinApp::IsTaskbarInteractionEnabled
- AFXWIN/CWinApp::LoadCursor
- AFXWIN/CWinApp::LoadIcon
- AFXWIN/CWinApp::LoadOEMCursor
- AFXWIN/CWinApp::LoadOEMIcon
- AFXWIN/CWinApp::LoadStandardCursor
- AFXWIN/CWinApp::LoadStandardIcon
- AFXWIN/CWinApp::OnDDECommand
- AFXWIN/CWinApp::OnIdle
- AFXWIN/CWinApp::OpenDocumentFile
- AFXWIN/CWinApp::ParseCommandLine
- AFXWIN/CWinApp::PreTranslateMessage
- AFXWIN/CWinApp::ProcessMessageFilter
- AFXWIN/CWinApp::ProcessShellCommand
- AFXWIN/CWinApp::ProcessWndProcException
- AFXWIN/CWinApp::Register
- AFXWIN/CWinApp::RegisterWithRestartManager
- AFXWIN/CWinApp::ReopenPreviousFilesAtRestart
- AFXWIN/CWinApp::RestartInstance
- AFXWIN/CWinApp::RestoreAutosavedFilesAtRestart
- AFXWIN/CWinApp::Run
- AFXWIN/CWinApp::RunAutomated
- AFXWIN/CWinApp::RunEmbedded
- AFXWIN/CWinApp::SaveAllModified
- AFXWIN/CWinApp::SelectPrinter
- AFXWIN/CWinApp::SetHelpMode
- AFXWIN/CWinApp::SupportsApplicationRecovery
- AFXWIN/CWinApp::SupportsAutosaveAtInterval
- AFXWIN/CWinApp::SupportsAutosaveAtRestart
- AFXWIN/CWinApp::SupportsRestartManager
- AFXWIN/CWinApp::Unregister
- AFXWIN/CWinApp::WinHelp
- AFXWIN/CWinApp::WriteProfileBinary
- AFXWIN/CWinApp::WriteProfileInt
- AFXWIN/CWinApp::WriteProfileString
- AFXWIN/CWinApp::EnableShellOpen
- AFXWIN/CWinApp::LoadStdProfileSettings
- AFXWIN/CWinApp::OnContextHelp
- AFXWIN/CWinApp::OnFileNew
- AFXWIN/CWinApp::OnFileOpen
- AFXWIN/CWinApp::OnFilePrintSetup
- AFXWIN/CWinApp::OnHelp
- AFXWIN/CWinApp::OnHelpFinder
- AFXWIN/CWinApp::OnHelpIndex
- AFXWIN/CWinApp::OnHelpUsing
- AFXWIN/CWinApp::RegisterShellFileTypes
- AFXWIN/CWinApp::SetAppID
- AFXWIN/CWinApp::SetRegistryKey
- AFXWIN/CWinApp::UnregisterShellFileTypes
- AFXWIN/CWinApp::m_bHelpMode
- AFXWIN/CWinApp::m_eHelpType
- AFXWIN/CWinApp::m_hInstance
- AFXWIN/CWinApp::m_lpCmdLine
- AFXWIN/CWinApp::m_nCmdShow
- AFXWIN/CWinApp::m_pActiveWnd
- AFXWIN/CWinApp::m_pszAppID
- AFXWIN/CWinApp::m_pszAppName
- AFXWIN/CWinApp::m_pszExeName
- AFXWIN/CWinApp::m_pszHelpFilePath
- AFXWIN/CWinApp::m_pszProfileName
- AFXWIN/CWinApp::m_pszRegistryKey
- AFXWIN/CWinApp::m_dwRestartManagerSupportFlags
- AFXWIN/CWinApp::m_nAutosaveInterval
- AFXWIN/CWinApp::m_pDataRecoveryHandler
helpviewer_keywords:
- CWinApp [MFC], CWinApp
- CWinApp [MFC], AddDocTemplate
- CWinApp [MFC], AddToRecentFileList
- CWinApp [MFC], ApplicationRecoveryCallback
- CWinApp [MFC], CloseAllDocuments
- CWinApp [MFC], CreatePrinterDC
- CWinApp [MFC], DelRegTree
- CWinApp [MFC], DoMessageBox
- CWinApp [MFC], DoWaitCursor
- CWinApp [MFC], EnableD2DSupport
- CWinApp [MFC], EnableHtmlHelp
- CWinApp [MFC], EnableTaskbarInteraction
- CWinApp [MFC], ExitInstance
- CWinApp [MFC], GetApplicationRecoveryParameter
- CWinApp [MFC], GetApplicationRecoveryPingInterval
- CWinApp [MFC], GetApplicationRestartFlags
- CWinApp [MFC], GetAppRegistryKey
- CWinApp [MFC], GetDataRecoveryHandler
- CWinApp [MFC], GetFirstDocTemplatePosition
- CWinApp [MFC], GetHelpMode
- CWinApp [MFC], GetNextDocTemplate
- CWinApp [MFC], GetPrinterDeviceDefaults
- CWinApp [MFC], GetProfileBinary
- CWinApp [MFC], GetProfileInt
- CWinApp [MFC], GetProfileString
- CWinApp [MFC], GetSectionKey
- CWinApp [MFC], HideApplication
- CWinApp [MFC], HtmlHelp
- CWinApp [MFC], InitInstance
- CWinApp [MFC], IsTaskbarInteractionEnabled
- CWinApp [MFC], LoadCursor
- CWinApp [MFC], LoadIcon
- CWinApp [MFC], LoadOEMCursor
- CWinApp [MFC], LoadOEMIcon
- CWinApp [MFC], LoadStandardCursor
- CWinApp [MFC], LoadStandardIcon
- CWinApp [MFC], OnDDECommand
- CWinApp [MFC], OnIdle
- CWinApp [MFC], OpenDocumentFile
- CWinApp [MFC], ParseCommandLine
- CWinApp [MFC], PreTranslateMessage
- CWinApp [MFC], ProcessMessageFilter
- CWinApp [MFC], ProcessShellCommand
- CWinApp [MFC], ProcessWndProcException
- CWinApp [MFC], Register
- CWinApp [MFC], RegisterWithRestartManager
- CWinApp [MFC], ReopenPreviousFilesAtRestart
- CWinApp [MFC], RestartInstance
- CWinApp [MFC], RestoreAutosavedFilesAtRestart
- CWinApp [MFC], Run
- CWinApp [MFC], RunAutomated
- CWinApp [MFC], RunEmbedded
- CWinApp [MFC], SaveAllModified
- CWinApp [MFC], SelectPrinter
- CWinApp [MFC], SetHelpMode
- CWinApp [MFC], SupportsApplicationRecovery
- CWinApp [MFC], SupportsAutosaveAtInterval
- CWinApp [MFC], SupportsAutosaveAtRestart
- CWinApp [MFC], SupportsRestartManager
- CWinApp [MFC], Unregister
- CWinApp [MFC], WinHelp
- CWinApp [MFC], WriteProfileBinary
- CWinApp [MFC], WriteProfileInt
- CWinApp [MFC], WriteProfileString
- CWinApp [MFC], EnableShellOpen
- CWinApp [MFC], LoadStdProfileSettings
- CWinApp [MFC], OnContextHelp
- CWinApp [MFC], OnFileNew
- CWinApp [MFC], OnFileOpen
- CWinApp [MFC], OnFilePrintSetup
- CWinApp [MFC], OnHelp
- CWinApp [MFC], OnHelpFinder
- CWinApp [MFC], OnHelpIndex
- CWinApp [MFC], OnHelpUsing
- CWinApp [MFC], RegisterShellFileTypes
- CWinApp [MFC], SetAppID
- CWinApp [MFC], SetRegistryKey
- CWinApp [MFC], UnregisterShellFileTypes
- CWinApp [MFC], m_bHelpMode
- CWinApp [MFC], m_eHelpType
- CWinApp [MFC], m_hInstance
- CWinApp [MFC], m_lpCmdLine
- CWinApp [MFC], m_nCmdShow
- CWinApp [MFC], m_pActiveWnd
- CWinApp [MFC], m_pszAppID
- CWinApp [MFC], m_pszAppName
- CWinApp [MFC], m_pszExeName
- CWinApp [MFC], m_pszHelpFilePath
- CWinApp [MFC], m_pszProfileName
- CWinApp [MFC], m_pszRegistryKey
- CWinApp [MFC], m_dwRestartManagerSupportFlags
- CWinApp [MFC], m_nAutosaveInterval
- CWinApp [MFC], m_pDataRecoveryHandler
ms.assetid: e426a3cd-0d15-40d6-bd55-beaa5feb2343
ms.openlocfilehash: 3f9afdf18fcaff0d3613b4204d8690f915079e7d
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178942"
---
# <a name="cwinapp-class"></a>CWinApp クラス

Windows のアプリケーション オブジェクトを派生させるための基底クラスです。

## <a name="syntax"></a>構文

```
class CWinApp : public CWinThread
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CWinApp::CWinApp](#cwinapp)|`CWinApp` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[とき](#adddoctemplate)|ドキュメント テンプレートを使用可能なドキュメント テンプレートのアプリケーションの一覧に追加します。|
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|最近使用した (MRU) ファイルの一覧には、ファイル名を追加します。|
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。|
|[CWinApp::CloseAllDocuments](#closealldocuments)|すべての開いているドキュメントを閉じます。|
|[CWinApp::CreatePrinterDC](#createprinterdc)|プリンター デバイス コンテキストを作成します。|
|[CWinApp::DelRegTree](#delregtree)|指定したキーおよびそのすべてのサブキーを削除します。|
|[CWinApp::DoMessageBox](#domessagebox)|実装[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)アプリケーション。|
|[CWinApp::DoWaitCursor](#dowaitcursor)|オンとオフは、待機カーソルをオンにします。|
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|アプリケーションの D2D のサポートを有効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|WinHelp ではなく、アプリケーションの html ヘルプを実装します。|
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|タスク バーの相互作用を有効にします。|
|[使う](#exitinstance)|アプリケーションの終了時にクリーンアップをオーバーライドします。|
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|アプリケーションの復旧メソッドの入力パラメーターを取得します。|
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|再起動マネージャーが回復のコールバック関数が返すが待機する時間の長さを返します。|
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|再起動マネージャーのフラグを返します。|
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|HKEY_CURRENT_USER のキーを返す\\「ソフトウェア」\RegistryKey\ProfileName します。|
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|アプリケーションのこのインスタンスのデータ復旧のハンドラーを取得します。|
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|最初のドキュメント テンプレートの位置を取得します。|
|[CWinApp::GetHelpMode](#gethelpmode)|アプリケーションで使用するヘルプの種類を取得します。|
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|ドキュメント テンプレートの位置を取得します。 再帰的に使用できます。|
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|プリンター デバイスの既定値を取得します。|
|[は](#getprofilebinary)|アプリケーションのエントリからバイナリ データを取得します。INI ファイルです。|
|[は](#getprofileint)|アプリケーションのエントリから整数値を取得します。INI ファイルです。|
|[CWinApp::GetProfileString](#getprofilestring)|アプリケーションのエントリから文字列を取得します。INI ファイルです。|
|[CWinApp::GetSectionKey](#getsectionkey)|HKEY_CURRENT_USER のキーを返す\\「ソフトウェア」\RegistryKey\AppName\lpszSection します。|
|[CWinApp::HideApplication](#hideapplication)|すべてのドキュメントを閉じる前にアプリケーションを非表示にします。|
|[CWinApp::HtmlHelp](#htmlhelp)|呼び出し、 `HTMLHelp` Windows 関数。|
|[場合は](#initinstance)|オーバーライドすると、ウィンドウ オブジェクトの作成などの Windows インスタンスの初期化を実行します。|
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Windows 7 タスクバーの相互作用が有効になっているかどうかを指示します。|
|[CWinApp::LoadCursor](#loadcursor)|カーソル リソースを読み込みます。|
|[CWinApp::LoadIcon](#loadicon)|アイコン リソースを読み込みます。|
|[CWinApp::LoadOEMCursor](#loadoemcursor)|定義済みのカーソルの Windows OEM の負荷を**OCR_** WINDOWS での定数を指定します。H.|
|[CWinApp::LoadOEMIcon](#loadoemicon)|Windows の OEM の定義済みのアイコンを読み込みますが、 **OIC_** WINDOWS での定数を指定します。H.|
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|負荷を Windows にカーソルがあらかじめ定義されている、 **idc _** WINDOWS での定数を指定します。H.|
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Windows の定義済みのアイコンを読み込みますが、 **IDI_** WINDOWS での定数を指定します。H.|
|[CWinApp::OnDDECommand](#onddecommand)|呼ばれる動的なデータへの応答で、フレームワークによってエクス (チェンジ DDE) はコマンドを実行します。|
|[CWinApp::OnIdle](#onidle)|オーバーライドすると、アプリケーション固有のアイドル時間の処理を実行します。|
|[:Opendocumentfile](#opendocumentfile)|ファイルからドキュメントを開くために、フレームワークによって呼び出されます。|
|[CWinApp::ParseCommandLine](#parsecommandline)|個々 のパラメーターと、コマンドラインでフラグを解析します。|
|[Cwinapp::pretranslatemessage](#pretranslatemessage)|Windows 関数にディスパッチされる前に、メッセージをフィルター処理[TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage)します。|
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|アプリケーションに到達する前に、特定のメッセージを受け取ります。|
|[CWinApp::ProcessShellCommand](#processshellcommand)|コマンドライン引数とフラグを処理します。|
|[CWinApp::ProcessWndProcException](#processwndprocexception)|アプリケーションのメッセージとコマンド ハンドラーによってスローされたすべてのハンドルされない例外を受け取ります。|
|[CWinApp::Register](#register)|カスタマイズした登録を実行します。|
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|再起動マネージャーとアプリケーションを登録します。|
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|再起動マネージャーが、アプリケーションが予期せず終了したときに開いていたファイルを開くかどうかを判断します。|
|[CWinApp::RestartInstance](#restartinstance)|再起動マネージャーによって開始されたアプリケーションの再起動を処理します。|
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|アプリケーションが再起動すると再起動マネージャーが自動保存されたファイルを復元するかどうかを判断します。|
|[使わ](#run)|既定のメッセージ ループを実行します。 メッセージ ループをカスタマイズする上書きします。|
|[CWinApp::RunAutomated](#runautomated)|テスト アプリケーションのコマンドラインを **/Automation**オプション。 互換性のために残されています。 値を使用して、代わりに、 [CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated)呼び出した後[ParseCommandLine](#parsecommandline)します。|
|[CWinApp::RunEmbedded](#runembedded)|テスト アプリケーションのコマンドラインを **/automation**オプション。 互換性のために残されています。 値を使用して、代わりに、 [CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded)呼び出した後[ParseCommandLine](#parsecommandline)します。|
|[CWinApp::SaveAllModified](#saveallmodified)|変更されたすべてのドキュメントを保存するユーザーに求めます。|
|[通知](#selectprinter)|[印刷] ダイアログ ボックスで、ユーザーによって示される以前のプリンターを選択します。|
|[CWinApp::SetHelpMode](#sethelpmode)|設定して、アプリケーションで使用するヘルプの種類を初期化します。|
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|再起動マネージャーが予期せず終了したアプリケーションを回復するかどうかを判断します。|
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|再起動マネージャーによって自動保存が一定の間隔でドキュメントを開くかどうかを判断します。|
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|決定かどうか再起動マネージャーによって自動保存、アプリケーションを再起動すると、開いているドキュメント。|
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|アプリケーションが再起動マネージャーをサポートしているかどうかを判断します。|
|[CWinApp::Unregister](#unregister)|によって登録される既知のすべての登録を解除、`CWinApp`オブジェクト。|
|[Cwinapp::winhelp](#winhelp)|呼び出し、 `WinHelp` Windows 関数。|
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|バイナリ データ、アプリケーションのエントリを書き込みます。INI ファイルです。|
|[Cwinapp::writeprofileint](#writeprofileint)|アプリケーションのエントリには、整数を書き込みます。INI ファイルです。|
|[CWinApp::WriteProfileString](#writeprofilestring)|アプリケーションのエントリには、文字列を書き込みます。INI ファイルです。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CWinApp::EnableShellOpen](#enableshellopen)|Windows ファイル マネージャーからデータ ファイルを開くことができます。|
|[既定](#loadstdprofilesettings)|標準の.INI ファイルの設定と有効、MRU ファイル リスト機能をします。|
|[CWinApp::OnContextHelp](#oncontexthelp)|アプリケーション内で shift キーを押しながら F1 ヘルプを処理します。|
|[CWinApp::OnFileNew](#onfilenew)|ID_FILE_NEW コマンドを実装します。|
|[CWinApp::OnFileOpen](#onfileopen)|ID_FILE_OPEN コマンドを実装します。|
|[CWinApp::OnFilePrintSetup](#onfileprintsetup)|ID_FILE_PRINT_SETUP コマンドを実装します。|
|[:Onhelp](#onhelp)|アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。|
|[CWinApp::OnHelpFinder](#onhelpfinder)|ID_HELP_FINDER と ID_DEFAULT_HELP コマンドを処理します。|
|[CWinApp::OnHelpIndex](#onhelpindex)|ID_HELP_INDEX コマンドを処理し、既定のヘルプ トピックを提供します。|
|[CWinApp::OnHelpUsing](#onhelpusing)|ID_HELP_USING コマンドを処理します。|
|[登録](#registershellfiletypes)|Windows ファイル マネージャーで、アプリケーションのすべてのドキュメントの種類を登録します。|
|[CWinApp::SetAppID](#setappid)|アプリケーションのアプリケーション ユーザー モデル ID を明示的に設定します。 すべてのユーザー インターフェイスは (最適な場所では、アプリケーションのコンス トラクター) のユーザーに表示される前に、このメソッドを呼び出す必要があります。|
|[書き込むに](#setregistrykey)|アプリケーション設定の代わりに、レジストリに格納されます。INI ファイル。|
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|アプリケーションのすべてのドキュメントの種類の Windows ファイル マネージャーを登録解除します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|ユーザーがヘルプ コンテキストのモード (通常は shift キーを押しながら F1 と呼び出されます) になっていることを示します。|
|[CWinApp::m_eHelpType](#m_ehelptype)|アプリケーションで使用するヘルプの種類を指定します。|
|[CWinApp::m_hInstance](#m_hinstance)|アプリケーションの現在のインスタンスを識別します。|
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。|
|[CWinApp::m_nCmdShow](#m_ncmdshow)|ウィンドウの最初に表示する方法を指定します。|
|[先](#m_pactivewnd)|OLE サーバーがアクティブである場合は、コンテナー アプリケーションのメイン ウィンドウへのポインター。|
|[CWinApp::m_pszAppID](#m_pszappid)|アプリケーション ユーザー モデル id。|
|[CWinApp::m_pszAppName](#m_pszappname)|アプリケーション名を示します。|
|[CWinApp::m_pszExeName](#m_pszexename)|アプリケーションのモジュールの名前。|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|アプリケーションのヘルプ ファイルへのパス。|
|[CWinApp::m_pszProfileName](#m_pszprofilename)|アプリケーションの.INI ファイル名。|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|アプリケーションのプロファイル設定を格納するための完全なレジストリ キーを判断するために使用します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|再起動マネージャーの動作を決定するフラグ。|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|自動保存の間隔をミリ秒で時間の長さ。|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|アプリケーションのデータ復旧ハンドラーへのポインター。|

## <a name="remarks"></a>Remarks

アプリケーション オブジェクトは、アプリケーション (およびの各インスタンス) を初期化して、アプリケーションを実行するために、メンバー関数を提供します。

Microsoft Foundation classes を使用する各アプリケーションから派生した 1 つのオブジェクトを含めることができますのみ`CWinApp`します。 このオブジェクトは、他の C++ のグローバル オブジェクトが構築時に構成されは Windows を呼び出すときに既に使用可能な`WinMain`関数で、Microsoft Foundation Class ライブラリによって提供されます。 派生宣言`CWinApp`グローバル レベルのオブジェクト。

アプリケーションのクラスから派生すると`CWinApp`、オーバーライド、 [InitInstance](#initinstance)メンバー関数は、アプリケーションのメイン ウィンドウのオブジェクトを作成します。

加え、`CWinApp`メンバー関数は、Microsoft Foundation Class ライブラリは、次のグローバル関数へのアクセスを`CWinApp`オブジェクトとその他のグローバル情報。

- [AfxGetApp](application-information-and-management.md#afxgetapp)へのポインターを取得、`CWinApp`オブジェクト。

- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)は現在のアプリケーション インスタンスを識別するハンドルを取得します。

- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle)アプリケーションのリソースを識別するハンドルを取得します。

- [AfxGetAppName](application-information-and-management.md#afxgetappname)アプリケーションの名前を含む文字列へのポインターを取得します。 またはへのポインターがある場合、`CWinApp`オブジェクトを使用して`m_pszExeName`アプリケーションの名前を取得します。

参照してください[CWinApp:アプリケーション クラス](../../mfc/cwinapp-the-application-class.md)の詳細については、`CWinApp`など、次の概要については、クラス。

- `CWinApp`-アプリケーション ウィザードによって作成されたコードを派生します。

- `CWinApp`アプリケーションの実行シーケンス内のロール。

- `CWinApp`既定のメンバー関数の実装です。

- `CWinApp`主要 overridables します。

`m_hPrevInstance`データ メンバーが存在しません。 アプリケーションの別のインスタンスが実行されているかどうかを確認するのには、名前付きミュー テックスを使用します。 失敗すると、ミュー テックスを開く、実行中のアプリケーションの他のインスタンスはあるありません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="adddoctemplate"></a>  とき

ドキュメント テンプレートを保持する使用可能なドキュメント テンプレートの一覧に追加するには、このメンバー関数を呼び出します。

```
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>パラメーター

*pTemplate*<br/>
ポインター、`CDocTemplate`を追加します。

### <a name="remarks"></a>Remarks

呼び出す前に、すべてのドキュメントをアプリケーションにテンプレートを追加する必要があります[RegisterShellFileTypes](#registershellfiletypes)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

##  <a name="addtorecentfilelist"></a>  CWinApp::AddToRecentFileList

追加するには、このメンバー関数を呼び出す*終了*MRU ファイル リストにします。

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>パラメーター

*終了*<br/>
ファイルのパス。

### <a name="remarks"></a>Remarks

呼び出す必要があります、 [LoadStdProfileSettings](#loadstdprofilesettings)メンバー関数は、このメンバー関数を使用する前に、現在の MRU ファイル リストを読み込めません。

フレームワークは、ファイルを開くか、または新しい名前でファイルを保存する名前を付けて保存コマンドを実行するときにこのメンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

##  <a name="applicationrecoverycallback"></a>  CWinApp::ApplicationRecoveryCallback

アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>パラメーター

*lpvParam*<br/>
[in]将来使用するために予約されています。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は 0エラーが発生した場合は 0 以外の値。

### <a name="remarks"></a>Remarks

アプリケーションでは、再起動マネージャーをサポートする場合、フレームワークは、アプリケーションが予期せず終了したときに、この関数を呼び出します。

既定の実装`ApplicationRecoveryCallback`を使用して、`CDataRecoveryHandler`を現在開いているドキュメントの一覧をレジストリに保存します。 このメソッドは、すべてのファイルを自動保存にしません。

動作をカスタマイズするには、派生では、この関数をオーバーライド[CWinApp クラス](../../mfc/reference/cwinapp-class.md)独自アプリケーションの回復方法をパラメーターとして渡すまたは[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)します。

##  <a name="closealldocuments"></a>  CWinApp::CloseAllDocuments

終了する前にすべての開いているドキュメントを閉じるには、このメンバー関数を呼び出します。

```
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>パラメーター

*bEndSession*<br/>
Windows セッションを終了するかどうかを指定します。 TRUE である場合は、セッションが終了中です。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

呼び出す[HideApplication](#hideapplication)呼び出す前に`CloseAllDocuments`します。

##  <a name="createprinterdc"></a>  CWinApp::CreatePrinterDC

選択したプリンターのプリンター デバイス コンテキスト (DC) を作成するには、このメンバー関数を呼び出します。

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
プリンター デバイス コンテキストへの参照。

### <a name="return-value"></a>戻り値

プリンター デバイス コンテキストを正常に作成した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

`CreatePrinterDC` 参照渡しするで、印刷に使用できるようにしているデバイス コンテキストを初期化します。

印刷が完了したときに、関数が成功した場合は、デバイス コンテキストを破棄する必要があります。 デストラクターをさせることができます、 [CDC](../../mfc/reference/cdc-class.md)オブジェクトを実行または呼び出すことによって明示的に行うことができます[デバイス コンテキストの破棄](../../mfc/reference/cdc-class.md#deletedc)します。

##  <a name="cwinapp"></a>  CWinApp::CWinApp

構築、`CWinApp`オブジェクトを渡します*lpszAppName*をアプリケーション名として保存します。

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszAppName*<br/>
Windows を使用するアプリケーション名を含む null で終わる文字列。 この引数が指定されていないか NULL の場合は、 `CWinApp` AFX_IDS_APP_TITLE リソース文字列または実行可能ファイルのファイル名を使用します。

### <a name="remarks"></a>Remarks

1 つのグローバル オブジェクトを構築する必要があります、 `CWinApp`-クラスを派生します。 1 つのみできます`CWinApp`アプリケーション内のオブジェクト。 コンス トラクターへのポインターを格納する、`CWinApp`オブジェクトように`WinMain`オブジェクトのメンバーを初期化し、アプリケーションを実行する関数を呼び出すことができます。

##  <a name="delregtree"></a>  CWinApp::DelRegTree

特定のレジストリ キーおよびそのすべてのサブキーを削除します。

```
LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName);

LONG DelRegTree(
    HKEY hParentKey,
    const CString& strKeyName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*hParentKey*<br/>
レジストリ キーへのハンドルします。

*strKeyName*<br/>
削除するレジストリ キーの名前。

*pTM*<br/>
CAtlTransactionManager オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は、ERROR_SUCCESS を返します。 関数が失敗した場合は、Winerror.h で定義されている 0 以外のエラー コードは、戻り値。

### <a name="remarks"></a>Remarks

指定したキーおよびそのサブキーを削除するには、この関数を呼び出します。

##  <a name="domessagebox"></a>  CWinApp::DoMessageBox

フレームワークは、グローバル関数の場合、メッセージ ボックスを実装するには、このメンバー関数を呼び出す[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)します。

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>パラメーター

*lpszPrompt*<br/>
メッセージ ボックス内のテキストのアドレス。

*%n タイプ*<br/>
メッセージ ボックス[スタイル](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)します。

*nIDPrompt*<br/>
ヘルプ コンテキストの文字列のインデックスです。

### <a name="return-value"></a>戻り値

同じ値を返します`AfxMessageBox`します。

### <a name="remarks"></a>Remarks

メッセージ ボックスを開くには、このメンバー関数を呼び出さないでください。使用して、`AfxMessageBox`代わりにします。

アプリケーション全体の処理をカスタマイズするには、この関数をオーバーライド`AfxMessageBox`呼び出し。

##  <a name="dowaitcursor"></a>  CWinApp::DoWaitCursor

このメンバー関数が実装するためにフレームワークによって呼び出されます[CWaitCursor](../../mfc/reference/cwaitcursor-class.md)、 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)、 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)、および[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)します。

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>パラメーター

*nCode*<br/>
このパラメーターが 1 の場合は、待機カーソルが表示されます。 0 の場合は、参照カウントをインクリメントせずに待機カーソルが復元されます。 -1 の場合、待機カーソルを終了します。

### <a name="remarks"></a>Remarks

既定値は砂時計カーソルを実装します。 `DoWaitCursor` 参照カウントを保持します。 正の値とは砂時計カーソルが表示されます。

通常は呼び出すはありません、`DoWaitCursor`を直接待機カーソルを変更または待機カーソルが表示されますが、追加処理を行うには、このメンバー関数をオーバーライドできます。

待機カーソルを実装する簡単でより効率的な方法を使用して`CWaitCursor`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

##  <a name="enabled2dsupport"></a>  CWinApp::EnableD2DSupport

Visual Studio 2010 SP1 が必要です。

アプリケーションの D2D のサポートを有効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>パラメーター

*d2dFactoryType*<br/>
D2D ファクトリとリソースのスレッド処理モデルを作成します。

*writeFactoryType*<br/>
書き込みのファクトリ オブジェクトが共有か分離かどうかを指定する値

### <a name="return-value"></a>戻り値

D2D のサポートが有効な場合は FALSE、それ以外の場合に TRUE を返します

##  <a name="enablehtmlhelp"></a>  CWinApp::EnableHtmlHelp

コンス トラクター内からこのメンバー関数を呼び出す、 `CWinApp`-アプリケーションのヘルプの html ヘルプを使用するクラスを派生します。

```
void EnableHtmlHelp();
```

### <a name="remarks"></a>Remarks

##  <a name="enableshellopen"></a>  CWinApp::EnableShellOpen

通常、関数を呼び出す、`InitInstance`オーバーライドでは Windows ファイル マネージャー内からファイルをダブルクリックしたときに、データ ファイルを開くアプリケーションのユーザーを有効にします。

```
void EnableShellOpen();
```

### <a name="remarks"></a>Remarks

呼び出す、`RegisterShellFileTypes`メンバーは、この関数を組み合わせて機能または提供します。ドキュメントの種類の手動登録のため、アプリケーションと共に REG ファイル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

##  <a name="enabletaskbarinteraction"></a>  CWinApp::EnableTaskbarInteraction

タスク バーの相互作用を有効にします。

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
Windows 7 タスク バーとの対話が (TRUE) を有効にするか、無効 (FALSE) かどうかを指定します。

### <a name="return-value"></a>戻り値

タスク バーの相互作用を有効または無効にできる場合は、TRUE を返します。

### <a name="remarks"></a>Remarks

メイン ウィンドウの作成前に、このメソッドを呼び出す必要があります、それ以外の場合、アサートし、FALSE を返します。

##  <a name="exitinstance"></a>  使う

内から、フレームワークによって呼び出されます、`Run`メンバー関数は、アプリケーションのこのインスタンスを終了します。

```
virtual int ExitInstance();
```

### <a name="return-value"></a>戻り値

アプリケーションの終了コード。0 は、エラーを 、エラーを示す 0 より大きい値です。 この値からの戻り値として使用されます`WinMain`します。

### <a name="remarks"></a>Remarks

このメンバー関数から呼び出さないで任意の場所内では、`Run`メンバー関数。

この関数の既定の実装では、アプリケーションのフレームワークのオプションを書き込みます。INI ファイルです。 アプリケーションの終了時にクリーンアップするには、この関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

##  <a name="getapplicationrecoveryparameter"></a>  CWinApp::GetApplicationRecoveryParameter

アプリケーションの復旧メソッドの入力パラメーターを取得します。

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>戻り値

アプリケーションの回復方法の既定の入力パラメーター。

### <a name="remarks"></a>Remarks

この関数の既定の動作は、NULL を返します。

詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。

##  <a name="getapplicationrecoverypinginterval"></a>  CWinApp::GetApplicationRecoveryPingInterval

再起動マネージャーが回復のコールバック関数が返すが待機する時間の長さを返します。

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>戻り値

時間 (ミリ秒) の長さ。

### <a name="remarks"></a>Remarks

ときに予期せず、再起動マネージャーが終了に登録されているアプリケーション、アプリケーション開いているドキュメントを保存しようとし回復コールバック関数を呼び出します。 既定の復旧のコールバック関数は、 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。

回復のコールバック関数が返すのフレームワークが待機する時間の長さは、ping の間隔です。 Ping の間隔をカスタマイズするには、オーバーライド`CWinApp::GetApplicationRecoveryPingInterval`またはカスタム値を提供することで`RegisterWithRestartManager`します。

##  <a name="getapplicationrestartflags"></a>  CWinApp::GetApplicationRestartFlags

再起動マネージャーのフラグを返します。

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>戻り値

再起動マネージャーのフラグ。 既定の実装では、0 を返します。

### <a name="remarks"></a>Remarks

再起動マネージャーのフラグは、既定の実装に影響を与えるありません。 将来の使用に提供されます。

再起動マネージャーを使用して、アプリケーションを登録するときに、フラグを設定する[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)します。

再起動マネージャーのフラグを指定できる値は次のとおりです。

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="getappregistrykey"></a>  CWinApp::GetAppRegistryKey

HKEY_CURRENT_USER のキーを返します\\「ソフトウェア」\RegistryKey\ProfileName します。

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*pTM*<br/>
ポインターを`CAtlTransactionManager`オブジェクト。

### <a name="return-value"></a>戻り値

関数が成功した場合、アプリケーション キーそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

##  <a name="getdatarecoveryhandler"></a>  CWinApp::GetDataRecoveryHandler

アプリケーションのこのインスタンスのデータ復旧のハンドラーを取得します。

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>戻り値

アプリケーションのこのインスタンスのデータ復旧のハンドラー。

### <a name="remarks"></a>Remarks

再起動マネージャーを使用する各アプリケーションは、1 つのインスタンスをいる必要があります、 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)します。 このクラスは、開いているドキュメントと自動保存ファイルの監視を担当します。 動作、`CDataRecoveryHandler`再起動マネージャーの構成によって異なります。 詳細については、次を参照してください。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)します。

このメソッドは、Windows Vista より前のオペレーティング システムで NULL を返します。 再起動マネージャーは、Windows Vista より前のオペレーティング システムではサポートされていません。

アプリケーションがデータ復旧のハンドラーを現在持っていない場合、このメソッドは 1 つを作成し、ポインターを返します。

##  <a name="getfirstdoctemplateposition"></a>  CWinApp::GetFirstDocTemplatePosition

アプリケーション内の最初のドキュメント テンプレートの位置を取得します。

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>戻り値

イテレーションまたはオブジェクト ポインターの取得に使用できる位置の値リストが空の場合は NULL です。

### <a name="remarks"></a>Remarks

呼び出しで返される位置の値を使用して[GetNextDocTemplate](#getnextdoctemplate) 、最初に[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクト。

##  <a name="gethelpmode"></a>  CWinApp::GetHelpMode

アプリケーションで使用するヘルプの種類を取得します。

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>戻り値

アプリケーションで使用されるヘルプの種類。 参照してください[CWinApp::m_eHelpType](#m_ehelptype)詳細についてはします。

##  <a name="getnextdoctemplate"></a>  CWinApp::GetNextDocTemplate

識別されるドキュメント テンプレートを取得します。 *pos*、設定し、 *pos*位置の値にします。

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しによって返される位置の値への参照を`GetNextDocTemplate`または[GetFirstDocTemplatePosition](#getfirstdoctemplateposition)します。 値は、この呼び出しによって、次の位置に更新されます。

### <a name="return-value"></a>戻り値

ポインターを[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

使用することができます`GetNextDocTemplate`への呼び出しを初期位置を確立する場合は、順方向の反復ループで`GetFirstDocTemplatePosition`します。

位置の値が有効であることを確認する必要があります。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。

取得したドキュメントのテンプレートが最後の場合の新しい値*pos* NULL に設定されます。

##  <a name="getprinterdevicedefaults"></a>  CWinApp::GetPrinterDeviceDefaults

印刷をプリンター デバイス コンテキストを準備するには、このメンバー関数を呼び出します。

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>パラメーター

*pPrintDlg*<br/>
ポインターを[PRINTDLG](/windows/desktop/api/commdlg/ns-commdlg-tagpda)構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

Windows から、現在のプリンターの既定値を取得します。INI ファイルとして、必要に応じて、または印刷のセットアップでユーザーが前回のプリンター構成の設定を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

##  <a name="getprofilebinary"></a>  は

アプリケーションのレジストリの指定したセクション内のエントリからバイナリ データを取得するには、このメンバー関数を呼び出すか。INI ファイルです。

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>パラメーター

*大文字、小文字*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。

*lpszEntry*<br/>
値を取得するエントリを指定する NULL で終わる文字列へのポインター。

*ppData*<br/>
データのアドレスを受け取るポインターへのポインター。

*ペタバイト*<br/>
バイト単位でデータのサイズを受け取る UINT を指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数はそのため、大文字小文字を区別されていない内の文字列、*大文字、小文字*と*lpszEntry*場合パラメーターが異なる場合があります。

> [!NOTE]
> `GetProfileBinary` バッファーを割り当てるしでそのアドレスを返します\* *ppData*します。 呼び出し元を使用してバッファーを解放する**delete[]** します。

> [!IMPORTANT]
> この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

たとえば、次を参照してください。 [CWinApp::WriteProfileBinary](#writeprofilebinary)します。

##  <a name="getprofileint"></a>  は

アプリケーションのレジストリまたは .INI ファイルの指定のセクション内のエントリから整数値を取得します。

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>パラメーター

*大文字、小文字*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。

*lpszEntry*<br/>
値を取得するエントリを指定する NULL で終わる文字列へのポインター。

*見つからなかった*<br/>
フレームワークがエントリを見つけられなかったときのために指定する既定値。

### <a name="return-value"></a>戻り値

正常終了した場合は、指定されたエントリに続く文字列の整数値を返します。 戻り値は、の値、*見つからなかった*パラメーター、関数は、エントリが見つからない場合。 指定されたエントリに対応する値が整数でない場合は、0 を返します。

このメンバー関数は .INI ファイル内の値として 16 進表記をサポートします。 符号付き整数を取得するときに値をキャストする必要があります、 **int**します。

### <a name="remarks"></a>Remarks

このメンバー関数はそのため、大文字小文字を区別されていない内の文字列、*大文字、小文字*と*lpszEntry*場合パラメーターが異なる場合があります。

> [!IMPORTANT]
> この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

たとえば、次を参照してください。 [cwinapp::writeprofileint](#writeprofileint)します。

##  <a name="getprofilestring"></a>  CWinApp::GetProfileString

アプリケーションのレジストリで指定されたセクション内のエントリに関連付けられている文字列を取得するには、このメンバー関数を呼び出すか。INI ファイルです。

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>パラメーター

*大文字、小文字*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。

*lpszEntry*<br/>
文字列を取得するエントリを含む null で終わる文字列へのポインター。 この値は、NULL は指定できません。

*から*<br/>
初期化ファイルにエントリが見つからない場合は、指定したエントリの既定の文字列値を指します。

### <a name="return-value"></a>戻り値

戻り値は、アプリケーションの文字列です。INI ファイルまたは*から*文字列が見つからない場合。 フレームワークでサポートされる文字列の最大長は、_MAX_PATH です。 場合*から*が null の場合、戻り値は空の文字列。

### <a name="remarks"></a>Remarks

> [!IMPORTANT]
> この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

別の例の例を参照してください。[は](#getprofileint)します。

##  <a name="getsectionkey"></a>  CWinApp::GetSectionKey

HKEY_CURRENT_USER のキーを返します\\「ソフトウェア」\RegistryKey\AppName\lpszSection します。

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*大文字、小文字*<br/>
取得するキーの名前。

*pTM*<br/>
ポインターを`CAtlTransactionManager`オブジェクト。

### <a name="return-value"></a>戻り値

セクション キー、関数が成功した場合それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

##  <a name="hideapplication"></a>  CWinApp::HideApplication

開いているドキュメントを閉じる前にアプリケーションを非表示にするには、このメンバー関数を呼び出します。

```
void HideApplication();
```

##  <a name="htmlhelp"></a>  CWinApp::HtmlHelp

Html ヘルプ アプリケーションを起動するには、このメンバー関数を呼び出します。

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>パラメーター

*指定*<br/>
追加のデータを指定します。 使用される値の値によって異なります、 *nCmd*パラメーター。

*nCmd*<br/>
要求されるヘルプの種類を指定します。 使用可能な値、および影響についての一覧については、*指定*パラメーターを参照してください、 *uCommand*パラメーターについて、HTMLHelp API 関数で、Windows SDK で説明します。

### <a name="remarks"></a>Remarks

フレームワークでは、html ヘルプ アプリケーションを起動するには、この関数も呼び出します。

フレームワークでは、アプリケーションの終了時に、html ヘルプ アプリケーションは自動的に閉じます。

##  <a name="initinstance"></a>  場合は

Windows には、同時に実行する同じプログラムの複数のコピーができます。

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>戻り値

初期化が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションの初期化は概念的には 2 つのセクションに分かれています。: 1 回限りのアプリケーションの初期化は、最初に行われる、プログラムの実行の時間と、各実行のインスタンスを初期化時刻の最初の時間を含む、プログラムの実行のコピー。 フレームワークの実装の`WinMain`この関数を呼び出します。

オーバーライド`InitInstance`を Windows で実行されているアプリケーションの新しいインスタンスを初期化します。 通常、オーバーライドする`InitInstance`をメイン ウィンドウ オブジェクトを構築し、設定、`CWinThread::m_pMainWnd`データ メンバーは、そのウィンドウをポイントします。 このメンバー関数のオーバーライドの詳細については、次を参照してください[CWinApp:。アプリケーション クラス](../../mfc/cwinapp-the-application-class.md)します。

> [!NOTE]
> MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 呼び出す場合[CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex)で、`InitInstance`オーバーライド、COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED ではなく) を指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

##  <a name="istaskbarinteractionenabled"></a>  CWinApp::IsTaskbarInteractionEnabled

Windows 7 タスクバーの相互作用が有効になっているかどうかを指示します。

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>戻り値

場合に TRUE を返します`EnableTaskbarInteraction`が呼び出されて、オペレーティング システムが Windows 7 またはそれ以降。

### <a name="remarks"></a>Remarks

タスク バーの相互作用は、MDI アプリケーションがアプリケーションのタスク バー ボタンの上にマウス ポインターがときに表示される個別のタブ付きのサムネイルで MDI 子フォームのコンテンツを表示することを意味します。

##  <a name="loadcursor"></a>  CWinApp::LoadCursor

指定されたカーソル リソースを読み込みます*lpszResourceName*またはで指定*可能*現在の実行可能ファイルからです。

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
カーソル リソースの名前を含む null で終わる文字列へのポインター。 使用することができます、`CString`この引数にします。

*可能*<br/>
カーソル リソースの ID。 リソースの一覧は、次を参照してください。 [LoadCursor](/windows/desktop/api/winuser/nf-winuser-loadcursora) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

成功した場合、カーソルを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

`LoadCursor` 既に読み込まれていない; 場合にのみをメモリにカーソルを読み込むそれ以外の場合、既存のリソースのハンドルを取得します。

使用して、 [LoadStandardCursor](#loadstandardcursor)または[LoadOEMCursor](#loadoemcursor)メンバー関数は定義済みの Windows カーソルにアクセスします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

##  <a name="loadicon"></a>  CWinApp::LoadIcon

指定されたアイコン リソースを読み込みます*lpszResourceName*またはで指定*可能*実行可能ファイルからです。

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
アイコン リソースの名前を含む null で終わる文字列へのポインター。 使用することも、`CString`この引数にします。

*可能*<br/>
アイコン リソースの ID 番号。

### <a name="return-value"></a>戻り値

成功した場合は、アイコンを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

`LoadIcon` 既に読み込まれていない; 場合にのみ、アイコンを読み込むそれ以外の場合、既存のリソースのハンドルを取得します。

使用することができます、 [LoadStandardIcon](#loadstandardicon)または[LoadOEMIcon](#loadoemicon)メンバー関数は定義済みの Windows アイコンにアクセスします。

> [!NOTE]
> このメンバー関数は、Win32 API 関数を呼び出す[LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona)SM_CXICON と SM_CYICON システム メトリック値に準拠しているサイズのアイコンを読み込むことができますのみです。

##  <a name="loadoemcursor"></a>  CWinApp::LoadOEMCursor

定義済みで指定されたカーソル リソースの読み込み、Windows *nIDCursor*します。

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>パラメーター

*nIDCursor*<br/>
**OCR_** マニフェスト定数の識別子を定義済みの Windows カーソルを指定します。 必要があります`#define OEMRESOURCE`する前に`#include \<afxwin.h>`アクセスするために、 **OCR_** WINDOWS で使用される定数。H.

### <a name="return-value"></a>戻り値

成功した場合、カーソルを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

使用して、`LoadOEMCursor`または[LoadStandardCursor](#loadstandardcursor)メンバー関数は定義済みの Windows カーソルにアクセスします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

##  <a name="loadoemicon"></a>  CWinApp::LoadOEMIcon

定義済みで指定されたアイコン リソースを読み込み、Windows *nIDIcon*します。

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>パラメーター

*nIDIcon*<br/>
**OIC_** マニフェスト定数の識別子を定義済みの Windows アイコンを指定します。 必要があります`#define OEMRESOURCE`する前に`#include \<afxwin.h>`にアクセスする、 **OIC_** WINDOWS で使用される定数。H.

### <a name="return-value"></a>戻り値

成功した場合は、アイコンを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

使用して、`LoadOEMIcon`または[LoadStandardIcon](#loadstandardicon)メンバー関数は定義済みの Windows アイコンにアクセスします。

##  <a name="loadstandardcursor"></a>  CWinApp::LoadStandardCursor

定義済みのカーソル リソースを読み込み、Windows を*されています*を指定します。

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>パラメーター

*されています*<br/>
**Idc _** マニフェスト定数の識別子を定義済みの Windows カーソルを指定します。 WINDOWS では、これらの識別子が定義されています。H. 次の一覧は、使用可能な定義済みの値との意味を示しています*されています*:。

- IDC_ARROW 標準矢印カーソル

- IDC_IBEAM 標準のテキスト挿入カーソル

- Windows が時間のかかるタスクを実行するときに使用する IDC_WAIT 砂時計カーソル

- 選択範囲の IDC_CROSS 十字カーソル

- まっすぐ IDC_UPARROW 矢印

- IDC_SIZE 廃止とサポートされていません。IDC_SIZEALL を使用します。

- IDC_SIZEALL A 4 方向矢印カーソル。 ウィンドウのサイズ変更に使用するカーソル。

- IDC_ICON 廃止とサポートされていません。 IDC_ARROW を使用します。

- 左と右下の両端に IDC_SIZENWSE 双方向矢印

- 右方向と下の左上の両端に IDC_SIZENESW 双方向矢印

- 双方向の IDC_SIZEWE 水平矢印

- IDC_SIZENS 垂直の両方向矢印

### <a name="return-value"></a>戻り値

成功した場合、カーソルを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

使用して、`LoadStandardCursor`または[LoadOEMCursor](#loadoemcursor)メンバー関数は定義済みの Windows カーソルにアクセスします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

##  <a name="loadstandardicon"></a>  CWinApp::LoadStandardIcon

定義済みのアイコン リソースを読み込み、Windows を*lpszIconName*を指定します。

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>パラメーター

*lpszIconName*<br/>
定義済みの Windows アイコンを指定するマニフェスト定数の識別子。 WINDOWS では、これらの識別子が定義されています。H. 可能な定義済みの値とその説明の一覧は、次を参照してください。、*されています*パラメーター [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona) Windows SDK にします。

### <a name="return-value"></a>戻り値

成功した場合は、アイコンを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

使用して、`LoadStandardIcon`または[LoadOEMIcon](#loadoemicon)メンバー関数は定義済みの Windows アイコンにアクセスします。

##  <a name="loadstdprofilesettings"></a>  既定

このメンバー関数内から、 [InitInstance](#initinstance)メンバー関数を有効にし、最近使用した (MRU) ファイルの一覧を読み込むと最後の状態をプレビューします。

```
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>パラメーター

*nMaxMRU*<br/>
追跡するために最近使用したファイルの数。

### <a name="remarks"></a>Remarks

場合*nMaxMRU*は 0、MRU 一覧は維持されません。

##  <a name="m_bhelpmode"></a>  CWinApp::m_bHelpMode

アプリケーションがヘルプ コンテキスト モード (通常で起動される SHIFT + F1) 以外の場合は TRUE。それ以外の場合は FALSE です。

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>Remarks

ヘルプ コンテキスト モードでは、カーソルが疑問符になり、ユーザーが画面の移動できます。 ヘルプ モードの場合の特別な処理を実装する場合は、このフラグを確認します。 `m_bHelpMode` BOOL 型のパブリック変数です。

##  <a name="m_dwrestartmanagersupportflags"></a>  CWinApp::m_dwRestartManagerSupportFlags

再起動マネージャーの動作を決定するフラグ。

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>Remarks

再起動マネージャーを有効にするには設定`m_dwRestartManagerSupportFlags`する動作をします。 次の表では、使用できるフラグを示します。

|||
|-|-|
|フラグ|説明|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|使用して、アプリケーションが登録されている[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)します。 再起動マネージャーは予期せず終了した場合、アプリケーションを再起動します。|
|-AFX_RESTART_MANAGER_SUPPORT_RECOVERY|再起動マネージャーとアプリケーションを登録して、アプリケーションが再起動すると、再起動マネージャーが回復コールバック関数を呼び出します。 既定の復旧のコールバック関数は、 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。|
|-AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|自動保存が有効になっていると、再起動マネージャーによって自動保存、アプリケーションを再起動すると、開いているドキュメント。|
|-AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|自動保存が有効になっていると、再起動マネージャーによって自動保存、一定の間隔でドキュメントを開いています。 間隔が定義されている[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)します。|
|-AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|再起動マネージャーは、予期しない終了からアプリケーションを再起動した後に開いていたドキュメントを開きます。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)は開いているドキュメントの一覧を格納して、復元することを処理します。|
|-AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|再起動マネージャーは、アプリケーションの再起動後に自動保存されたファイルを復元するユーザーに求めます。 `CDataRecoveryHandler`クラスは、ユーザーをクエリします。|
|-AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|AFX_RESTART_MANAGER_SUPPORT_RESTART、AFX_RESTART_MANAGER_SUPPORT_RECOVER、および AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES の和集合。|
|-AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART、AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL、および AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES の和集合。|
|-AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_RESTART、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES、および AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES の和集合。|
|-AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|共用体 ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY、AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES、および AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES します。|

##  <a name="m_ehelptype"></a>  CWinApp::m_eHelpType

このデータ メンバーの型は、列挙型、AFX_HELP_TYPE 内で定義されている、`CWinApp`クラス。

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>Remarks

AFX_HELP_TYPE 列挙体の定義は次のとおりです。

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- HTML ヘルプに、アプリケーションのヘルプを設定するには、呼び出す[として](#sethelpmode)指定`afxHTMLHelp`します。

- WinHelp アプリケーションのヘルプを設定するには、呼び出す`SetHelpMode`指定`afxWinHelp`します。

##  <a name="m_hinstance"></a>  CWinApp::m_hInstance

対応する、 *hInstance*に Windows によって渡されるパラメーター`WinMain`します。

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>Remarks

`m_hInstance`データ メンバーは、Windows で実行されているアプリケーションの現在のインスタンスを識別するハンドル。 これは、グローバル関数によって返される[AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)します。 `m_hInstance` 型 HINSTANCE のパブリック変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

##  <a name="m_lpcmdline"></a>  CWinApp::m_lpCmdLine

対応する、 *lpCmdLine*に Windows によって渡されるパラメーター`WinMain`します。

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>Remarks

アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。 使用`m_lpCmdLine`ユーザーがアプリケーションを起動したときに入力した任意のコマンドライン引数にアクセスします。 `m_lpCmdLine` LPTSTR 型のパブリック変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="m_nautosaveinterval"></a>  CWinApp::m_nAutosaveInterval

自動保存の間隔をミリ秒で時間の長さ。

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>Remarks

設定された間隔で自動保存の開いているドキュメントに、再起動マネージャーを構成できます。 アプリケーションが自動保存ファイルではない場合は、このパラメーターは影響を与えません。

##  <a name="m_ncmdshow"></a>  CWinApp::m_nCmdShow

対応する、 *nCmdShow*に Windows によって渡されるパラメーター`WinMain`します。

```
int m_nCmdShow;
```

### <a name="remarks"></a>Remarks

渡す必要があります`m_nCmdShow`呼び出すときに引数として[また](../../mfc/reference/cwnd-class.md#showwindow)アプリケーションのメイン ウィンドウにします。 `m_nCmdShow` 型のパブリック変数**int**します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

##  <a name="m_pactivewnd"></a>  先

このデータ メンバーを使用すると、OLE サーバー アプリケーション、インプレース アクティブ化を含む OLE コンテナー アプリケーションのメイン ウィンドウへのポインターを格納できます。

### <a name="remarks"></a>Remarks

このデータ メンバーが NULL の場合は、アプリケーションがない、インプレース アクティブにします。

フレームワークは、フレーム ウィンドウは、インプレース OLE コンテナー アプリケーションによってアクティブ化されるときに、このメンバー変数を設定します。

##  <a name="m_pdatarecoveryhandler"></a>  CWinApp::m_pDataRecoveryHandler

アプリケーションのデータ復旧ハンドラーへのポインター。

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>Remarks

アプリケーションのデータ復旧のハンドラーは、開いているドキュメントと自動保存を監視しています。 フレームワークは、アプリケーションが予期せず終了した後に再起動すると、自動保存されたファイルを復元するのにデータ回復のハンドラーを使用します。 詳細については、次を参照してください。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)します。

##  <a name="m_pszappname"></a>  CWinApp::m_pszAppName

アプリケーション名を示します。

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>Remarks

アプリケーション名に渡されたパラメーターから取得できます、 [CWinApp](#cwinapp)コンス トラクター、または、AFX_IDS_APP_TITLE の ID のリソース文字列に指定しない場合。 リソースの アプリケーション名が見つからない場合は、プログラムから取得されます。EXE ファイル名。

グローバル関数によって返される[AfxGetAppName](application-information-and-management.md#afxgetappname)します。 `m_pszAppName` 型のパブリック変数**const char**<strong>\*</strong>します。

> [!NOTE]
> 値を割り当てる場合`m_pszAppName`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**このポインターに ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

##  <a name="m_pszexename"></a>  CWinApp::m_pszExeName

拡張子のないアプリケーションの実行可能ファイルの名前が含まれています。

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>Remarks

異なり[m_pszAppName](#m_pszappname)、この名前は空白を含めることはできません。 `m_pszExeName` 型のパブリック変数**const char**<strong>\*</strong>します。

> [!NOTE]
> 値を割り当てる場合`m_pszExeName`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**このポインターに ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

##  <a name="m_pszhelpfilepath"></a>  CWinApp::m_pszHelpFilePath

アプリケーションのヘルプ ファイルへのパスが含まれています。

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>Remarks

既定では、フレームワークを初期化します`m_pszHelpFilePath`を使用してアプリケーションの名前に"。HLP"を追加します。 ヘルプ ファイルの名前を変更するには、次のように設定します。`m_pszHelpFilePath`目的のヘルプ ファイルの完全な名前を含む文字列を指すようにします。 これを行う便利な場所がアプリケーションの[InitInstance](#initinstance)関数。 `m_pszHelpFilePath` 型のパブリック変数**const char**<strong>\*</strong>します。

> [!NOTE]
> 値を割り当てる場合`m_pszHelpFilePath`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**このポインターに ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

##  <a name="m_pszprofilename"></a>  CWinApp::m_pszProfileName

アプリケーションの名前を表します。INI ファイルです。

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>Remarks

`m_pszProfileName` 型のパブリック変数**const char**<strong>\*</strong>します。

> [!NOTE]
> 値を割り当てる場合`m_pszProfileName`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**このポインターに ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

##  <a name="m_pszregistrykey"></a>  CWinApp::m_pszRegistryKey

レジストリまたは INI ファイルで、アプリケーション プロファイルの設定の保存場所を決定するために使用します。

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>Remarks

通常、このデータ メンバーは、読み取り専用として扱われます。

- レジストリ キー値が格納されます。 アプリケーション プロファイルの設定の名前は、次のレジストリ キーに追加されます。HKEY_CURRENT_USER/ソフトウェア/LocalAppWizard で生成されるとします。

値を割り当てる場合`m_pszRegistryKey`ヒープに動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**無料**このポインターに ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例:

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

##  <a name="m_pszappid"></a>  CWinApp::m_pszAppID

アプリケーション ユーザー モデル id。

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>Remarks

##  <a name="oncontexthelp"></a>  CWinApp::OnContextHelp

アプリケーション内で shift キーを押しながら F1 ヘルプを処理します。

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Remarks

追加する必要があります、`ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )`ステートメントを`CWinApp`メッセージ マップのクラスし、追加アクセラレータ テーブル エントリを通常は shift キーを押しながら f1 キー、このメンバー関数を有効にすることもできます。

`OnContextHelp` ヘルプ モードにアプリケーションを配置します。 矢印と疑問符 (?) と、ユーザーがカーソルの変更は、マウス ポインターを移動し、 ダイアログ ボックス、ウィンドウ、メニューのまたはコマンド ボタンを選択するマウスの左ボタンを押します。 このメンバー関数は、カーソルの下にあるオブジェクトのヘルプ コンテキストを取得し、そのヘルプ コンテキストを持つ Windows 関数 WinHelp を呼び出します。

##  <a name="onddecommand"></a>  CWinApp::OnDDECommand

メイン フレーム ウィンドウは、DDE を受け取ると、フレームワークによって呼び出されますメッセージを実行します。

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>パラメーター

*lpszCommand*<br/>
アプリケーションによって受信 DDE コマンド文字列を指します。

### <a name="return-value"></a>戻り値

コマンドが処理された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

かどうかのコマンドは要求ドキュメントを開くためであり、そうである場合は、指定したドキュメントを開く既定の実装を確認します。 Windows ファイル マネージャーは、ユーザーがデータ ファイルをダブルクリックすると、通常、DDE コマンド文字列がこのようなを送信します。 オーバーライド他 DDE を処理するには、この関数は、印刷するコマンドなどのコマンドを実行します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

##  <a name="onfilenew"></a>  CWinApp::OnFileNew

ID_FILE_NEW コマンドを実装します。

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>Remarks

追加する必要があります、`ON_COMMAND( ID_FILE_NEW, OnFileNew )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 有効な場合、この関数は、ファイルの新しいコマンドの実行を処理します。

参照してください[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)については既定の動作と、このメンバー関数をオーバーライドする方法について説明します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileopen"></a>  CWinApp::OnFileOpen

ID_FILE_OPEN コマンドを実装します。

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>Remarks

追加する必要があります、`ON_COMMAND( ID_FILE_OPEN, OnFileOpen )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 有効な場合、この関数は、ファイルを開くコマンドの実行を処理します。

既定の動作と、このメンバー関数をオーバーライドする方法のガイダンスについては、次を参照してください。[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onfileprintsetup"></a>  CWinApp::OnFilePrintSetup

ID_FILE_PRINT_SETUP コマンドを実装します。

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>Remarks

追加する必要があります、`ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 有効な場合、この関数は、ファイルの印刷コマンドの実行を処理します。

既定の動作と、このメンバー関数をオーバーライドする方法のガイダンスについては、次を参照してください。[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

##  <a name="onhelp"></a>  :Onhelp

アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>Remarks

通常は、F1 キーのアクセラレータ キー エントリも追加されます。 F1 キーを有効にするは、要件ではありません、規則のみです。

追加する必要があります、`ON_COMMAND( ID_HELP, OnHelp )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 有効な場合は、ユーザーが F1 キーを押したときに、フレームワークによって呼び出されます。

このメッセージ ハンドラー関数の既定の実装は、現在のウィンドウ、ダイアログ ボックスで、またはメニュー項目に対応する、winhelp をヘルプ コンテキストを決定します。実行可能ファイルです。 現在使用可能なコンテキストがない場合、関数は、既定のコンテキストを使用します。

ウィンドウ、ダイアログ ボックス、メニュー項目、または現在フォーカスのあるツール バー ボタン以外に、ヘルプ コンテキストを設定するには、このメンバー関数をオーバーライドします。 呼び出す`WinHelp`目的のヘルプ コンテキスト id。

##  <a name="onhelpfinder"></a>  CWinApp::OnHelpFinder

ID_HELP_FINDER と ID_DEFAULT_HELP コマンドを処理します。

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>Remarks

追加する必要があります、`ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 フレームワークが、アプリケーションのユーザー呼び出しを検索するコマンドを選択したときに、このメッセージ ハンドラー関数を呼び出しますが有効な場合`WinHelp`標準**メニュー**トピック。

##  <a name="onhelpindex"></a>  CWinApp::OnHelpIndex

ID_HELP_INDEX コマンドを処理し、既定のヘルプ トピックを提供します。

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>Remarks

追加する必要があります、`ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 アプリケーションのユーザーが呼び出すヘルプ コマンドを選択すると、フレームワークがこのメッセージ ハンドラー関数を呼び出す有効な場合、`WinHelp`標準**メニュー**トピック。

##  <a name="onhelpusing"></a>  CWinApp::OnHelpUsing

ID_HELP_USING コマンドを処理します。

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>Remarks

追加する必要があります、`ON_COMMAND( ID_HELP_USING, OnHelpUsing )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 フレームワークが、アプリケーションのユーザーが呼び出すヘルプを使用してコマンドを選択すると、このメッセージ ハンドラー関数を呼び出し、`WinHelp`標準アプリケーション**有効**トピック。

##  <a name="onidle"></a>  CWinApp::OnIdle

アイドル状態時の処理を実行するには、このメンバー関数をオーバーライドします。

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>パラメーター

*lCount*<br/>
カウンターは毎回増加`OnIdle`アプリケーションのメッセージ キューが空のときに呼び出されます。 この数は、新しいメッセージが処理されるたびに 0 にリセットされます。 使用することができます、 *lCount*相対アプリケーション メッセージを処理することがなくがアイドル時間の長さを決定するパラメーター。

### <a name="return-value"></a>戻り値

0 以外の場合よりアイドル処理時間を受信するにはアイドル時間が必要な場合は 0 を返します。

### <a name="remarks"></a>Remarks

`OnIdle` アプリケーションのメッセージ キューが空の場合、既定のメッセージ ループで呼びます。 オーバーライドを使用して、独自の背景のアイドル処理を呼び出します。

`OnIdle` アイドル状態の処理時間が必要ないことを示すために 0 を返す必要があります。 *LCount*パラメーターはたびに増分`OnIdle`メッセージ キューが空で、新しいメッセージが処理されるたびに 0 にリセットするときに呼び出されます。 この数に基づく、別のアイドル処理ルーチンを呼び出すことができます。

アイドル ループ処理を以下に示します。

1. Microsoft Foundation Class ライブラリでのメッセージ ループがメッセージ キューを確認します、保留中のメッセージいいえ判明した場合は、呼び出す`OnIdle`アプリケーション オブジェクトおよび装置 0 として、 *lCount*引数。

2. `OnIdle` いくつかの処理を実行し、取得を行うことを示すゼロ以外の値をもう一度呼び出す必要がさらに処理します。

3. メッセージ ループでは、メッセージ キューをもう一度確認します。 保留中のメッセージがない場合は、呼び出す`OnIdle`もう一度、インクリメント、 *lCount*引数。

4. 最終的には、`OnIdle`アイドル状態のすべてのタスクの処理が終了し、0 を返します。 これにより、呼び出しを停止するメッセージ ループ`OnIdle`メッセージ キューから次のメッセージを受信するまでこの時点でアイドル状態にサイクルが再開引数を 0 に設定します。

時に、時間のかかるタスクを実行しない`OnIdle`アプリケーションまで、ユーザー入力を処理できないため、`OnIdle`を返します。

> [!NOTE]
> 既定の実装`OnIdle`更新コマンドのメニュー項目やツールバーのボタンなどのユーザー インターフェイス オブジェクトと内部データ構造体のクリーンアップを実行します。 そのため、オーバーライドする場合は`OnIdle`、呼び出す必要があります`CWinApp::OnIdle`で、`lCount`オーバーライドされたバージョン。 まずアイドル処理のすべての基本クラスを呼び出す (つまり、基本クラスまで`OnIdle`0 を返します)。 基本クラスの処理が完了する前に、作業を実行する必要がある場合、適切なを選択する基本クラスの実装を確認してください。 *lCount*する作業を行います。

たくない場合`OnIdle`にするには、メッセージがメッセージ キューから取得されるたびに呼び出されると、オーバーライド、 [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage)します。 アプリケーションが、非常に短い時間のタイマーを設定した場合、またはシステムときのメッセージの送信は`OnIdle`、繰り返し呼び出され、パフォーマンスが低下します。

### <a name="example"></a>例

次の 2 つの例を使用する方法を表示する`OnIdle`します。 最初の例を使用して 2 つのアイドル状態のタスクの処理、 *lCount*タスクの優先順位を設定する引数。 最初のタスクは、優先度の高いと、可能であればこれを行う必要があります。 2 番目のタスクは、重要度の低いユーザー入力を一時停止時間がある場合にのみ行う必要があります。 基本クラスのバージョンへの呼び出しに注意してください`OnIdle`します。 2 番目の例では、さまざまな優先順位がアイドル状態のタスクのグループを管理します。

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

##  <a name="opendocumentfile"></a>  :Opendocumentfile

フレームワークは、このメソッドを名前付き[CDocument](../../mfc/reference/cdocument-class.md)アプリケーション用のファイル。

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>パラメーター

*場合*<br/>
[in]開かれるファイルの名前。

*baddtomru です。*<br/>
[in]TRUE は、ドキュメントが最新のファイルのいずれかを示しますFALSE は、ドキュメントがない最新のファイルのいずれかを示します。

### <a name="return-value"></a>戻り値

ポインター、`CDocument`成功。 それ以外の場合に NULL の場合。

### <a name="remarks"></a>Remarks

その名前を持つドキュメントが既に開いている場合、そのドキュメントを含む最初のフレーム ウィンドウはフォーカスを取得します。 アプリケーションでは、複数のドキュメント テンプレートをサポートする場合、フレームワークは、ドキュメントの読み込みしようとする適切なドキュメント テンプレートを検索するファイル名拡張子を使用します。 成功した場合、ドキュメント テンプレートは、フレーム ウィンドウとドキュメントの表示にし、作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

##  <a name="parsecommandline"></a>  CWinApp::ParseCommandLine

コマンドラインを解析し、このパラメーターは、一度に 1 つずつに送信するには、このメンバー関数を呼び出して[後](../../mfc/reference/ccommandlineinfo-class.md#parseparam)します。

```
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>パラメーター

*rCmdInfo*<br/>
参照を[CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

アプリケーション ウィザードがのローカル インスタンスを作成するアプリケーション ウィザードを使用して新しい MFC プロジェクトを開始するときに`CCommandLineInfo`を呼び出して`ProcessShellCommand`と`ParseCommandLine`で、 [InitInstance](#initinstance)メンバー関数。 コマンド ラインは、以下に説明を次に示します。

1. 後で作成されている`InitInstance`、`CCommandLineInfo`にオブジェクトが渡される`ParseCommandLine`します。

2. `ParseCommandLine` 呼び出して`CCommandLineInfo::ParseParam`繰り返し、各パラメーターに対して 1 回です。

3. `ParseParam` 入力、`CCommandLineInfo`に渡されますが、オブジェクト[ProcessShellCommand](#processshellcommand)します。

4. `ProcessShellCommand` コマンドライン引数とフラグを処理します。

呼び出すことのできる注`ParseCommandLine`必要に応じて、直接します。

コマンド ライン フラグの説明は、次を参照してください。 [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)します。

##  <a name="pretranslatemessage"></a>  Cwinapp::pretranslatemessage

Windows 関数にディスパッチされる前に、ウィンドウ メッセージをフィルター処理するには、この関数をオーバーライド[TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage)と[DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage)既定の実装は、アクセラレータ キーを実行します。変換では、呼び出す必要があるため、`CWinApp::PreTranslateMessage`オーバーライドされたバージョンのメンバー関数。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*pMsg*<br/>
ポインターを[MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg)処理するメッセージを含む構造体。

### <a name="return-value"></a>戻り値

メッセージで完全に処理された場合は 0 以外`PreTranslateMessage`さらに処理する必要があります。 通常の方法で、メッセージを処理する必要がありますがある場合は 0 します。

##  <a name="processmessagefilter"></a>  CWinApp::ProcessMessageFilter

フレームワークのフック関数は、特定の Windows メッセージに応答をフィルター処理には、このメンバー関数を呼び出します。

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*code*<br/>
フック コードを指定します。 このメンバー関数では、コードを使用して、処理する方法を決定*lpMsg します。*

*lpMsg*<br/>
Windows へのポインター [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg)構造体。

### <a name="return-value"></a>戻り値

メッセージが処理された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションの通常のメッセージを送信する前に、イベントを処理するフック関数を処理します。

この高度な機能をオーバーライドする場合は、フレームワークを維持するために基本クラスのバージョンを呼び出すことを確認する処理をフックします。

##  <a name="processshellcommand"></a>  CWinApp::ProcessShellCommand

によって呼び出されます[InitInstance](#initinstance)から渡されたパラメーターを受け入れるように、`CCommandLineInfo`で識別されるオブジェクト*rCmdInfo*、し、指定されたアクションを実行します。

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>パラメーター

*rCmdInfo*<br/>
参照を[CCommandLineInfo](../../mfc/reference/ccommandlineinfo-class.md)オブジェクト。

### <a name="return-value"></a>戻り値

以外の場合は、シェル コマンドが正常に処理されます。 0 の場合にから FALSE が返されます場合[InitInstance](#initinstance)します。

### <a name="remarks"></a>Remarks

アプリケーション ウィザードがのローカル インスタンスを作成するアプリケーション ウィザードを使用して新しい MFC プロジェクトを開始するときに`CCommandLineInfo`を呼び出して`ProcessShellCommand`と[ParseCommandLine](#parsecommandline)で、`InitInstance`メンバー関数。 コマンド ラインは、以下に説明を次に示します。

1. 後で作成されている`InitInstance`、`CCommandLineInfo`にオブジェクトが渡される`ParseCommandLine`します。

2. `ParseCommandLine` 呼び出して[後](../../mfc/reference/ccommandlineinfo-class.md#parseparam)繰り返し、各パラメーターに対して 1 回です。

3. `ParseParam` 入力、`CCommandLineInfo`に渡されますが、オブジェクト`ProcessShellCommand`します。

4. `ProcessShellCommand` コマンドライン引数とフラグを処理します。

データ メンバー、`CCommandLineInfo`で識別されるオブジェクト[CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)、次の列挙型内で定義されているは、`CCommandLineInfo`クラス。

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

これらの各値の簡単な説明を参照してください。`CCommandLineInfo::m_nShellCommand`します。

##  <a name="processwndprocexception"></a>  CWinApp::ProcessWndProcException

フレームワークは、ハンドラーは、アプリケーションのメッセージまたはコマンド ハンドラーのいずれかでスローされる例外をキャッチしませんたびに、このメンバー関数を呼び出します。

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*e*<br/>
キャッチされない例外へのポインター。

*pMsg*<br/>
A [MSG](/windows/desktop/api/winuser/ns-winuser-tagmsg)フレームワークが例外をスローする原因となった windows メッセージに関する情報を含む構造体。

### <a name="return-value"></a>戻り値

この値は、Windows に返される必要があります。 通常これは 0l に windows メッセージを 1 L (TRUE) コマンド メッセージのです。

### <a name="remarks"></a>Remarks

このメンバー関数を直接呼び出さないでください。

このメンバー関数の既定の実装は、メッセージ ボックスを作成します。 メッセージ ボックス、メニューのツールバー、またはアクセラレータ コマンド エラーのキャッチされない例外の作成元;「コマンドが失敗しました」メッセージが表示されます。それ以外の場合、「アプリケーションの内部エラー」メッセージが表示されます。

グローバルに、例外の処理を提供するには、このメンバー関数をオーバーライドします。 メッセージ ボックスを表示する場合は、基本機能を呼び出すのみです。

##  <a name="register"></a>  CWinApp::Register

処理されない登録タスクが実行`RegisterShellFileTypes`します。

```
virtual BOOL Register();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>Remarks

既定の実装は、単に TRUE を返します。 カスタマイズした登録手順を提供するには、この関数をオーバーライドします。

##  <a name="registershellfiletypes"></a>  登録

アプリケーションのドキュメントの種類のすべての Windows ファイル マネージャーを登録するには、このメンバー関数を呼び出します。

```
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>パラメーター

*bCompat*<br/>
[in]TRUE は、シェル コマンドの印刷と印刷する、またはプリンター オブジェクトにファイルをドラッグして、シェルから直接ファイルを印刷するユーザーの登録エントリを追加します。 DefaultIcon キーも追加します。 このパラメーターは FALSE を既定では、旧バージョンとの互換性のためです。

### <a name="remarks"></a>Remarks

これにより、ユーザー ファイル マネージャー内をダブルクリックしてから、アプリケーションによって作成されたデータ ファイルを開くことができます。 呼び出す`RegisterShellFileTypes`を呼び出した後[AddDocTemplate](#adddoctemplate)のそれぞれのアプリケーションでドキュメント テンプレート。 呼び出すことも、 [EnableShellOpen](#enableshellopen)メンバー関数を呼び出すと`RegisterShellFileTypes`します。

`RegisterShellFileTypes` リストを反復処理[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)アプリケーションの管理し、ドキュメント テンプレートごとに、ファイルの関連付けに対して Windows が保持している登録情報データベースにエントリを追加します。 あるオブジェクト。 ファイル マネージャーでは、これらのエントリを使用して、ユーザーをダブルクリックすると、そのデータ ファイルを開きます。 これを出荷する必要があるをします。REG ファイルとアプリケーション。

> [!NOTE]
> `RegisterShellFileTypes` ユーザーが管理者権限を持つ、プログラムを実行している場合にのみ機能します。 プログラムが管理者権限を持たない場合レジストリ キーを変更することはできません。

登録情報データベースは、既に別のファイルの種類に指定されたファイル名拡張子を関連付けます、新しい関連付けは作成されません。 参照してください、`CDocTemplate`この情報を登録するために必要な文字列の形式のクラス。

##  <a name="registerwithrestartmanager"></a>  CWinApp::RegisterWithRestartManager

再起動マネージャーとアプリケーションを登録します。

```
virtual HRESULT RegisterWithRestartManager(
    BOOL bRegisterRecoveryCallback,
    const CString& strRestartIdentifier);

virtual HRESULT RegisterWithRestartManager(
    LPCWSTR pwzCommandLineArgs,
    DWORD dwRestartFlags,
    APPLICATION_RECOVERY_CALLBACK pRecoveryCallback,
    LPVOID lpvParam,
    DWORD dwPingInterval,
    DWORD dwCallbackFlags);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*bRegisterRecoveryCallback*|[in]TRUE は、アプリケーションのこのインスタンスが回復のコールバック関数では; を使用することを示しますFALSE は、しないことを示します。 フレームワークは、アプリケーションが予期せず終了したときに、回復のコールバック関数を呼び出します。 詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。|
|*strRestartIdentifier*|[in]再起動マネージャーのインスタンスを識別する一意の文字列。 再起動マネージャー識別子は、アプリケーションの各インスタンスに対して一意です。|
|*pwzCommandLineArgs*|[in]コマンドラインから余分な引数を含む文字列。|
|*dwRestartFlags*|[in]再起動マネージャーのオプションのフラグ。 詳細については、「解説」を参照してください。|
|*pRecoveryCallback*|[in]回復のコールバック関数。 この関数は、入力として LPVOID パラメーターを受け取るし、DWORD を返す必要があります。 既定の復旧のコールバック関数は、`CWinApp::ApplicationRecoveryCallback`します。|
|*lpvParam*|[in]回復のコールバック関数の入力パラメーター。 詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)します。|
|*dwPingInterval*|[in]再起動マネージャーが回復のコールバック関数が返すを待機する時間の長さ。 このパラメーターは、ミリ秒単位です。|
|*dwCallbackFlags*|[in]フラグは、回復のコールバック関数に渡されます。 将来使用するために予約されています。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合は s_ok を返します。それ以外の場合、エラー コード。

### <a name="remarks"></a>Remarks

簡易バージョンを使用する場合は、アプリケーションでは、既定の MFC 実装を使用してファイルを自動保存、する必要があります`RegisterWithRestartManager`します。 複雑なバージョンの使用`RegisterWithRestartManager`アプリケーションの自動保存の動作をカスタマイズする場合。

空の文字列では、このメソッドを呼び出すかどうか*strRestartIdentifier*、`RegisterWithRestartManager`マネージャー、再起動のこのインスタンスの一意の識別子の文字列を作成します。

アプリケーションが予期せず終了したときに、再起動マネージャーは、コマンドラインからアプリケーションを再起動し、一意の再起動オプションの引数としての識別子を提供します。 このシナリオで、フレームワーク`RegisterWithRestartManager`2 回です。 最初の呼び出し元が[:initinstance](#initinstance)文字列識別子の空の文字列に置き換えます。 メソッドでは、 [CWinApp::ProcessShellCommand](#processshellcommand)呼び出し`RegisterWithRestartManager`再起動の一意の識別子を使用します。

再起動マネージャーとアプリケーションを登録した後、再起動マネージャーは、アプリケーションを監視します。 アプリケーションが予期せず終了した場合、再起動マネージャーは、シャット ダウン処理中に回復コールバック関数を呼び出します。 再起動マネージャーの待機、 *dwPingInterval*回復コールバック関数からの応答。 回復のコールバック関数がこの時間内に応答しない場合は、回復のコールバック関数を実行することがなくアプリケーションが終了します。

既定では、dwRestartFlags はサポートされていませんが、将来使用するために提供されます。 使用可能な値を*dwRestartFlags*次に示します。

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

##  <a name="reopenpreviousfilesatrestart"></a>  CWinApp::ReopenPreviousFilesAtRestart

再起動マネージャーが、アプリケーションが予期せず終了したときに開いていたファイルを開くかどうかを判断します。

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>戻り値

True の場合、再起動マネージャーには、開いていたファイルが再度開かれますFALSE は、再起動マネージャーがいないことを示します。

##  <a name="restartinstance"></a>  CWinApp::RestartInstance

再起動マネージャーによって開始されたアプリケーションの再起動を処理します。

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>戻り値

データ回復のハンドラーが既に開いているドキュメントを開いた場合は TRUE。データ回復のハンドラーでエラーがある場合、または以前に開かれているドキュメントがない場合は FALSE です。

### <a name="remarks"></a>Remarks

再起動マネージャーは、アプリケーションが再起動したら、フレームワークは、このメソッドを呼び出します。 このメソッドは、データ回復のハンドラーを取得し、自動保存されたファイルを復元します。 このメソッドを呼び出す[CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments)をユーザーが自動保存されたファイルを復元するかどうかを判断します。

場合、このメソッドは FALSE を返します、 [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md)開いているドキュメントがないことを決定します。 開いているドキュメントがない場合、通常、アプリケーションを開始します。

##  <a name="restoreautosavedfilesatrestart"></a>  CWinApp::RestoreAutosavedFilesAtRestart

アプリケーションが再起動すると再起動マネージャーが自動保存されたファイルを復元するかどうかを判断します。

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>戻り値

True の場合、再起動マネージャーは、自動保存されたファイルを復元FALSE は、再起動マネージャーがいないことを示します。

##  <a name="run"></a>  使わ

既定のメッセージ ループを提供します。

```
virtual int Run();
```

### <a name="return-value"></a>戻り値

**Int**によって返される値`WinMain`します。

### <a name="remarks"></a>Remarks

`Run` 取得し、アプリケーションが WM_QUIT メッセージを受信するまで、Windows メッセージをディスパッチします。 アプリケーションのメッセージ キューにメッセージがない場合`Run`呼び出し[OnIdle](#onidle)アイドル処理を実行します。 受信メッセージに移動、 [PreTranslateMessage](#pretranslatemessage)メンバー関数の特別な処理と、Windows 関数に`TranslateMessage`標準キーボードの翻訳の最後に、 `DispatchMessage` Windows 関数が呼び出されます。

`Run` オーバーライドされることはほとんどありませんが、特別な動作を提供するオーバーライドできます。

##  <a name="runautomated"></a>  CWinApp::RunAutomated

確認するには、この関数を呼び出すかどうか、" **/Automation**「または」 **-Automation**"オプションが存在するサーバー アプリケーションがクライアント アプリケーションによって起動されたかどうかを示します。

```
BOOL RunAutomated();
```

### <a name="return-value"></a>戻り値

オプションが見つかった場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

存在する場合、オプションは、コマンドラインから削除されます。 OLE オートメーションの詳細については、記事を参照してください。[オートメーション サーバー](../../mfc/automation-servers.md)します。

##  <a name="runembedded"></a>  CWinApp::RunEmbedded

確認するには、この関数を呼び出すかどうか、" **/automation**「または」 **-埋め込み**"オプションが存在するサーバー アプリケーションがクライアント アプリケーションによって起動されたかどうかを示します。

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>戻り値

オプションが見つかった場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

存在する場合、オプションは、コマンドラインから削除されます。 埋め込みの詳細については、記事を参照してください。[サーバー。サーバーを実装する](../../mfc/servers-implementing-a-server.md)します。

##  <a name="saveallmodified"></a>  CWinApp::SaveAllModified

WM_QUERYENDSESSION メッセージや、アプリケーションのメイン フレーム ウィンドウが閉じられるときに、すべてのドキュメントを保存するためにフレームワークによって呼び出されます。

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>戻り値

0 以外の場合は、アプリケーションを終了してもよい場合アプリケーションを終了する安全でない場合は 0。

### <a name="remarks"></a>Remarks

このメンバー関数の既定の実装、[に対して、順番](../../mfc/reference/cdocument-class.md#savemodified)さらに、アプリケーション内で変更したドキュメントのすべてのメンバー関数。

##  <a name="selectprinter"></a>  通知

特定のプリンターを選択するには、このメンバー関数を呼び出すし、[印刷] ダイアログ ボックスで選択されていたプリンターをリリースします。

```
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>パラメーター

*場合*<br/>
識別するハンドルを[DEVNAMES](/windows/desktop/api/commdlg/ns-commdlg-tagdevnames)ドライバー、デバイス、および特定のプリンターの出力ポート名を識別する構造体。

*hDevMode*<br/>
識別するハンドルを[DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)デバイスの初期化とプリンターの環境に関する情報を指定する構造体。

*bFreeOld*<br/>
選択したプリンターを解放します。

### <a name="remarks"></a>Remarks

両方*hDevMode*と*と*が null の場合、`SelectPrinter`現在の既定のプリンターを使用します。

##  <a name="sethelpmode"></a>  CWinApp::SetHelpMode

アプリケーションのヘルプの種類を設定します。

```
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>パラメーター

*eHelpType*<br/>
使用するヘルプの種類を指定します。 参照してください[CWinApp::m_eHelpType](#m_ehelptype)詳細についてはします。

### <a name="remarks"></a>Remarks

アプリケーションのヘルプの種類を設定します。

Html ヘルプには、アプリケーションのヘルプの種類を設定を呼び出すことができます[EnableHTMLHelp](#enablehtmlhelp)します。 呼び出す`EnableHTMLHelp`アプリケーションは、そのヘルプ アプリケーションとして html ヘルプを使用する必要があります。 WinHelp の使用に変更する場合は、呼び出すことが`SetHelpMode`設定と*eHelpType*に`afxWinHelp`します。

##  <a name="setregistrykey"></a>  書き込むに

INI ファイルではなくレジストリに格納されるアプリケーションの設定をによりします。

```
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>パラメーター

*lpszRegistryKey*<br/>
キーの名前を含む文字列へのポインター。

*nIDRegistryKey*<br/>
レジストリ キーの名前を含む文字列リソースの ID。

### <a name="remarks"></a>Remarks

この関数は、設定*m_pszRegistryKey*で使用される、 `GetProfileInt`、 `GetProfileString`、 `WriteProfileInt`、および`WriteProfileString`のメンバー関数`CWinApp`します。 この関数が呼び出された場合、最近使用 (した MRU) ファイルの一覧は、レジストリにも格納されます。 レジストリ キーは、会社の名前です。 次の形式のキーに格納されます。\Software\\< 会社名\>\\< アプリケーション名\>\\< セクション名\>\\< 値の名前\>します。

##  <a name="supportsapplicationrecovery"></a>  CWinApp::SupportsApplicationRecovery

再起動マネージャーが予期せず終了したアプリケーションを回復するかどうかを判断します。

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>戻り値

TRUE は、再起動マネージャーは、アプリケーションを回復することを示しますFALSE は、再起動マネージャーがいないことを示します。

##  <a name="supportsautosaveatinterval"></a>  CWinApp::SupportsAutosaveAtInterval

再起動マネージャーによって自動保存が一定の間隔でドキュメントを開くかどうかを判断します。

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>戻り値

TRUE は、再起動マネージャーによって自動保存がドキュメントを開くことを示しますFALSE は、再起動マネージャーがいないことを示します。

##  <a name="supportsautosaveatrestart"></a>  CWinApp::SupportsAutosaveAtRestart

決定かどうか再起動マネージャーによって自動保存、アプリケーションを再起動すると、開いているドキュメント。

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>戻り値

TRUE は、アプリケーションが再起動と再起動マネージャーによって自動保存がドキュメントを開くことを示しますFALSE は、再起動マネージャーがいないことを示します。

##  <a name="supportsrestartmanager"></a>  CWinApp::SupportsRestartManager

アプリケーションが再起動マネージャーをサポートしているかどうかを判断します。

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>戻り値

TRUE は、アプリケーションは、再起動マネージャーをサポートしていることを示しますFALSE では、アプリケーションがないことを示します。

##  <a name="unregister"></a>  CWinApp::Unregister

アプリケーション オブジェクトによって登録されたすべてのファイルを登録解除します。

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>Remarks

`Unregister`関数は、アプリケーション オブジェクトが実行する登録を元に戻します、[登録](#register)関数。 通常、両方の関数は、MFC によって暗黙的に呼び出され、そのため、コードでは表示されません。

カスタム登録解除の手順を実行するには、この関数をオーバーライドします。

##  <a name="unregistershellfiletypes"></a>  CWinApp::UnregisterShellFileTypes

すべてのアプリケーションのドキュメントの種類の Windows ファイル マネージャーの登録を解除するには、このメンバー関数を呼び出します。

```
void UnregisterShellFileTypes();
```

##  <a name="winhelp"></a>  Cwinapp::winhelp

WinHelp アプリケーションを起動するには、このメンバー関数を呼び出します。

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>パラメーター

*指定*<br/>
追加のデータを指定します。 使用される値の値によって異なります、 *nCmd*パラメーター。

*nCmd*<br/>
要求されるヘルプの種類を指定します。 使用可能な値、および影響についての一覧については、*指定*パラメーターを参照してください、 [WinHelp](/windows/desktop/api/winuser/nf-winuser-winhelpa) Windows 関数。

### <a name="remarks"></a>Remarks

フレームワークでは、WinHelp アプリケーションを起動するには、この関数も呼び出します。

フレームワークでは、アプリケーションの終了時に、WinHelp アプリケーションは自動的に閉じます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

##  <a name="writeprofilebinary"></a>  CWinApp::WriteProfileBinary

バイナリ データを指定されたセクションのアプリケーションのレジストリに書き込むには、このメンバー関数を呼び出すか。INI ファイルです。

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>パラメーター

*大文字、小文字*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。任意の大文字と小文字の文字列があります。

*lpszEntry*<br/>
値が書き込まれるエントリを含む null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。

*pData*<br/>
書き込むデータへのポインター。

*nBytes*<br/>
書き込むバイト数が含まれています。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

この例では`CWinApp* pApp = AfxGetApp();`方法を示す CWinApp クラスを取得するを`WriteProfileBinary`と`GetProfileBinary`MFC アプリケーションで任意の関数から使用できます。

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

別の例の例を参照してください。[は](#getprofilebinary)します。

##  <a name="writeprofileint"></a>  Cwinapp::writeprofileint

アプリケーションのレジストリの指定したセクションに指定した値を書き込むには、このメンバー関数を呼び出すか。INI ファイルです。

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>パラメーター

*大文字、小文字*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。任意の大文字と小文字の文字列があります。

*lpszEntry*<br/>
値が書き込まれるエントリを含む null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。

*値*<br/>
書き込む値が含まれています。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

この例では`CWinApp* pApp = AfxGetApp();`方法を示す CWinApp クラスを取得するを`WriteProfileString`、 `WriteProfileInt`、 `GetProfileString`、および`GetProfileInt`MFC アプリケーションで任意の関数から使用できます。

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

別の例の例を参照してください。[は](#getprofileint)します。

##  <a name="writeprofilestring"></a>  CWinApp::WriteProfileString

アプリケーションのレジストリの指定したセクションに指定した文字列を書き込むには、このメンバー関数を呼び出すか。INI ファイルです。

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>パラメーター

*大文字、小文字*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。任意の大文字と小文字の文字列があります。

*lpszEntry*<br/>
値が書き込まれるエントリを含む null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。 このパラメーターが NULL の場合、セクションが指定された*大文字、小文字*は削除されます。

*lpszValue*<br/>
書き込まれる文字列を指します。 このパラメーターが NULL の場合、エントリが指定された、 *lpszEntry*パラメーターを削除します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

別の例の例を参照してください。[は](#getprofileint)します。

##  <a name="setappid"></a>  CWinApp::SetAppID

アプリケーションのアプリケーション ユーザー モデル ID を明示的に設定します。 すべてのユーザー インターフェイスは (最適な場所では、アプリケーションのコンス トラクター) のユーザーに表示される前に、このメソッドを呼び出す必要があります。

```
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>パラメーター

*lpcszAppID*<br/>
アプリケーションのユーザー モデル ID を指定します

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>関連項目

[CWinThread クラス](../../mfc/reference/cwinthread-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[操作方法：再起動マネージャーのサポートを追加します。](../../mfc/how-to-add-restart-manager-support.md)
