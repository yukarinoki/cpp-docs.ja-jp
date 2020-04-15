---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::CAtlExeModuleT
- ATLBASE/ATL::CAtlExeModuleT::InitializeCom
- ATLBASE/ATL::CAtlExeModuleT::ParseCommandLine
- ATLBASE/ATL::CAtlExeModuleT::PostMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::PreMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::RegisterClassObjects
- ATLBASE/ATL::CAtlExeModuleT::RevokeClassObjects
- ATLBASE/ATL::CAtlExeModuleT::Run
- ATLBASE/ATL::CAtlExeModuleT::RunMessageLoop
- ATLBASE/ATL::CAtlExeModuleT::UninitializeCom
- ATLBASE/ATL::CAtlExeModuleT::Unlock
- ATLBASE/ATL::CAtlExeModuleT::WinMain
- ATLBASE/ATL::CAtlExeModuleT::m_bDelayShutdown
- ATLBASE/ATL::CAtlExeModuleT::m_dwPause
- ATLBASE/ATL::CAtlExeModuleT::m_dwTimeOut
helpviewer_keywords:
- CAtlExeModuleT class
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
ms.openlocfilehash: a20a02a467d74a89e3cda176a6a15961be4ffd61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318983"
---
# <a name="catlexemodulet-class"></a>クラス

