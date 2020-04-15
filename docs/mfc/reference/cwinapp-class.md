---
title: CWinApp クラス
ms.date: 07/15/2019
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
ms.openlocfilehash: 946de5768829330f84b826a1fc9b2f6278847357
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366829"
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
|[::ドッカテンプレート](#adddoctemplate)|アプリケーションの使用可能なドキュメント テンプレートの一覧にドキュメント テンプレートを追加します。|
|[一覧に追加します。](#addtorecentfilelist)|最近使用した (MRU) ファイルリストにファイル名を追加します。|
|[::アプリケーション回復コールバック](#applicationrecoverycallback)|アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。|
|[CWinApp::すべてのドキュメントを閉じる](#closealldocuments)|開いているすべてのドキュメントを閉じます。|
|[::プリンタDCの作成](#createprinterdc)|プリンターデバイス コンテキストを作成します。|
|[CWinApp::Dエルレグツリー](#delregtree)|指定したキーとそのすべてのサブキーを削除します。|
|[CWinApp::Doメッセージボックス](#domessagebox)|アプリケーションの[Afx メッセージ ボックス](cstring-formatting-and-message-box-display.md#afxmessagebox)を実装します。|
|[クウィナップ::Dウェイトカーソル](#dowaitcursor)|待機カーソルのオン/オフを切り替えます。|
|[CWinApp::有効化D2Dサポート](#enabled2dsupport)|アプリケーション D2D のサポートを有効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|
|[::有効なHtmlヘルプ](#enablehtmlhelp)|WinHelp ではなく、アプリケーションの HTML ヘルプを実装します。|
|[CWinApp::タスクバーインタラクションを有効にする](#enabletaskbarinteraction)|タスク バーの操作を有効にします。|
|[::インスタンスの終了](#exitinstance)|アプリケーションが終了したときにクリーンアップするようにオーバーライドします。|
|[を指定します。](#getapplicationrecoveryparameter)|アプリケーションの回復方法の入力パラメーターを取得します。|
|[アプリケーションの回復の間隔を取得します。](#getapplicationrecoverypinginterval)|再起動マネージャーが回復コールバック関数が戻るのを待機する時間の長さを返します。|
|[::アプリケーション再起動フラグを取得します。](#getapplicationrestartflags)|再起動マネージャーのフラグを返します。|
|[::ゲットアップレジストリキー](#getappregistrykey)|"ソフトウェア"\\\レジストリ キー\プロファイル名HKEY_CURRENT_USERキーを返します。|
|[::データ回復ハンドラー](#getdatarecoveryhandler)|アプリケーションのこのインスタンスのデータ回復ハンドラーを取得します。|
|[::最初のテンプレートの位置](#getfirstdoctemplateposition)|最初のドキュメント テンプレートの位置を取得します。|
|[::ヘルプモードを取得します。](#gethelpmode)|アプリケーションで使用されるヘルプの種類を取得します。|
|[::次のテンプレート](#getnextdoctemplate)|ドキュメント テンプレートの位置を取得します。 再帰的に使用できます。|
|[::プリンタデバイスのデフォルトを取得します。](#getprinterdevicedefaults)|プリンター デバイスの既定値を取得します。|
|[::ゲットプロファイルバイナリ](#getprofilebinary)|アプリケーションの エントリからバイナリ データを取得します。INI ファイル。|
|[::ゲットプロファイルイント](#getprofileint)|アプリケーションの エントリから整数を取得します。INI ファイル。|
|[::プロファイル文字列を取得します。](#getprofilestring)|アプリケーションの エントリから文字列を取得します。INI ファイル。|
|[::ゲットセクションキー](#getsectionkey)|"ソフトウェア"\\\レジストリキー\アプリ名\lpszセクションHKEY_CURRENT_USERのキーを返します。|
|[アプリケーションを非表示にします。](#hideapplication)|すべてのドキュメントを閉じる前にアプリケーションを非表示にします。|
|[次のヘルプ](#htmlhelp)|Windows`HTMLHelp`関数を呼び出します。|
|[::イニトインスタンス](#initinstance)|ウィンドウ オブジェクトの作成など、Windows インスタンスの初期化を実行する場合にオーバーライドします。|
|[CWinApp::Isタスクバーインタラクションが有効になっています](#istaskbarinteractionenabled)|Windows 7 タスク バーの操作が有効になっているかどうかを示します。|
|[::ロードカーソル](#loadcursor)|カーソル リソースを読み込みます。|
|[CWinApp::ロードアイコン](#loadicon)|アイコン リソースを読み込みます。|
|[::ロードオームカーソル](#loadoemcursor)|**OCR_** 定数が WINDOWS で指定する Windows OEM の定義済みカーソルを読み込みます。H。|
|[::ロードOEMアイコン](#loadoemicon)|**OIC_** 定数が WINDOWS で指定する Windows OEM の定義済みアイコンを読み込みます。H。|
|[::ロードスタンダードカーソル](#loadstandardcursor)|**IDC_** 定数が WINDOWS で指定する Windows 定義済みカーソルを読み込みます。H。|
|[::ロードスタンダードアイコン](#loadstandardicon)|**IDI_** 定数が WINDOWS で指定する Windows の定義済みアイコンを読み込みます。H。|
|[CWinApp::オンドデコマンド](#onddecommand)|動的データ交換 (DDE) 実行コマンドに応答してフレームワークによって呼び出されます。|
|[CWinApp::オンアイドル](#onidle)|アプリケーション固有のアイドル時間処理を実行する場合にオーバーライドします。|
|[ファイルを開く](#opendocumentfile)|ファイルからドキュメントを開くために、フレームワークによって呼び出されます。|
|[CWinApp::Pアルセコマンドライン](#parsecommandline)|コマンド ラインで個々のパラメーターとフラグを解析します。|
|[メッセージを:P](#pretranslatemessage)|メッセージが Windows[関数に](/windows/win32/api/winuser/nf-winuser-translatemessage)ディスパッチされる前にフィルター処理されます[。](/windows/win32/api/winuser/nf-winuser-dispatchmessage)|
|[CWinApp::Pロセスメッセージフィルタ](#processmessagefilter)|特定のメッセージがアプリケーションに到達する前にインターセプトします。|
|[CWinApp::Pロセスシェルコマンド](#processshellcommand)|コマンド ライン引数とフラグを処理します。|
|[:Pロセスウンドプロセッサ例外](#processwndprocexception)|アプリケーションのメッセージおよびコマンド ハンドラーによってスローされた、未処理の例外をすべてインターセプトします。|
|[CWinApp::登録](#register)|カスタマイズされた登録を実行します。|
|[::登録と再起動マネージャー](#registerwithrestartmanager)|再起動マネージャーにアプリケーションを登録します。|
|[CWinApp::再オープン前のファイルアットリスタート](#reopenpreviousfilesatrestart)|アプリケーションが予期せず終了したときに開いていたファイルを再起動マネージャーが再び開くかどうかを決定します。|
|[を使用します。](#restartinstance)|再起動マネージャーによって開始されたアプリケーションの再起動を処理します。|
|[CWinApp::復元自動保存ファイルアットスタート](#restoreautosavedfilesatrestart)|アプリケーションを再起動したときに、自動保存されたファイルを再起動マネージャーが復元するかどうかを決定します。|
|[CWinApp::実行](#run)|既定のメッセージ ループを実行します。 メッセージ ループをカスタマイズする場合にオーバーライドします。|
|[CWinApp::自動実行](#runautomated)|**/Automation**オプションのアプリケーションのコマンド ラインをテストします。 互換性のために残されています。 代わりに、コマンド ラインを呼び出した後[、CCommandLineInfo::m_bRunAutomated](../../mfc/reference/ccommandlineinfo-class.md#m_brunautomated)の値[を](#parsecommandline)使用します。|
|[CWinApp::埋め込まれた実行](#runembedded)|**/Embedding**オプションのアプリケーションのコマンド ラインをテストします。 互換性のために残されています。 代わりに、コマンド ラインを呼び出した後[、CCommandLineInfo::m_bRunEmbedded](../../mfc/reference/ccommandlineinfo-class.md#m_brunembedded)の値[を](#parsecommandline)使用します。|
|[::セーブオールア修正](#saveallmodified)|変更されたすべてのドキュメントを保存するようにユーザーに求めます。|
|[CWinApp::選択プリンター](#selectprinter)|印刷ダイアログ ボックスでユーザーが以前に指定したプリンタを選択します。|
|[::セットヘルプモード](#sethelpmode)|アプリケーションで使用されるヘルプの種類を設定および初期化します。|
|[アプリケーションの回復をサポートします。](#supportsapplicationrecovery)|再起動マネージャーが、予期せず終了したアプリケーションを回復するかどうかを決定します。|
|[CWinApp::サポート自動保存間隔](#supportsautosaveatinterval)|再起動マネージャーが、開いているドキュメントを定期的に自動保存するかどうかを決定します。|
|[CWinApp::サポートオートセーブアットリスタート](#supportsautosaveatrestart)|アプリケーションの再起動時に、再起動マネージャーが開いているドキュメントを自動的に保存するかどうかを決定します。|
|[::サポートリスタートマネージャー](#supportsrestartmanager)|アプリケーションが再起動マネージャーをサポートするかどうかを決定します。|
|[CWinApp::登録解除](#unregister)|オブジェクトによって登録されていることがわかっているすべての登録を`CWinApp`解除します。|
|[CWinApp::ウィンヘルプ](#winhelp)|Windows`WinHelp`関数を呼び出します。|
|[::プロファイルバイナリを書き込みます](#writeprofilebinary)|バイナリ データをアプリケーションの エントリに書き込みます。INI ファイル。|
|[::プロファイルの書き込み](#writeprofileint)|アプリケーションの エントリに整数を書き込みます。INI ファイル。|
|[::プロファイル文字列を書き込みます](#writeprofilestring)|アプリケーションの エントリに文字列を書き込みます。INI ファイル。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CWinApp::有効にシェルオープン](#enableshellopen)|ユーザーが Windows ファイル マネージャーからデータ ファイルを開くことを許可します。|
|[設定を読み込む](#loadstdprofilesettings)|標準をロードします。INI ファイルの設定を有効にし、MRU ファイル リスト機能を有効にします。|
|[::オンコンテキストヘルプ](#oncontexthelp)|アプリケーション内で Shift + F1 ヘルプを処理します。|
|[CWinApp::オンファイルニュー](#onfilenew)|ID_FILE_NEW コマンドを実装します。|
|[ファイルを開く](#onfileopen)|ID_FILE_OPEN コマンドを実装します。|
|[ファイルプリントセットアップ](#onfileprintsetup)|ID_FILE_PRINT_SETUP コマンドを実装します。|
|[CWinApp::オンヘルプ](#onhelp)|アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。|
|[クウィナップ::オンヘルプファインダー](#onhelpfinder)|ID_HELP_FINDERおよびID_DEFAULT_HELPコマンドを処理します。|
|[::オンヘルプインデックス](#onhelpindex)|ID_HELP_INDEX コマンドを処理し、既定のヘルプ トピックを提供します。|
|[CWinApp::オンヘルプの使用](#onhelpusing)|ID_HELP_USING コマンドを処理します。|
|[次のファイルの種類を指定します。](#registershellfiletypes)|Windows ファイル マネージャーを使用して、アプリケーションのすべてのドキュメントの種類を登録します。|
|[::セットアプID](#setappid)|アプリケーションのアプリケーション ユーザー モデル ID を明示的に設定します。 このメソッドは、ユーザー インターフェイスがユーザーに提示される前に呼び出す必要があります (最適な場所はアプリケーション コンストラクターです)。|
|[::セットレジストリキー](#setregistrykey)|アプリケーションの設定を レジストリではなくに格納します。INI ファイル。|
|[CWinApp::ファイルの種類を登録解除します。](#unregistershellfiletypes)|Windows ファイル マネージャーを使用して、アプリケーションのすべてのドキュメントの種類の登録を解除します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CWinApp::m_bHelpMode](#m_bhelpmode)|ユーザーがヘルプ コンテキスト モード (通常は Shift + F1 で起動) かどうかを示します。|
|[CWinApp::m_eHelpType](#m_ehelptype)|アプリケーションで使用されるヘルプの種類を指定します。|
|[CWinApp::m_hInstance](#m_hinstance)|アプリケーションの現在のインスタンスを識別します。|
|[CWinApp::m_lpCmdLine](#m_lpcmdline)|アプリケーションのコマンド ラインを指定する null で終わる文字列を指します。|
|[CWinApp::m_nCmdShow](#m_ncmdshow)|ウィンドウを最初に表示する方法を指定します。|
|[CWinApp::m_pActiveWnd](#m_pactivewnd)|OLE サーバーが埋め込み場所でアクティブな場合のコンテナー アプリケーションのメイン ウィンドウへのポインター。|
|[CWinApp::m_pszAppID](#m_pszappid)|アプリケーション ユーザー モデル ID。|
|[CWinApp::m_pszAppName](#m_pszappname)|アプリケーションの名前を指定します。|
|[CWinApp::m_pszExeName](#m_pszexename)|アプリケーションのモジュール名。|
|[CWinApp::m_pszHelpFilePath](#m_pszhelpfilepath)|アプリケーションのヘルプ ファイルへのパス。|
|[CWinApp::m_pszProfileName](#m_pszprofilename)|アプリケーションの .INI ファイル名。|
|[CWinApp::m_pszRegistryKey](#m_pszregistrykey)|アプリケーション プロファイルの設定を格納するための完全なレジストリ キーを決定するために使用します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CWinApp::m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags)|再起動マネージャーの動作を決定するフラグ。|
|[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)|自動保存の間隔 (ミリ秒単位)。|
|[CWinApp::m_pDataRecoveryHandler](#m_pdatarecoveryhandler)|アプリケーションのデータ回復ハンドラーへのポインター。|

## <a name="remarks"></a>解説

アプリケーション オブジェクトは、アプリケーション (およびアプリケーションの各インスタンス) を初期化し、アプリケーションを実行するためのメンバー関数を提供します。

Microsoft Foundation クラスを使用する各アプリケーションには、 から`CWinApp`派生したオブジェクトを 1 つだけ含めることができます。 このオブジェクトは、他の C++ グローバル オブジェクトが構築されるときに構築され、Windows`WinMain`が関数を呼び出すときに既に使用できます。 派生`CWinApp`オブジェクトをグローバル レベルで宣言します。

から`CWinApp`アプリケーション クラスを派生させる場合は[、InitInstance](#initinstance)メンバー関数をオーバーライドして、アプリケーションのメイン ウィンドウ オブジェクトを作成します。

`CWinApp`メンバ関数に加えて、Microsoft Foundation クラス ライブラリには、オブジェクトおよびその他のグローバル`CWinApp`情報にアクセスするための次のグローバル関数が用意されています。

- [AfxGetApp](application-information-and-management.md#afxgetapp)オブジェクトへのポインターを`CWinApp`取得します。

- [ハンドル](application-information-and-management.md#afxgetinstancehandle)現在のアプリケーション インスタンスへのハンドルを取得します。

- [ハンドルを取得します。](application-information-and-management.md#afxgetresourcehandle)アプリケーションのリソースへのハンドルを取得します。

- [アfxゲットアプリ名](application-information-and-management.md#afxgetappname)アプリケーション名を含む文字列へのポインターを取得します。 または、`CWinApp`オブジェクトへのポインターがある場合は、 を使用`m_pszExeName`してアプリケーションの名前を取得します。

次の概要を含む`CWinApp`、クラスの詳細については[、「CWinApp: アプリケーション クラス](../../mfc/cwinapp-the-application-class.md)」を参照してください。

- `CWinApp`-アプリケーション ウィザードによって作成された派生コード。

- `CWinApp`アプリケーションの実行シーケンスにおける 's の役割。

- `CWinApp`の既定のメンバー関数の実装。

- `CWinApp`のキーオーバーライド可能。

データ`m_hPrevInstance`メンバーは存在しません。 アプリケーションの別のインスタンスが実行されているかどうかを確認するには、名前付きミューテックスを使用します。 ミューテックスを開くのに失敗した場合、実行中のアプリケーションの他のインスタンスはありません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

`CWinApp`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cwinappadddoctemplate"></a><a name="adddoctemplate"></a>::ドッカテンプレート

アプリケーションが管理する使用可能なドキュメント テンプレートの一覧にドキュメント テンプレートを追加します。

```
void AddDocTemplate(CDocTemplate* pTemplate);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
追加するを`CDocTemplate`指すポインター。

### <a name="remarks"></a>解説

を呼び出す前に、すべてのドキュメント テンプレートをアプリケーションに追加[する必要があります](#registershellfiletypes)。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#35](../../mfc/reference/codesnippet/cpp/cwinapp-class_1.cpp)]

## <a name="cwinappaddtorecentfilelist"></a><a name="addtorecentfilelist"></a>一覧に追加します。

このメンバー関数を呼び出して *、LPSzPathName*を MRU ファイル リストに追加します。

```
virtual void AddToRecentFileList(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>パラメーター

*パス名*<br/>
ファイルのパス。

### <a name="remarks"></a>解説

このメンバー関数を使用する前に[、LoadStdProfileSettings](#loadstdprofilesettings)メンバー関数を呼び出して、現在の MRU ファイル リストを読み込む必要があります。

フレームワークは、ファイルを開くとき、または新しい名前でファイルを保存する名前を付けて保存コマンドを実行するときに、このメンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#36](../../mfc/reference/codesnippet/cpp/cwinapp-class_2.cpp)]

## <a name="cwinappapplicationrecoverycallback"></a><a name="applicationrecoverycallback"></a>::アプリケーション回復コールバック

アプリケーションが予期せず終了したときに、フレームワークによって呼び出されます。

```
virtual DWORD ApplicationRecoveryCallback(LPVOID lpvParam);
```

### <a name="parameters"></a>パラメーター

*lpvパラム*<br/>
[in]将来の使用のために予約されています。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は 0。エラーが発生した場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

アプリケーションが再起動マネージャーをサポートしている場合、アプリケーションが予期せず終了したときに、フレームワークはこの関数を呼び出します。

の既定の`ApplicationRecoveryCallback`実装では、`CDataRecoveryHandler`を使用して現在開いているドキュメントの一覧をレジストリに保存します。 このメソッドは、ファイルを自動保存しません。

動作をカスタマイズするには、派生[CWinApp クラス](../../mfc/reference/cwinapp-class.md)でこの関数をオーバーライドするか、独自のアプリケーション回復メソッドをパラメーターとして[CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)に渡します。

## <a name="cwinappclosealldocuments"></a><a name="closealldocuments"></a>CWinApp::すべてのドキュメントを閉じる

このメンバー関数を呼び出して、開いているすべてのドキュメントを閉じてから終了します。

```
void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>パラメーター

*セッション*<br/>
Windows セッションを終了するかどうかを指定します。 セッションが終了している場合は TRUE です。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

を呼び出す`CloseAllDocuments`前に[HideApplication](#hideapplication)を呼び出します。

## <a name="cwinappcreateprinterdc"></a><a name="createprinterdc"></a>::プリンタDCの作成

選択したプリンターからプリンターデバイス コンテキスト (DC) を作成します。

```
BOOL CreatePrinterDC(CDC& dc);
```

### <a name="parameters"></a>パラメーター

*Dc*<br/>
プリンターデバイス コンテキストへの参照。

### <a name="return-value"></a>戻り値

プリンターデバイスコンテキストが正常に作成された場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

`CreatePrinterDC`は、参照渡しで渡すデバイス コンテキストを初期化するため、これを使用して印刷できます。

関数が正常に実行された場合は、印刷が終了したら、デバイス コンテキストを破棄する必要があります。 [CDC](../../mfc/reference/cdc-class.md)オブジェクトのデストラクターに実行させるか[、CDC::DeleteDC](../../mfc/reference/cdc-class.md#deletedc)を呼び出して明示的に実行できます。

## <a name="cwinappcwinapp"></a><a name="cwinapp"></a>CWinApp::CWinApp

オブジェクトを`CWinApp`構築し、lpszAppName を渡してアプリケーション名として格納します。 *lpszAppName*

```
CWinApp(LPCTSTR lpszAppName = NULL);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
Windows が使用するアプリケーション名を含む null で終わる文字列。 この引数が指定されていないか NULL の`CWinApp`場合は、リソース文字列AFX_IDS_APP_TITLE、または実行可能ファイルのファイル名を使用します。

### <a name="remarks"></a>解説

派生クラスのグローバル オブジェクトを`CWinApp`1 つ作成する必要があります。 アプリケーション内に持つことができる`CWinApp`オブジェクトは 1 つだけです。 コンストラクターは、オブジェクトへのポインターを`CWinApp`格納して、`WinMain`オブジェクトのメンバー関数を呼び出してアプリケーションを初期化および実行できるようにします。

## <a name="cwinappdelregtree"></a><a name="delregtree"></a>CWinApp::Dエルレグツリー

特定のレジストリ キーとそのすべてのサブキーを削除します。

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

*キー*<br/>
レジストリ キーへのハンドル。

*ストレーナ*<br/>
削除するレジストリ キーの名前。

*Ptm*<br/>
オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合、戻り値はERROR_SUCCESS。 関数が失敗した場合、戻り値は Winerror.h で定義された 0 以外のエラー コードです。

### <a name="remarks"></a>解説

指定したキーとそのサブキーを削除します。

## <a name="cwinappdomessagebox"></a><a name="domessagebox"></a>CWinApp::Doメッセージボックス

フレームワークは、グローバル関数[AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)のメッセージ ボックスを実装するために、このメンバー関数を呼び出します。

```
virtual int DoMessageBox(
    LPCTSTR lpszPrompt,
    UINT nType,
    UINT nIDPrompt);
```

### <a name="parameters"></a>パラメーター

*プロンプトを表示します。*<br/>
メッセージ ボックス内のテキストのアドレスです。

*nType*<br/>
メッセージ ボックス[のスタイル](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)。

*プロンプトを表示します。*<br/>
ヘルプ コンテキスト文字列へのインデックス。

### <a name="return-value"></a>戻り値

と同じ値を`AfxMessageBox`返します。

### <a name="remarks"></a>解説

メッセージ ボックスを開くには、このメンバー関数を呼び出しません。代`AfxMessageBox`わりに使用します。

アプリケーション全体の呼び出し処理をカスタマイズするには、`AfxMessageBox`このメンバー関数をオーバーライドします。

## <a name="cwinappdowaitcursor"></a><a name="dowaitcursor"></a>クウィナップ::Dウェイトカーソル

このメンバー関数は、フレームワークによって呼び出され[、CWaitCursor](../../mfc/reference/cwaitcursor-class.md) [、CCmdTarget::BeginWaitCursor、CCmdTarget::](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)[エンドウェイトカーソル](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)、および[CCmdTarget::復元待ちカーソル](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)を実装します。

```
virtual void DoWaitCursor(int nCode);
```

### <a name="parameters"></a>パラメーター

*nコード*<br/>
このパラメーターが 1 の場合は、待機カーソルが表示されます。 0 の場合、待機カーソルは参照カウントをインクリメントせずに復元されます。 1 の場合、待機カーソルは終了します。

### <a name="remarks"></a>解説

既定では、砂時計カーソルを実装します。 `DoWaitCursor`は、参照カウントを維持します。 正の場合、砂時計カーソルが表示されます。

通常は直接呼び出`DoWaitCursor`さないかもしれませんが、待機カーソルを変更したり、待機カーソルが表示されている間に追加の処理を行ったりするために、このメンバー関数をオーバーライドできます。

待機カーソルを実装する、より簡単で合理化された方法を使用`CWaitCursor`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#37](../../mfc/reference/codesnippet/cpp/cwinapp-class_3.cpp)]

## <a name="cwinappenabled2dsupport"></a><a name="enabled2dsupport"></a>CWinApp::有効化D2Dサポート

Visual Studio 2010 SP1 が必要です。

アプリケーション D2D のサポートを有効にします。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。

```
BOOL EnableD2DSupport(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>パラメーター

*d2dファクトリータイプ*<br/>
D2D ファクトリのスレッド モデルと、それが作成するリソース。

*書き込みファクトリタイプ*<br/>
書き込みファクトリ オブジェクトを共有するか分離するかを指定する値。

### <a name="return-value"></a>戻り値

D2D サポートが有効になっている場合は TRUE を返します。

## <a name="cwinappenablehtmlhelp"></a><a name="enablehtmlhelp"></a>::有効なHtmlヘルプ

アプリケーションのヘルプに HTMLHelp を`CWinApp`使用するには、派生クラスのコンストラクター内からこのメンバー関数を呼び出します。

```
void EnableHtmlHelp();
```

### <a name="remarks"></a>解説

## <a name="cwinappenableshellopen"></a><a name="enableshellopen"></a>CWinApp::有効にシェルオープン

通常は、この関数を`InitInstance`呼び出して、アプリケーションのユーザーが Windows ファイル マネージャー内でファイルをダブルクリックしたときにデータ ファイルを開くようにします。

```
void EnableShellOpen();
```

### <a name="remarks"></a>解説

この関数`RegisterShellFileTypes`と共にメンバー関数を呼び出すか、 を指定します。REGファイルは、ドキュメントタイプの手動登録のためのあなたのアプリケーションと一緒に。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#38](../../mfc/reference/codesnippet/cpp/cwinapp-class_4.cpp)]

## <a name="cwinappenabletaskbarinteraction"></a><a name="enabletaskbarinteraction"></a>CWinApp::タスクバーインタラクションを有効にする

タスク バーの操作を有効にします。

```
BOOL EnableTaskbarInteraction(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
Windows 7 タスク バーとの対話を有効にする (TRUE)、無効 (FALSE) を指定します。

### <a name="return-value"></a>戻り値

タスク バーの操作を有効または無効にできる場合は TRUE を返します。

### <a name="remarks"></a>解説

このメソッドは、メイン ウィンドウを作成する前に呼び出す必要があります。

## <a name="cwinappexitinstance"></a><a name="exitinstance"></a>::インスタンスの終了

アプリケーションのこのインスタンスを終了するために`Run`、メンバー関数内からフレームワークによって呼び出されます。

```
virtual int ExitInstance();
```

### <a name="return-value"></a>戻り値

アプリケーションの終了コード。0 はエラーがないことを示し、0 より大きい値はエラーを示します。 この値は、 からの`WinMain`戻り値として使用されます。

### <a name="remarks"></a>解説

このメンバー関数は、`Run`メンバー関数以外の場所から呼び出す必要があります。

この関数の既定の実装では、フレームワーク オプションをアプリケーションの .INI ファイル。 アプリケーションが終了したときにクリーンアップするには、この関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#39](../../mfc/reference/codesnippet/cpp/cwinapp-class_5.cpp)]

## <a name="cwinappgetapplicationrecoveryparameter"></a><a name="getapplicationrecoveryparameter"></a>を指定します。

アプリケーションの回復方法の入力パラメーターを取得します。

```
virtual LPVOID GetApplicationRecoveryParameter();
```

### <a name="return-value"></a>戻り値

アプリケーションの回復方法の既定の入力パラメーター。

### <a name="remarks"></a>解説

この関数の既定の動作は NULL を返します。

詳細については[、「CWinApp::アプリケーション回復コールバック](#applicationrecoverycallback)」を参照してください。

## <a name="cwinappgetapplicationrecoverypinginterval"></a><a name="getapplicationrecoverypinginterval"></a>アプリケーションの回復の間隔を取得します。

再起動マネージャーが回復コールバック関数が戻るのを待機する時間の長さを返します。

```
virtual DWORD GetApplicationRecoveryPingInterval();
```

### <a name="return-value"></a>戻り値

ミリ秒単位の時間の長さ。

### <a name="remarks"></a>解説

再起動マネージャーに登録されているアプリケーションが予期せず終了すると、アプリケーションは開いているドキュメントを保存しようとし、回復コールバック関数を呼び出します。 既定の回復コールバック関数は[、CWinApp::アプリケーション回復コールバック](#applicationrecoverycallback)です。

フレームワークが回復コールバック関数が戻るのを待機する時間の長さは、ping 間隔です。 ping の間隔をカスタマイズするには、オーバーライド`CWinApp::GetApplicationRecoveryPingInterval`するか、カスタム値を に`RegisterWithRestartManager`指定します。

## <a name="cwinappgetapplicationrestartflags"></a><a name="getapplicationrestartflags"></a>::アプリケーション再起動フラグを取得します。

再起動マネージャーのフラグを返します。

```
virtual DWORD GetApplicationRestartFlags();
```

### <a name="return-value"></a>戻り値

再起動マネージャーのフラグ。 既定の実装では 0 が返されます。

### <a name="remarks"></a>解説

再起動マネージャーのフラグは、既定の実装では効果がありません。 これらは、将来の使用のために提供されています。

再起動マネージャーにアプリケーションを登録するときに[、CWinApp::RegisterWithRestartManager](#registerwithrestartmanager)を使用してフラグを設定します。

再起動マネージャーフラグの値は、次のとおりです。

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappgetappregistrykey"></a><a name="getappregistrykey"></a>::ゲットアップレジストリキー

"ソフトウェア"\レジストリ\\キー\プロファイル名HKEY_CURRENT_USERキーを返します。

```
HKEY GetAppRegistryKey(CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*Ptm*<br/>
`CAtlTransactionManager`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合はアプリケーションキー。それ以外の場合は NULL。

### <a name="remarks"></a>解説

## <a name="cwinappgetdatarecoveryhandler"></a><a name="getdatarecoveryhandler"></a>::データ回復ハンドラー

アプリケーションのこのインスタンスのデータ回復ハンドラーを取得します。

```
virtual CDataRecoveryHandler *GetDataRecoveryHandler();
```

### <a name="return-value"></a>戻り値

アプリケーションのこのインスタンスのデータ回復ハンドラー。

### <a name="remarks"></a>解説

再起動マネージャーを使用する各アプリケーションには[、 CDataRecoveryHandler クラス](../../mfc/reference/cdatarecoveryhandler-class.md)のインスタンスが 1 つ必要です。 このクラスは、開いているドキュメントの監視とファイルの自動保存を行います。 の`CDataRecoveryHandler`動作は、再起動マネージャーの構成によって異なります。 詳細については、「[クラス」](../../mfc/reference/cdatarecoveryhandler-class.md)を参照してください。

このメソッドは、Windows Vista より前のオペレーティング システムでは NULL を返します。 再起動マネージャーは、Windows Vista より前のオペレーティング システムではサポートされていません。

アプリケーションに現在データ回復ハンドラーがない場合、このメソッドは、データ回復ハンドラーを作成し、ポインターを返します。

## <a name="cwinappgetfirstdoctemplateposition"></a><a name="getfirstdoctemplateposition"></a>::最初のテンプレートの位置

アプリケーション内の最初のドキュメント テンプレートの位置を取得します。

```
POSITION GetFirstDocTemplatePosition() const;
```

### <a name="return-value"></a>戻り値

反復またはオブジェクト・ポインターの取得に使用できる POSITION 値。リストが空の場合は NULL。

### <a name="remarks"></a>解説

最初の[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトを[取得](#getnextdoctemplate)するには、呼び出しで返される POSITION 値を使用します。

## <a name="cwinappgethelpmode"></a><a name="gethelpmode"></a>::ヘルプモードを取得します。

アプリケーションで使用されるヘルプの種類を取得します。

```
AFX_HELP_TYPE GetHelpMode();
```

### <a name="return-value"></a>戻り値

アプリケーションで使用されるヘルプの種類。 詳細については[、CWinApp::m_eHelpType](#m_ehelptype)を参照してください。

## <a name="cwinappgetnextdoctemplate"></a><a name="getnextdoctemplate"></a>::次のテンプレート

*pos*で識別されるドキュメント テンプレートを取得し *、pos*を POSITION 値に設定します。

```
CDocTemplate* GetNextDocTemplate(POSITION& pos) const;
```

### <a name="parameters"></a>パラメーター

*pos*<br/>
以前の呼び出しまたは`GetNextDocTemplate`[GetFirstDocTemplatePosition](#getfirstdoctemplateposition)への呼び出しによって返される位置値への参照。 この呼び出しによって、値は次の位置に更新されます。

### <a name="return-value"></a>戻り値

[オブジェクトへの](../../mfc/reference/cdoctemplate-class.md)ポインター。

### <a name="remarks"></a>解説

の呼び`GetNextDocTemplate`出しで初期位置を確立する場合は、順方向反復ループ`GetFirstDocTemplatePosition`で使用できます。

POSITION 値が有効であることを確認する必要があります。 無効な場合は、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。

取得したドキュメント テンプレートが最後に使用可能な場合 *、pos*の新しい値は NULL に設定されます。

## <a name="cwinappgetprinterdevicedefaults"></a><a name="getprinterdevicedefaults"></a>::プリンタデバイスのデフォルトを取得します。

印刷用のプリンター デバイス コンテキストを準備します。

```
BOOL GetPrinterDeviceDefaults(struct tagPDA* pPrintDlg);
```

### <a name="parameters"></a>パラメーター

*pプリントドアルグ*<br/>
[PRINTDLG](/windows/win32/api/commdlg/ns-commdlg-printdlga)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

Windows から現在のプリンタの既定値を取得します。INI ファイルを必要に応じて、または印刷設定でユーザーが設定した最後のプリンタ構成を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#40](../../mfc/reference/codesnippet/cpp/cwinapp-class_6.cpp)]

## <a name="cwinappgetprofilebinary"></a><a name="getprofilebinary"></a>::ゲットプロファイルバイナリ

アプリケーションのレジストリまたはの指定したセクション内のエントリからバイナリ データを取得します。INI ファイル。

```
BOOL GetProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE* ppData,
    UINT* pBytes);
```

### <a name="parameters"></a>パラメーター

*セクション*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。

*をクリックします。*<br/>
値を取得するエントリを指定する NULL で終わる文字列へのポインター。

*Ppdata*<br/>
データのアドレスを受け取るポインターへのポインター。

*バイト数*<br/>
データのサイズ (バイト単位) を受け取る UINT へのポインタ。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数では大文字と小文字が区別されないので *、lpszSection*パラメーターと*lpszEntry*パラメーターの文字列は大文字と小文字が異なる場合があります。

> [!NOTE]
> `GetProfileBinary`バッファを割り当て、そのアドレス\*を*ppData*に返します。 呼び出し元は **、delete []** を使用してバッファを解放する必要があります。

> [!IMPORTANT]
> この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#41](../../mfc/reference/codesnippet/cpp/cwinapp-class_7.cpp)]

その他の例については[、「CWinApp::WriteProfileBinary」](#writeprofilebinary)を参照してください。

## <a name="cwinappgetprofileint"></a><a name="getprofileint"></a>::ゲットプロファイルイント

アプリケーションのレジストリまたは .INI ファイルの指定のセクション内のエントリから整数値を取得します。

```
UINT GetProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nDefault);
```

### <a name="parameters"></a>パラメーター

*セクション*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。

*をクリックします。*<br/>
値を取得するエントリを指定する NULL で終わる文字列へのポインター。

*nデフォルト*<br/>
フレームワークがエントリを見つけられなかったときのために指定する既定値。

### <a name="return-value"></a>戻り値

正常終了した場合は、指定されたエントリに続く文字列の整数値を返します。 関数がエントリを見つけられない場合、戻り値は*nDefault*パラメーターの値です。 指定されたエントリに対応する値が整数でない場合は、0 を返します。

このメンバー関数は .INI ファイル内の値として 16 進表記をサポートします。 符号付き整数を取得する場合は、その値を**int**にキャストする必要があります。

### <a name="remarks"></a>解説

このメンバー関数では大文字と小文字が区別されないので *、lpszSection*パラメーターと*lpszEntry*パラメーターの文字列は大文字と小文字が異なる場合があります。

> [!IMPORTANT]
> この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#42](../../mfc/reference/codesnippet/cpp/cwinapp-class_8.cpp)]

その他の例については[、「CWinApp::WriteProfileInt」を参照](#writeprofileint)してください。

## <a name="cwinappgetprofilestring"></a><a name="getprofilestring"></a>::プロファイル文字列を取得します。

アプリケーションのレジストリまたは内の指定したセクション内のエントリに関連付けられている文字列を取得します。INI ファイル。

```
CString GetProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszDefault = NULL);
```

### <a name="parameters"></a>パラメーター

*セクション*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。

*をクリックします。*<br/>
取得する文字列を含むエントリを含む null で終わる文字列へのポイント。 この値は NULL にできません。

*デフォルト*<br/>
指定されたエントリが初期化ファイルに見つからない場合は、そのエントリの既定の文字列値を指します。

### <a name="return-value"></a>戻り値

戻り値は、アプリケーションの .INI ファイルまたは*lpsz 文字列*が見つからない場合は、デフォルトです。 フレームワークでサポートされる文字列の最大長は_MAX_PATH。 *lpszDefault*が NULL の場合、戻り値は空の文字列です。

### <a name="remarks"></a>解説

> [!IMPORTANT]
> この関数が返すデータは、NULL で終わるデータとは限らないため、呼び出し元で検証を行う必要があります。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

別の例については[、CWinApp::GetProfileInt](#getprofileint)の例を参照してください。

## <a name="cwinappgetsectionkey"></a><a name="getsectionkey"></a>::ゲットセクションキー

"ソフトウェア"\レジストリ\\キー\アプリケーション名\lpszセクションHKEY_CURRENT_USERキーを返します。

```
HKEY GetSectionKey(
    LPCTSTR lpszSection,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>パラメーター

*セクション*<br/>
取得するキーの名前。

*Ptm*<br/>
`CAtlTransactionManager`オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合はセクション キー。それ以外の場合は NULL。

### <a name="remarks"></a>解説

## <a name="cwinapphideapplication"></a><a name="hideapplication"></a>アプリケーションを非表示にします。

開いているドキュメントを閉じる前にアプリケーションを非表示にします。

```
void HideApplication();
```

## <a name="cwinapphtmlhelp"></a><a name="htmlhelp"></a>次のヘルプ

HTMLHelp アプリケーションを呼び出します。

```
virtual void HtmlHelp(
    DWORD_PTR dwData,
    UINT nCmd = 0x000F);
```

### <a name="parameters"></a>パラメーター

*dw データ*<br/>
追加データを指定します。 使用される値は *、nCmd*パラメーターの値によって異なります。 既定値は、 `0x000F` [HH_HELP_CONTEXT](/previous-versions/windows/desktop/htmlhelp/hh-help-context-command)を意味します。

*nCmd*<br/>
要求されるヘルプの種類を指定します。 考えられる値の一覧と、それらが*dwData*パラメーターに与える影響については、Windows SDK の[HtmlHelpW](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpw)または[HtmlHelpA](/windows/win32/api/htmlhelp/nf-htmlhelp-htmlhelpa) API 関数で説明されている*uCommand*パラメーターを参照してください。

### <a name="remarks"></a>解説

フレームワークは、HTMLHelp アプリケーションを呼び出すためにもこの関数を呼び出します。

フレームワークは、アプリケーションが終了すると、HTMLHelp アプリケーションを自動的に閉じます。

## <a name="cwinappinitinstance"></a><a name="initinstance"></a>::イニトインスタンス

Windows では、同じプログラムの複数のコピーを同時に実行できます。

```
virtual BOOL InitInstance();
```

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

アプリケーションの初期化は、概念的には、プログラムの初回実行時に実行されるアプリケーションの 1 回限りの初期化と、プログラムのコピーが実行されるたびに実行されるインスタンス初期化 (最初の時刻を含む) の 2 つのセクションに分けられます。 フレームワークの実装はこの関数を`WinMain`呼び出します。

Windows`InitInstance`で実行されているアプリケーションの新しいインスタンスを初期化する場合にオーバーライドします。 通常は、メイン`InitInstance`ウィンドウ オブジェクトを構築するためにオーバーライドし`CWinThread::m_pMainWnd`、そのウィンドウを指すデータ メンバーを設定します。 このメンバー関数のオーバーライドの詳細については、「 [CWinApp: アプリケーション クラス](../../mfc/cwinapp-the-application-class.md)」を参照してください。

> [!NOTE]
> MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 オーバーライドで[CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex)を`InitInstance`呼び出す場合は、COINIT_MULTITHREADEDではなくCOINIT_APARTMENTTHREADEDを指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCListView#9](../../atl/reference/codesnippet/cpp/cwinapp-class_10.cpp)]

## <a name="cwinappistaskbarinteractionenabled"></a><a name="istaskbarinteractionenabled"></a>CWinApp::Isタスクバーインタラクションが有効になっています

Windows 7 タスク バーの操作が有効になっているかどうかを示します。

```
virtual BOOL IsTaskbarInteractionEnabled();
```

### <a name="return-value"></a>戻り値

呼び出`EnableTaskbarInteraction`され、オペレーティング システムが Windows 7 以上の場合は TRUE を返します。

### <a name="remarks"></a>解説

タスク バーの操作とは、MDI アプリケーションが、マウス ポインターがアプリケーションのタスク バー ボタンの上にあるときに表示されるタブ付きサムネイルに MDI 子の内容を表示することを意味します。

## <a name="cwinapploadcursor"></a><a name="loadcursor"></a>::ロードカーソル

*lpszResourceName*で指定されたカーソル リソースを、現在の実行可能ファイルから*nIDResource*で指定されたカーソル リソースを読み込みます。

```
HCURSOR LoadCursor(LPCTSTR lpszResourceName) const;  HCURSOR LoadCursor(UINT nIDResource) const;
```

### <a name="parameters"></a>パラメーター

*リソース名*<br/>
カーソル リソースの名前を含む null で終わる文字列を指します。 この引数には`CString`を使用できます。

*リソース*<br/>
カーソル リソースの ID。 リソースの一覧については、Windows SDK の[「ロード カーソル](/windows/win32/api/winuser/nf-winuser-loadcursorw)」を参照してください。

### <a name="return-value"></a>戻り値

成功した場合はカーソルへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`LoadCursor`カーソルが以前に読み込まれていない場合にのみ、カーソルをメモリにロードします。それ以外の場合は、既存のリソースのハンドルを取得します。

定義済みの[LoadStandardCursor](#loadstandardcursor)Windows[カーソル](#loadoemcursor)にアクセスするには、関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#44](../../mfc/reference/codesnippet/cpp/cwinapp-class_11.cpp)]

## <a name="cwinapploadicon"></a><a name="loadicon"></a>CWinApp::ロードアイコン

*lpszResourceName*で指定されたアイコン リソースを、または*nIDResource*によって指定された実行可能ファイルから読み込みます。

```
HICON LoadIcon(LPCTSTR lpszResourceName) const;  HICON LoadIcon(UINT nIDResource) const;
```

### <a name="parameters"></a>パラメーター

*リソース名*<br/>
アイコン リソースの名前を含む null で終わる文字列を指します。 この引数には を`CString`使用することもできます。

*リソース*<br/>
アイコン リソースの ID 番号です。

### <a name="return-value"></a>戻り値

成功した場合はアイコンへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`LoadIcon`アイコンが以前に読み込まれていない場合にのみ、アイコンを読み込みます。それ以外の場合は、既存のリソースのハンドルを取得します。

[定義済みの](#loadstandardicon)Windows アイコンにアクセス[LoadOEMIcon](#loadoemicon)するには、関数を使用します。

> [!NOTE]
> このメンバー関数は、SM_CXICONに準拠するアイコンとシステム メトリック値SM_CYICONを読み込むことのできる Win32 API 関数[LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)を呼び出します。

## <a name="cwinapploadoemcursor"></a><a name="loadoemcursor"></a>::ロードオームカーソル

*nIDCursor*で指定された Windows の定義済みカーソル リソースを読み込みます。

```
HCURSOR LoadOEMCursor(UINT nIDCursor) const;
```

### <a name="parameters"></a>パラメーター

*カーソルを持つ*<br/>
定義済みの Windows カーソルを指定する**OCR_** マニフェスト定数識別子。 windows の`#define OEMRESOURCE`OCR_`#include \<afxwin.h>`定数にアクセスするには、**OCR_** あらかじめ必要です。H。

### <a name="return-value"></a>戻り値

成功した場合はカーソルへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`LoadOEMCursor`または、定義済みの Windows カーソルにアクセスするには、または[LoadStandardCursor](#loadstandardcursor)メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#45](../../mfc/reference/codesnippet/cpp/cwinapp-class_12.h)]

[!code-cpp[NVC_MFCWindowing#46](../../mfc/reference/codesnippet/cpp/cwinapp-class_13.cpp)]

## <a name="cwinapploadoemicon"></a><a name="loadoemicon"></a>::ロードOEMアイコン

*nIDIcon*で指定された Windows の定義済みアイコン リソースを読み込みます。

```
HICON LoadOEMIcon(UINT nIDIcon) const;
```

### <a name="parameters"></a>パラメーター

*nIDアイコン*<br/>
定義済**みの**Windows アイコンを指定するマニフェスト定数のOIC_識別子。 windows の`#define OEMRESOURCE`OIC_`#include \<afxwin.h>`定数にアクセス**OIC_** する前に持っている必要があります。H。

### <a name="return-value"></a>戻り値

成功した場合はアイコンへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`LoadOEMIcon`または、定義済みの Windows アイコンにアクセスするには、または[LoadStandardIcon](#loadstandardicon)メンバー関数を使用します。

## <a name="cwinapploadstandardcursor"></a><a name="loadstandardcursor"></a>::ロードスタンダードカーソル

*lpszCursorName*が指定する Windows の定義済みカーソル リソースを読み込みます。

```
HCURSOR LoadStandardCursor(LPCTSTR lpszCursorName) const;
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
定義済みの Windows カーソルを指定する**IDC_** マニフェスト定数識別子。 これらの識別子は、WINDOWS で定義されます。H。 次のリストは *、lpszCursorName*の定義済みの値と意味を示しています。

- 標準矢印カーソルIDC_ARROW

- 標準テキスト挿入カーソルをIDC_IBEAM

- Windows IDC_WAIT時間のかかるタスクを実行するときに使用される砂時計カーソル

- 選択用のクロスヘア カーソルをIDC_CROSS

- IDC_UPARROW矢印はまっすぐ上を向く

- IDC_SIZE 廃止され、サポートされていません。IDC_SIZEALLを使用する

- IDC_SIZEALL 4 つの矢印。 ウィンドウのサイズを変更するために使用するカーソル。

- IDC_ICON 廃止され、サポートされていません。 IDC_ARROWを使用します。

- IDC_SIZENWSE左上と右下に端点がある二方向矢印

- IDC_SIZENESW右上と左下に端点がある二方向矢印

- IDC_SIZEWE横向き矢印

- IDC_SIZENS縦向き矢印

### <a name="return-value"></a>戻り値

成功した場合はカーソルへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

`LoadStandardCursor`または、または[LoadOEMCursor](#loadoemcursor)メンバー関数を使用して、定義済みの Windows カーソルにアクセスします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#47](../../mfc/reference/codesnippet/cpp/cwinapp-class_14.cpp)]

## <a name="cwinapploadstandardicon"></a><a name="loadstandardicon"></a>::ロードスタンダードアイコン

*lpszIconName*が指定する Windows の定義済みのアイコン リソースを読み込みます。

```
HICON LoadStandardIcon(LPCTSTR lpszIconName) const;
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
定義済みの Windows アイコンを指定するマニフェスト定数識別子。 これらの識別子は、WINDOWS で定義されます。H。 使用できる定義済みの値とその説明の一覧については、Windows SDK の LoadIcon の*lpIconName*パラメーターを参照してください。 [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)

### <a name="return-value"></a>戻り値

成功した場合はアイコンへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

または`LoadStandardIcon`[LoadOEMIcon](#loadoemicon)メンバー関数を使用して、定義済みの Windows アイコンにアクセスします。

## <a name="cwinapploadstdprofilesettings"></a><a name="loadstdprofilesettings"></a>設定を読み込む

[InitInstance](#initinstance)メンバー関数内からこのメンバー関数を呼び出して、最近使用した (MRU) ファイルと最後のプレビュー状態の一覧を有効にして読み込みます。

```
void LoadStdProfileSettings(UINT nMaxMRU = _AFX_MRU_COUNT);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
追跡する最近使用したファイルの数。

### <a name="remarks"></a>解説

*nMaxMRU*が 0 の場合、MRU リストは保持されません。

## <a name="cwinappm_bhelpmode"></a><a name="m_bhelpmode"></a>CWinApp::m_bHelpMode

アプリケーションがヘルプ コンテキスト モード (従来は SHIFT + F1 で呼び出される) の場合は TRUE。それ以外の場合は FALSE。

```
BOOL m_bHelpMode;
```

### <a name="remarks"></a>解説

ヘルプ コンテキスト モードでは、カーソルが疑問符になり、ユーザーは画面を移動できます。 ヘルプ モードで特別な処理を実装する場合は、このフラグを確認します。 `m_bHelpMode`は、BOOL 型のパブリック変数です。

## <a name="cwinappm_dwrestartmanagersupportflags"></a><a name="m_dwrestartmanagersupportflags"></a>CWinApp::m_dwRestartManagerSupportFlags

再起動マネージャーの動作を決定するフラグ。

```
DWORD m_dwRestartManagerSupportFlags;
```

### <a name="remarks"></a>解説

再起動マネージャーを有効にするには、目的`m_dwRestartManagerSupportFlags`の動作を設定します。 次の表は、使用可能なフラグを示しています。

|||
|-|-|
|フラグ|説明|
|AFX_RESTART_MANAGER_SUPPORT_RESTART|アプリケーションは[、CWinApp::レジスタを使用して登録されます](#registerwithrestartmanager)。 再起動マネージャーは、アプリケーションが予期せず終了した場合に、アプリケーションを再起動する必要があります。|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY|アプリケーションは再起動マネージャーに登録され、再起動マネージャーは、アプリケーションを再起動するときに、回復コールバック関数を呼び出します。 既定の回復コールバック関数は[、CWinApp::アプリケーション回復コールバック](#applicationrecoverycallback)です。|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART|自動保存が有効になり、アプリケーションの再起動時に、再起動マネージャが開いているドキュメントを自動的に保存します。|
|- AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL|自動保存が有効になり、再起動マネージャは、開いているドキュメントを一定の間隔で自動保存します。 間隔は[CWinApp::m_nAutosaveInterval](#m_nautosaveinterval)によって定義されます。|
|- AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES|再起動マネージャーは、予期しない終了からアプリケーションを再起動した後、以前に開いているドキュメントを開きます。 [クラス](../../mfc/reference/cdatarecoveryhandler-class.md)は、開いているドキュメントのリストを格納し、それらを復元します。|
|- AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES|再起動マネージャーは、アプリケーションを再起動した後に、自動保存されたファイルを復元するようにユーザーに求めます。 クラス`CDataRecoveryHandler`はユーザーにクエリを実行します。|
|- AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE|AFX_RESTART_MANAGER_SUPPORT_RESTART、AFX_RESTART_MANAGER_SUPPORT_RECOVER、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILESの組合。|
|- AFX_RESTART_MANAGER_SUPPORT_ALL_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_NO_AUTOSAVE、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART、AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL、AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILESの組合。|
|- AFX_RESTART_MANAGER_SUPPORT_RESTART_ASPECTS|AFX_RESTART_MANAGER_SUPPORT_RESTART、AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES、AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILESの組合。|
|- AFX_RESTART_MANAGER_SUPPORT_RECOVERY_ASPECTS|組合のofAFX_RESTART_MANAGER_SUPPORT_RECOVERY、AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL、AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES、AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES。|

## <a name="cwinappm_ehelptype"></a><a name="m_ehelptype"></a>CWinApp::m_eHelpType

このデータ メンバーの型は、`CWinApp`クラス内で定義されている列挙型AFX_HELP_TYPEです。

```
AFX_HELP_TYPE m_eHelpType;
```

### <a name="remarks"></a>解説

AFX_HELP_TYPE列挙体は、次のように定義されます。

```
enum AFX_HELP_TYPE {
    afxWinHelp = 0,
    afxHTMLHelp = 1
    };
```

- アプリケーションのヘルプを HTML ヘルプに設定するには[、SetHelpMode](#sethelpmode)を`afxHTMLHelp`呼び出して を指定します。

- アプリケーションのヘルプを WinHelp に設定するには、`SetHelpMode`を`afxWinHelp`呼び出して 指定します。

## <a name="cwinappm_hinstance"></a><a name="m_hinstance"></a>CWinApp::m_hInstance

に渡される*hInstance*パラメーターに対応します`WinMain`。

```
HINSTANCE m_hInstance;
```

### <a name="remarks"></a>解説

データ`m_hInstance`メンバーは、Windows で実行されているアプリケーションの現在のインスタンスへのハンドルです。 これは、グローバル関数[AfxGet インスタンス ハンドル](application-information-and-management.md#afxgetinstancehandle)によって返されます。 `m_hInstance`は HINSTANCE 型のパブリック変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#55](../../mfc/reference/codesnippet/cpp/cwinapp-class_15.cpp)]

## <a name="cwinappm_lpcmdline"></a><a name="m_lpcmdline"></a>CWinApp::m_lpCmdLine

に Windows によって渡される*lpCmdLine* `WinMain`パラメーターに対応します。

```
LPTSTR m_lpCmdLine;
```

### <a name="remarks"></a>解説

アプリケーションのコマンド ラインを指定する null で終わる文字列を指します。 アプリケーション`m_lpCmdLine`の起動時にユーザーが入力したコマンド ライン引数にアクセスするときに使用します。 `m_lpCmdLine`は、LPTSTR 型のパブリック変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappm_nautosaveinterval"></a><a name="m_nautosaveinterval"></a>CWinApp::m_nAutosaveInterval

自動保存の間隔 (ミリ秒単位)。

```
int m_nAutosaveInterval;
```

### <a name="remarks"></a>解説

再起動マネージャーを構成して、設定された間隔で開いているドキュメントを自動保存できます。 アプリケーションでファイルが自動保存されない場合、このパラメータは無効です。

## <a name="cwinappm_ncmdshow"></a><a name="m_ncmdshow"></a>CWinApp::m_nCmdShow

に Windows によって渡される*nCmdShow* `WinMain`パラメーターに対応します。

```
int m_nCmdShow;
```

### <a name="remarks"></a>解説

アプリケーションのメイン`m_nCmdShow`ウィンドウに対して[CWnd::ShowWindow](../../mfc/reference/cwnd-class.md#showwindow)を呼び出すときは、引数として渡す必要があります。 `m_nCmdShow`は**int**型のパブリック変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#56](../../mfc/reference/codesnippet/cpp/cwinapp-class_17.cpp)]

## <a name="cwinappm_pactivewnd"></a><a name="m_pactivewnd"></a>CWinApp::m_pActiveWnd

このデータ メンバを使用して、OLE サーバー アプリケーションを埋め込み場所でアクティブにした OLE コンテナー アプリケーションのメイン ウィンドウへのポインターを格納します。

### <a name="remarks"></a>解説

このデータ メンバーが NULL の場合、アプリケーションはインプレース アクティブではありません。

フレームワークは、フレーム ウィンドウが OLE コンテナー アプリケーションによってインプレース アクティブ化されるときに、このメンバー変数を設定します。

## <a name="cwinappm_pdatarecoveryhandler"></a><a name="m_pdatarecoveryhandler"></a>CWinApp::m_pDataRecoveryHandler

アプリケーションのデータ回復ハンドラーへのポインター。

```
CDataRecoveryHandler* m_pDataRecoveryHandler;
```

### <a name="remarks"></a>解説

アプリケーションのデータ回復ハンドラーは、開いているドキュメントを監視し、自動保存します。 フレームワークは、データ回復ハンドラーを使用して、アプリケーションが予期せず終了した後にアプリケーションが再起動したときに、自動保存されたファイルを復元します。 詳細については、「[クラス」](../../mfc/reference/cdatarecoveryhandler-class.md)を参照してください。

## <a name="cwinappm_pszappname"></a><a name="m_pszappname"></a>CWinApp::m_pszAppName

アプリケーションの名前を指定します。

```
LPCTSTR m_pszAppName;
```

### <a name="remarks"></a>解説

アプリケーション名は[、CWinApp](#cwinapp)コンストラクターに渡されたパラメーターから取得することも、指定しない場合は id の ID を持つリソース文字列にAFX_IDS_APP_TITLE。 アプリケーション名がリソースに見つからない場合は、プログラムの .EXE ファイル名。

グローバル関数[AfxGetAppName](application-information-and-management.md#afxgetappname)によって返されます。 `m_pszAppName`は**const char**<strong>\*</strong>型のパブリック変数です。

> [!NOTE]
> に値`m_pszAppName`を割り当てる場合は、ヒープ上で動的に割り当てる必要があります。 デス`CWinApp`トラクターは、このポインターを使用して**free**( ) を呼び出します。 多くの場合、( `_tcsdup`) ランタイム ライブラリ関数を使用して割り当てを行いたいと思っています。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 次に例を示します。

[!code-cpp[NVC_MFCWindowing#57](../../mfc/reference/codesnippet/cpp/cwinapp-class_18.cpp)]

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#65](../../mfc/reference/codesnippet/cpp/cwinapp-class_19.cpp)]

## <a name="cwinappm_pszexename"></a><a name="m_pszexename"></a>CWinApp::m_pszExeName

拡張子を付けずにアプリケーションの実行可能ファイルの名前を格納します。

```
LPCTSTR m_pszExeName;
```

### <a name="remarks"></a>解説

[m_pszAppName](#m_pszappname)とは異なり、この名前にはブランクを含めることはできません。 `m_pszExeName`は**const char**<strong>\*</strong>型のパブリック変数です。

> [!NOTE]
> に値`m_pszExeName`を割り当てる場合は、ヒープ上で動的に割り当てる必要があります。 デス`CWinApp`トラクターは、このポインターを使用して**free**( ) を呼び出します。 多くの場合、( `_tcsdup`) ランタイム ライブラリ関数を使用して割り当てを行いたいと思っています。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 次に例を示します。

[!code-cpp[NVC_MFCWindowing#58](../../mfc/reference/codesnippet/cpp/cwinapp-class_20.cpp)]

## <a name="cwinappm_pszhelpfilepath"></a><a name="m_pszhelpfilepath"></a>CWinApp::m_pszHelpFilePath

アプリケーションのヘルプ ファイルへのパスを格納します。

```
LPCTSTR m_pszHelpFilePath;
```

### <a name="remarks"></a>解説

既定では、フレームワークは`m_pszHelpFilePath`、アプリケーションの名前に初期化を ".HLP"が追加されました。 ヘルプ ファイルの名前を変更するには、目的`m_pszHelpFilePath`のヘルプ ファイルの完全な名前を含む文字列を指す設定を行います。 これを行う便利な場所は、アプリケーションの[InitInstance](#initinstance)関数です。 `m_pszHelpFilePath`は**const char**<strong>\*</strong>型のパブリック変数です。

> [!NOTE]
> に値`m_pszHelpFilePath`を割り当てる場合は、ヒープ上で動的に割り当てる必要があります。 デス`CWinApp`トラクターは、このポインターを使用して**free**( ) を呼び出します。 多くの場合、( `_tcsdup`) ランタイム ライブラリ関数を使用して割り当てを行いたいと思っています。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 次に例を示します。

[!code-cpp[NVC_MFCWindowing#59](../../mfc/reference/codesnippet/cpp/cwinapp-class_21.cpp)]

## <a name="cwinappm_pszprofilename"></a><a name="m_pszprofilename"></a>CWinApp::m_pszProfileName

アプリケーションの 名前が含まれています。INI ファイル。

```
LPCTSTR m_pszProfileName;
```

### <a name="remarks"></a>解説

`m_pszProfileName`は**const char**<strong>\*</strong>型のパブリック変数です。

> [!NOTE]
> に値`m_pszProfileName`を割り当てる場合は、ヒープ上で動的に割り当てる必要があります。 デス`CWinApp`トラクターは、このポインターを使用して**free**( ) を呼び出します。 多くの場合、( `_tcsdup`) ランタイム ライブラリ関数を使用して割り当てを行いたいと思っています。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 次に例を示します。

[!code-cpp[NVC_MFCWindowing#60](../../mfc/reference/codesnippet/cpp/cwinapp-class_22.cpp)]

## <a name="cwinappm_pszregistrykey"></a><a name="m_pszregistrykey"></a>CWinApp::m_pszRegistryKey

レジストリまたは INI ファイル内のアプリケーション プロファイル設定が格納される場所を特定するために使用します。

```
LPCTSTR m_pszRegistryKey;
```

### <a name="remarks"></a>解説

通常、このデータ メンバーは読み取り専用として扱われます。

- 値はレジストリ キーに格納されます。 アプリケーション プロファイル設定の名前は、HKEY_CURRENT_USER/ソフトウェア/LocalAppWizard 生成/というレジストリ キーに追加されます。

に値`m_pszRegistryKey`を割り当てる場合は、ヒープ上で動的に割り当てる必要があります。 デス`CWinApp`トラクターは、このポインターを使用して**free**( ) を呼び出します。 多くの場合、( `_tcsdup`) ランタイム ライブラリ関数を使用して割り当てを行いたいと思っています。 また、新しい値を割り当てる前に、現在のポインターに関連付けられているメモリを解放します。 次に例を示します。

[!code-cpp[NVC_MFCWindowing#61](../../mfc/reference/codesnippet/cpp/cwinapp-class_23.cpp)]

## <a name="cwinappm_pszappid"></a><a name="m_pszappid"></a>CWinApp::m_pszAppID

アプリケーション ユーザー モデル ID。

```
LPCTSTR m_pszAppID;
```

### <a name="remarks"></a>解説

## <a name="cwinapponcontexthelp"></a><a name="oncontexthelp"></a>::オンコンテキストヘルプ

アプリケーション内で Shift + F1 ヘルプを処理します。

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>解説

このメンバー関数を`ON_COMMAND( ID_CONTEXT_HELP, OnContextHelp )`有効にするには、`CWinApp`ステートメントをクラス メッセージ マップに追加し、アクセラレータ テーブルエントリ (通常は SHIFT + F1) を追加する必要があります。

`OnContextHelp`アプリケーションをヘルプ モードにします。 カーソルが矢印と疑問符に変わり、マウス ポインタを移動してマウスの左ボタンを押すと、ダイアログ ボックス、ウィンドウ、メニュー、またはコマンド ボタンを選択できます。 このメンバー関数は、カーソルの下にあるオブジェクトのヘルプ コンテキストを取得し、そのヘルプ コンテキストを使用して Windows 関数 WinHelp を呼び出します。

## <a name="cwinapponddecommand"></a><a name="onddecommand"></a>CWinApp::オンドデコマンド

メイン フレーム ウィンドウが DDE 実行メッセージを受信したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnDDECommand(LPTSTR lpszCommand);
```

### <a name="parameters"></a>パラメーター

*コマンド*<br/>
アプリケーションが受け取る DDE コマンド文字列へのポイント。

### <a name="return-value"></a>戻り値

コマンドが処理される場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

既定の実装では、コマンドがドキュメントを開く要求であるかどうかを確認し、開いている場合は、指定されたドキュメントを開きます。 通常、Windows ファイル マネージャは、ユーザーがデータ ファイルをダブルクリックすると、このような DDE コマンド文字列を送信します。 印刷するコマンドなど、他の DDE 実行コマンドを処理するには、この関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#48](../../mfc/reference/codesnippet/cpp/cwinapp-class_24.cpp)]

## <a name="cwinapponfilenew"></a><a name="onfilenew"></a>CWinApp::オンファイルニュー

ID_FILE_NEW コマンドを実装します。

```
afx_msg void OnFileNew();
```

### <a name="remarks"></a>解説

このメンバー関数を`ON_COMMAND( ID_FILE_NEW, OnFileNew )`有効にするには、`CWinApp`ステートメントをクラス メッセージ マップに追加する必要があります。 有効にすると、この関数は[ファイル]メニューの [新規作成] コマンドの実行を処理します。

このメンバー関数をオーバーライドする方法の既定の動作とガイダンスについては、[テクニカル ノート 22](../../mfc/tn022-standard-commands-implementation.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileopen"></a><a name="onfileopen"></a>ファイルを開く

ID_FILE_OPEN コマンドを実装します。

```
afx_msg void OnFileOpen();
```

### <a name="remarks"></a>解説

このメンバー関数を`ON_COMMAND( ID_FILE_OPEN, OnFileOpen )`有効にするには、`CWinApp`ステートメントをクラス メッセージ マップに追加する必要があります。 有効にすると、この関数はファイルを開くコマンドの実行を処理します。

このメンバー関数をオーバーライドする方法の既定の動作とガイダンスについては、[テクニカル ノート 22](../../mfc/tn022-standard-commands-implementation.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponfileprintsetup"></a><a name="onfileprintsetup"></a>ファイルプリントセットアップ

ID_FILE_PRINT_SETUP コマンドを実装します。

```
afx_msg void OnFilePrintSetup();
```

### <a name="remarks"></a>解説

このメンバー関数を`ON_COMMAND( ID_FILE_PRINT_SETUP, OnFilePrintSetup )`有効にするには、`CWinApp`ステートメントをクラス メッセージ マップに追加する必要があります。 有効にすると、この関数はファイル印刷コマンドの実行を処理します。

このメンバー関数をオーバーライドする方法の既定の動作とガイダンスについては、[テクニカル ノート 22](../../mfc/tn022-standard-commands-implementation.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#49](../../mfc/reference/codesnippet/cpp/cwinapp-class_25.cpp)]

[!code-cpp[NVC_MFCWindowing#50](../../mfc/reference/codesnippet/cpp/cwinapp-class_26.cpp)]

## <a name="cwinapponhelp"></a><a name="onhelp"></a>CWinApp::オンヘルプ

アプリケーション内で F1 ヘルプを (現在のコンテキストを使って) 処理します。

```
afx_msg void OnHelp();
```

### <a name="remarks"></a>解説

通常は、F1 キーのアクセラレータ キー エントリも追加します。 F1 キーを有効にすることは、単なる規則であり、要件ではありません。

このメンバー関数を`ON_COMMAND( ID_HELP, OnHelp )`有効にするには、`CWinApp`ステートメントをクラス メッセージ マップに追加する必要があります。 有効な場合は、ユーザーが F1 キーを押したときにフレームワークによって呼び出されます。

このメッセージ ハンドラー関数の既定の実装は、現在のウィンドウ、ダイアログ ボックス、またはメニュー項目に対応するヘルプ コンテキストを決定し、WINHELP を呼び出します。Exe。 現在使用できるコンテキストがない場合、関数はデフォルトのコンテキストを使用します。

現在フォーカスがあるウィンドウ、ダイアログ ボックス、メニュー項目、またはツール バー ボタン以外のボタンにヘルプ コンテキストを設定するには、このメンバー関数をオーバーライドします。 目的`WinHelp`のヘルプ コンテキスト ID を使用して呼び出します。

## <a name="cwinapponhelpfinder"></a><a name="onhelpfinder"></a>クウィナップ::オンヘルプファインダー

ID_HELP_FINDERおよびID_DEFAULT_HELPコマンドを処理します。

```
afx_msg void OnHelpFinder();
```

### <a name="remarks"></a>解説

このメンバー関数を`ON_COMMAND( ID_HELP_FINDER, OnHelpFinder )`有効にするには、`CWinApp`ステートメントをクラス メッセージ マップに追加する必要があります。 有効にすると、アプリケーションのユーザーが標準**のHELP_FINDER**トピックで呼び出すヘルプ ファインダ コマンドを選択`WinHelp`すると、フレームワークはこのメッセージ ハンドラー関数を呼び出します。

## <a name="cwinapponhelpindex"></a><a name="onhelpindex"></a>::オンヘルプインデックス

ID_HELP_INDEX コマンドを処理し、既定のヘルプ トピックを提供します。

```
afx_msg void OnHelpIndex();
```

### <a name="remarks"></a>解説

このメンバー関数を`ON_COMMAND( ID_HELP_INDEX, OnHelpIndex )`有効にするには、`CWinApp`ステートメントをクラス メッセージ マップに追加する必要があります。 有効にすると、アプリケーションのユーザーが標準`WinHelp`**のHELP_INDEX**トピックで呼び出すヘルプインデックスコマンドを選択すると、フレームワークはこのメッセージハンドラー関数を呼び出します。

## <a name="cwinapponhelpusing"></a><a name="onhelpusing"></a>CWinApp::オンヘルプの使用

ID_HELP_USING コマンドを処理します。

```
afx_msg void OnHelpUsing();
```

### <a name="remarks"></a>解説

このメンバー関数を`ON_COMMAND( ID_HELP_USING, OnHelpUsing )`有効にするには、`CWinApp`ステートメントをクラス メッセージ マップに追加する必要があります。 フレームワークは、アプリケーションのユーザーがヘルプ using コマンドを選択して標準`WinHelp`**のHELP_HELPONHELP**トピックでアプリケーションを呼び出すと、このメッセージ ハンドラー関数を呼び出します。

## <a name="cwinapponidle"></a><a name="onidle"></a>CWinApp::オンアイドル

アイドル時間処理を実行するには、このメンバー関数をオーバーライドします。

```
virtual BOOL OnIdle(LONG lCount);
```

### <a name="parameters"></a>パラメーター

*Lcount*<br/>
アプリケーションのメッセージ キューが`OnIdle`空の場合は、毎回インクリメントされたカウンタが呼び出されます。 このカウントは、新しいメッセージが処理されるたびに 0 にリセットされます。 *lCount*パラメーターを使用して、メッセージを処理せずにアプリケーションがアイドル状態になった時間の相対的な長さを決定できます。

### <a name="return-value"></a>戻り値

より多くのアイドル処理時間を受け取る場合は 0 以外の値を指定します。アイドル時間が必要ない場合は 0。

### <a name="remarks"></a>解説

`OnIdle`は、アプリケーションのメッセージ キューが空の場合に、既定のメッセージ ループで呼び出されます。 オーバーライドを使用して、独自のバックグラウンド アイドル ハンドラ タスクを呼び出します。

`OnIdle`は、アイドル処理時間が必要でないです。 *lCount*パラメーターは、メッセージ・キュー`OnIdle`が空のときに呼び出されるたびにインクリメントされ、新しいメッセージが処理されるたびに 0 にリセットされます。 このカウントに基づいて、さまざまなアイドル ルーチンを呼び出すことができます。

アイドル ループ処理の概要を次に示します。

1. Microsoft Foundation クラス ライブラリのメッセージ ループがメッセージ キューをチェックし、保留中のメッセージ`OnIdle`が見つからなかった場合は、アプリケーション オブジェクトを呼び出し、0 を*lCount*引数として指定します。

2. `OnIdle`は、処理を実行し、ゼロ以外の値を返して、さらに処理を行うために再度呼び出す必要があることを示します。

3. メッセージ ループは、メッセージ キューを再度チェックします。 保留中のメッセージがない場合は、再`OnIdle`び呼び出し *、lCount*引数をインクリメントします。

4. 最終的に`OnIdle`、すべてのアイドルタスクの処理が終了し、0 が返されます。 これにより、メッセージ・ループは、次`OnIdle`のメッセージがメッセージ・キューから受信されるまで呼び出しを停止するように指示します。

アプリケーションはユーザー入力を処理できないため`OnIdle`、ユーザー入力が戻されるまで`OnIdle`処理できないため、時間のかかるタスクを実行しないでください。

> [!NOTE]
> メニュー項目やツール`OnIdle`バー ボタンなどのコマンド ユーザー インターフェイス オブジェクトの更新の既定の実装、および内部データ構造のクリーンアップを実行します。 したがって、 をオーバーライド`OnIdle`する場合は、`CWinApp::OnIdle`オーバーライドされた`lCount`バージョンで を呼び出す必要があります。 最初にすべての基本クラスのアイドル処理を呼び出します (つまり、`OnIdle`基本クラスが 0 を返すまで)。 基本クラスの処理が完了する前に作業を実行する必要がある場合は、基本クラスの実装を確認して、作業を実行する適切な*lCount*を選択します。

メッセージ キューからメッセージ`OnIdle`が取得されるたびに呼び出されないようにする場合は[、CWinThreadIsIdleMessage](../../mfc/reference/cwinthread-class.md#isidlemessage)をオーバーライドできます。 アプリケーションが非常に短いタイマーを設定した場合、またはシステムがWM_SYSTIMERメッセージを送信する場合`OnIdle`は、繰り返し呼び出され、パフォーマンスが低下します。

### <a name="example"></a>例

次の 2 つの例では`OnIdle`、 を使用する方法を示します。 最初の例では *、lCount*引数を使用してタスクの優先順位を設定する 2 つのアイドル タスクを処理します。 最初のタスクは優先度が高く、可能な限り実行する必要があります。 2 番目のタスクは重要度が低く、ユーザー入力が長い時間が過ぎた場合にのみ実行する必要があります。 基本クラス バージョンの 呼び出し`OnIdle`に注意してください。 2 番目の例では、異なる優先順位を持つアイドル タスクのグループを管理します。

[!code-cpp[NVC_MFCWindowing#51](../../mfc/reference/codesnippet/cpp/cwinapp-class_27.cpp)]

## <a name="cwinappopendocumentfile"></a><a name="opendocumentfile"></a>ファイルを開く

フレームワークは、このメソッドを呼び出して、アプリケーションの名前付き[CDocument](../../mfc/reference/cdocument-class.md)ファイルを開きます。

```
virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszFileName
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
[in]開くファイルの名前。

*ブアドトムル*<br/>
[in]TRUE は、ドキュメントが最新のファイルの 1 つであることを示します。FALSE は、文書が最新のファイルの 1 つではないことを示します。

### <a name="return-value"></a>戻り値

成功した場合は`CDocument`、 へのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

その名前のドキュメントが既に開いている場合は、そのドキュメントを含む最初のフレーム ウィンドウにフォーカスが移動します。 アプリケーションが複数のドキュメント テンプレートをサポートしている場合、フレームワークはファイル名拡張子を使用して、ドキュメントの読み込みを試みる適切なドキュメント テンプレートを検索します。 正常に実行された場合、ドキュメント テンプレートは、ドキュメントのフレーム ウィンドウとビューを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#52](../../mfc/reference/codesnippet/cpp/cwinapp-class_16.cpp)]

## <a name="cwinappparsecommandline"></a><a name="parsecommandline"></a>CWinApp::Pアルセコマンドライン

コマンド ラインを解析し、パラメーターを一度に 1 つずつ[CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam)に送信するには、このメンバー関数を呼び出します。

```
void ParseCommandLine(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[オブジェクトへの](../../mfc/reference/ccommandlineinfo-class.md)参照。

### <a name="remarks"></a>解説

アプリケーション ウィザードを使用して新しい MFC プロジェクトを起動すると、アプリケーション ウィザードによって`CCommandLineInfo`のローカル インスタンス`ProcessShellCommand`が`ParseCommandLine`作成され[、InitInstance](#initinstance)メンバー関数を呼び出して、その後で呼び出されます。 コマンド ラインは、次の手順に従います。

1. で`InitInstance`作成された後、`CCommandLineInfo`オブジェクトは に`ParseCommandLine`渡されます。

2. `ParseCommandLine`その後`CCommandLineInfo::ParseParam`、各パラメータに対して 1 回ずつ繰り返し呼び出します。

3. `ParseParam`オブジェクトを`CCommandLineInfo`埋め、そのオブジェクトを[ProcessShellCommand](#processshellcommand)に渡します。

4. `ProcessShellCommand`コマンド ライン引数とフラグを処理します。

必要に応じて直接`ParseCommandLine`呼び出すことができます。

コマンド ライン フラグの詳細については[、「CCommandLineInfo::m_nShellCommand」](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)を参照してください。

## <a name="cwinapppretranslatemessage"></a><a name="pretranslatemessage"></a>メッセージを:P

ウィンドウ メッセージが Windows 関数[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)および[DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage)にディスパッチされる前にウィンドウ メッセージをフィルター処理するには、この関数をオーバーライドする`CWinApp::PreTranslateMessage`既定の実装ではアクセラレータ キーの変換が実行されるため、オーバーライドされたバージョンでメンバー関数を呼び出す必要があります。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*Pmsg*<br/>
処理するメッセージを含む[MSG](/windows/win32/api/winuser/ns-winuser-msg)構造体へのポインター。

### <a name="return-value"></a>戻り値

メッセージが完全に`PreTranslateMessage`処理され、それ以上処理されない場合は、0 以外の値を指定します。 メッセージを通常の方法で処理する場合は 0。

## <a name="cwinappprocessmessagefilter"></a><a name="processmessagefilter"></a>CWinApp::Pロセスメッセージフィルタ

フレームワークのフック関数は、特定の Windows メッセージをフィルター処理して応答するために、このメンバー関数を呼び出します。

```
virtual BOOL ProcessMessageFilter(
    int code,
    LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
フック コードを指定します。 このメンバー関数は、コードを使用して *、lpMsg*の処理方法を決定します。

*をクリックします。*<br/>
Windows [MSG](/windows/win32/api/winuser/ns-winuser-msg)の問題へのポインター。

### <a name="return-value"></a>戻り値

メッセージが処理される場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

フック関数は、イベントをアプリケーションの通常のメッセージ処理に送信する前に処理します。

この高度な機能をオーバーライドする場合は、フレームワークのフック処理を維持するために、必ず基本クラスバージョンを呼び出してください。

## <a name="cwinappprocessshellcommand"></a><a name="processshellcommand"></a>CWinApp::Pロセスシェルコマンド

このメンバー関数は[、initInstance](#initinstance)によって呼び出され、 `CCommandLineInfo` *rCmdInfo*によって識別されるオブジェクトから渡されたパラメーターを受け取り、指定されたアクションを実行します。

```
BOOL ProcessShellCommand(CCommandLineInfo& rCmdInfo);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[オブジェクトへの](../../mfc/reference/ccommandlineinfo-class.md)参照。

### <a name="return-value"></a>戻り値

シェル・コマンドが正常に処理された場合は、ゼロ以外の値。 0 の場合は[、InitInstance](#initinstance)から FALSE を返します。

### <a name="remarks"></a>解説

アプリケーション ウィザードを使用して新しい MFC プロジェクトを起動すると、アプリケーション ウィザードによって`CCommandLineInfo`のローカル インスタンス`ProcessShellCommand`が作成され、`InitInstance`メンバー関数で[ParseCommandLine](#parsecommandline)を呼び出します。 コマンド ラインは、次の手順に従います。

1. で`InitInstance`作成された後、`CCommandLineInfo`オブジェクトは に`ParseCommandLine`渡されます。

2. `ParseCommandLine`次に、各パラメーターに対して 1 回ずつ[、CCommandLineInfo::ParseParam](../../mfc/reference/ccommandlineinfo-class.md#parseparam)を繰り返し呼び出します。

3. `ParseParam`オブジェクトを`CCommandLineInfo`埋め、そのオブジェクトを に`ProcessShellCommand`渡します。

4. `ProcessShellCommand`コマンド ライン引数とフラグを処理します。

[CCommandLineInfo::m_nShellCommand](../../mfc/reference/ccommandlineinfo-class.md#m_nshellcommand)で識別される`CCommandLineInfo``CCommandLineInfo`オブジェクトのデータ メンバーは、クラス内で定義されている次の列挙型です。

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE
    };
```

これらの各値の簡単な説明については、を参照`CCommandLineInfo::m_nShellCommand`してください。

## <a name="cwinappprocesswndprocexception"></a><a name="processwndprocexception"></a>:Pロセスウンドプロセッサ例外

フレームワークは、アプリケーションのメッセージまたはコマンド ハンドラーのいずれかでスローされた例外をハンドラーがキャッチしない場合は常に、このメンバー関数を呼び出します。

```
virtual LRESULT ProcessWndProcException(
    CException* e,
    const MSG* pMsg);
```

### <a name="parameters"></a>パラメーター

*E*<br/>
キャッチされない例外へのポインター。

*Pmsg*<br/>
フレームワークが例外をスローする原因となったウィンドウ メッセージに関する情報を含む[MSG](/windows/win32/api/winuser/ns-winuser-msg)トラクチャ。

### <a name="return-value"></a>戻り値

Windows に返される値。 通常、これは、Windows メッセージの場合は 0L、コマンド メッセージの場合は 1L (TRUE) です。

### <a name="remarks"></a>解説

このメンバー関数を直接呼び出さないでください。

このメンバー関数の既定の実装では、メッセージ ボックスが作成されます。 キャッチされない例外がメニュー、ツールバー、またはアクセラレータ コマンドの失敗によって発生した場合、メッセージ ボックスに "コマンド失敗" メッセージが表示されます。それ以外の場合は、「内部アプリケーション エラー」メッセージが表示されます。

例外のグローバル処理を提供するには、このメンバー関数をオーバーライドします。 メッセージ ボックスを表示する場合にのみ、基本機能を呼び出します。

## <a name="cwinappregister"></a><a name="register"></a>CWinApp::登録

で処理されない登録タスクを`RegisterShellFileTypes`実行します。

```
virtual BOOL Register();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>解説

既定の実装では、TRUE が返されます。 カスタマイズされた登録手順を提供するには、この関数をオーバーライドします。

## <a name="cwinappregistershellfiletypes"></a><a name="registershellfiletypes"></a>次のファイルの種類を指定します。

このメンバー関数を呼び出して、アプリケーションのすべてのドキュメントの種類を Windows ファイル マネージャーに登録します。

```
void RegisterShellFileTypes(BOOL bCompat = FALSE);
```

### <a name="parameters"></a>パラメーター

*bコンパト*<br/>
[in]TRUE は、シェル コマンドの [印刷] および [印刷] のエントリを追加し、ユーザーがシェルから直接ファイルを印刷したり、ファイルをプリンタ オブジェクトにドラッグしたりできるようにします。 また、既定のアイコン キーも追加します。 既定では、このパラメーターは、下位互換性のため FALSE です。

### <a name="remarks"></a>解説

これにより、ユーザーはファイル マネージャー内でダブルクリックして、アプリケーションによって作成されたデータ ファイルを開きます。 アプリケーション`RegisterShellFileTypes`の各ドキュメント テンプレートに対して[AddDocTemplate](#adddoctemplate)を呼び出した後に呼び出します。 また、呼び出すときに[メンバー関数を呼](#enableshellopen)び出します`RegisterShellFileTypes`。

`RegisterShellFileTypes`アプリケーションが管理する[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)オブジェクトのリストを反復処理し、各ドキュメント テンプレートに対して、ファイルの関連付けのために Windows が管理する登録データベースにエントリを追加します。 ファイル マネージャは、ユーザーがデータ ファイルをダブルクリックしたときに、これらのエントリを使用してデータ ファイルを開きます。 これにより、 を出荷する必要がなくなります。REG ファイルをアプリケーションに保存します。

> [!NOTE]
> `RegisterShellFileTypes`ユーザーが管理者権限でプログラムを実行する場合にのみ機能します。 プログラムに管理者権限がない場合、レジストリ キーを変更することはできません。

登録データベースが指定されたファイル名拡張子を別のファイルタイプに既に関連付けている場合、新しい関連付けは作成されません。 この情報`CDocTemplate`を登録するために必要な文字列の形式については、クラスを参照してください。

## <a name="cwinappregisterwithrestartmanager"></a><a name="registerwithrestartmanager"></a>::登録と再起動マネージャー

再起動マネージャーにアプリケーションを登録します。

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
|*コールバックを実行します。*|[in]TRUE は、アプリケーションのこのインスタンスが回復コールバック関数を使用することを示します。FALSE は、それがないことを示します。 アプリケーションが予期せず終了すると、フレームワークは回復コールバック関数を呼び出します。 詳細については[、「CWinApp::アプリケーション回復コールバック](#applicationrecoverycallback)」を参照してください。|
|*を使用します。*|[in]再起動マネージャーのこのインスタンスを識別する一意の文字列。 再起動マネージャー識別子は、アプリケーションの各インスタンスで一意です。|
|*コマンド ライン引数*|[in]コマンド ラインからの追加の引数を含む文字列。|
|*フラグを変更します。*|[in]再起動マネージャーのオプション のフラグ。 詳細については、「解説」を参照してください。|
|*コールバック*|[in]回復コールバック関数。 この関数は、LPVOID パラメーターを入力として受け取り、DWORD を返す必要があります。 既定の回復コールバック関数は`CWinApp::ApplicationRecoveryCallback`です。|
|*lpvパラム*|[in]回復コールバック関数の入力パラメーター。 詳細については[、「CWinApp::アプリケーション回復コールバック](#applicationrecoverycallback)」を参照してください。|
|*間隔を変更します。*|[in]再起動マネージャーが回復コールバック関数が戻るのを待機する時間の長さ。 このパラメータはミリ秒単位です。|
|*フラグ*|[in]回復コールバック関数に渡されるフラグ。 将来利用するために予約されています。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合はS_OK。それ以外の場合はエラー コード。

### <a name="remarks"></a>解説

アプリケーションでファイルの自動保存に既定の MFC 実装を使用する場合は、単純`RegisterWithRestartManager`なバージョンの を使用する必要があります。 アプリケーションの自動保存動作`RegisterWithRestartManager`をカスタマイズする場合は、複雑なバージョンの の を使用します。

*strRestartIdentifier*の空の文字列を指定してこのメソッドを`RegisterWithRestartManager`呼び出すと、再起動マネージャーのこのインスタンスの一意の識別子文字列が作成されます。

アプリケーションが予期せず終了すると、再起動マネージャーはコマンド ラインからアプリケーションを再起動し、オプションの引数として一意の再起動識別子を提供します。 このシナリオでは、フレームワークは`RegisterWithRestartManager`2 回呼び出します。 最初の呼び出しは、文字列識別子の空の文字列を持つ[CWinApp::InitInstance](#initinstance)から来ています。 次に、メソッド[CWinApp::ProcessShellCommand は](#processshellcommand)一意の再起動識別子を使用して呼び出`RegisterWithRestartManager`します。

再起動マネージャーにアプリケーションを登録した後、再起動マネージャーは、アプリケーションを監視します。 アプリケーションが予期せず終了した場合、再起動マネージャーはシャットダウンプロセス中に回復コールバック関数を呼び出します。 再起動マネージャーは、回復コールバック関数からの応答を*dwPingInterval*を待機します。 この時間内に回復コールバック関数が応答しない場合、アプリケーションは回復コールバック関数を実行せずに終了します。

既定では、dwRestart フラグはサポートされていませんが、今後使用するために提供されます。 *dwRestart フラグ*の値は次のとおりです。

- RESTART_NO_CRASH

- RESTART_NO_HANG

- RESTART_NO_PATCH

- RESTART_NO_REBOOT

## <a name="cwinappreopenpreviousfilesatrestart"></a><a name="reopenpreviousfilesatrestart"></a>CWinApp::再オープン前のファイルアットリスタート

アプリケーションが予期せず終了したときに開いていたファイルを再起動マネージャーが再び開くかどうかを決定します。

```
virtual BOOL ReopenPreviousFilesAtRestart() const;
```

### <a name="return-value"></a>戻り値

TRUE は、再起動マネージャーが以前に開いたファイルを再度開くことを示します。FALSE は、再起動マネージャーが行わない場合を示します。

## <a name="cwinapprestartinstance"></a><a name="restartinstance"></a>を使用します。

再起動マネージャーによって開始されたアプリケーションの再起動を処理します。

```
virtual BOOL CWinApp::RestartInstance();
```

### <a name="return-value"></a>戻り値

データ回復ハンドラーが以前に開いたドキュメントを開く場合は TRUE。データ回復ハンドラーにエラーがある場合、または以前に開いているドキュメントがない場合は FALSE。

### <a name="remarks"></a>解説

再起動マネージャーがアプリケーションを再起動すると、フレームワークはこのメソッドを呼び出します。 このメソッドは、データ回復ハンドラーを取得し、自動保存されたファイルを復元します。 このメソッドは、ユーザーが自動保存されたファイルを復元するかどうかを決定するために[、CDataRecoveryHandler::RestoreAutosavedDocuments](../../mfc/reference/cdatarecoveryhandler-class.md#restoreautosaveddocuments)を呼び出します。

このメソッドは、[開](../../mfc/reference/cdatarecoveryhandler-class.md)いているドキュメントがないと判断した場合に FALSE を返します。 開いているドキュメントがない場合、通常はアプリケーションが起動します。

## <a name="cwinapprestoreautosavedfilesatrestart"></a><a name="restoreautosavedfilesatrestart"></a>CWinApp::復元自動保存ファイルアットスタート

アプリケーションを再起動したときに、自動保存されたファイルを再起動マネージャーが復元するかどうかを決定します。

```
virtual BOOL RestoreAutosavedFilesAtRestart() const;
```

### <a name="return-value"></a>戻り値

TRUE は、再起動マネージャーが自動保存されたファイルを復元します。FALSE は、再起動マネージャーが行わない場合を示します。

## <a name="cwinapprun"></a><a name="run"></a>CWinApp::実行

既定のメッセージ ループを提供します。

```
virtual int Run();
```

### <a name="return-value"></a>戻り値

によって`WinMain`返される**int**値。

### <a name="remarks"></a>解説

`Run`アプリケーションがWM_QUITメッセージを受信するまで、Windows メッセージを取得してディスパッチします。 アプリケーションのメッセージ キューに現在メッセージが含まれている場合`Run`は[、OnIdle](#onidle)を呼び出してアイドル時間処理を実行します。 受信メッセージは、特別な処理のために[PreTranslateMessage](#pretranslatemessage)メンバー関数に移動し、`TranslateMessage`次に標準のキーボード変換の Windows 関数に移動します。最後に、Windows`DispatchMessage`関数が呼び出されます。

`Run`めったにオーバーライドされませんが、特別な動作を提供するためにオーバーライドできます。

## <a name="cwinapprunautomated"></a><a name="runautomated"></a>CWinApp::自動実行

サーバー アプリケーションがクライアント アプリケーションによって起動されたかどうかを示す **"/Automation"** または **"-Automation"** オプションが存在するかどうかを確認します。

```
BOOL RunAutomated();
```

### <a name="return-value"></a>戻り値

オプションが見つかった場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

存在する場合、オプションはコマンド ラインから削除されます。 OLE オートメーションの詳細については、「[オートメーション サーバー](../../mfc/automation-servers.md)」を参照してください。

## <a name="cwinapprunembedded"></a><a name="runembedded"></a>CWinApp::埋め込まれた実行

サーバー アプリケーションがクライアント アプリケーションによって起動されたかどうかを示す **"/Embedding**" または " **-Embedding**" オプションが存在するかどうかを調べます。

```
BOOL RunEmbedded();
```

### <a name="return-value"></a>戻り値

オプションが見つかった場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

存在する場合、オプションはコマンド ラインから削除されます。 埋め込み方法の詳細については、「サーバー [: サーバーの実装](../../mfc/servers-implementing-a-server.md)」を参照してください。

## <a name="cwinappsaveallmodified"></a><a name="saveallmodified"></a>::セーブオールア修正

アプリケーションのメイン フレーム ウィンドウを閉じる場合、またはWM_QUERYENDSESSION メッセージを介してすべてのドキュメントを保存するために、フレームワークによって呼び出されます。

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>戻り値

アプリケーションを安全に終了する場合は 0 以外。アプリケーションを終了しても安全でない場合は 0。

### <a name="remarks"></a>解説

このメンバー関数の既定の実装では、アプリケーション内のすべての変更されたドキュメントに対して[、CDocument::SaveModified](../../mfc/reference/cdocument-class.md#savemodified)メンバー関数を順番に呼び出します。

## <a name="cwinappselectprinter"></a><a name="selectprinter"></a>CWinApp::選択プリンター

特定のプリンタを選択し、印刷ダイアログボックスで以前に選択したプリンタを解放します。

```
void SelectPrinter(
    HANDLE hDevNames,
    HANDLE hDevMode,
    BOOL bFreeOld = TRUE);
```

### <a name="parameters"></a>パラメーター

*名前*<br/>
特定のプリンターのドライバー、デバイス、および出力ポート名を識別する[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)の tructure へのハンドル。

*を使用します。*<br/>
プリンターの装置初期設定および環境に関する情報を指定する[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)構造体へのハンドル。

*お問いいま*<br/>
以前に選択したプリンタを解放します。

### <a name="remarks"></a>解説

*hDevMode*と*hDevNames の*両方`SelectPrinter`が NULL の場合は、現在の既定のプリンターを使用します。

## <a name="cwinappsethelpmode"></a><a name="sethelpmode"></a>::セットヘルプモード

アプリケーションのヘルプの種類を設定します。

```
void SetHelpMode(AFX_HELP_TYPE eHelpType);
```

### <a name="parameters"></a>パラメーター

*電子ヘルプの種類*<br/>
使用するヘルプの種類を指定します。 詳細については[、CWinApp::m_eHelpType](#m_ehelptype)を参照してください。

### <a name="remarks"></a>解説

アプリケーションのヘルプの種類を設定します。

アプリケーションのヘルプの種類を HTMLHelp に設定するには[、EnableHTMLHelp](#enablehtmlhelp)を呼び出します。 を呼び`EnableHTMLHelp`出したら、アプリケーションはヘルプ アプリケーションとして HTMLHelp を使用する必要があります。 WinHelp を使用するように変更する場合は *、eHelpType*を呼び出`afxWinHelp``SetHelpMode`して に設定します。

## <a name="cwinappsetregistrykey"></a><a name="setregistrykey"></a>::セットレジストリキー

アプリケーション設定を INI ファイルではなくレジストリに格納します。

```
void SetRegistryKey(LPCTSTR lpszRegistryKey);
void SetRegistryKey(UINT nIDRegistryKey);
```

### <a name="parameters"></a>パラメーター

*キーを指定します。*<br/>
キーの名前を含む文字列へのポインター。

*キー*<br/>
レジストリ キーの名前を含む文字列リソースの ID。

### <a name="remarks"></a>解説

この関数は *、 m_pszRegistryKey*を設定`GetProfileInt`し、 `GetProfileString`、 `WriteProfileInt`、`WriteProfileString`および の`CWinApp`メンバー関数で使用します。 この関数が呼び出された場合、最近使用された (MRU) ファイルの一覧もレジストリに格納されます。 レジストリ キーは通常、会社の名前です。 \\このファイルは\>\\\>\\\>、<\><<<HKEY_CURRENT_USER 次の形式のキーに格納されます。\\

## <a name="cwinappsupportsapplicationrecovery"></a><a name="supportsapplicationrecovery"></a>アプリケーションの回復をサポートします。

再起動マネージャーが、予期せず終了したアプリケーションを回復するかどうかを決定します。

```
virtual BOOL SupportsApplicationRecovery() const;
```

### <a name="return-value"></a>戻り値

TRUE は、再起動マネージャーがアプリケーションを回復したことを示します。FALSE は、再起動マネージャーが行わない場合を示します。

## <a name="cwinappsupportsautosaveatinterval"></a><a name="supportsautosaveatinterval"></a>CWinApp::サポート自動保存間隔

再起動マネージャーが、開いているドキュメントを定期的に自動保存するかどうかを決定します。

```
virtual BOOL SupportsAutosaveAtInterval() const;
```

### <a name="return-value"></a>戻り値

TRUE は、再起動マネージャーが開いているドキュメントを自動保存します。FALSE は、再起動マネージャーが行わない場合を示します。

## <a name="cwinappsupportsautosaveatrestart"></a><a name="supportsautosaveatrestart"></a>CWinApp::サポートオートセーブアットリスタート

アプリケーションの再起動時に、再起動マネージャーが開いているドキュメントを自動的に保存するかどうかを決定します。

```
virtual BOOL SupportsAutosaveAtRestart() const;
```

### <a name="return-value"></a>戻り値

TRUE は、アプリケーションの再起動時に、再起動マネージャーが開いているドキュメントを自動的に保存します。FALSE は、再起動マネージャーが行わない場合を示します。

## <a name="cwinappsupportsrestartmanager"></a><a name="supportsrestartmanager"></a>::サポートリスタートマネージャー

アプリケーションが再起動マネージャーをサポートするかどうかを決定します。

```
virtual BOOL SupportsRestartManager() const;
```

### <a name="return-value"></a>戻り値

TRUE は、アプリケーションが再起動マネージャーをサポートするを示します。FALSE は、アプリケーションが行わない場合を示します。

## <a name="cwinappunregister"></a><a name="unregister"></a>CWinApp::登録解除

アプリケーション オブジェクトによって登録されているすべてのファイルの登録を解除します。

```
virtual BOOL Unregister();
```

### <a name="return-value"></a>戻り値

正常に完了した場合はゼロ以外、それ以外の場合は 0 です。

### <a name="remarks"></a>解説

この`Unregister`関数は、アプリケーション オブジェクトと[Register](#register)関数によって実行された登録を元に行います。 通常、どちらの関数も MFC によって暗黙的に呼び出されるため、コードには表示されません。

カスタム登録解除手順を実行するには、この関数をオーバーライドします。

## <a name="cwinappunregistershellfiletypes"></a><a name="unregistershellfiletypes"></a>CWinApp::ファイルの種類を登録解除します。

Windows ファイル マネージャーでアプリケーションのすべてのドキュメントの種類の登録を解除するには、このメンバー関数を呼び出します。

```
void UnregisterShellFileTypes();
```

## <a name="cwinappwinhelp"></a><a name="winhelp"></a>CWinApp::ウィンヘルプ

WinHelp アプリケーションを呼び出します。

```
virtual void WinHelp(
    DWORD_PTR dwData,
    UINT nCmd = HELP_CONTEXT);
```

### <a name="parameters"></a>パラメーター

*dw データ*<br/>
追加データを指定します。 使用される値は *、nCmd*パラメーターの値によって異なります。

*nCmd*<br/>
要求されるヘルプの種類を指定します。 可能な値の一覧と *、それらが dwData*パラメーターに与える影響については[、WinHelp](/windows/win32/api/winuser/nf-winuser-winhelpw) Windows 関数を参照してください。

### <a name="remarks"></a>解説

フレームワークは、WinHelp アプリケーションを呼び出すためにもこの関数を呼び出します。

フレームワークは、アプリケーションが終了すると、WinHelp アプリケーションを自動的に閉じます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#53](../../mfc/reference/codesnippet/cpp/cwinapp-class_28.cpp)]

## <a name="cwinappwriteprofilebinary"></a><a name="writeprofilebinary"></a>::プロファイルバイナリを書き込みます

バイナリ データをアプリケーションのレジストリの指定したセクションに書き込むか、または にバイナリ データを書き込むには、このメンバー関数を呼び出します。INI ファイル。

```
BOOL WriteProfileBinary(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPBYTE pData,
    UINT nBytes);
```

### <a name="parameters"></a>パラメーター

*セクション*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は、作成されます。 セクションの名前は大文字と小文字は独立しています。文字列は、大文字と小文字の任意の組み合わせで指定できます。

*をクリックします。*<br/>
値の書き込み先のエントリを含む null で終わる文字列へのポイント。 指定したセクションにエントリが存在しない場合は、エントリが作成されます。

*Pdata*<br/>
書き込むデータへのポイント。

*Nbytes*<br/>
書き込むバイト数を含みます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

この例では`CWinApp* pApp = AfxGetApp();`、MFC アプリケーションの任意の関数から使用`WriteProfileBinary``GetProfileBinary`できる方法を示す CWinApp クラスを取得します。

[!code-cpp[NVC_MFCWindowing#54](../../mfc/reference/codesnippet/cpp/cwinapp-class_29.cpp)]

別の例については、次の例[を](#getprofilebinary)参照してください。

## <a name="cwinappwriteprofileint"></a><a name="writeprofileint"></a>::プロファイルの書き込み

指定した値をアプリケーションのレジストリの指定したセクションに書き込むか、または に書き込みます。INI ファイル。

```
BOOL WriteProfileInt(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    int nValue);
```

### <a name="parameters"></a>パラメーター

*セクション*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は、作成されます。 セクションの名前は大文字と小文字は独立しています。文字列は、大文字と小文字の任意の組み合わせで指定できます。

*をクリックします。*<br/>
値の書き込み先のエントリを含む null で終わる文字列へのポイント。 指定したセクションにエントリが存在しない場合は、エントリが作成されます。

*n値*<br/>
書き込む値を格納します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

この例では`CWinApp* pApp = AfxGetApp();`、MFC アプリケーションの任意の関数から`WriteProfileString`、 、 、 `WriteProfileInt` `GetProfileString`、 `GetProfileInt` 、 、 、 を使用できる方法を示す CWinApp クラスを取得するために使用します。

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

別の例については[、CWinApp::GetProfileInt](#getprofileint)の例を参照してください。

## <a name="cwinappwriteprofilestring"></a><a name="writeprofilestring"></a>::プロファイル文字列を書き込みます

指定した文字列をアプリケーションのレジストリの指定したセクションに書き込むか、または に書き込みます。INI ファイル。

```
BOOL WriteProfileString(
    LPCTSTR lpszSection,
    LPCTSTR lpszEntry,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>パラメーター

*セクション*<br/>
エントリがあるセクションを指定する NULL で終わる文字列へのポインター。 セクションが存在しない場合は、作成されます。 セクションの名前は大文字と小文字は独立しています。文字列は、大文字と小文字の任意の組み合わせで指定できます。

*をクリックします。*<br/>
値の書き込み先のエントリを含む null で終わる文字列へのポイント。 指定したセクションにエントリが存在しない場合は、エントリが作成されます。 このパラメーターが NULL の場合は *、lpszSection*で指定されたセクションが削除されます。

*値*<br/>
書き込む文字列へのポイント。 このパラメーターが NULL の場合は *、lpszEntry*パラメーターで指定された項目が削除されます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#43](../../mfc/reference/codesnippet/cpp/cwinapp-class_9.cpp)]

別の例については[、CWinApp::GetProfileInt](#getprofileint)の例を参照してください。

## <a name="cwinappsetappid"></a><a name="setappid"></a>::セットアプID

アプリケーションのアプリケーション ユーザー モデル ID を明示的に設定します。 このメソッドは、ユーザー インターフェイスがユーザーに提示される前に呼び出す必要があります (最適な場所はアプリケーション コンストラクターです)。

```
void SetAppID(LPCTSTR lpcszAppID);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
アプリケーション・ユーザー・モデル ID を指定します。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cwinthread-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[方法: 再起動マネージャーのサポートを追加する](../../mfc/how-to-add-restart-manager-support.md)
