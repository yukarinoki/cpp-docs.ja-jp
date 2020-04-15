---
title: クラス
ms.date: 05/06/2019
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
helpviewer_keywords:
- CAtlServiceModuleT class
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
ms.openlocfilehash: 5d87eada997d0bbfe44cd07a819f6b012a7a3a20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321338"
---
# <a name="catlservicemodulet-class"></a>クラス

このクラスはサービスを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T, UINT nServiceNameID>
class ATL_NO_VTABLE CAtlServiceModuleT : public CAtlExeModuleT<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
クラスから派生`CAtlServiceModuleT`したクラス。

*サービス名ID*<br/>
サービスのリソース識別子。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[サービスサービスモジュール](#catlservicemodulet)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ハンドラーサービスモジュールT::ハンドラー](#handler)|サービスのハンドラー ルーチン。|
|[サービスモジュールT::初期化セキュリティ](#initializesecurity)|サービスの既定のセキュリティ設定を提供します。|
|[サービスモジュール::インストール](#install)|サービスをインストールして作成します。|
|[サービスモジュールを使用します。](#isinstalled)|サービスがインストールされたことを確認します。|
|[イベントを発生させます。](#logevent)|イベント ログに書き込みます。|
|[サービスモジュール::オンコニュ](#oncontinue)|サービスを続行するには、このメソッドをオーバーライドします。|
|[サービスモジュールT::オンアセアフェデ](#oninterrogate)|サービスを問い取るために、このメソッドをオーバーライドします。|
|[サービスモジュール::オンポーズ](#onpause)|サービスを一時停止するには、このメソッドをオーバーライドします。|
|[サービスモジュールT::シャットダウン時](#onshutdown)|サービスをシャットダウンするには、このメソッドをオーバーライドします|
|[サービスモジュール::オンストップ](#onstop)|サービスを停止するには、このメソッドをオーバーライドします|
|[サービスサービスモジュール::オンUnknownリクエスト](#onunknownrequest)|サービスに対する不明な要求を処理するには、このメソッドをオーバーライドします|
|[サービスモジュールT::Pアルセストライン](#parsecommandline)|コマンド ラインを解析し、必要に応じて登録を実行します。|
|[サービスサービスモジュール::Pメッセージループ](#premessageloop)|このメソッドは、メッセージ ループに入る直前に呼び出されます。|
|[をクリックします。](#registerappid)|サービスをレジストリに登録します。|
|[実行](#run)|サービスを実行します。|
|[サービスサービスモジュール](#servicemain)|サービス コントロール マネージャによって呼び出されるメソッド。|
|[サービス状況を設定します。](#setservicestatus)|サービスの状態を更新します。|
|[開始](#start)|サービスの`CAtlServiceModuleT::WinMain`開始時に呼び出されます。|
|[をクリックします。](#uninstall)|サービスを停止および削除します。|
|[サービスモジュールT::ロック解除](#unlock)|サービスのロックカウントを減算します。|
|[を登録解除します。](#unregisterappid)|レジストリからサービスを削除します。|
|[サービスモジュール::ウィンメイン](#winmain)|このメソッドは、サービスの実行に必要なコードを実装します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[サービスサービスモジュール::m_bService](#m_bservice)|プログラムがサービスとして実行されていることを示すフラグ。|
|[サービスサービスモジュール::m_dwThreadID](#m_dwthreadid)|スレッド識別子を格納するメンバー変数。|
|[サービスモジュール::m_hServiceStatus](#m_hservicestatus)|現在のサービスの状態情報構造体へのハンドルを格納するメンバー変数。|
|[m_status](#m_status)|現在のサービスの状態情報構造体を格納するメンバー変数。|
|[サービスモジュール::m_szServiceName](#m_szservicename)|登録するサービスの名前。|

## <a name="remarks"></a>解説

`CAtlServiceModuleT`から派生した[、ATL](../../atl/reference/catlexemodulet-class.md)サービス モジュールを実装します。 `CAtlServiceModuleT`には、コマンド ライン処理、インストール、登録、および削除のメソッドが用意されています。 追加の機能が必要な場合は、これらのメソッドおよびその他のメソッドをオーバーライドできます。

このクラスは、以前のバージョンの ATL で使用された、古い[CComModule クラス](../../atl/reference/ccommodule-class.md)を置き換えます。 詳細については[、「ATL モジュール クラス](../../atl/atl-module-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[カトルモジュール](../../atl/reference/catlmodule-class.md)

[カトルモジュール](../../atl/reference/catlmodulet-class.md)

[カトルエクセスト](../../atl/reference/catlexemodulet-class.md)

`CAtlServiceModuleT`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="catlservicemoduletcatlservicemodulet"></a><a name="catlservicemodulet"></a>サービスサービスモジュール

コンストラクターです。

```
CAtlServiceModuleT() throw();
```

### <a name="remarks"></a>解説

データ メンバーを初期化し、初期サービスの状態を設定します。

## <a name="catlservicemodulethandler"></a><a name="handler"></a>ハンドラーサービスモジュールT::ハンドラー

サービスのハンドラー ルーチン。

```
void Handler(DWORD dwOpcode) throw();
```

### <a name="parameters"></a>パラメーター

*ドウオプコード*<br/>
ハンドラー操作を定義するスイッチ。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

これは、サービス コントロール マネージャー (SCM) がサービスの状態を取得し、停止または一時停止などの命令を発行するために呼び出すコードです。 SCM は、サービスが実行する操作を示すために`Handler`、次に示すオペレーション コードを渡します。

|作業コード|意味|
|--------------------|-------------|
|SERVICE_CONTROL_STOP|サービスを停止します。 動作を変更するには、atlbase.h のメソッド[CAtlServiceModuleT::OnStop](#onstop)をオーバーライドします。|
|SERVICE_CONTROL_PAUSE|ユーザーが実装されました。 サービスを一時停止するには、atlbase.h の空のメソッド[CAtlServiceModuleT::OnPause](#onpause)をオーバーライドします。|
|SERVICE_CONTROL_CONTINUE|ユーザーが実装されました。 サービスを継続するには、atlbase.h の空のメソッド[CAtlServiceModuleT::OnContinue](#oncontinue)をオーバーライドします。|
|SERVICE_CONTROL_INTERROGATE|ユーザーが実装されました。 サービスを問い換えるために、atlbase.h の空のメソッド[CAtlServiceModuleT::On尋問](#oninterrogate)をオーバーライドします。|
|SERVICE_CONTROL_SHUTDOWN|ユーザーが実装されました。 サービスをシャットダウンするには、atlbase.h の空のメソッド[CAtlServiceModuleT::OnShutdown](#onshutdown)をオーバーライドします。|

操作コードが認識されない場合は、メソッド[CAtlServiceModuleT::OnUnknownRequest](#onunknownrequest)が呼び出されます。

ATL によって生成された既定のサービスは、停止命令のみを処理します。 SCM が停止命令を渡した場合、サービスは SCM にプログラムが停止しようとしていることを通知します。 その後、サービス`PostThreadMessage`は終了メッセージを自身に投稿する呼び出しを行います。 これにより、メッセージ ループが終了し、サービスは最終的に終了します。

## <a name="catlservicemoduletinitializesecurity"></a><a name="initializesecurity"></a>サービスモジュールT::初期化セキュリティ

サービスの既定のセキュリティ設定を提供します。

```
HRESULT InitializeSecurity() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

派生`CAtlServiceModuleT`元のクラスは、派生クラスでこのメソッドを実装する必要があります。

PKT レベルの認証、RPC_C_IMP_LEVEL_IDENTIFYの偽装レベル、および適切な null 以外のセキュリティ記述子を`CoInitializeSecurity`呼び出しで使用します。

ウィザードで生成された属性なしサービス プロジェクトの場合は、

[!code-cpp[NVC_ATL_Service#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_1.cpp)]

属性付きサービス プロジェクトの場合は、

[!code-cpp[NVC_ATL_ServiceAttrib#1](../../atl/reference/codesnippet/cpp/catlservicemodulet-class_2.cpp)]

## <a name="catlservicemoduletinstall"></a><a name="install"></a>サービスモジュール::インストール

サービスをインストールして作成します。

```
BOOL Install() throw();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

サービス コントロール マネージャー (SCM) データベースにサービスをインストールし、サービス オブジェクトを作成します。 サービスを作成できなかった場合は、メッセージ ボックスが表示され、メソッドは FALSE を返します。

## <a name="catlservicemoduletisinstalled"></a><a name="isinstalled"></a>サービスモジュールを使用します。

サービスがインストールされたことを確認します。

```
BOOL IsInstalled() throw();
```

### <a name="return-value"></a>戻り値

サービスがインストールされている場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="catlservicemoduletlogevent"></a><a name="logevent"></a>イベントを発生させます。

イベント ログに書き込みます。

```
void __cdecl LogEvent(LPCTSTR pszFormat, ...) throw();
```

### <a name="parameters"></a>パラメーター

*フォーマット*<br/>
イベント ログに書き込む文字列。

*...*<br/>
イベント ログに書き込む追加の文字列 (省略可能)。

### <a name="remarks"></a>解説

このメソッドは、関数[ReportEvent](/windows/win32/api/winbase/nf-winbase-reporteventw)を使用して、イベント ログに詳細を書き込みます。 サービスが実行されていない場合、文字列はコンソールに送信されます。

## <a name="catlservicemoduletm_bservice"></a><a name="m_bservice"></a>サービスサービスモジュール::m_bService

プログラムがサービスとして実行されていることを示すフラグ。

```
BOOL m_bService;
```

### <a name="remarks"></a>解説

サービス EXE とアプリケーション EXE を区別するために使用します。

## <a name="catlservicemoduletm_dwthreadid"></a><a name="m_dwthreadid"></a>サービスサービスモジュール::m_dwThreadID

サービスのスレッド識別子を格納するメンバー変数。

```
DWORD m_dwThreadID;
```

### <a name="remarks"></a>解説

この変数は、現在のスレッドのスレッド ID を格納します。

## <a name="catlservicemoduletm_hservicestatus"></a><a name="m_hservicestatus"></a>サービスモジュール::m_hServiceStatus

現在のサービスの状態情報構造体へのハンドルを格納するメンバー変数。

```
SERVICE_STATUS_HANDLE m_hServiceStatus;
```

### <a name="remarks"></a>解説

[SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status)構造体には、サービスに関する情報が含まれています。

## <a name="catlservicemoduletm_status"></a><a name="m_status"></a>m_status

現在のサービスの状態情報構造体を格納するメンバー変数。

```
SERVICE_STATUS m_status;
```

### <a name="remarks"></a>解説

[SERVICE_STATUS](/windows/win32/api/winsvc/ns-winsvc-service_status)構造体には、サービスに関する情報が含まれています。

## <a name="catlservicemoduletm_szservicename"></a><a name="m_szservicename"></a>サービスモジュール::m_szServiceName

登録するサービスの名前。

```
TCHAR [256] m_szServiceName;
```

### <a name="remarks"></a>解説

サービスの名前を格納する null で終わる文字列。

## <a name="catlservicemoduletoncontinue"></a><a name="oncontinue"></a>サービスモジュール::オンコニュ

サービスを続行するには、このメソッドをオーバーライドします。

```
void OnContinue() throw();
```

## <a name="catlservicemoduletoninterrogate"></a><a name="oninterrogate"></a>サービスモジュールT::オンアセアフェデ

サービスを問い取るために、このメソッドをオーバーライドします。

```
void OnInterrogate() throw();
```

## <a name="catlservicemoduletonpause"></a><a name="onpause"></a>サービスモジュール::オンポーズ

サービスを一時停止するには、このメソッドをオーバーライドします。

```
void OnPause() throw();
```

## <a name="catlservicemoduletonshutdown"></a><a name="onshutdown"></a>サービスモジュールT::シャットダウン時

サービスをシャットダウンするには、このメソッドをオーバーライドします。

```
void OnShutdown() throw();
```

## <a name="catlservicemoduletonstop"></a><a name="onstop"></a>サービスモジュール::オンストップ

サービスを停止するには、このメソッドをオーバーライドします。

```
void OnStop() throw();
```

## <a name="catlservicemoduletonunknownrequest"></a><a name="onunknownrequest"></a>サービスサービスモジュール::オンUnknownリクエスト

サービスに対する不明な要求を処理するには、このメソッドをオーバーライドします。

```
void OnUnknownRequest(DWORD /* dwOpcode*/) throw();
```

### <a name="parameters"></a>パラメーター

*ドウオプコード*<br/>
予約済み。

## <a name="catlservicemoduletparsecommandline"></a><a name="parsecommandline"></a>サービスモジュールT::Pアルセストライン

コマンド ラインを解析し、必要に応じて登録を実行します。

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>パラメーター

*ライン*<br/>
コマンド ライン。

*コード*<br/>
登録に対応する HRESULT (発生した場合)。

### <a name="return-value"></a>戻り値

成功した場合は true を返し、コマンド ラインに指定された RG ファイルを登録できなかった場合は false を返します。

### <a name="remarks"></a>解説

コマンド ラインを解析し、必要に応じて、指定された RGS ファイルを登録または登録解除します。 このメソッドは **、/RegServer**と **/アンレグサーバー**をチェックするために[CAtlExeModuleT::Parse コマンド ライン](../../atl/reference/catlexemodulet-class.md#parsecommandline)を呼び出します。 引数を追加**する -/サービス**は、サービスを登録します。

## <a name="catlservicemoduletpremessageloop"></a><a name="premessageloop"></a>サービスサービスモジュール::Pメッセージループ

このメソッドは、メッセージ ループに入る直前に呼び出されます。

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>パラメーター

*を表示します。*<br/>
このパラメーターは[、CAtlExeModuleT::Pメッセージループに渡されます](../../atl/reference/catlexemodulet-class.md#premessageloop)。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

サービスのカスタム初期化コードを追加するには、このメソッドをオーバーライドします。

## <a name="catlservicemoduletregisterappid"></a><a name="registerappid"></a>をクリックします。

サービスをレジストリに登録します。

```
inline HRESULT RegisterAppId(bool bService = false) throw();
```

### <a name="parameters"></a>パラメーター

*bサービス*<br/>
サービスとして登録するには true にする必要があります。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catlservicemoduletrun"></a><a name="run"></a>実行

サービスを実行します。

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>パラメーター

*を表示します。*<br/>
ウィンドウの表示方法を指定します。 このパラメーターは[、WinMain](/windows/win32/api/winbase/nf-winbase-winmain)セクションで説明されている値のいずれかです。 既定値は SW_HIDE です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

呼び出された`Run`後、呼び出し[、CAtlServiceModuleT::Pメッセージループ](#premessageloop)[、CAtlExeModuleT::および](../../atl/reference/catlexemodulet-class.md#runmessageloop)[CAtlExeModuleT::PostMessageLoop](../../atl/reference/catlexemodulet-class.md#postmessageloop)を呼び出します。

## <a name="catlservicemoduletservicemain"></a><a name="servicemain"></a>サービスサービスモジュール

このメソッドは、サービス コントロール マネージャによって呼び出されます。

```
void ServiceMain(DWORD dwArgc, LPTSTR* lpszArgv) throw();
```

### <a name="parameters"></a>パラメーター

*ドウアーク*<br/>
引数 argc。

*lpszArgv*<br/>
引数 argv。

### <a name="remarks"></a>解説

コントロール パネルの [サービス]`ServiceMain`アプリケーションを開き、サービスを選択して [開始] をクリックすると、サービス コントロール マネージャー (SCM) が呼び出されます。

SCM が呼`ServiceMain`び出された後、サービスは SCM にハンドラー関数を与える必要があります。 この機能により、SCM はサービスのステータスを取得し、特定の命令 (一時停止や停止など) を渡すことができます。 その後、[サービス](#run)の主な処理を実行するために呼び出されます。 `Run`サービスが停止するまで実行を継続します。

## <a name="catlservicemoduletsetservicestatus"></a><a name="setservicestatus"></a>サービス状況を設定します。

このメソッドは、サービスの状態を更新します。

```
void SetServiceStatus(DWORD dwState) throw();
```

### <a name="parameters"></a>パラメーター

*dwステート*<br/>
新しいステータス。 可能な値については[、サービスステータス](/windows/win32/api/winsvc/nf-winsvc-setservicestatus)の設定を参照してください。

### <a name="remarks"></a>解説

サービス コントロール マネージャのサービスのステータス情報を更新します。 これは[、CAtlServiceModuleT::実行](#run)[、CAtlServiceModuleT::サービスメイン](#servicemain)および他のハンドラーメソッドによって呼び出されます。 ステータスは、メンバー変数[CAtlServiceModuleT::m_status](#m_status)にも格納されます。

## <a name="catlservicemoduletstart"></a><a name="start"></a>開始

サービスの`CAtlServiceModuleT::WinMain`開始時に呼び出されます。

```
HRESULT Start(int nShowCmd) throw();
```

### <a name="parameters"></a>パラメーター

*を表示します。*<br/>
ウィンドウの表示方法を指定します。 このパラメーターは[、WinMain](/windows/win32/api/winbase/nf-winbase-winmain)セクションで説明されている値のいずれかです。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[CAtlServiceModuleT::WinMain](#winmain)メソッドは、登録とインストールの両方を処理するだけでなく、レジストリ エントリの削除とモジュールのアンインストールに関連するタスクも処理します。 サービスが実行されると、`WinMain`が`Start`呼び出されます。

## <a name="catlservicemoduletuninstall"></a><a name="uninstall"></a>をクリックします。

サービスを停止および削除します。

```
BOOL Uninstall() throw();
```

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

サービスの実行を停止し、サービス コントロール マネージャー データベースから削除します。

## <a name="catlservicemoduletunlock"></a><a name="unlock"></a>サービスモジュールT::ロック解除

サービスのロックカウントを減算します。

```
LONG Unlock() throw();
```

### <a name="return-value"></a>戻り値

ロックカウントを返します。

## <a name="catlservicemoduletunregisterappid"></a><a name="unregisterappid"></a>を登録解除します。

レジストリからサービスを削除します。

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catlservicemoduletwinmain"></a><a name="winmain"></a>サービスモジュール::ウィンメイン

このメソッドは、サービスを開始するために必要なコードを実装します。

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>パラメーター

*を表示します。*<br/>
ウィンドウの表示方法を指定します。 このパラメーターは[、WinMain](/windows/win32/api/winbase/nf-winbase-winmain)セクションで説明されている値のいずれかです。

### <a name="return-value"></a>戻り値

サービスの戻り値を返します。

### <a name="remarks"></a>解説

このメソッドは、コマンド ラインを処理し[(CAtlServiceModuleT::Parse コマンドライン](#parsecommandline)) を処理し、サービスを開始します ( [CAtlServiceModuleT::Start](#start)を使用して )。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/catlexemodulet-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