このクラスは、アプリケーションのモジュールを表します。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE CAtlExeModuleT : public CAtlModuleT<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
クラスから派生`CAtlExeModuleT`したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#catlexemodulet)|コンストラクターです。|
|[をクリックします。](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#initializecom)|COM を初期化します。|
|[をクリック :Pします。](#parsecommandline)|コマンド ラインを解析し、必要に応じて登録を実行します。|
|[をクリック :Pします。](#postmessageloop)|このメソッドは、メッセージ ループが終了した直後に呼び出されます。|
|[を:P](#premessageloop)|このメソッドは、メッセージ ループに入る直前に呼び出されます。|
|[クラスクラスのオブジェクト](#registerclassobjects)|クラス オブジェクトを登録します。|
|[クラスオブジェクトを取り消す](#revokeclassobjects)|クラス オブジェクトを取り消します。|
|[実行](#run)|このメソッドは、EXE モジュール内のコードを実行して、初期化、メッセージ ループの実行、およびクリーンアップを実行します。|
|[をクリックします。](#runmessageloop)|このメソッドは、メッセージ ループを実行します。|
|[を初期化しません。](#uninitializecom)|COM の初期化を解除します。|
|[CAtlExeモジュール::ロック解除](#unlock)|モジュールのロックカウントを減算します。|
|[をクリックします。](#winmain)|このメソッドは、EXE を実行するために必要なコードを実装します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[をクリックします m_bDelayShutdown。](#m_bdelayshutdown)|モジュールのシャットダウンが遅れる必要があることを示すフラグ。|
|[m_dwPause](#m_dwpause)|すべてのオブジェクトがシャットダウン前に解放されるようにするために使用される一時停止値。|
|[カトルエクセスト::m_dwTimeOut](#m_dwtimeout)|モジュールのアンロードを遅延させるために使用されるタイムアウト値。|

## <a name="remarks"></a>解説

`CAtlExeModuleT`は、アプリケーション (EXE) のモジュールを表し、EXE の作成、コマンド ラインの処理、クラス オブジェクトの登録、メッセージ ループの実行、終了時のクリーンアップをサポートするコードを含んでいます。

このクラスは、EXE サーバー内の COM オブジェクトが継続的に作成および破棄される場合のパフォーマンスを向上させるように設計されています。 最後の COM オブジェクトが解放された後、EXE は[CAtlExeModuleT::m_dwTimeOut](#m_dwtimeout)データ メンバーで指定された期間待機します。 この期間中にアクティビティがない場合 (つまり、COM オブジェクトが作成されていない場合)、シャットダウンプロセスが開始されます。

[CAtlExeModuleT::m_bDelayShutdown](#m_bdelayshutdown)データ メンバーは、EXE が上記で定義したメカニズムを使用するかどうかを判断するために使用されるフラグです。 false に設定されている場合、モジュールは直ちに終了します。

ATL のモジュールの詳細については[、「ATL モジュール クラス](../../atl/atl-module-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[カトルモジュール](../../atl/reference/catlmodule-class.md)

[カトルモジュール](../../atl/reference/catlmodulet-class.md)

`CAtlExeModuleT`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="catlexemoduletcatlexemodulet"></a><a name="catlexemodulet"></a>をクリックします。

コンストラクターです。

```
CAtlExeModuleT() throw();
```

### <a name="remarks"></a>解説

EXE モジュールを初期化できなかった場合、WinMain は処理を行わずに直ちに戻ります。

## <a name="catlexemoduletcatlexemodulet"></a><a name="dtor"></a>をクリックします。

デストラクターです。

```
~CAtlExeModuleT() throw();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="catlexemoduletinitializecom"></a><a name="initializecom"></a>をクリックします。

COM を初期化します。

```
static HRESULT InitializeCom() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドはコンストラクターから呼び出され、既定の実装とは異なる方法で COM を初期化するためにオーバーライドできます。 既定の実装は、`CoInitializeEx(NULL, COINIT_MULTITHREADED)`プロジェクト`CoInitialize(NULL)`構成に応じて呼び出すか、または依存します。

通常、このメソッドをオーバーライドするには[、オーバーライド](#uninitializecom)する必要があります。

## <a name="catlexemoduletm_bdelayshutdown"></a><a name="m_bdelayshutdown"></a>をクリックします m_bDelayShutdown。

モジュールのシャットダウンが遅れる必要があることを示すフラグ。

```
bool m_bDelayShutdown;
```

### <a name="remarks"></a>解説

詳細については[、CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)の概要を参照してください。

## <a name="catlexemoduletm_dwpause"></a><a name="m_dwpause"></a>m_dwPause

シャットダウン前にすべてのオブジェクトがなくなることを確認するために使用される一時停止値。

```
DWORD m_dwPause;
```

### <a name="remarks"></a>解説

[CAtlExeModuleT::InitializeCom](#initializecom)を呼び出した後にこの値を変更して、サーバーをシャットダウンするための休止値として使用されるミリ秒数を設定します。 デフォルト値は 1000 ミリ秒です。

## <a name="catlexemoduletm_dwtimeout"></a><a name="m_dwtimeout"></a>カトルエクセスト::m_dwTimeOut

モジュールのアンロードを遅延させるために使用されるタイムアウト値。

```
DWORD m_dwTimeOut;
```

### <a name="remarks"></a>解説

[CAtlExeModuleT::InitializeCom](#initializecom)を呼び出した後にこの値を変更して、サーバーをシャットダウンするためのタイムアウト値として使用されるミリ秒数を定義します。 既定値は 5000 ミリ秒です。 詳細については[、CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)の概要を参照してください。

## <a name="catlexemoduletparsecommandline"></a><a name="parsecommandline"></a>をクリック :Pします。

コマンド ラインを解析し、必要に応じて登録を実行します。

```
bool ParseCommandLine(LPCTSTR lpCmdLine, HRESULT* pnRetCode) throw();
```

### <a name="parameters"></a>パラメーター

*ライン*<br/>
アプリケーションに渡されるコマンド ライン。

*コード*<br/>
登録に対応する HRESULT (発生した場合)。

### <a name="return-value"></a>戻り値

アプリケーションの実行を継続する場合は true を返し、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

このメソッドは[、CAtlExeModuleT::WinMain](#winmain)から呼び出され、コマンド ライン スイッチを処理するためにオーバーライドできます。 既定の実装では **、/RegServer**および **/UnRegServer**コマンド ライン引数をチェックし、登録または登録解除を実行します。

## <a name="catlexemoduletpostmessageloop"></a><a name="postmessageloop"></a>をクリック :Pします。

このメソッドは、メッセージ ループが終了した直後に呼び出されます。

```
HRESULT PostMessageLoop() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

カスタム アプリケーションのクリーンアップを実行するには、このメソッドをオーバーライドします。 既定の実装は[、CAtlExeModuleT::取り消しクラスオブジェクト](#revokeclassobjects)を呼び出します。

## <a name="catlexemoduletpremessageloop"></a><a name="premessageloop"></a>を:P

このメソッドは、メッセージ ループに入る直前に呼び出されます。

```
HRESULT PreMessageLoop(int nShowCmd) throw();
```

### <a name="parameters"></a>パラメーター

*を表示します。*<br/>
WinMain で*nShowCmd*パラメーターとして渡される値。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

アプリケーションのカスタム初期化コードを追加するには、このメソッドをオーバーライドします。 既定の実装では、クラス オブジェクトを登録します。

## <a name="catlexemoduletregisterclassobjects"></a><a name="registerclassobjects"></a>クラスクラスのオブジェクト

他のアプリケーションが OLE に接続できるように、クラス オブジェクトを OLE に登録します。

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>パラメーター

*コンテキスト*<br/>
クラス オブジェクトを実行するコンテキストを指定します。 指定できる値は、CLSCTX_INPROC_SERVER、CLSCTX_INPROC_HANDLER、またはCLSCTX_LOCAL_SERVERです。

*dwFlags*<br/>
クラス オブジェクトへの接続の種類を決定します。 指定できる値は、REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、またはREGCLS_MULTI_SEPARATEです。

### <a name="return-value"></a>戻り値

登録するクラスがなかった場合S_FALSE成功時にS_OKを返します。

## <a name="catlexemoduletrevokeclassobjects"></a><a name="revokeclassobjects"></a>クラスオブジェクトを取り消す

クラス オブジェクトを削除します。

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>戻り値

登録するクラスがなかった場合S_FALSE成功時にS_OKを返します。

## <a name="catlexemoduletrun"></a><a name="run"></a>実行

このメソッドは、EXE モジュール内のコードを実行して、初期化、メッセージ ループの実行、およびクリーンアップを実行します。

```
HRESULT Run(int nShowCmd = SW_HIDE) throw();
```

### <a name="parameters"></a>パラメーター

*を表示します。*<br/>
ウィンドウの表示方法を指定します。 このパラメーターは[、WinMain](/windows/win32/api/winbase/nf-winbase-winmain)セクションで説明されている値のいずれかです。 既定値は SW_HIDE です。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドはオーバーライドできます。 しかし、実際には[、代わりにCAtlExeModuleT::Pメッセージループ](#premessageloop)[、CAtlExeModuleT::または](#runmessageloop)[CAtlExeModuleT::PostMessageLoop](#postmessageloop)をオーバーライドする方が良いです。

## <a name="catlexemoduletrunmessageloop"></a><a name="runmessageloop"></a>をクリックします。

このメソッドは、メッセージ ループを実行します。

```
void RunMessageLoop() throw();
```

### <a name="remarks"></a>解説

このメソッドをオーバーライドして、メッセージ ループの動作を変更できます。

## <a name="catlexemoduletuninitializecom"></a><a name="uninitializecom"></a>を初期化しません。

COM の初期化を解除します。

```
static void UninitializeCom() throw();
```

### <a name="remarks"></a>解説

既定では、このメソッドは[単に CoUninitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize)を呼び出し、デストラクターから呼び出されます。 このメソッドをオーバーライドする場合[は、この](#initializecom)メソッドをオーバーライドします。

## <a name="catlexemoduletunlock"></a><a name="unlock"></a>CAtlExeモジュール::ロック解除

モジュールのロックカウントを減算します。

```
LONG Unlock() throw();
```

### <a name="return-value"></a>戻り値

診断またはテストに役立つ値を返します。

## <a name="catlexemoduletwinmain"></a><a name="winmain"></a>をクリックします。

このメソッドは、EXE を実行するために必要なコードを実装します。

```
int WinMain(int nShowCmd) throw();
```

### <a name="parameters"></a>パラメーター

*を表示します。*<br/>
ウィンドウの表示方法を指定します。 このパラメーターは[、WinMain](/windows/win32/api/winbase/nf-winbase-winmain)セクションで説明されている値のいずれかです。

### <a name="return-value"></a>戻り値

実行可能ファイルの戻り値を返します。

### <a name="remarks"></a>解説

このメソッドはオーバーライドできます。 オーバーライドする場合[、CAtlExeModuleT::Pメッセージループ](#premessageloop)[、CAtlExeModuleT::PostMessageLoop、](#postmessageloop)または[CAtlExeModuleT::RunMessageLoop](#runmessageloop)は、このメソッドを使用して`WinMain`関数をオーバーライドできます。

## <a name="see-also"></a>関連項目

[ATLダックサンプル](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../atl/reference/catlmodulet-class.md)<br/>
[クラス](../../atl/reference/catldllmodulet-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
