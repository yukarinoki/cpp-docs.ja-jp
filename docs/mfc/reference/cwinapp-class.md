---
title: CWinApp クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aab01b0f55d19ef3c9d39fed38b42471f559ba8d
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123202"
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
|[CWinApp::AddToRecentFileList](#addtorecentfilelist)|最近使用した (MRU) ファイルの一覧にファイル名を追加します。|  
|[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)|アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。|  
|[CWinApp::CloseAllDocuments](#closealldocuments)|すべての開いているドキュメントを閉じます。|  
|[CWinApp::CreatePrinterDC](#createprinterdc)|プリンター デバイス コンテキストを作成します。|  
|[CWinApp::DelRegTree](#delregtree)|指定したキーとそのすべてのサブキーを削除します。|  
|[CWinApp::DoMessageBox](#domessagebox)|実装して[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)アプリケーションです。|  
|[CWinApp::DoWaitCursor](#dowaitcursor)|待機カーソルをオンおよびオフにします。|  
|[CWinApp::EnableD2DSupport](#enabled2dsupport)|アプリケーションの D2D のサポートを有効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|  
|[CWinApp::EnableHtmlHelp](#enablehtmlhelp)|WinHelp ではなく、アプリケーションの html ヘルプを実装します。|  
|[CWinApp::EnableTaskbarInteraction](#enabletaskbarinteraction)|タスク バーの相互作用を有効にします。|  
|[し](#exitinstance)|アプリケーションが終了するときにクリーンアップをオーバーライドします。|  
|[CWinApp::GetApplicationRecoveryParameter](#getapplicationrecoveryparameter)|アプリケーションの回復メソッドの入力パラメーターを取得します。|  
|[CWinApp::GetApplicationRecoveryPingInterval](#getapplicationrecoverypinginterval)|再起動マネージャーが、回復コールバック関数を返すまで待機する時間の長さを返します。|  
|[CWinApp::GetApplicationRestartFlags](#getapplicationrestartflags)|再起動マネージャーのフラグを返します。|  
|[CWinApp::GetAppRegistryKey](#getappregistrykey)|HKEY_CURRENT_USER のキーを返す\\「ソフトウェア」\RegistryKey\ProfileName です。|  
|[CWinApp::GetDataRecoveryHandler](#getdatarecoveryhandler)|アプリケーションのこのインスタンスのデータ回復のハンドラーを取得します。|  
|[CWinApp::GetFirstDocTemplatePosition](#getfirstdoctemplateposition)|最初のドキュメント テンプレートの位置を取得します。|  
|[CWinApp::GetHelpMode](#gethelpmode)|アプリケーションで使用するヘルプの種類を取得します。|  
|[CWinApp::GetNextDocTemplate](#getnextdoctemplate)|ドキュメント テンプレートの位置を取得します。 再帰的に使用できます。|  
|[CWinApp::GetPrinterDeviceDefaults](#getprinterdevicedefaults)|プリンター デバイスの既定値を取得します。|  
|[は](#getprofilebinary)|アプリケーションのエントリからバイナリ データを取得します。INI ファイルです。|  
|[は](#getprofileint)|アプリケーションのエントリから整数値を取得します。INI ファイルです。|  
|[CWinApp::GetProfileString](#getprofilestring)|アプリケーションのエントリから文字列を取得します。INI ファイルです。|  
|[CWinApp::GetSectionKey](#getsectionkey)|HKEY_CURRENT_USER のキーを返す\\「ソフトウェア」\RegistryKey\AppName\lpszSection です。|  
|[CWinApp::HideApplication](#hideapplication)|すべてのドキュメントを閉じる前に、アプリケーションは表示されません。|  
|[CWinApp::HtmlHelp](#htmlhelp)|呼び出し、 `HTMLHelp` Windows の機能です。|  
|[場合は](#initinstance)|ウィンドウ オブジェクトの作成など、Windows のインスタンスを初期化を実行するためにオーバーライドします。|  
|[CWinApp::IsTaskbarInteractionEnabled](#istaskbarinteractionenabled)|Windows 7 のタスク バーの相互作用が有効になっているかどうかを指示します。|  
|[CWinApp::LoadCursor](#loadcursor)|カーソル リソースを読み込みます。|  
|[CWinApp::LoadIcon](#loadicon)|アイコン リソースを読み込みます。|  
|[CWinApp::LoadOEMCursor](#loadoemcursor)|読み込み Windows OEM には、カーソルがあらかじめ定義されている、 **OCR_** WINDOWS で定数を指定します。H.|  
|[CWinApp::LoadOEMIcon](#loadoemicon)|Windows OEM の定義済み アイコンをロードする、 **OIC_** WINDOWS で定数を指定します。H.|  
|[CWinApp::LoadStandardCursor](#loadstandardcursor)|読み込み、Windows にカーソルがあらかじめ定義されている、 **idc _** WINDOWS で定数を指定します。H.|  
|[CWinApp::LoadStandardIcon](#loadstandardicon)|Windows の定義済みアイコンの読み込みを**IDI_** WINDOWS で定数を指定します。H.|  
|[CWinApp::OnDDECommand](#onddecommand)|呼ばれる動的なデータへの応答として、フレームワークによってエクス (チェンジ DDE) はコマンドを実行します。|  
|[CWinApp::OnIdle](#onidle)|アプリケーション固有のアイドル時間の処理を実行するためにオーバーライドします。|  
|[:Opendocumentfile](#opendocumentfile)|ファイルからドキュメントを開くために、フレームワークによって呼び出されます。|  
|[CWinApp::ParseCommandLine](#parsecommandline)|個別のパラメーターおよびコマンドラインにフラグを解析します。|  
|[Cwinapp::pretranslatemessage](#pretranslatemessage)|Windows 関数にディスパッチされる前にメッセージをフィルター [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)です。|  
|[CWinApp::ProcessMessageFilter](#processmessagefilter)|アプリケーションに到達する前に、特定のメッセージを受け取ります。|  
|[CWinApp::ProcessShellCommand](#processshellcommand)|コマンドライン引数とフラグを処理します。|  
|[CWinApp::ProcessWndProcException](#processwndprocexception)|アプリケーションのメッセージとコマンド ハンドラーによってスローされたすべてのハンドルされない例外を受け取ります。|  
|[CWinApp::Register](#register)|カスタマイズした登録を実行します。|  
|[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)|再起動マネージャーとアプリケーションを登録します。|  
|[CWinApp::ReopenPreviousFilesAtRestart](#reopenpreviousfilesatrestart)|再起動マネージャーが、アプリケーションが予期せず終了したときに開いていたファイルを再度開くかどうかを判断します。|  
|[CWinApp::RestartInstance](#restartinstance)|再起動マネージャーによって開始されたアプリケーションの再起動を処理します。|  
|[CWinApp::RestoreAutosavedFilesAtRestart](#restoreautosavedfilesatrestart)|アプリケーションが再起動すると、再起動マネージャーが自動保存されたファイルを復元するかどうかを判断します。|  
|[:Run](#run)|既定のメッセージ ループを実行します。 メッセージ ループをカスタマイズするためにオーバーライドします。|  
|[CWinApp::RunAutomated](#runautomated)|アプリケーションのコマンドラインのテスト、 **/Automation**オプション。 互換性のために残されています。 代わりに、値を使用して[CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated)呼び出した後[ParseCommandLine](#parsecommandline)です。|  
|[CWinApp::RunEmbedded](#runembedded)|アプリケーションのコマンドラインのテスト、 **/embedding か**オプション。 互換性のために残されています。 代わりに、値を使用して[CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded)呼び出した後[ParseCommandLine](#parsecommandline)です。|  
|[CWinApp::SaveAllModified](#saveallmodified)|ユーザーが変更されたすべてのドキュメントを保存するように求められます。|  
|[通知](#selectprinter)|印刷ダイアログ ボックスを使用してユーザーによって示される以前プリンターを選択します。|  
|[CWinApp::SetHelpMode](#sethelpmode)|設定して、アプリケーションで使用するヘルプの種類を初期化します。|  
|[CWinApp::SupportsApplicationRecovery](#supportsapplicationrecovery)|再起動マネージャーが予期せず終了したアプリケーションを回復するかどうかを判断します。|  
|[CWinApp::SupportsAutosaveAtInterval](#supportsautosaveatinterval)|再起動マネージャーによって自動保存が一定の間隔でドキュメントを開くかどうかを判断します。|  
|[CWinApp::SupportsAutosaveAtRestart](#supportsautosaveatrestart)|指定するかどうか再起動マネージャーによって自動保存、アプリケーションを再起動すると、開いているドキュメントです。|  
|[CWinApp::SupportsRestartManager](#supportsrestartmanager)|アプリケーションが再起動マネージャーをサポートしているかどうかを判断します。|  
|[CWinApp::Unregister](#unregister)|によって登録されるまで既知のすべての登録を解除、`CWinApp`オブジェクト。|  
|[Cwinapp::winhelp](#winhelp)|呼び出し、 `WinHelp` Windows の機能です。|  
|[CWinApp::WriteProfileBinary](#writeprofilebinary)|バイナリ データ、アプリケーションのエントリを書き込みます。INI ファイルです。|  
|[Cwinapp::writeprofileint](#writeprofileint)|アプリケーションのエントリに整数を書き込みます。INI ファイルです。|  
|[CWinApp::WriteProfileString](#writeprofilestring)|アプリケーションのエントリに文字列を書き込みます。INI ファイルです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWinApp::EnableShellOpen](#enableshellopen)|データ ファイルから、Windows ファイル マネージャーを開くことができます。|  
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
|[CWinApp::SetAppID](#setappid)|アプリケーションのアプリケーション ユーザー モデル ID が明示的に設定します。 すべてのユーザー インターフェイスがユーザー (アプリケーションのコンス トラクターでは、最適な場所) に表示される前に、このメソッドを呼び出す必要があります。|  
|[書き込むに](#setregistrykey)|代わりに、レジストリに格納されるアプリケーションの設定が発生します。INI ファイル。|  
|[CWinApp::UnregisterShellFileTypes](#unregistershellfiletypes)|アプリケーションのすべてのドキュメントの種類、Windows ファイル マネージャーでの登録を解除します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWinApp::m_bHelpMode](#m_bhelpmode)|かどうか、ユーザーが (通常は shift キーを押しながら f1 キーを指定して呼び出さ) ヘルプ コンテキスト モードを示します。|  
|[CWinApp::m_eHelpType](#m_ehelptype)|アプリケーションで使用するヘルプの種類を指定します。|  
|[CWinApp::m_hInstance](#m_hinstance)|アプリケーションの現在のインスタンスを識別します。|  
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。|  
|[CWinApp::m_nCmdShow](#m_ncmdshow)|ウィンドウの最初に表示する方法を指定します。|  
|[先](#m_pactivewnd)|OLE サーバーが、インプレース アクティブである場合は、コンテナー アプリケーションのメイン ウィンドウへのポインター。|  
|[CWinApp::m_pszAppID](#m_pszappid)|アプリケーション ユーザー モデルの id。|  
|[CWinApp::m_pszAppName](#m_pszappname)|アプリケーション名を示します。|  
|[CWinApp::m_pszExeName](#m_pszexename)|アプリケーションのモジュールの名前。|  
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|アプリケーションのヘルプ ファイルへのパス。|  
|[CWinApp::m_pszProfileName](#m_pszprofilename)|アプリケーションのです。INI ファイル名です。|  
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|アプリケーションのプロファイル設定を格納するためのフル レジストリ キーを決定するために使用します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|再起動マネージャーの動作方法を決定するフラグ。|  
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|自動保存の間隔をミリ秒で時間の長さ。|  
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|アプリケーションのデータ回復ハンドラーへのポインター。|  
  
## <a name="remarks"></a>Remarks  
 アプリケーション オブジェクトは、アプリケーション (およびの各インスタンス) を初期化するためと、アプリケーションを実行するために、メンバー関数を提供します。  
  
 Microsoft Foundation classes を使用する各アプリケーションから派生した 1 つのオブジェクトを含めることができますのみ`CWinApp`です。 このオブジェクトは他の C++ のグローバル オブジェクトが構築されるときに構築し、Windows を呼び出すときは、既に使用可能な`WinMain`関数は、これは、Microsoft Foundation Class ライブラリを提供します。 宣言、派生`CWinApp`グローバル レベルのオブジェクト。  
  
 アプリケーション クラスを派生する`CWinApp`、オーバーライド、 [InitInstance](#initinstance)アプリケーションのメイン ウィンドウのオブジェクトを作成するメンバー関数。  
  
 加え、`CWinApp`メンバー関数にアクセスする次のグローバル関数を提供する、Microsoft Foundation Class ライブラリ、`CWinApp`オブジェクトおよびその他のグローバル情報。  
  
- [AfxGetApp](application-information-and-management.md#afxgetapp)へのポインターを取得、`CWinApp`オブジェクト。  
  
- [AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)現在のアプリケーション インスタンスへのハンドルを取得します。  
  
- [AfxGetResourceHandle](application-information-and-management.md#afxgetresourcehandle)アプリケーションのリソースへのハンドルを取得します。  
  
- [AfxGetAppName](application-information-and-management.md#afxgetappname)アプリケーションの名前を含む文字列へのポインターを取得します。 またはへのポインターがある場合、`CWinApp`オブジェクトを使用して`m_pszExeName`アプリケーションの名前を取得します。  
  
 参照してください[CWinApp: アプリケーション クラス](../../mfc/cwinapp-the-application-class.md)詳細については、`CWinApp`次の概要も含め、クラス。  
  
- `CWinApp`-アプリケーションのウィザードによって作成されたコードを派生します。  
  
- `CWinApp`ロール、アプリケーションの実行順序にします。  
  
- `CWinApp`既定のメンバー関数の実装です。  
  
- `CWinApp`キーのオーバーライド可能な関数です。  
  
 `m_hPrevInstance`データ メンバーが存在しません。 以前のインスタンスの検出について`CWinApp`に、サポート技術情報の記事「どのように識別、以前のインスタンスのアプリケーションへ」(KB106385) を参照して[ http://support.microsoft.com/default.aspxscid=kb; en-us; 106385](http://support.microsoft.com/default.aspxscid=kb;en-us;106385)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 `CWinApp`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="adddoctemplate"></a>  とき  
 ドキュメント テンプレートをアプリケーションが管理する使用可能なドキュメント テンプレートの一覧に追加するのには、このメンバー関数を呼び出します。  
  
```  
void AddDocTemplate(CDocTemplate* pTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 *pTemplate*  
 ポインター、`CDocTemplate`を追加します。  
  
### <a name="remarks"></a>Remarks  
 呼び出す前に、すべてのドキュメントをアプリケーションにテンプレートを追加する必要があります[RegisterShellFileTypes](#registershellfiletypes)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]  
  
##  <a name="addtorecentfilelist"></a>  CWinApp::AddToRecentFileList  
 追加するには、このメンバー関数を呼び出す*終了*MRU ファイル リストにします。  
  
```  
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>パラメーター  
 *終了*  
 ファイルのパス。  
  
### <a name="remarks"></a>Remarks  
 呼び出す必要があります、 [LoadStdProfileSettings](#loadstdprofilesettings)メンバー関数をこのメンバー関数を使用する前に、現在の MRU ファイル リストを読み込めません。  
  
 フレームワークは、ファイルを開くか、または新しい名前を付けてファイルを保存する名前を付けて保存コマンドを実行するときに、このメンバー関数を呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]  
  
##  <a name="applicationrecoverycallback"></a>  CWinApp::ApplicationRecoveryCallback  
 アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。  
  
```  
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpvParam*  
 将来使用するために予約されています。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は 0以外の場合は、エラーが発生します。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションでは、再起動マネージャーをサポートする場合、フレームワークは、アプリケーションが予期せず終了したときに、この関数を呼び出します。  
  
 既定の実装`ApplicationRecoveryCallback`を使用して、`CDataRecoveryHandler`現在開いているドキュメントの一覧をレジストリに保存します。 このメソッドは、自動保存はすべてのファイルをしません。  
  
 動作をカスタマイズするには、派生では、この関数をオーバーライド[CWinApp クラス](../../mfc/reference/cwinapp-class.md)へのパラメーターとして独自のアプリケーションの回復方法を渡すまたは[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)です。  
  
##  <a name="closealldocuments"></a>  CWinApp::CloseAllDocuments  
 終了する前にすべての開いているドキュメントを閉じるには、このメンバー関数を呼び出します。  
  
```  
void CloseAllDocuments(BOOL bEndSession);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEndSession*  
 Windows セッションを終了するかどうかを指定します。 これは、場合は TRUE をセッションが終了中です。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 呼び出す[HideApplication](#hideapplication)呼び出す前に`CloseAllDocuments`です。  
  
##  <a name="createprinterdc"></a>  CWinApp::CreatePrinterDC  
 選択したプリンターからプリンター デバイス コンテキスト (DC) を作成するには、このメンバー関数を呼び出します。  
  
```  
BOOL CreatePrinterDC(CDC& dc);
```  
  
### <a name="parameters"></a>パラメーター  
 *dc*  
 プリンター デバイス コンテキストへの参照。  
  
### <a name="return-value"></a>戻り値  
 プリンター デバイス コンテキストを正常に作成する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `CreatePrinterDC` 参照渡しで渡す、印刷に使用できるようにデバイス コンテキストを初期化します。  
  
 印刷が完了したときに、関数が成功した場合は、デバイス コンテキストを破棄する必要があります。 デストラクターは、ことができます、 [CDC](../../mfc/reference/cdc-class.md)オブジェクトは、または呼び出すことによって明示的に行うことができます[デバイス コンテキストの破棄](../../mfc/reference/cdc-class.md#deletedc)です。  
  
##  <a name="cwinapp"></a>  CWinApp::CWinApp  
 構築、`CWinApp`オブジェクトを渡します*lpszAppName*をアプリケーション名として保存します。  
  
```  
CWinApp(LPCTSTR lpszAppName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszAppName*  
 Windows で使用されるアプリケーション名を表す null で終わる文字列。 この引数が指定されていないか、null、`CWinApp`リソース文字列 AFX_IDS_APP_TITLE または実行可能ファイルのファイル名を使用します。  
  
### <a name="remarks"></a>Remarks  
 1 つのグローバル オブジェクトを構築する必要があります、 `CWinApp`-クラスを派生します。 1 つだけ持つことができます`CWinApp`アプリケーションのオブジェクト。 コンス トラクターへのポインターを格納する、`CWinApp`オブジェクトように`WinMain`オブジェクトのメンバーを初期化し、アプリケーションを実行する関数を呼び出すことができます。  
  
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
 *hParentKey*  
 レジストリ キーへのハンドルします。  
  
 *strKeyName*  
 削除するレジストリ キーの名前。  
  
 *pTM*  
 CAtlTransactionManager オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 関数が成功すると、戻り値は、error_success を返します。 関数が失敗した場合、戻り値は、Winerror.h で定義されている 0 以外のエラー コードです。  
  
### <a name="remarks"></a>Remarks  
 指定したキーとそのサブキーを削除するには、この関数を呼び出します。  
  
##  <a name="domessagebox"></a>  CWinApp::DoMessageBox  
 グローバル関数でメッセージ ボックスを実装するには、このメンバー関数をフレームワーク[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)です。  
  
```  
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,  
    UINT nType,  
    UINT nIDPrompt);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszPrompt*  
 メッセージ ボックス内のテキストのアドレスです。  
  
 *タイプ*  
 メッセージ ボックス[スタイル](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)です。  
  
 *nIDPrompt*  
 ヘルプ コンテキスト文字列のインデックスです。  
  
### <a name="return-value"></a>戻り値  
 同じ値を返します`AfxMessageBox`です。  
  
### <a name="remarks"></a>Remarks  
 メッセージ ボックスを開くには、このメンバー関数を呼び出す必要はありません。使用して`AfxMessageBox`代わりにします。  
  
 アプリケーション全体の処理をカスタマイズするには、このメンバー関数をオーバーライド`AfxMessageBox`呼び出しです。  
  
##  <a name="dowaitcursor"></a>  CWinApp::DoWaitCursor  
 このメンバー関数が実装するためにフレームワークによって呼び出されます[CWaitCursor](../../mfc/reference/cwaitcursor-class.md)、 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)、 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)、および[CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)です。  
  
```  
virtual void DoWaitCursor(int nCode);
```  
  
### <a name="parameters"></a>パラメーター  
 *nCode*  
 このパラメーターが 1 の場合は、待機カーソルが表示されます。 0 の場合、参照カウントをインクリメントせずに待機カーソルが復元されます。 -1 の場合、待機カーソルを終了します。  
  
### <a name="remarks"></a>Remarks  
 既定値は砂時計カーソルを実装します。 `DoWaitCursor` 参照カウントを保持します。 正の値、砂時計カーソルが表示されます。  
  
 呼び出すことながら`DoWaitCursor`を直接待機カーソルを変更するかを待機カーソルが表示されている間に、追加の処理を行うには、このメンバー関数をオーバーライドする可能性があります。  
  
 使用する方法についてより効率化され、簡単に待機カーソルを実装する、`CWaitCursor`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]  
  
##  <a name="enabled2dsupport"></a>  CWinApp::EnableD2DSupport  
 [!INCLUDE[dev10_sp1required](../../mfc/reference/includes/dev10_sp1required_md.md)]  
  
 アプリケーションの D2D のサポートを有効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。  
  
```  
BOOL EnableD2DSupport(
D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,  
DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```  
  
### <a name="parameters"></a>パラメーター  
 *d2dFactoryType*  
 D2D ファクトリとリソースのスレッド モデルが作成されます。  
  
 *writeFactoryType*  
 書き込みのファクトリ オブジェクトが共有または分離されたかどうかを指定する値  
  
### <a name="return-value"></a>戻り値  
 かどうか D2D のサポートが有効な場合は FALSE、それ以外の場合は TRUE を返します  
  
##  <a name="enablehtmlhelp"></a>  CWinApp::EnableHtmlHelp  
 コンス トラクター内からこのメンバー関数を呼び出して、 `CWinApp`-アプリケーションのヘルプの html ヘルプを使用するクラスを派生します。  
  
```  
void EnableHtmlHelp();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="enableshellopen"></a>  CWinApp::EnableShellOpen  
 通常、この関数を呼び出す、 `InitInstance` override、Windows ファイル マネージャー内からファイルをダブルクリックしたときに、データ ファイルを開くアプリケーションのユーザーを有効にします。  
  
```  
void EnableShellOpen();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出す、`RegisterShellFileTypes`メンバーは、この関数を組み合わせて機能または提供します。ドキュメントの種類の手動登録のため、アプリケーションで REG ファイル。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]  
  
##  <a name="enabletaskbarinteraction"></a>  CWinApp::EnableTaskbarInteraction  
 タスク バーの相互作用を有効にします。  
  
```  
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnable*  
 Windows 7 のタスク バーとの対話が (TRUE) を有効にするか、無効 (FALSE) かどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 タスク バーの相互作用を有効または無効になっている場合は、TRUE を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、メイン ウィンドウの作成前に呼び出す必要があります、それ以外の場合、アサート FALSE を返します。  
  
##  <a name="exitinstance"></a>  し  
 内から、フレームワークによって呼び出されます、`Run`メンバー関数をアプリケーションのこのインスタンスを終了します。  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションの終了コードです。0 は、エラーを 、エラーを示す 0 より大きい値です。 この値はからの戻り値として使用`WinMain`です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数から呼び出さないで任意の場所が内、`Run`メンバー関数。  
  
 この関数の既定の実装では、アプリケーションのフレームワーク オプションを書き込みます。INI ファイルです。 アプリケーションが終了するときにクリーンアップするには、この関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]  
  
##  <a name="getapplicationrecoveryparameter"></a>  CWinApp::GetApplicationRecoveryParameter  
 アプリケーションの回復メソッドの入力パラメーターを取得します。  
  
```  
virtual LPVOID GetApplicationRecoveryParameter();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションの回復方法の既定の入力パラメーターです。  
  
### <a name="remarks"></a>Remarks  
 この関数の既定の動作は、NULL を返します。  
  
 詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)です。  
  
##  <a name="getapplicationrecoverypinginterval"></a>  CWinApp::GetApplicationRecoveryPingInterval  
 再起動マネージャーが、回復コールバック関数を返すまで待機する時間の長さを返します。  
  
```  
virtual DWORD GetApplicationRecoveryPingInterval();
```  
  
### <a name="return-value"></a>戻り値  
 時間 (ミリ秒) の長さ。  
  
### <a name="remarks"></a>Remarks  
 予期せず再起動マネージャーが終了に登録されているアプリケーション、アプリケーションの開いているドキュメントを保存しようとしています。 と回復コールバック関数を呼び出します。 既定の復旧のコールバック関数は[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)です。  
  
 回復のコールバック関数が返すのフレームワークが待機する時間の長さは、ping の間隔です。 Ping の間隔をカスタマイズするには、オーバーライドする`CWinApp::GetApplicationRecoveryPingInterval`またはカスタムの値を提供することによって`RegisterWithRestartManager`です。  
  
##  <a name="getapplicationrestartflags"></a>  CWinApp::GetApplicationRestartFlags  
 再起動マネージャーのフラグを返します。  
  
```  
virtual DWORD GetApplicationRestartFlags();
```  
  
### <a name="return-value"></a>戻り値  
 再起動マネージャーのフラグ。 既定の実装では、0 を返します。  
  
### <a name="remarks"></a>Remarks  
 再起動マネージャーのフラグは、既定の実装で影響を与えるありません。 将来使用するが提供されます。  
  
 再起動マネージャーを使用して、アプリケーションを登録するときに、フラグを設定する[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)です。  
  
 再起動マネージャーのフラグの値は次のとおりです。  
  
- RESTART_NO_CRASH  
  
- RESTART_NO_HANG  
  
- RESTART_NO_PATCH  
  
- RESTART_NO_REBOOT  
  
##  <a name="getappregistrykey"></a>  CWinApp::GetAppRegistryKey  
 HKEY_CURRENT_USER のキーを返します\\「ソフトウェア」\RegistryKey\ProfileName です。  
  
```  
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pTM*  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、アプリケーション キーそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getdatarecoveryhandler"></a>  CWinApp::GetDataRecoveryHandler  
 アプリケーションのこのインスタンスのデータ回復のハンドラーを取得します。  
  
```  
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションのこのインスタンスのデータ回復ハンドラー。  
  
### <a name="remarks"></a>Remarks  
 再起動マネージャーを使用する各アプリケーションは 1 つのインスタンスを持つ必要があります、 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)です。 このクラスは、開いているドキュメントと自動保存ファイルの監視を担当します。 動作、`CDataRecoveryHandler`再起動マネージャーの構成によって異なります。 詳細については、次を参照してください。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)です。  
  
 このメソッドは、Windows Vista より前のオペレーティング システムで NULL を返します。 再起動マネージャーは、Windows Vista より前のオペレーティング システムではサポートされていません。  
  
 アプリケーションがデータの回復ハンドラーを現在持っていない場合、このメソッドは 1 つを作成し、ポインターを返します。  
  
##  <a name="getfirstdoctemplateposition"></a>  CWinApp::GetFirstDocTemplatePosition  
 アプリケーション内の最初のドキュメント テンプレートの位置を取得します。  
  
```  
POSITION GetFirstDocTemplatePosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 イテレーションまたはオブジェクト ポインターの取得に使用できる位置の値リストが空の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 呼び出しで返される位置の値を使用して[GetNextDocTemplate](#getnextdoctemplate)最初を取得する[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクト。  
  
##  <a name="gethelpmode"></a>  CWinApp::GetHelpMode  
 アプリケーションで使用するヘルプの種類を取得します。  
  
```  
AFX_HELP_TYPE GetHelpMode();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションのヘルプ型です。 参照してください[CWinApp::m_eHelpType](#m_ehelptype)詳細についてはします。  
  
##  <a name="getnextdoctemplate"></a>  CWinApp::GetNextDocTemplate  
 によって識別されるドキュメント テンプレートを取得*pos*を設定し、 *pos*位置の値にします。  
  
```  
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pos*  
 以前の呼び出しによって返される位置の値への参照を`GetNextDocTemplate`または[GetFirstDocTemplatePosition](#getfirstdoctemplateposition)です。 値は、この呼び出しによって次の位置に更新されます。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 使用することができます`GetNextDocTemplate`への呼び出しに最初の位置を確立する場合は、順方向の反復ループで`GetFirstDocTemplatePosition`です。  
  
 位置の値が有効であることを確認する必要があります。 有効な場合は、Microsoft Foundation Class ライブラリのデバッグ バージョンはアサートします。  
  
 取得したドキュメント テンプレートが最後の場合の新しい値*pos*は NULL に設定します。  
  
##  <a name="getprinterdevicedefaults"></a>  CWinApp::GetPrinterDeviceDefaults  
 印刷用のプリンター デバイス コンテキストを準備するには、このメンバー関数を呼び出します。  
  
```  
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pPrintDlg*  
 ポインター、 [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843)構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 Windows から、現在のプリンターの既定値を取得します。INI ファイルとして、必要に応じて、またはプリンターの設定でユーザーが最新のプリンター構成の設定を使用します。  
  
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
 *大文字、小文字*  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。  
  
 *lpszEntry*  
 値を取得するエントリを指定する NULL で終わる文字列へのポインター。  
  
 *ppData*  
 データのアドレスを受け取るポインターへのポインター。  
  
 *ペタバイト*  
 (バイト単位) のデータのサイズを受け取る UINT へのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は大文字と小文字およびため内の文字列、*大文字、小文字*と*lpszEntry*パラメーターは、ケースで異なる場合があります。  
  
> [!NOTE]
> `GetProfileBinary` バッファーを割り当てるしでそのアドレスを返します\* *ppData*です。 使用して、バッファーを解放するため、呼び出し元が**delete[]** です。  
  
> [!IMPORTANT]
>  この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]  
  
 たとえば、次を参照してください。 [CWinApp::WriteProfileBinary](#writeprofilebinary)です。  
  
##  <a name="getprofileint"></a>  は  
 アプリケーションのレジストリまたは .INI ファイルの指定のセクション内のエントリから整数値を取得します。  
  
```  
UINT GetProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 *大文字、小文字*  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。  
  
 *lpszEntry*  
 値を取得するエントリを指定する NULL で終わる文字列へのポインター。  
  
 *見つからなかった*  
 フレームワークがエントリを見つけられなかったときのために指定する既定値。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、指定されたエントリに続く文字列の整数値を返します。 戻り値は、の値、*見つからなかった*パラメーターの場合は、関数にエントリが見つかりません。 指定されたエントリに対応する値が整数でない場合は、0 を返します。  
  
 このメンバー関数は .INI ファイル内の値として 16 進表記をサポートします。 符号付き整数を取得するときに値をキャストする必要があります、 **int**です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は大文字と小文字およびため内の文字列、*大文字、小文字*と*lpszEntry*パラメーターは、ケースで異なる場合があります。  
  
> [!IMPORTANT]
>  この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]  
  
 たとえば、次を参照してください。 [cwinapp::writeprofileint](#writeprofileint)です。  
  
##  <a name="getprofilestring"></a>  CWinApp::GetProfileString  
 アプリケーションのレジストリで指定されたセクション内のエントリに関連付けられている文字列を取得するには、このメンバー関数を呼び出すか。INI ファイルです。  
  
```  
CString GetProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszDefault = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *大文字、小文字*  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。  
  
 *lpszEntry*  
 文字列を取得するエントリを表す null で終わる文字列へのポインター。 この値は NULL をすることはできません。  
  
 *から*  
 初期化ファイルにエントリが見つからない場合は、指定したエントリの既定の文字列値を指します。  
  
### <a name="return-value"></a>戻り値  
 戻り値は、アプリケーションの文字列です。INI ファイルまたは*から*文字列が見つからない場合。 フレームワークでサポートされている文字列の最大長は、_MAX_PATH です。 場合*から*が NULL の場合、戻り値は空の文字列。  
  
### <a name="remarks"></a>Remarks  
  
> [!IMPORTANT]
>  この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 別の例では、例を参照してください。[は](#getprofileint)します。  
  
##  <a name="getsectionkey"></a>  CWinApp::GetSectionKey  
 HKEY_CURRENT_USER のキーを返します\\「ソフトウェア」\RegistryKey\AppName\lpszSection です。  
  
```  
HKEY GetSectionKey(
LPCTSTR lpszSection,  
CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *大文字、小文字*  
 取得するキーの名前です。  
  
 *pTM*  
 ポインター、`CAtlTransactionManager`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合のセクションのキーそれ以外の場合は NULL です。  
  
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
 *dwData*  
 追加のデータを指定します。 使用される値は、の値によって異なります、 *nCmd*パラメーター。  
  
 *nCmd*  
 要求されるヘルプの種類を指定します。 指定できる値とどのように影響の一覧については、 *dwData*パラメーターを参照してください、 *uCommand*パラメーターは、html ヘルプ API 関数で、Windows SDK で説明します。  
  
### <a name="remarks"></a>Remarks  
 フレームワークも html ヘルプ アプリケーションを起動するには、この関数を呼び出します。  
  
 フレームワークでは、アプリケーションが終了すると、html ヘルプ アプリケーションは自動的に閉じます。  
  
##  <a name="initinstance"></a>  場合は  
 Windows には、同時に実行する同じプログラムの複数のコピーが許可されます。  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションの初期化が 2 つのセクションに分かれています概念的には: 1 回限りのアプリケーションの初期化は、最初に行われる、プログラムが起動されるたびと時刻の最初の時間も含めて、プログラムの実行のコピーをそれぞれを実行しているインスタンスを初期化します。 フレームワークの実装の`WinMain`この関数を呼び出します。  
  
 オーバーライド`InitInstance`を Windows で実行されているアプリケーションの新しいインスタンスを初期化します。 通常、オーバーライドする`InitInstance`メイン ウィンドウ オブジェクトを構築し、設定、`CWinThread::m_pMainWnd`そのウィンドウをポイントするデータ メンバーです。 このメンバー関数のオーバーライドの詳細については、次を参照してください。 [CWinApp: アプリケーション クラス](../../mfc/cwinapp-the-application-class.md)です。  
  
> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 呼び出す場合[CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)で、`InitInstance`上書き、COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED ではなく) を指定します。 詳細については、[prb] を参照してください: MFC アプリケーションとして、マルチ スレッド アパートメント (828643) でアプリケーションを初期化するときの応答を停止[ http://support.microsoft.com/default.aspxscid=kb; en-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]  
  
##  <a name="istaskbarinteractionenabled"></a>  CWinApp::IsTaskbarInteractionEnabled  
 Windows 7 のタスク バーの相互作用が有効になっているかどうかを指示します。  
  
```  
virtual BOOL IsTaskbarInteractionEnabled();
```  
  
### <a name="return-value"></a>戻り値  
 場合に TRUE を返します`EnableTaskbarInteraction`が呼び出されたオペレーティング システムが Windows 7 以上とします。  
  
### <a name="remarks"></a>Remarks  
 タスク バーの相互作用は、MDI アプリケーションがアプリケーションのタスク バー ボタンの上にマウス ポインターがときに表示される個別のタブ付きのサムネイルで MDI 子フォームのコンテンツを表示することを意味します。  
  
##  <a name="loadcursor"></a>  CWinApp::LoadCursor  
 によって指定されたカーソル リソースを読み込みます*lpszResourceName*またはで指定*可能*現在の実行可能ファイルからです。  
  
```  
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszResourceName*  
 カーソル リソースの名前を表す null で終わる文字列へのポインター。 使用することができます、`CString`この引数にします。  
  
 *可能*  
 カーソル リソースの ID です。 リソースの一覧は、次を参照してください。 [LoadCursor](http://msdn.microsoft.com/library/windows/desktop/ms648391) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、カーソルのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 `LoadCursor` これがまだ読み込まれていない; 場合にのみ、メモリにカーソルを読み込みますそれ以外の場合、既存のリソースのハンドルを取得します。  
  
 使用して、 [LoadStandardCursor](#loadstandardcursor)または[LoadOEMCursor](#loadoemcursor)定義済みの Windows カーソルにアクセスするメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]  
  
##  <a name="loadicon"></a>  CWinApp::LoadIcon  
 によって指定されたアイコン リソースを読み込みます*lpszResourceName*またはで指定*可能*実行可能ファイルからです。  
  
```  
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszResourceName*  
 アイコン リソースの名前を表す null で終わる文字列へのポインター。 使用することも、`CString`この引数にします。  
  
 *可能*  
 アイコン リソースの ID 番号。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、アイコンへのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 `LoadIcon` これがまだ読み込まれていない; 場合にのみ、アイコンを読み込みますそれ以外の場合、既存のリソースのハンドルを取得します。  
  
 使用することができます、 [LoadStandardIcon](#loadstandardicon)または[LoadOEMIcon](#loadoemicon)定義済みの Windows のアイコンにアクセスするメンバー関数。  
  
> [!NOTE]
>  このメンバー関数は、Win32 API 関数を呼び出す[LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072)SM_CXICON と SM_CYICON システム メトリックの値に準拠しているサイズがアイコンを読み込むことができますのみです。  
  
##  <a name="loadoemcursor"></a>  CWinApp::LoadOEMCursor  
 定義済みで指定されたカーソル リソースの読み込み、Windows *nIDCursor*です。  
  
```  
HCURSOR LoadOEMCursor(UINT nIDCursor) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDCursor*  
 **OCR_** マニフェストの定義済みの Windows カーソルを指定する定数の識別子。 必要があります`#define OEMRESOURCE`する前に`#include \<afxwin.h>`にアクセスするために、 **OCR_** WINDOWS 内の定数です。H.  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、カーソルのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 使用して、`LoadOEMCursor`または[LoadStandardCursor](#loadstandardcursor)定義済みの Windows カーソルにアクセスするメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]  
  
 [!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]  
  
##  <a name="loadoemicon"></a>  CWinApp::LoadOEMIcon  
 定義済みで指定されたアイコン リソースを読み込み、Windows *nIDIcon*です。  
  
```  
HICON LoadOEMIcon(UINT nIDIcon) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDIcon*  
 **OIC_** マニフェストの定義済みの Windows アイコンを指定する定数の識別子。 必要があります`#define OEMRESOURCE`する前に`#include \<afxwin.h>`にアクセスする、 **OIC_** WINDOWS 内の定数です。H.  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、アイコンへのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 使用して、`LoadOEMIcon`または[LoadStandardIcon](#loadstandardicon)定義済みの Windows のアイコンにアクセスするメンバー関数。  
  
##  <a name="loadstandardcursor"></a>  CWinApp::LoadStandardCursor  
 定義済みのカーソル リソースを読み込み、Windows を*されています*を指定します。  
  
```  
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *されています*  
 **Idc _** マニフェストの定義済みの Windows カーソルを指定する定数の識別子。 これらの識別子は、WINDOWS で定義されます。H. 次の一覧は、使用可能な定義済みの値との意味を示しています*されています*:。  
  
- IDC_ARROW 標準の矢印カーソル  
  
- IDC_IBEAM 標準のテキスト挿入カーソル  
  
- Windows が時間のかかるタスクを実行するときに使用する IDC_WAIT 砂時計カーソル  
  
- IDC_CROSS 十字カーソルの選択  
  
- 上向き IDC_UPARROW 矢印  
  
- IDC_SIZE 不使用とサポートされていません。IDC_SIZEALL を使用します。  
  
- IDC_SIZEALL A 4 方向矢印カーソル。 使用して、ウィンドウのサイズを変更するカーソル。  
  
- IDC_ICON 不使用とサポートされていません。 IDC_ARROW を使用します。  
  
- 左と右下の両端に IDC_SIZENWSE 両方向矢印  
  
- 右方向と下の左上の両端に IDC_SIZENESW 両方向矢印  
  
- 双方向の IDC_SIZEWE 水平矢印  
  
- IDC_SIZENS 縦の双方向の矢印  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、カーソルのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 使用して、`LoadStandardCursor`または[LoadOEMCursor](#loadoemcursor)定義済みの Windows カーソルにアクセスするメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]  
  
##  <a name="loadstandardicon"></a>  CWinApp::LoadStandardIcon  
 定義済みのアイコン リソースを読み込み、Windows を*lpszIconName*を指定します。  
  
```  
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszIconName*  
 定義済みの Windows アイコンを指定するマニフェスト定数の識別子。 これらの識別子は、WINDOWS で定義されます。H. 可能な定義済みの値とその説明の一覧は、次を参照してください。、*されています*内のパラメーター [LoadIcon](http://msdn.microsoft.com/library/windows/desktop/ms648072) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、アイコンへのハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 使用して、`LoadStandardIcon`または[LoadOEMIcon](#loadoemicon)定義済みの Windows のアイコンにアクセスするメンバー関数。  
  
##  <a name="loadstdprofilesettings"></a>  既定  
 このメンバー関数内から、 [InitInstance](#initinstance)メンバー関数を有効にし、最近使用した (MRU) ファイルの一覧を読み込むと最後の状態をプレビューします。  
  
```  
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```  
  
### <a name="parameters"></a>パラメーター  
 *nMaxMRU*  
 追跡するために、最近使用したファイルの数。  
  
### <a name="remarks"></a>Remarks  
 場合*nMaxMRU*は 0、MRU 一覧は維持されません。  
  
##  <a name="m_bhelpmode"></a>  CWinApp::m_bHelpMode  
 アプリケーションが (従来どおりで起動される shift キーを押しながら f1 キー) です。 ヘルプ コンテキスト モードの場合は TRUE。それ以外の場合は FALSE。  
  
```  
BOOL m_bHelpMode;  
```  
  
### <a name="remarks"></a>Remarks  
 ヘルプ コンテキスト モードでは、カーソルが疑問符 () になり、ユーザーを使用すると、画面について移動できます。 ヘルプ モードのときに特別な処理を実装する場合は、このフラグを調べてください。 `m_bHelpMode` BOOL 型のパブリック変数です。  
  
##  <a name="m_dwrestartmanagersupportflags"></a>  CWinApp::m_dwRestartManagerSupportFlags  
 再起動マネージャーの動作方法を決定するフラグ。  
  
```  
DWORD m_dwRestartManagerSupportFlags;  
```  
  
### <a name="remarks"></a>Remarks  
 再起動マネージャーを有効にするには設定`m_dwRestartManagerSupportFlags`する動作をします。 次の表は、使用できるフラグを示します。  
  
|||  
|-|-|  
|フラグ|説明|  
|AFX_RESTART_MANAGER_SUPPORT_RESTART|使用してアプリケーションを登録する[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)です。 再起動マネージャーは、予期せず終了した場合、アプリケーションを再起動します。|  
|-AFX_RESTART_MANAGER_SUPPORT_RECOVERY|再起動マネージャーとアプリケーションを登録して、再起動マネージャーが、アプリケーションが再起動すると、復旧コールバック関数を呼び出します。 既定の復旧のコールバック関数は[CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)です。|  
|-AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|自動保存が有効にし、再起動マネージャーによって自動保存、アプリケーションを再起動すると、開いているドキュメントです。|  
|-AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|自動保存が有効にし、再起動マネージャーによって自動保存の開いているドキュメントを定期的な間隔でします。 間隔がによって定義された[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)です。|  
|-AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|再起動マネージャーは、予期しない終了からアプリケーションを再起動した後に開いていたドキュメントを開きます。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)開いているドキュメントの一覧を格納して、復元することを処理します。|  
|-AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|再起動マネージャーは、アプリケーションの再起動後に自動保存されたファイルを復元するかどうかを求めるメッセージを表示します。 `CDataRecoveryHandler`クラスは、ユーザーを照会します。|  
|-AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|AFX_RESTART_MANAGER_SUPPORT_RESTART、AFX_RESTART_MANAGER_SUPPORT_RECOVER、および AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES の和集合です。|  
|-AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART、AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL、および AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES の和集合です。|  
|-AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_RESTART、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES、および AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES の和集合です。|  
|-AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|共用体 ofAFX_RESTART_MANAGER_SUPPORT_RECOVERY、AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES、および AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES です。|  
  
##  <a name="m_ehelptype"></a>  CWinApp::m_eHelpType  
 このデータ メンバーの型は列挙型内で定義されている AFX_HELP_TYPE、`CWinApp`クラスです。  
  
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
  
-   HTML ヘルプ アプリケーションのヘルプを設定するには、呼び出す[として](#sethelpmode)指定と`afxHTMLHelp`です。  
  
-   WinHelp アプリケーションのヘルプを設定するには、呼び出す`SetHelpMode`指定と`afxWinHelp`です。  
  
##  <a name="m_hinstance"></a>  CWinApp::m_hInstance  
 対応する、 *hInstance*に Windows によって渡されるパラメーター`WinMain`です。  
  
```  
HINSTANCE m_hInstance;  
```  
  
### <a name="remarks"></a>Remarks  
 `m_hInstance`データ メンバーは、Windows で実行されているアプリケーションの現在のインスタンスへのハンドル。 これは、グローバル関数によって返される[AfxGetInstanceHandle](application-information-and-management.md#afxgetinstancehandle)です。 `m_hInstance` 型 HINSTANCE のパブリック変数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]  
  
##  <a name="m_lpcmdline"></a>  CWinApp::m_lpCmdLine  
 対応する、 *lpCmdLine*に Windows によって渡されるパラメーター`WinMain`です。  
  
```  
LPTSTR m_lpCmdLine;  
```  
  
### <a name="remarks"></a>Remarks  
 アプリケーションのコマンドラインを指定する null で終わる文字列へのポインター。 使用して`m_lpCmdLine`ユーザーがアプリケーションを起動したときに入力したコマンドライン引数にアクセスします。 `m_lpCmdLine` 型の lptstr などのパブリック変数です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="m_nautosaveinterval"></a>  CWinApp::m_nAutosaveInterval  
 自動保存の間隔をミリ秒で時間の長さ。  
  
```  
int m_nAutosaveInterval;  
```  
  
### <a name="remarks"></a>Remarks  
 自動保存の開いているドキュメントに、再起動マネージャーは、設定された間隔で構成できます。 アプリケーションが自動保存ファイルではない場合は、このパラメーターは影響を与えません。  
  
##  <a name="m_ncmdshow"></a>  CWinApp::m_nCmdShow  
 対応する、 *nCmdShow*に Windows によって渡されるパラメーター`WinMain`です。  
  
```  
int m_nCmdShow;  
```  
  
### <a name="remarks"></a>Remarks  
 渡す必要があります`m_nCmdShow`呼び出すときに引数として[また](../../mfc/reference/cwnd-class.md#showwindow)アプリケーションのメイン ウィンドウです。 `m_nCmdShow` 型のパブリック変数**int**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]  
  
##  <a name="m_pactivewnd"></a>  先  
 このデータ メンバーを使用すると、OLE サーバー アプリケーション、インプレース アクティブ化されている OLE コンテナー アプリケーションのメイン ウィンドウへのポインターを格納できます。  
  
### <a name="remarks"></a>Remarks  
 このデータ メンバーが NULL の場合は、アプリケーションが、インプレース アクティブです。  
  
 フレーム ウィンドウは、インプレース OLE コンテナー アプリケーションによってアクティブ化されるときに、フレームワークはこのメンバー変数を設定します。  
  
##  <a name="m_pdatarecoveryhandler"></a>  CWinApp::m_pDataRecoveryHandler  
 アプリケーションのデータ回復ハンドラーへのポインター。  
  
```  
CDataRecoveryHandler* m_pDataRecoveryHandler;  
```  
  
### <a name="remarks"></a>Remarks  
 アプリケーションのデータ回復のハンドラーは、開いているドキュメントと自動保存を監視します。 フレームワークでは、データ回復ハンドラーを使用して、アプリケーションが予期せず終了した後に再起動したときに、自動保存されたファイルを復元します。 詳細については、次を参照してください。 [CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)です。  
  
##  <a name="m_pszappname"></a>  CWinApp::m_pszAppName  
 アプリケーション名を示します。  
  
```  
LPCTSTR m_pszAppName;  
```  
  
### <a name="remarks"></a>Remarks  
 アプリケーション名に渡されたパラメーターから取得できます、 [CWinApp](#cwinapp)コンス トラクター、または、AFX_IDS_APP_TITLE の ID とリソース文字列を指定しない場合。 リソースの アプリケーション名が見つからない場合は、プログラムの由来とします。EXE ファイル名です。  
  
 グローバル関数によって返される[AfxGetAppName](application-information-and-management.md#afxgetappname)です。 `m_pszAppName` 型のパブリック変数**const char\*** です。  
  
> [!NOTE]
>  値を割り当てる場合`m_pszAppName`ヒープで動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**空き**this ポインターのに関するページ ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例えば:  
  
 [!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]  
  
##  <a name="m_pszexename"></a>  CWinApp::m_pszExeName  
 拡張子のないアプリケーションの実行可能ファイルの名前が含まれています。  
  
```  
LPCTSTR m_pszExeName;  
```  
  
### <a name="remarks"></a>Remarks  
 異なり[m_pszAppName](#m_pszappname)、この名前は空白を含めることはできません。 `m_pszExeName` 型のパブリック変数**const char\*** です。  
  
> [!NOTE]
>  値を割り当てる場合`m_pszExeName`ヒープで動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**空き**this ポインターのに関するページ ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例えば:  
  
 [!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]  
  
##  <a name="m_pszhelpfilepath"></a>  CWinApp::m_pszHelpFilePath  
 アプリケーションのヘルプ ファイルへのパスが含まれています。  
  
```  
LPCTSTR m_pszHelpFilePath;  
```  
  
### <a name="remarks"></a>Remarks  
 既定では、フレームワークを初期化します`m_pszHelpFilePath`を使用してアプリケーションの名前に"です。HLP"付加されます。 ヘルプ ファイルの名前を変更するには、次のように設定します。`m_pszHelpFilePath`目的のヘルプ ファイルの完全な名前を表す文字列を指すです。 これを行う便利な点は、アプリケーションの[InitInstance](#initinstance)関数。 `m_pszHelpFilePath` 型のパブリック変数**const char\*** です。  
  
> [!NOTE]
>  値を割り当てる場合`m_pszHelpFilePath`ヒープで動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**空き**this ポインターのに関するページ ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例えば:  
  
 [!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]  
  
##  <a name="m_pszprofilename"></a>  CWinApp::m_pszProfileName  
 アプリケーションの名前を表します。INI ファイルです。  
  
```  
LPCTSTR m_pszProfileName;  
```  
  
### <a name="remarks"></a>Remarks  
 `m_pszProfileName` 型のパブリック変数**const char\*** です。  
  
> [!NOTE]
>  値を割り当てる場合`m_pszProfileName`ヒープで動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**空き**this ポインターのに関するページ ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例えば:  
  
 [!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]  
  
##  <a name="m_pszregistrykey"></a>  CWinApp::m_pszRegistryKey  
 ここで、レジストリまたは INI ファイルで、アプリケーションのプロファイル設定の保存を決定するために使用します。  
  
```  
LPCTSTR m_pszRegistryKey;  
```  
  
### <a name="remarks"></a>Remarks  
 通常、このデータ メンバーは、読み取り専用として扱われます。  
  
-   レジストリ キー値が格納されます。 アプリケーション プロファイルの設定の名前が次のレジストリ キーに追加されます: HKEY_CURRENT_USER/ソフトウェア/LocalAppWizard で生成されるとします。  
  
 値を割り当てる場合`m_pszRegistryKey`ヒープで動的に割り当てる必要があります。 `CWinApp`デストラクター呼び出し**空き**this ポインターのに関するページ ()。 使用する多くの`_tcsdup`() のランタイム ライブラリ関数、割り当てを行う。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 例えば:  
  
 [!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]  
  
##  <a name="m_pszappid"></a>  CWinApp::m_pszAppID  
 アプリケーション ユーザー モデルの id。  
  
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
 追加する必要があります、`ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )`ステートメントを`CWinApp`クラスのメッセージ マップと追加アクセラレータ テーブル エントリを通常 shift キーを押しながら F1、このメンバー関数を有効にすることもできます。  
  
 `OnContextHelp` ヘルプ モードにアプリケーションを配置します。 カーソルが矢印と疑問符 () と、ユーザーに変わりますはマウス ポインターを移動し、 ダイアログ ボックス、ウィンドウ、メニューのまたはコマンド ボタンを選択する左マウス ボタンをクリックします。 このメンバー関数は、カーソルの下にあるオブジェクトのヘルプ コンテキストを取得し、そのヘルプ コンテキストを持つ Windows 関数 WinHelp を呼び出します。  
  
##  <a name="onddecommand"></a>  CWinApp::OnDDECommand  
 メイン フレーム ウィンドウは、DDE を受け取ると、フレームワークによって呼び出されますメッセージを実行します。  
  
```  
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszCommand*  
 アプリケーションによって受信 DDE コマンド文字列を指します。  
  
### <a name="return-value"></a>戻り値  
 コマンドが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 既定の実装では、かどうか、コマンドは要求を開くには、ドキュメントであり場合は、指定されたドキュメントが開きますを確認します。 Windows ファイル マネージャーでは、ユーザーがデータ ファイルをダブルクリックすると、DDE コマンド文字列がこのような一般送信します。 その他の DDE を処理するには、この関数は、コマンドを印刷するコマンドなどを実行します。 上書きします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]  
  
##  <a name="onfilenew"></a>  CWinApp::OnFileNew  
 ID_FILE_NEW コマンドを実装します。  
  
```  
afx_msg void OnFileNew();
```  
  
### <a name="remarks"></a>Remarks  
 追加する必要があります、`ON_COMMAND( ID_FILE_NEW, OnFileNew )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 有効な場合、この関数は、ファイルの新しいコマンドの実行を処理します。  
  
 参照してください[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)の既定の動作と、このメンバー関数を上書きする方法のガイダンスについてはします。  
  
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
  
 既定の動作と、このメンバー関数をオーバーライドする方法の詳細については、次を参照してください。[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onfileprintsetup"></a>  CWinApp::OnFilePrintSetup  
 ID_FILE_PRINT_SETUP コマンドを実装します。  
  
```  
afx_msg void OnFilePrintSetup();
```  
  
### <a name="remarks"></a>Remarks  
 追加する必要があります、`ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 有効な場合、この関数は、ファイルの印刷 コマンドの実行を処理します。  
  
 既定の動作と、このメンバー関数をオーバーライドする方法の詳細については、次を参照してください。[テクニカル ノート 22:](../../mfc/tn022-standard-commands-implementation.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]  
  
##  <a name="onhelp"></a>  :Onhelp  
 アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。  
  
```  
afx_msg void OnHelp();
```  
  
### <a name="remarks"></a>Remarks  
 通常、F1 キーをアクセラレータ キーのエントリを追加することもされます。 F1 キーを有効にするは、要件ではありません、規則だけです。  
  
 追加する必要があります、`ON_COMMAND( ID_HELP, OnHelp )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 有効な場合は、ユーザーが F1 キーを押したときに、フレームワークによって呼び出されます。  
  
 このメッセージ ハンドラー関数の既定の実装では、現在のウィンドウ、ダイアログ ボックスで、またはメニュー項目に対応する、winhelp をヘルプ コンテキストを決定します。EXE です。 現在使用可能なコンテキストがない場合、関数は、既定のコンテキストを使用します。  
  
 ウィンドウ、ダイアログ ボックス、メニュー項目または現在フォーカスがツール バー ボタン以外に、ヘルプ コンテキストを設定するには、この関数をオーバーライドします。 呼び出す`WinHelp`目的のヘルプ コンテキスト id。  
  
##  <a name="onhelpfinder"></a>  CWinApp::OnHelpFinder  
 ID_HELP_FINDER と ID_DEFAULT_HELP コマンドを処理します。  
  
```  
afx_msg void OnHelpFinder();
```  
  
### <a name="remarks"></a>Remarks  
 追加する必要があります、`ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 フレームワークが、アプリケーションのユーザーが呼び出すを検索するコマンドを選択したときにこのメッセージ ハンドラー関数を呼び出す有効な場合、`WinHelp`標準と**メニュー**トピックです。  
  
##  <a name="onhelpindex"></a>  CWinApp::OnHelpIndex  
 ID_HELP_INDEX コマンドを処理し、既定のヘルプ トピックを提供します。  
  
```  
afx_msg void OnHelpIndex();
```  
  
### <a name="remarks"></a>Remarks  
 追加する必要があります、`ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 アプリケーションのユーザーが呼び出すヘルプ コマンドを選択したときにフレームワークがこのメッセージ ハンドラー関数を呼び出す有効な場合、`WinHelp`標準と**メニュー**トピックです。  
  
##  <a name="onhelpusing"></a>  CWinApp::OnHelpUsing  
 ID_HELP_USING コマンドを処理します。  
  
```  
afx_msg void OnHelpUsing();
```  
  
### <a name="remarks"></a>Remarks  
 追加する必要があります、`ON_COMMAND( ID_HELP_USING, OnHelpUsing )`ステートメントを`CWinApp`このメンバー関数を有効にするクラスのメッセージ マップです。 フレームワークは、アプリケーションのユーザーが呼び出すヘルプを使用してコマンドを選択したときにこのメッセージ ハンドラー関数を呼び出します、`WinHelp`標準アプリケーション**有効**トピックです。  
  
##  <a name="onidle"></a>  CWinApp::OnIdle  
 アイドル処理を実行するには、このメンバー関数をオーバーライドします。  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>パラメーター  
 *lCount*  
 カウンターたびに増分されます`OnIdle`は、アプリケーションのメッセージ キューが空のときに呼び出されます。 この数は、新しいメッセージが処理されるたびに 0 にリセットされます。 使用することができます、 *lCount*パラメーターをアプリケーションがアイドル状態になったメッセージを処理することがなく時間の相対的な長さを決定します。  
  
### <a name="return-value"></a>戻り値  
 さらにアイドル処理時間の受信には 0 以外。これ以上のアイドル時間が必要な場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `OnIdle` アプリケーションのメッセージ キューが空とき、既定のメッセージ ループで呼び出されます。 これらに上書きを使用して、独自の背景のアイドル処理を呼び出します。  
  
 `OnIdle` アイドル状態の処理時間が必要ないことを示すために 0 を返す必要があります。 *LCount*パラメーターはたびに増分`OnIdle`は、メッセージ キューが空で、新しいメッセージが処理されるたびに、0 にリセットときに呼び出されます。 この数に基づく、別のアイドル処理ルーチンを呼び出すことができます。  
  
 アイドル ループ処理を以下に示します。  
  
1.  Microsoft Foundation Class ライブラリにメッセージ ループが、メッセージ キューをチェックして、保留中のメッセージを検索しない場合は呼び出します`OnIdle`application オブジェクトや装置 0 としての*lCount*引数。  
  
2. `OnIdle` 一部の処理を実行し、0 以外の値を示すを行うにはもう一度呼び出す必要がありますを返しますさらに処理します。  
  
3.  メッセージ ループは、メッセージ キューをもう一度確認します。 保留中のメッセージがない場合は、呼び出す`OnIdle`もう一度、インクリメント、 *lCount*引数。  
  
4.  最終的には、`OnIdle`アイドル状態のすべてのタスクの処理が完了すると、0 を返します。 これにより、メッセージ ループの呼び出しを停止する`OnIdle`まで、メッセージ キューから次のメッセージを受信すると、この時点でアイドル状態にサイクルが再開引数を 0 に設定します。  
  
 時に、時間のかかるタスクを実行しない`OnIdle`アプリケーションまでのユーザー入力を処理できないため`OnIdle`を返します。  
  
> [!NOTE]
>  既定の実装`OnIdle`更新コマンドのメニュー項目とツール バー ボタンなどのユーザー インターフェイス オブジェクトと、内部データ構造体の後処理を行います。 そのため、オーバーライドする場合は`OnIdle`、呼び出す必要があります`CWinApp::OnIdle`で、`lCount`オーバーライドのバージョン。 まずアイドル処理のすべての基本クラスを呼び出す (つまり、基本クラスまで`OnIdle`0 を返します)。 基本クラスの処理が完了する前に、作業を実行する必要がある場合は、適切なを選択する基本クラスの実装を確認*lCount*する作業を行います。  
  
 たくない場合`OnIdle`には、するには、メッセージ キューからメッセージが取得されるたびに呼び出されると、オーバーライド、 [CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage)です。 アプリケーションが、非常に短いタイマーを設定した場合、またはシステム メッセージを送信して、とき、し`OnIdle`、繰り返し呼び出され、パフォーマンスが低下します。  
  
### <a name="example"></a>例  
 次の 2 つの例は、使用する方法を示して`OnIdle`です。 最初の例を使用して 2 つのアイドル状態のタスクの処理、 *lCount*タスクの優先順位を設定する引数。 最初のタスクは、優先度の高いと、可能な限りこれを行う必要があります。 2 番目のタスクは、重要度の低いユーザー入力に長い一時停止する場合にのみ行う必要があります。 基本クラスのバージョンへの呼び出しに注意してください`OnIdle`です。 2 番目の例では、異なる優先順位がアイドル状態のタスクのグループを管理します。  
  
 [!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]  
  
##  <a name="opendocumentfile"></a>  :Opendocumentfile  
 フレームワークは、このメソッドを開くには、名前付き[CDocument](../../mfc/reference/cdocument-class.md)アプリケーション用のファイルです。  
  
```  
virtual CDocument* OpenDocumentFile(
LPCTSTR lpszFileName  
BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*場合*  
 開かれるファイルの名前。  
  
 [in]*bAddToMRU*  
 TRUE は、このドキュメントは、最新のファイルのいずれかのことを示しますFALSE は、ドキュメントが最新のファイルのいずれかを示します。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CDocument`成功、それ以外の場合に NULL 以外の場合。  
  
### <a name="remarks"></a>Remarks  
 その名前を持つドキュメントを既に開いている場合、そのドキュメントを含む最初のフレーム ウィンドウは、フォーカスを取得します。 アプリケーションでは、複数のドキュメント テンプレートをサポートする場合、フレームワークは、ドキュメントの読み込みしようとする適切なドキュメント テンプレートを検索するファイル名拡張子を使用します。 成功した場合、ドキュメント テンプレートは、フレーム ウィンドウとドキュメントのビューに、作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]  
  
##  <a name="parsecommandline"></a>  CWinApp::ParseCommandLine  
 コマンドラインを解析し、一度に 1 つずつパラメーターに送信するには、このメンバー関数を呼び出す[後](../../mfc/reference/ccommandlineinfo-class.md#parseparam)です。  
  
```  
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *rCmdInfo*  
 参照、[メンバー](../../mfc/reference/ccommandlineinfo-class.md)オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションのウィザードでのローカル インスタンスを作成するアプリケーションのウィザードを使用して新しい MFC プロジェクトを開始するときに`CCommandLineInfo`、およびを呼び出す`ProcessShellCommand`と`ParseCommandLine`で、 [InitInstance](#initinstance)メンバー関数。 コマンド ラインには、次に示すルートが次に示します。  
  
1.  後で作成されている`InitInstance`、`CCommandLineInfo`にオブジェクトが渡される`ParseCommandLine`です。  
  
2. `ParseCommandLine` 呼び出して`CCommandLineInfo::ParseParam`繰り返し、各パラメーターに対して 1 回です。  
  
3. `ParseParam` 入力、`CCommandLineInfo`に渡され、オブジェクト[ProcessShellCommand](#processshellcommand)です。  
  
4. `ProcessShellCommand` コマンドライン引数とフラグを処理します。  
  
 呼び出すことのできる注`ParseCommandLine`必要に応じて、直接です。  
  
 コマンド ライン フラグの説明は、次を参照してください。 [CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)です。  
  
##  <a name="pretranslatemessage"></a>  Cwinapp::pretranslatemessage  
 Windows 関数にディスパッチされる前に、ウィンドウ メッセージをフィルター処理するには、この関数をオーバーライド[TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)既定の実装には、アクセラレータ キーを実行します翻訳を呼び出す必要がありますので、`CWinApp::PreTranslateMessage`オーバーライドのバージョンのメンバー関数。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pMsg*  
 ポインター、 [MSG](../../mfc/reference/msg-structure1.md)を処理するメッセージを含む構造体。  
  
### <a name="return-value"></a>戻り値  
 メッセージで完全に処理された場合は 0 以外`PreTranslateMessage`さらに処理する必要がないとします。 通常の方法で、メッセージを処理する必要がある場合は 0 します。  
  
##  <a name="processmessagefilter"></a>  CWinApp::ProcessMessageFilter  
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
 Windows へのポインター [MSG](../../mfc/reference/msg-structure1.md)構造体。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 フック関数の処理、アプリケーションの通常のメッセージを送信する前に、イベントを処理します。  
  
 この高度な機能をオーバーライドする場合は、フレームワークを維持するために基本クラスのバージョンを呼び出すことを確認する処理をフックします。  
  
##  <a name="processshellcommand"></a>  CWinApp::ProcessShellCommand  
 によって呼び出されます[InitInstance](#initinstance)から渡されたパラメーターを受け入れるように、`CCommandLineInfo`で識別されるオブジェクト*rCmdInfo*、指定されたアクションを実行します。  
  
```  
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *rCmdInfo*  
 参照、[メンバー](../../mfc/reference/ccommandlineinfo-class.md)オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、シェル コマンドが正常に処理されます。 0 の場合から FALSE を返す場合[InitInstance](#initinstance)です。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションのウィザードでのローカル インスタンスを作成するアプリケーションのウィザードを使用して新しい MFC プロジェクトを開始するときに`CCommandLineInfo`、およびを呼び出す`ProcessShellCommand`と[ParseCommandLine](#parsecommandline)で、`InitInstance`メンバー関数。 コマンド ラインには、次に示すルートが次に示します。  
  
1.  後で作成されている`InitInstance`、`CCommandLineInfo`にオブジェクトが渡される`ParseCommandLine`です。  
  
2. `ParseCommandLine` 呼び出して[後](../../mfc/reference/ccommandlineinfo-class.md#parseparam)繰り返し、各パラメーターに対して 1 回です。  
  
3. `ParseParam` 入力、`CCommandLineInfo`に渡され、オブジェクト`ProcessShellCommand`です。  
  
4. `ProcessShellCommand` コマンドライン引数とフラグを処理します。  
  
 データ メンバーの`CCommandLineInfo`で識別されるオブジェクト[CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)、次の列挙型内で定義されているは、`CCommandLineInfo`クラスです。  
  
```  
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };  
```
  
 これらの各値の簡単な説明を参照してください。`CCommandLineInfo::m_nShellCommand`です。  
  
##  <a name="processwndprocexception"></a>  CWinApp::ProcessWndProcException  
 ハンドラーは、アプリケーションのメッセージまたはコマンド ハンドラーのいずれかでスローされる例外をキャッチしませんされるたびに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *e*  
 キャッチされない例外へのポインター。  
  
 *pMsg*  
 A [MSG](../../mfc/reference/msg-structure1.md)フレームワークが例外をスローする原因となった windows メッセージについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 Windows に返される値。 通常これは 0 L 1 L、ウィンドウ メッセージ (TRUE) コマンド メッセージです。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数を直接呼び出さないでください。  
  
 このメンバー関数の既定の実装では、メッセージ ボックスを作成します。 メッセージ ボックス、メニューのツールバー、またはアクセラレータ コマンド エラーのキャッチされない例外の作成元;「コマンドが失敗しました」メッセージが表示されます。それ以外の場合、「内部アプリケーション エラー」メッセージが表示されます。  
  
 グローバルに、例外の処理を提供するには、このメンバー関数をオーバーライドします。 メッセージ ボックスを表示する場合は、基本的な機能を呼び出すのみです。  
  
##  <a name="register"></a>  CWinApp::Register  
 登録タスクで処理されない実行`RegisterShellFileTypes`です。  
  
```  
virtual BOOL Register();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 既定の実装は、単に TRUE を返します。 カスタマイズした登録ステップを提供するには、この関数をオーバーライドします。  
  
##  <a name="registershellfiletypes"></a>  登録  
 Windows ファイル マネージャーで、アプリケーションのドキュメントの種類をすべて登録するには、このメンバー関数を呼び出します。  
  
```  
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bCompat*  
 TRUE は、シェル コマンドの印刷と印刷を許可する場合にファイルを印刷するプリンター オブジェクトに、ファイルをドラッグするか、シェルから直接ユーザーの登録エントリを追加します。 また、DefaultIcon キーを追加します。 このパラメーターが FALSE は既定では、旧バージョンとの互換性のためです。  
  
### <a name="remarks"></a>Remarks  
 こうと、ユーザーをダブルクリックしてからファイル マネージャー内で、アプリケーションによって作成されたデータ ファイルを開くことができます。 呼び出す`RegisterShellFileTypes`を呼び出した後[AddDocTemplate](#adddoctemplate)アプリケーションのドキュメント テンプレートの各します。 呼び出すことも、 [EnableShellOpen](#enableshellopen)メンバー関数を呼び出すと`RegisterShellFileTypes`です。  
  
 `RegisterShellFileTypes` リストを反復処理[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)アプリケーションの維持し、それぞれのドキュメント テンプレートのファイルの関連付けを管理する Windows レジストリ データベースにエントリを追加するオブジェクトします。 ファイル マネージャーでは、これらのエントリを使用してユーザーをダブルクリックすると、そのデータ ファイルを開きます。 これを出荷する必要がある、します。アプリケーションを使用して REG ファイルです。  
  
> [!NOTE]
> `RegisterShellFileTypes` ユーザーが管理者権限を持つ、プログラムを実行する場合にのみ機能します。 プログラムが管理者権限を持っていない場合のレジストリ キーを変更することはできません。  
  
 登録情報データベースは、既に別のファイル タイプに指定されたファイル名拡張子を関連付けます、新しい関連付けは作成されません。 参照してください、`CDocTemplate`この情報を登録するために必要な文字列の形式のクラスです。  
  
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
|[in]*bRegisterRecoveryCallback*|TRUE は、アプリケーションのこのインスタンスが回復コールバック関数では; を使用することを示しますFALSE は、しないことを示します。 フレームワークは、アプリケーションが予期せず終了したときに、回復のコールバック関数を呼び出します。 詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)です。|  
|[in]*strRestartIdentifier*|再起動マネージャーのインスタンスを識別する一意の文字列。 再起動マネージャーの識別子は、アプリケーションの各インスタンスに対して一意です。|  
|[in]*pwzCommandLineArgs*|コマンドラインから余分な引数を表す文字列。|  
|[in]*dwRestartFlags*|再起動マネージャーのオプションのフラグ。 詳細については、「解説」を参照してください。|  
|[in]*pRecoveryCallback*|回復のコールバック関数。 この関数は、入力として LPVOID パラメーターを使用し、DWORD を返す必要があります。 既定の復旧のコールバック関数は`CWinApp::ApplicationRecoveryCallback`します。|  
|[in]*lpvParam*|回復のコールバック関数の入力パラメーター。 詳細については、次を参照してください。 [CWinApp::ApplicationRecoveryCallback](#applicationrecoverycallback)です。|  
|[in]*dwPingInterval*|再起動マネージャーが、回復コールバック関数を返すまで待機する時間の長さ。 このパラメーターはミリ秒です。|  
|[in]*dwCallbackFlags*|フラグは、回復のコールバック関数に渡されます。 将来使用するために予約されています。|  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK、それ以外の場合はエラー コード。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションでは、ファイルを自動保存の既定の MFC 実装を使用する場合は、単純なバージョンを使用する必要があります`RegisterWithRestartManager`です。 複雑なバージョンの使用`RegisterWithRestartManager`アプリケーションの自動保存の動作をカスタマイズする場合。  
  
 空の文字列では、このメソッドを呼び出すかどうか*strRestartIdentifier*、`RegisterWithRestartManager`マネージャーを再起動のこのインスタンスの一意の識別子の文字列を作成します。  
  
 アプリケーションが予期せず終了したときに、再起動マネージャーは、コマンドラインからアプリケーションを再起動し、一意の再起動オプションの引数としての識別子を提供します。 このシナリオでは、フレームワークによって呼び出されます`RegisterWithRestartManager`2 倍です。 最初の呼び出し元となる[場合は](#initinstance)文字列識別子として空の文字列にします。 メソッドではその後、 [CWinApp::ProcessShellCommand](#processshellcommand)呼び出し`RegisterWithRestartManager`一意の再起動の識別子を使用します。  
  
 再起動マネージャーとアプリケーションを登録した後、再起動マネージャーは、アプリケーションを監視します。 アプリケーションが予期せず終了した場合、再起動マネージャーは、シャット ダウン処理中に回復コールバック関数を呼び出します。 再起動マネージャーの待機時間、 *dwPingInterval*回復コールバック関数からの応答。 回復コールバック関数がこの時間内に応答しない場合は、回復コールバック関数を実行することがなく、アプリケーションが終了します。  
  
 既定は、dwRestartFlags はサポートされていませんが、将来使用するために提供されます。 値は、使用可能な*dwRestartFlags*次に示します。  
  
- RESTART_NO_CRASH  
  
- RESTART_NO_HANG  
  
- RESTART_NO_PATCH  
  
- RESTART_NO_REBOOT  
  
##  <a name="reopenpreviousfilesatrestart"></a>  CWinApp::ReopenPreviousFilesAtRestart  
 再起動マネージャーが、アプリケーションが予期せず終了したときに開いていたファイルを再度開くかどうかを判断します。  
  
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
 データ回復のハンドラーが開いていたドキュメントを開いた場合は TRUE。データ回復ハンドラー エラーがある場合、または開いていたドキュメントが存在しない場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 再起動マネージャーには、アプリケーションが再起動したら、フレームワークは、このメソッドを呼び出します。 このメソッドは、データ回復のハンドラーを取得し、自動保存されたファイルを復元します。 このメソッドを呼び出す[CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments)をユーザーが自動保存されたファイルを復元するかどうかを判断します。  
  
 このメソッドは、場合に FALSE を返します、 [CDataRecoveryHandler](../../mfc/reference/cdatarecoveryhandler-class.md)開いているドキュメントが含まれていなかったことを決定します。 開いているドキュメントがない場合、通常、アプリケーションを開始します。  
  
##  <a name="restoreautosavedfilesatrestart"></a>  CWinApp::RestoreAutosavedFilesAtRestart  
 アプリケーションが再起動すると、再起動マネージャーが自動保存されたファイルを復元するかどうかを判断します。  
  
```  
virtual BOOL RestoreAutosavedFilesAtRestart() const;  
```  
  
### <a name="return-value"></a>戻り値  
 True の場合、再起動マネージャーは、自動保存されたファイルを復元FALSE は、再起動マネージャーがいないことを示します。  
  
##  <a name="run"></a>  :Run  
 既定のメッセージ ループを提供します。  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>戻り値  
 **Int**によって返される値`WinMain`です。  
  
### <a name="remarks"></a>Remarks  
 `Run` 取得し、アプリケーションが WM_QUIT メッセージを受信するまでは、Windows メッセージをディスパッチします。 アプリケーションのメッセージ キューにメッセージがない場合`Run`呼び出し[OnIdle](#onidle)アイドル処理を実行します。 受信メッセージに移動、 [PreTranslateMessage](#pretranslatemessage)メンバー関数は、特別な処理し、Windows 関数に`TranslateMessage`標準キーボード翻訳; の最後に、 `DispatchMessage` Windows 関数が呼び出されます。  
  
 `Run` オーバーライドされることはほとんどありませんが、特別な動作を提供するメソッドをオーバーライドすることができます。  
  
##  <a name="runautomated"></a>  CWinApp::RunAutomated  
 判断するには、この関数を呼び出すかどうか、" **/Automation**「または」 **-オートメーション**"オプションは、サーバー アプリケーションがクライアント アプリケーションによって起動されるかどうかを示します。  
  
```  
BOOL RunAutomated();
```  
  
### <a name="return-value"></a>戻り値  
 オプションが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 存在する場合、オプションはコマンドラインから削除されます。 OLE オートメーションの詳細については、記事を参照してください。[オートメーション サーバー](../../mfc/automation-servers.md)です。  
  
##  <a name="runembedded"></a>  CWinApp::RunEmbedded  
 判断するには、この関数を呼び出すかどうか、" **/embedding か**「または」 **-埋め込み**"オプションは、サーバー アプリケーションがクライアント アプリケーションによって起動されるかどうかを示します。  
  
```  
BOOL RunEmbedded();
```  
  
### <a name="return-value"></a>戻り値  
 オプションが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 存在する場合、オプションはコマンドラインから削除されます。 埋め込みの詳細については、記事を参照してください。[サーバー: サーバーの実装](../../mfc/servers-implementing-a-server.md)です。  
  
##  <a name="saveallmodified"></a>  CWinApp::SaveAllModified  
 または閉じられる、アプリケーションのメイン フレーム ウィンドウが閉じられるときに、すべてのドキュメントを保存するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL SaveAllModified();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションを終了してもよい場合は 0 以外。アプリケーションを終了する安全でない場合は 0 を返します。  
  
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
 *と*  
 ハンドル、 [DEVNAMES](../../mfc/reference/devnames-structure.md)ドライバー、デバイス、および特定のプリンターの出力ポート名を識別する構造体。  
  
 *hDevMode*  
 ハンドル、 [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565)をデバイスの初期化とプリンターの環境に関する情報を指定します。  
  
 *bFreeOld*  
 選択したプリンターを解放します。  
  
### <a name="remarks"></a>Remarks  
 両方*hDevMode*と*と*null、`SelectPrinter`現在の既定のプリンターを使用します。  
  
##  <a name="sethelpmode"></a>  CWinApp::SetHelpMode  
 アプリケーションのヘルプの種類を設定します。  
  
```  
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```  
  
### <a name="parameters"></a>パラメーター  
 *eHelpType*  
 使用するヘルプの種類を指定します。 参照してください[CWinApp::m_eHelpType](#m_ehelptype)詳細についてはします。  
  
### <a name="remarks"></a>Remarks  
 アプリケーションのヘルプの種類を設定します。  
  
 Html ヘルプに、アプリケーションのヘルプの種類を設定するに呼び出せる[EnableHTMLHelp](#enablehtmlhelp)です。 呼び出す`EnableHTMLHelp`アプリケーションは、そのヘルプ アプリケーションとして html ヘルプを使用する必要があります。 WinHelp を使用して変更する場合は、呼び出す`SetHelpMode`設定と*eHelpType*に`afxWinHelp`です。  
  
##  <a name="setregistrykey"></a>  書き込むに  
 INI ファイルではなく、レジストリに格納されるアプリケーションの設定が発生します。  
  
```  
void SetRegistryKey(LPCTSTR lpszRegistryKey);  
void SetRegistryKey(UINT nIDRegistryKey);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszRegistryKey*  
 キーの名前を含む文字列へのポインター。  
  
 *nIDRegistryKey*  
 レジストリ キーの名前を含む文字列リソースの ID です。  
  
### <a name="remarks"></a>Remarks  
 この関数は、設定*m_pszRegistryKey*が、使用して、 `GetProfileInt`、 `GetProfileString`、 `WriteProfileInt`、および`WriteProfileString`のメンバー関数は`CWinApp`します。 この関数が呼び出された場合最近使用 (した MRU) ファイルの一覧は、レジストリにも格納されます。 レジストリ キーは、通常、会社の名前です。 次の形式のキーに格納されている: ように\\< 会社名\>\\< アプリケーション名\>\\< セクション名\>\\< 値名前\>です。  
  
##  <a name="supportsapplicationrecovery"></a>  CWinApp::SupportsApplicationRecovery  
 再起動マネージャーが予期せず終了したアプリケーションを回復するかどうかを判断します。  
  
```  
virtual BOOL SupportsApplicationRecovery() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE は、再起動マネージャー アプリケーションを回復することを示しますFALSE は、再起動マネージャーがいないことを示します。  
  
##  <a name="supportsautosaveatinterval"></a>  CWinApp::SupportsAutosaveAtInterval  
 再起動マネージャーによって自動保存が一定の間隔でドキュメントを開くかどうかを判断します。  
  
```  
virtual BOOL SupportsAutosaveAtInterval() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE は、再起動マネージャーによって自動保存がドキュメントを開くことを示しますFALSE は、再起動マネージャーがいないことを示します。  
  
##  <a name="supportsautosaveatrestart"></a>  CWinApp::SupportsAutosaveAtRestart  
 指定するかどうか再起動マネージャーによって自動保存、アプリケーションを再起動すると、開いているドキュメントです。  
  
```  
virtual BOOL SupportsAutosaveAtRestart() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE は、アプリケーションの再起動時; に、再起動マネージャーによって自動保存がドキュメントを開くことを示しますFALSE は、再起動マネージャーがいないことを示します。  
  
##  <a name="supportsrestartmanager"></a>  CWinApp::SupportsRestartManager  
 アプリケーションが再起動マネージャーをサポートしているかどうかを判断します。  
  
```  
virtual BOOL SupportsRestartManager() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE は、アプリケーションが再起動マネージャー; をサポートしていることを示しますFALSE は、アプリケーションがいないことを示します。  
  
##  <a name="unregister"></a>  CWinApp::Unregister  
 アプリケーションのオブジェクトによって登録されたすべてのファイルを登録解除します。  
  
```  
virtual BOOL Unregister();
```  
  
### <a name="return-value"></a>戻り値  
 正常に完了した場合はゼロ以外、それ以外の場合は 0 です。  
  
### <a name="remarks"></a>Remarks  
 `Unregister`関数は、アプリケーションのオブジェクトが実行する登録を元に戻すと、[登録](#register)関数。 通常は、どちらの関数は MFC によって暗黙的に呼び出され、そのため、コードでは表示されません。  
  
 カスタムの登録解除の手順を実行するには、この関数をオーバーライドします。  
  
##  <a name="unregistershellfiletypes"></a>  CWinApp::UnregisterShellFileTypes  
 すべてのアプリケーションのドキュメントの種類、Windows ファイル マネージャーでの登録を解除するには、このメンバー関数を呼び出します。  
  
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
 *dwData*  
 追加のデータを指定します。 使用される値は、の値によって異なります、 *nCmd*パラメーター。  
  
 *nCmd*  
 要求されるヘルプの種類を指定します。 指定できる値とどのように影響の一覧については、 *dwData*パラメーターを参照してください、 [WinHelp](http://msdn.microsoft.com/library/windows/desktop/bb762267) Windows の機能です。  
  
### <a name="remarks"></a>Remarks  
 フレームワークも WinHelp アプリケーションを起動するには、この関数を呼び出します。  
  
 フレームワークでは、アプリケーションが終了するとき、WinHelp アプリケーションが自動的に閉じます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]  
  
##  <a name="writeprofilebinary"></a>  CWinApp::WriteProfileBinary  
 アプリケーションのレジストリの指定したセクションにバイナリ データを書き込むには、このメンバー関数を呼び出すか。INI ファイルです。  
  
```  
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPBYTE pData,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 *大文字、小文字*  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。文字列には、任意の大文字と小文字があります。  
  
 *lpszEntry*  
 値を記述するエントリを表す null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。  
  
 *pData*  
 書き込まれるデータへのポインター。  
  
 *nBytes*  
 書き込むバイト数が含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 この例では`CWinApp* pApp = AfxGetApp();`方法を示す CWinApp クラスを取得するを`WriteProfileBinary`と`GetProfileBinary`任意の関数は MFC アプリケーションから使用できます。  
  
 [!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]  
  
 別の例では、例を参照してください。[は](#getprofilebinary)します。  
  
##  <a name="writeprofileint"></a>  Cwinapp::writeprofileint  
 アプリケーションのレジストリの指定したセクションに指定された値を書き込むには、このメンバー関数を呼び出すか。INI ファイルです。  
  
```  
BOOL WriteProfileInt(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    int nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *大文字、小文字*  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。文字列には、任意の大文字と小文字があります。  
  
 *lpszEntry*  
 値を記述するエントリを表す null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。  
  
 *値*  
 書き込まれる値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 この例では`CWinApp* pApp = AfxGetApp();`方法を示す CWinApp クラスを取得するを`WriteProfileString`、 `WriteProfileInt`、 `GetProfileString`、および`GetProfileInt`任意の関数は MFC アプリケーションから使用できます。  
  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 別の例では、例を参照してください。[は](#getprofileint)します。  
  
##  <a name="writeprofilestring"></a>  CWinApp::WriteProfileString  
 アプリケーションのレジストリの指定したセクションに指定した文字列を書き込むには、このメンバー関数を呼び出すか。INI ファイルです。  
  
```  
BOOL WriteProfileString(
    LPCTSTR lpszSection,  
    LPCTSTR lpszEntry,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *大文字、小文字*  
 エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は作成されます。 セクションの名前が区別されません。文字列には、任意の大文字と小文字があります。  
  
 *lpszEntry*  
 値を記述するエントリを表す null で終わる文字列へのポインター。 指定されたセクションにエントリが存在しない場合は作成されます。 このパラメーターが NULL の場合、セクションが指定された*大文字、小文字*を削除します。  
  
 *lpszValue*  
 書き込まれる文字列を指します。 エントリがで指定されたこのパラメーターが NULL の場合、 *lpszEntry*パラメーターを削除します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]  
  
 別の例では、例を参照してください。[は](#getprofileint)します。  
  
##  <a name="setappid"></a>  CWinApp::SetAppID  
 アプリケーションのアプリケーション ユーザー モデル ID が明示的に設定します。 すべてのユーザー インターフェイスは、ユーザー (アプリケーションのコンス トラクターでは、最適な場所) に表示される前に、このメソッドを呼び出す必要があります。  
  
```  
void SetAppID(LPCTSTR lpcszAppID);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpcszAppID*  
 アプリケーション ユーザー モデル ID を指定します  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [CWinThread クラス](../../mfc/reference/cwinthread-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)



