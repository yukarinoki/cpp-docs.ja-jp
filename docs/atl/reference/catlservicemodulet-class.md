---
title: CAtlServiceModuleT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::CAtlServiceModuleT
- ATLBASE/ATL::CAtlServiceModuleT::Handler
- ATLBASE/ATL::CAtlServiceModuleT::InitializeSecurity
- ATLBASE/ATL::CAtlServiceModuleT::Install
- ATLBASE/ATL::CAtlServiceModuleT::IsInstalled
- ATLBASE/ATL::CAtlServiceModuleT::LogEvent
- ATLBASE/ATL::CAtlServiceModuleT::OnContinue
- ATLBASE/ATL::CAtlServiceModuleT::OnInterrogate
- ATLBASE/ATL::CAtlServiceModuleT::OnPause
- ATLBASE/ATL::CAtlServiceModuleT::OnShutdown
- ATLBASE/ATL::CAtlServiceModuleT::OnStop
- ATLBASE/ATL::CAtlServiceModuleT::OnUnknownRequest
- ATLBASE/ATL::CAtlServiceModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlServiceModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlServiceModuleT::RegisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::Run
- ATLBASE/ATL::CAtlServiceModuleT::ServiceMain
- ATLBASE/ATL::CAtlServiceModuleT::SetServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::Start
- ATLBASE/ATL::CAtlServiceModuleT::Uninstall
- ATLBASE/ATL::CAtlServiceModuleT::Unlock
- ATLBASE/ATL::CAtlServiceModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlServiceModuleT::WinMain
- ATLBASE/ATL::CAtlServiceModuleT::m_bService
- ATLBASE/ATL::CAtlServiceModuleT::m_dwThreadID
- ATLBASE/ATL::CAtlServiceModuleT::m_hServiceStatus
- ATLBASE/ATL::CAtlServiceModuleT::m_status
- ATLBASE/ATL::CAtlServiceModuleT::m_szServiceName
dev_langs:
- C++
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c81df88dfdf2b40b5196d219159b48023d9db6d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="catlservicemodulet-class"></a>CAtlServiceModuleT クラス
このクラスは、サービスを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, UINT nServiceNameID>  
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`CAtlServiceModuleT`です。  
  
 *nServiceNameID*  
 サービスのリソースの識別子です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](#catlservicemodulet)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlServiceModuleT::Handler](#handler)|サービスのハンドラー ルーチンです。|  
|[CAtlServiceModuleT::InitializeSecurity](#initializesecurity)|既定値に、サービスのセキュリティ設定を提供します。|  
|[CAtlServiceModuleT::Install](#install)|インストールし、サービスを作成します。|  
|[CAtlServiceModuleT::IsInstalled](#isinstalled)|サービスがインストールされていることを確認します。|  
|[CAtlServiceModuleT::LogEvent](#logevent)|イベント ログに書き込みます。|  
|[CAtlServiceModuleT::OnContinue](#oncontinue)|サービスを続行するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::OnInterrogate](#oninterrogate)|サービスを調査するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::OnPause](#onpause)|サービスを一時停止するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::OnShutdown](#onshutdown)|サービスをシャット ダウンするには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::OnStop](#onstop)|サービスを停止するには、このメソッドをオーバーライドします。|  
|[されない](#onunknownrequest)|サービスに不明な要求を処理するには、このメソッドをオーバーライドします。|  
|[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)|コマンドラインを解析し、必要な場合は、登録を実行します。|  
|[CAtlServiceModuleT::PreMessageLoop](#premessageloop)|このメソッドは、メッセージ ループに入る直前に呼び出されます。|  
|[CAtlServiceModuleT::RegisterAppId](#registerappid)|レジストリにサービスを登録します。|  
|[主要な](#run)|サービスを実行します。|  
|[CAtlServiceModuleT::ServiceMain](#servicemain)|サービス コントロール マネージャーによって呼び出されるメソッド。|  
|[CAtlServiceModuleT::SetServiceStatus](#setservicestatus)|サービスの状態を更新します。|  
|[CAtlServiceModuleT::Start](#start)|によって呼び出されます`CAtlServiceModuleT::WinMain`サービスの開始時です。|  
|[CAtlServiceModuleT::Uninstall](#uninstall)|停止し、サービスを削除します。|  
|[CAtlServiceModuleT::Unlock](#unlock)|サービスのロック カウントをデクリメントします。|  
|[CAtlServiceModuleT::UnregisterAppId](#unregisterappid)|レジストリからサービスを削除します。|  
|[起動時](#winmain)|このメソッドは、サービスの実行に必要なコードを実装します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlServiceModuleT::m_bService](#m_bservice)|プログラムがサービスとして実行されていることを示すフラグです。|  
|[CAtlServiceModuleT::m_dwThreadID](#m_dwthreadid)|スレッド識別子を格納するメンバー変数です。|  
|[CAtlServiceModuleT::m_hServiceStatus](#m_hservicestatus)|メンバー変数が現在のサービスのステータス情報の構造体へのハンドルを格納します。|  
|[CAtlServiceModuleT::m_status](#m_status)|メンバー変数が現在のサービスのステータス情報の構造体を格納します。|  
|[CAtlServiceModuleT::m_szServiceName](#m_szservicename)|登録されているサービスの名前。|  
  
## <a name="remarks"></a>コメント  
 `CAtlServiceModuleT`、から派生した[CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)、ATL サービス モジュールを実装します。 `CAtlServiceModuleT` コマンドライン処理、インストール、登録、および削除のメソッドを提供します。 追加の機能が必要な場合は、これらおよびその他のメソッドをオーバーライドできます。  
  
 このクラスは廃止された置換[CComModule クラス](../../atl/reference/ccommodule-class.md)ATL の以前のバージョンで使用されます。 参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="catlservicemodulet"></a>  CAtlServiceModuleT::CAtlServiceModuleT  
 コンストラクターです。  
  
```
CAtlServiceModuleT() throw();
```  
  
### <a name="remarks"></a>コメント  
 データ メンバーを初期化し、初期サービスの状態を設定します。  
  
##  <a name="handler"></a>  CAtlServiceModuleT::Handler  
 サービスのハンドラー ルーチンです。  
  
```
void Handler(DWORD dwOpcode) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwOpcode*  
 ハンドラーの操作を定義するスイッチです。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 これは、停止などのサービスと問題の手順の状態を取得または一時停止するサービス コントロール マネージャー (SCM) を呼び出すコードです。 SCM は、以下に示すように、操作コードを渡します`Handler`を示す、サービスが行う必要があります。  
  
|操作コード|説明|  
|--------------------|-------------|  
|SERVICE_CONTROL_STOP|サービスを停止します。 メソッドをオーバーライドする[CAtlServiceModuleT::OnStop](#onstop)動作を変更する atlbase.h にします。|  
|SERVICE_CONTROL_PAUSE|ユーザーが実装されています。 空のメソッドをオーバーライドして[CAtlServiceModuleT::OnPause](#onpause) atlbase.h サービスを一時停止にします。|  
|SERVICE_CONTROL_CONTINUE|ユーザーが実装されています。 空のメソッドをオーバーライド[CAtlServiceModuleT::OnContinue](#oncontinue)で atlbase.h、サービスを続行します。|  
|SERVICE_CONTROL_INTERROGATE|ユーザーが実装されています。 空のメソッドをオーバーライドして[CAtlServiceModuleT::OnInterrogate](#oninterrogate) atlbase.h をサービスを問い合わせるためにします。|  
|SERVICE_CONTROL_SHUTDOWN|ユーザーが実装されています。 空のメソッドをオーバーライドして[CAtlServiceModuleT::OnShutdown](#onshutdown)サービスをシャット ダウンする atlbase.h にします。|  
  
 この操作のコードが認識されない場合、メソッド[されない](#onunknownrequest)と呼びます。  
  
 既定の ATL で生成されたサービスは、stop 命令を処理するのみです。 SCM には、stop 命令が成功した場合、サービスは、プログラムを停止するが、SCM を指示します。 サービスを呼び出すし`PostThreadMessage`自体に終了メッセージを送信します。 メッセージ ループを終了このし、サービスが最終的に終了します。  
  
##  <a name="initializesecurity"></a>  CAtlServiceModuleT::InitializeSecurity  
 既定値に、サービスのセキュリティ設定を提供します。  
  
```
HRESULT InitializeSecurity() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 Visual Studio .NET 2003 では、このメソッドは、基底クラスで実装されていません。 Visual Studio プロジェクト ウィザードには、生成されたコードでこのメソッドが含まれていますが、以前のバージョンの Visual C で作成されたプロジェクトが ATL 7.1 を使用してコンパイルされた場合、コンパイル エラーが発生します。 派生したクラス`CAtlServiceModuleT`派生クラスでこのメソッドを実装する必要があります。  
  
 呼び出しで PKT レベルの認証、RPC_C_IMP_LEVEL_IDENTIFY の偽装レベルおよび適切な非 null セキュリティ記述子を使用して**CoInitializeSecurity**です。  
  
 属性なしのサービスをウィザードで生成されたプロジェクトでは、次のようになります。  
  
 [!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]  
  
 属性付きサービス プロジェクトでは、次のようになります。  
  
 [!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]  
  
##  <a name="install"></a>  CAtlServiceModuleT::Install  
 インストールし、サービスを作成します。  
  
```
BOOL Install() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 サービス コントロール マネージャー (SCM) データベースにサービスをインストールし、サービス オブジェクトを作成します。 場合は、サービスを作成できませんでした、メッセージ ボックスが表示され、FALSE を返します。  
  
##  <a name="isinstalled"></a>  CAtlServiceModuleT::IsInstalled  
 サービスがインストールされていることを確認します。  
  
```
BOOL IsInstalled() throw();
```  
  
### <a name="return-value"></a>戻り値  
 かどうか、サービスがインストールされている、それ以外の場合は TRUE を返します。  
  
##  <a name="logevent"></a>  CAtlServiceModuleT::LogEvent  
 イベント ログに書き込みます。  
  
```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pszFormat`  
 イベント ログに書き込む文字列。  
  
 ...  
 イベント ログに書き込まれる省略可能な余分な文字列。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、詳細を関数を使用して、イベント ログに書き込みます[ReportEvent](http://msdn.microsoft.com/library/windows/desktop/aa363679)です。 サービスが実行されていない場合、文字列は、コンソールに送信します。  
  
##  <a name="m_bservice"></a>  CAtlServiceModuleT::m_bService  
 プログラムがサービスとして実行されていることを示すフラグです。  
  
```
BOOL m_bService;
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションの exe ファイルからサービス EXE を区別するために使用されます。  
  
##  <a name="m_dwthreadid"></a>  CAtlServiceModuleT::m_dwThreadID  
 メンバー変数が、サービスのスレッド識別子を格納します。  
  
```
DWORD m_dwThreadID;
```  
  
### <a name="remarks"></a>コメント  
 この変数は、現在のスレッドのスレッド識別子を格納します。  
  
##  <a name="m_hservicestatus"></a>  CAtlServiceModuleT::m_hServiceStatus  
 メンバー変数が現在のサービスのステータス情報の構造体へのハンドルを格納します。  
  
```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```  
  
### <a name="remarks"></a>コメント  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996)構造体には、サービスに関する情報が含まれています。  
  
##  <a name="m_status"></a>  CAtlServiceModuleT::m_status  
 メンバー変数が現在のサービスのステータス情報の構造体を格納します。  
  
```
SERVICE_STATUS m_status;
```  
  
### <a name="remarks"></a>コメント  
 [SERVICE_STATUS](http://msdn.microsoft.com/library/windows/desktop/ms685996)構造体には、サービスに関する情報が含まれています。  
  
##  <a name="m_szservicename"></a>  CAtlServiceModuleT::m_szServiceName  
 登録されているサービスの名前。  
  
```
TCHAR [256] m_szServiceName;
```  
  
### <a name="remarks"></a>コメント  
 サービスの名前を格納する null で終わる文字列。  
  
##  <a name="oncontinue"></a>  CAtlServiceModuleT::OnContinue  
 サービスを続行するには、このメソッドをオーバーライドします。  
  
```
void OnContinue() throw();
```  
  
##  <a name="oninterrogate"></a>  CAtlServiceModuleT::OnInterrogate  
 サービスを調査するには、このメソッドをオーバーライドします。  
  
```
void OnInterrogate() throw();
```  
  
##  <a name="onpause"></a>  CAtlServiceModuleT::OnPause  
 サービスを一時停止するには、このメソッドをオーバーライドします。  
  
```
void OnPause() throw();
```  
  
##  <a name="onshutdown"></a>  CAtlServiceModuleT::OnShutdown  
 サービスをシャット ダウンするには、このメソッドをオーバーライドします。  
  
```
void OnShutdown() throw();
```  
  
##  <a name="onstop"></a>  CAtlServiceModuleT::OnStop  
 サービスを停止するには、このメソッドをオーバーライドします。  
  
```
void OnStop() throw();
```  
  
##  <a name="onunknownrequest"></a>  されない  
 サービスに不明な要求を処理するには、このメソッドをオーバーライドします。  
  
```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 */\* dwOpcode \*/*  
 予約済み。  
  
##  <a name="parsecommandline"></a>  CAtlServiceModuleT::ParseCommandLine  
 コマンドラインを解析し、必要な場合は、登録を実行します。  
  
```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCmdLine`  
 コマンド ライン。  
  
 `pnRetCode`  
 (これが、行われた) 場合は、登録に対応する HRESULT。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、または false コマンドラインで指定された RGS ファイルを登録されていない場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 コマンドラインを解析して登録するか必要な場合は、指定された RGS ファイルの登録を解除します。 このメソッドを呼び出す[CAtlExeModuleT::ParseCommandLine](../../atl/reference/catlexemodulet-class.md#parsecommandline)をチェックする **/RegServer**と **/UnregServer**です。 引数を追加する **-/service**サービスに登録されます。  
  
##  <a name="premessageloop"></a>  CAtlServiceModuleT::PreMessageLoop  
 このメソッドは、メッセージ ループに入る直前に呼び出されます。  
  
```
HRESULT PreMessageLoop(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 このパラメーターに渡された[CAtlExeModuleT::PreMessageLoop](../../atl/reference/catlexemodulet-class.md#premessageloop)です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 サービスのカスタムの初期化コードを追加するには、このメソッドをオーバーライドします。  
  
##  <a name="registerappid"></a>  CAtlServiceModuleT::RegisterAppId  
 レジストリにサービスを登録します。  
  
```
inline HRESULT RegisterAppId(bool bService = false) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *bService*  
 サービスとして登録する場合は true にする必要があります。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="run"></a>  主要な  
 サービスを実行します。  
  
```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターで説明した値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。 既定値は、SW_HIDE です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出される後**実行**呼び出し[CAtlServiceModuleT::PreMessageLoop](#premessageloop)、 [CAtlExeModuleT::RunMessageLoop](../../atl/reference/catlexemodulet-class.md#runmessageloop)、および[CAtlExeModuleT:。PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop)です。  
  
##  <a name="servicemain"></a>  CAtlServiceModuleT::ServiceMain  
 このメソッドには、サービス コントロール マネージャーからは呼び出されます。  
  
```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwArgc*  
 Argc 引数。  
  
 *lpszArgv*  
 Argv 引数。  
  
### <a name="remarks"></a>コメント  
 サービス コントロール マネージャー (SCM) 呼び出し`ServiceMain`コントロール パネルの サービス アプリケーションを開いたときに、サービスを選択し、開始 をクリックします。  
  
 SCM 後、呼び出して`ServiceMain`サービスがハンドラー関数には、SCM の与える必要があります。 この関数は、サービスの状態を取得して (一時停止または停止) などの具体的な手順を渡す SCM を使用できます。 その後、[主要な](#run)サービスの主な作業を実行すると呼びます。 **実行**サービスが停止されるまでの実行を継続します。  
  
##  <a name="setservicestatus"></a>  CAtlServiceModuleT::SetServiceStatus  
 このメソッドは、サービスの状態を更新します。  
  
```
void SetServiceStatus(DWORD dwState) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwState`  
 新しいステータス。 参照してください[SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241)使用可能な値です。  
  
### <a name="remarks"></a>コメント  
 サービスのサービス コントロール マネージャーのステータス情報を更新します。 メソッドによって呼び出されます[主要な](#run)、 [CAtlServiceModuleT::ServiceMain](#servicemain)およびその他のハンドラーのメソッドです。 状態は、メンバー変数にも格納[CAtlServiceModuleT::m_status](#m_status)です。  
  
##  <a name="start"></a>  CAtlServiceModuleT::Start  
 によって呼び出されます`CAtlServiceModuleT::WinMain`サービスの開始時です。  
  
```
HRESULT Start(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターで説明した値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 [起動時](#winmain)メソッド登録と、インストールの両方を処理するだけでなくタスクのレジストリ エントリを削除して、モジュールをアンインストールするのに関与します。 サービスが実行されると`WinMain`呼び出し**開始**です。  
  
##  <a name="uninstall"></a>  CAtlServiceModuleT::Uninstall  
 停止し、サービスを削除します。  
  
```
BOOL Uninstall() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 実行中のサービスを停止し、サービス コントロール マネージャー データベースから削除します。  
  
##  <a name="unlock"></a>  CAtlServiceModuleT::Unlock  
 サービスのロック カウントをデクリメントします。  
  
```
LONG Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 診断に役立つとデバッグ可能性のあるロック カウントを返します。  
  
##  <a name="unregisterappid"></a>  CAtlServiceModuleT::UnregisterAppId  
 レジストリからサービスを削除します。  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="winmain"></a>  起動時  
 このメソッドは、サービスを開始するために必要なコードを実装します。  
  
```
int WinMain(int nShowCmd) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nShowCmd`  
 ウィンドウの表示方法を指定します。 このパラメーターで説明した値のいずれかを指定できます、 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)セクションです。  
  
### <a name="return-value"></a>戻り値  
 サービスの戻り値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コマンドラインを処理 (で[CAtlServiceModuleT::ParseCommandLine](#parsecommandline)) と、サービスが開始されます (を使用して[CAtlServiceModuleT::Start](#start))。  
  
## <a name="see-also"></a>関連項目  
 [CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
