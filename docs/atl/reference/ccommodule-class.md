---
title: クラス
ms.date: 08/19/2019
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
ms.openlocfilehash: 652c5f078ddbaf8d3e333f7003d6515a94dd8f83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327760"
---
# <a name="ccommodule-class"></a>クラス

ATL 7.0 では`CComModule`、非推奨になりました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CComModule : public _ATL_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クラスオブジェクト](#getclassobject)|指定した CLSID のオブジェクトを作成します。 DLL の場合のみ。|
|[インスタンスを取得します。](#getmoduleinstance)|`m_hInst` が返されます。|
|[を使用します。](#getresourceinstance)|`m_hInstResource` が返されます。|
|[インスタンスを取得します。](#gettypelibinstance)|`m_hInstTypeLib` が返されます。|
|[ココムモジュール:イニト](#init)|データ メンバーを初期化します。|
|[クラスヘルパーを登録します。](#registerclasshelper)|システム レジストリにオブジェクトの標準クラス登録を入力します。|
|[クラスオブジェクトを登録します。](#registerclassobjects)|クラス オブジェクトを登録します。 EXE の場合のみ。|
|[をクリックします。](#registerserver)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。|
|[を使用します。](#registertypelib)|タイプ ライブラリを登録します。|
|[クラスオブジェクトを取り消す](#revokeclassobjects)|クラス オブジェクトを取り消します。 EXE の場合のみ。|
|[CComモジュール:用語](#term)|データ メンバーを解放します。|
|[クラスヘルパーを登録解除します。](#unregisterclasshelper)|システム レジストリからオブジェクトの標準クラス登録を削除します。|
|[サーバーを登録解除します。](#unregisterserver)|オブジェクト マップ内の各オブジェクトの登録を解除します。|
|[クラスを更新します。](#updateregistryclass)|オブジェクトの標準クラス登録を登録または登録解除します。|
|[リソースからレジストリを更新します。](#updateregistryfromresourced)|オブジェクトを登録または登録解除するために、指定したリソースに含まれるスクリプトを実行します。|
|[リソースからレジストリを更新します。](#updateregistryfromresources)|ATL レジストリ コンポーネントに静的にリンクします。 オブジェクトを登録または登録解除するために、指定したリソースに含まれるスクリプトを実行します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ココムモジュール:m_csObjMap](#m_csobjmap)|オブジェクト マップ情報への同期アクセスを保証します。|
|[コムモジュール:m_csTypeInfoHolder](#m_cstypeinfoholder)|タイプ ライブラリ情報への同期アクセスを保証します。|
|[コムモジュール::m_csWindowCreate](#m_cswindowcreate)|ウィンドウの作成時に使用されるウィンドウ クラス情報と静的データへの同期アクセスを保証します。|
|[ココムモジュール::m_hInst](#m_hinst)|モジュール インスタンスへのハンドルを格納します。|
|[ココムモジュール:m_hInstResource](#m_hinstresource)|既定では、モジュール インスタンスへのハンドルが含まれます。|
|[ココムモジュール:m_hInstTypeLib](#m_hinsttypelib)|既定では、モジュール インスタンスへのハンドルが含まれます。|
|[ココムモジュール:m_pObjMap](#m_pobjmap)|モジュール インスタンスによって維持されるオブジェクト マップへのポイント。|

## <a name="remarks"></a>解説

> [!NOTE]
> このクラスは非推奨となっており、ATL コード生成ウィザードでは[、CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)および[CAtlModule](../../atl/reference/catlmodule-class.md)派生クラスが使用されるようになりました。 詳細については[、「ATL モジュール クラス](../../atl/atl-module-classes.md)」を参照してください。 以下の情報は、ATL の古いリリースで作成されたアプリケーションで使用するためのものです。 `CComModule`は、後方機能の ATL の一部です。

`CComModule`は、クライアントがモジュールのコンポーネントにアクセスできるように、COM サーバー モジュールを実装します。 `CComModule`DLL (インプロセス) モジュールと EXE (ローカル) モジュールの両方をサポートします。

インスタンス`CComModule`は、オブジェクト マップを使用して、クラス オブジェクト定義のセットを維持します。 このオブジェクト マップは構造体の配列として実装`_ATL_OBJMAP_ENTRY`され、次の情報が含まれています。

- システム レジストリでオブジェクトの説明を入力および削除する。

- クラス ファクトリを通じてオブジェクトをインスタンス化する。

- クライアントとコンポーネント内のルート オブジェクトとの間の通信を確立します。

- クラス オブジェクトの有効期間管理を実行する。

ATL COM AppWizard を実行すると、ウィザードによって、`_Module`のグローバル インスタンス`CComModule`または派生クラスが自動的に生成されます。 ATL プロジェクト ウィザードの詳細については、ATL[プロジェクトの作成に関する記事を](../../atl/reference/creating-an-atl-project.md)参照してください。

ATL`CComModule`には、Exes および Windows サービス用のアパートメント モデル モジュールを実装する[CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)も用意されています。 複数のアパートメントに`CComAutoThreadModule`オブジェクトを作成する場合からモジュールを派生します。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[カトルモジュール](../../atl/reference/catlmodule-class.md)

[カトルモジュール](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccommodulegetclassobject"></a><a name="getclassobject"></a>クラスオブジェクト

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>パラメーター

*rclsid*<br/>
[in]作成するオブジェクトの CLSID。

*riid*<br/>
[in]要求されたインターフェイスの IID。

*Ppv*<br/>
[アウト]*riid*によって識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppv*は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。

`GetClassObject`は DLL でのみ使用できます。

## <a name="ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>インスタンスを取得します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>戻り値

このモジュールを識別する HINSTANCE。

### <a name="remarks"></a>解説

[m_hInst](#m_hinst)データ メンバーを返します。

## <a name="ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a>を使用します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>戻り値

インスタンス。

### <a name="remarks"></a>解説

[m_hInstResource](#m_hinstresource)データ メンバーを返します。

## <a name="ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a>インスタンスを取得します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>戻り値

インスタンス。

### <a name="remarks"></a>解説

[m_hInstTypeLib](#m_hinsttypelib)データ メンバーを返します。

## <a name="ccommoduleinit"></a><a name="init"></a>ココムモジュール:イニト

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]オブジェクト マップ エントリの配列へのポインター。

*H*<br/>
[in]HINSTANCE は`DLLMain`または`WinMain`に渡されます。

*プリビッド*<br/>
[in]プロジェクトに関連付けられているタイプ ライブラリの LIBID へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

すべてのデータ メンバーを初期化します。

## <a name="ccommodulem_csobjmap"></a><a name="m_csobjmap"></a>ココムモジュール:m_csObjMap

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>解説

オブジェクト マップへの同期アクセスを保証します。

## <a name="ccommodulem_cstypeinfoholder"></a><a name="m_cstypeinfoholder"></a>コムモジュール:m_csTypeInfoHolder

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>解説

タイプ ライブラリへの同期アクセスを保証します。

## <a name="ccommodulem_cswindowcreate"></a><a name="m_cswindowcreate"></a>コムモジュール::m_csWindowCreate

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>解説

ウィンドウの作成時に使用されるウィンドウ クラス情報と静的データへの同期アクセスを保証します。

## <a name="ccommodulem_hinst"></a><a name="m_hinst"></a>ココムモジュール::m_hInst

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>解説

モジュール インスタンスへのハンドルを格納します。

[Init](#init)メソッドは`m_hInst`、 または`WinMain`に`DLLMain`渡されたハンドルに設定します。

## <a name="ccommodulem_hinstresource"></a><a name="m_hinstresource"></a>ココムモジュール:m_hInstResource

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>解説

既定では、モジュール インスタンスへのハンドルが含まれます。

[Init](#init)メソッドは`m_hInstResource`、 または`WinMain`に`DLLMain`渡されたハンドルに設定します。 リソースのハンドルを明示的`m_hInstResource`に設定できます。

メソッドは[、](#getresourceinstance)に`m_hInstResource`格納されているハンドルを返します。

## <a name="ccommodulem_hinsttypelib"></a><a name="m_hinsttypelib"></a>ココムモジュール:m_hInstTypeLib

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>解説

既定では、モジュール インスタンスへのハンドルが含まれます。

[Init](#init)メソッドは`m_hInstTypeLib`、 または`WinMain`に`DLLMain`渡されたハンドルに設定します。 タイプ ライブラリのハンドル`m_hInstTypeLib`に明示的に設定できます。

メソッドは[、](#gettypelibinstance)に`m_hInstTypeLib`格納されているハンドルを返します。

## <a name="ccommodulem_pobjmap"></a><a name="m_pobjmap"></a>ココムモジュール:m_pObjMap

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>解説

モジュール インスタンスによって維持されるオブジェクト マップへのポイント。

## <a name="ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a>クラスヘルパーを登録します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
ATL_DEPRECATED HRESULT RegisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
[in]登録するオブジェクトの CLSID。

*をクリックします。*<br/>
[in]オブジェクトに関連付けられている ProgID。

*プシズベリドプログID*<br/>
[in]オブジェクトに関連付けられているバージョンに依存しない ProgID。

*nデスクジド*<br/>
[in]オブジェクトの説明の文字列リソースの識別子。

*dwFlags*<br/>
[in]レジストリに入力するスレッド モデルを指定します。 指定できる値は、THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

システム レジストリにオブジェクトの標準クラス登録を入力します。

メソッド[を](#updateregistryclass)呼び出`RegisterClassHelper`します。

## <a name="ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a>クラスオブジェクトを登録します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>パラメーター

*コンテキスト*<br/>
[in]クラス オブジェクトを実行するコンテキストを指定します。 指定できる値は、CLSCTX_INPROC_SERVER、CLSCTX_INPROC_HANDLER、またはCLSCTX_LOCAL_SERVERです。 これらの値の説明については、Windows SDK[の CLSCTX](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx)を参照してください。

*dwFlags*<br/>
[in]クラス オブジェクトへの接続の種類を決定します。 指定できる値は、REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、またはREGCLS_MULTI_SEPARATEです。 これらの値の説明については、Windows SDK[の REGCLS](/windows/win32/api/combaseapi/ne-combaseapi-regcls)を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

EXE クラス オブジェクトを OLE に登録して、他のアプリケーションが接続できるようにします。 このメソッドは、EXE でのみ使用できます。

## <a name="ccommoduleregisterserver"></a><a name="registerserver"></a>をクリックします。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
[in]タイプ ライブラリを登録するかどうかを示します。 既定値は FALSE です。

*pCLSID*<br/>
[in]登録するオブジェクトの CLSID へのポイント。 NULL (既定値) の場合、オブジェクト マップ内のすべてのオブジェクトが登録されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*pCLSID*パラメーターに応じて、単一のクラス オブジェクトまたはオブジェクト マップ内のすべてのオブジェクトのシステム レジストリを更新します。

*bRegTypeLib*が TRUE の場合、タイプ ライブラリ情報も更新されます。

オブジェクト マップにエントリを追加する方法については[、OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto)を参照してください。

`RegisterServer`は、DLL`DLLRegisterServer`の場合は自動的に呼`WinMain`び出されるか、EXE`/RegServer`がコマンド ライン オプションを使用して実行されます。

## <a name="ccommoduleregistertypelib"></a><a name="registertypelib"></a>を使用します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>パラメーター

*インデックスを使用します。*<br/>
[in]形式`"\\N"`の文字列は、TYPELIB`N`リソースの整数インデックスです。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

タイプ ライブラリに関する情報をシステム レジストリに追加します。

モジュール インスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの 2 番目のバージョンを使用して、使用するタイプ ライブラリを指定します。

## <a name="ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a>クラスオブジェクトを取り消す

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

クラス オブジェクトを削除します。 このメソッドは、EXE でのみ使用できます。

## <a name="ccommoduleterm"></a><a name="term"></a>CComモジュール:用語

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
void Term() throw();
```

### <a name="remarks"></a>解説

すべてのデータ メンバーを解放します。

## <a name="ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a>クラスヘルパーを登録解除します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
[in]登録解除するオブジェクトの CLSID。

*をクリックします。*<br/>
[in]オブジェクトに関連付けられている ProgID。

*プシズベリドプログID*<br/>
[in]オブジェクトに関連付けられているバージョンに依存しない ProgID。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

システム レジストリからオブジェクトの標準クラス登録を削除します。

メソッド[を](#updateregistryclass)呼び出`UnregisterClassHelper`します。

## <a name="ccommoduleunregisterserver"></a><a name="unregisterserver"></a>サーバーを登録解除します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
TRUE の場合、タイプ ライブラリも登録解除されます。

*pCLSID*<br/>
登録解除するオブジェクトの CLSID へのポイント。 NULL (既定値) の場合、オブジェクト マップ内のすべてのオブジェクトの登録が解除されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*pCLSID*パラメーターに応じて、単一のクラス・オブジェクトまたはオブジェクト・マップ内のすべてのオブジェクトの登録を解除します。

`UnregisterServer`は、DLL`DLLUnregisterServer`の場合は自動的に呼`WinMain`び出されるか、EXE`/UnregServer`がコマンド ライン オプションを使用して実行されます。

オブジェクト マップにエントリを追加する方法については[、OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto)を参照してください。

## <a name="ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a>クラスを更新します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
登録または登録解除するオブジェクトの CLSID。

*をクリックします。*<br/>
オブジェクトに関連付けられている ProgID。

*プシズベリドプログID*<br/>
オブジェクトに関連付けられているバージョンに依存しない ProgID。

*nデスクジド*<br/>
オブジェクトの説明の文字列リソースの識別子。

*szDesc*<br/>
オブジェクトの説明を含む文字列。

*dwFlags*<br/>
レジストリに入力するスレッド モデルを指定します。 指定できる値は、THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG です。

*b登録*<br/>
オブジェクトを登録するかどうかを示します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*bRegister*が TRUE の場合、このメソッドは、システム レジストリにオブジェクトの標準クラス登録を入力します。

*bRegister*が FALSE の場合、オブジェクトの登録を削除します。

*bRegister*の値に応じて`UpdateRegistryClass`、[レジスタクラスヘルパー](#registerclasshelper)または[登録解除クラスヘルパー](#unregisterclasshelper)を呼び出します。

[DECLARE_REGISTRY](registry-macros.md#declare_registry)マクロを指定すると、`UpdateRegistryClass`オブジェクト マップが処理されるときに自動的に呼び出されます。

## <a name="ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>リソースからレジストリを更新します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
virtual HRESULT UpdateRegistryFromResourceD(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```

### <a name="parameters"></a>パラメーター

*lpszRes*<br/>
[in]リソース名。

*nResID*<br/>
[in]リソース ID。

*b登録*<br/>
[in]オブジェクトを登録するかどうかを示します。

*エントリ*<br/>
[in]スクリプトの置き換え可能パラメーターに関連付けられた値を格納する置換マップへのポインター。 ATL は`%MODULE%`自動的に を使用します。 追加の置き換え可能パラメータを使用する方法については、「解説」を参照してください。 それ以外の場合は、NULL の既定値を使用します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*lpszRes*または*nResID*で指定されたリソースに含まれるスクリプトを実行します。

*bRegister*が TRUE の場合、このメソッドはオブジェクトをシステム レジストリに登録します。それ以外の場合は、オブジェクトの登録を解除します。

[DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource)または[DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid)マクロを指定すると、`UpdateRegistryFromResourceD`オブジェクト マップの処理時に自動的に呼び出されます。

> [!NOTE]
> 実行時に置換値を置き換える場合は、DECLARE_REGISTRY_RESOURCEまたはマクロDECLARE_REGISTRY_RESOURCEID指定しないでください。 代わりに、構造体の`_ATL_REGMAP_ENTRIES`配列を作成し、各エントリには、実行時にプレースホルダーを置き換える値と組み合わせた変数のプレースホルダーが含まれています。 次に`UpdateRegistryFromResourceD`*、pMapEntries*パラメーターの配列を渡して 呼び出します。 これにより、構造体内のすべての置換値が`_ATL_REGMAP_ENTRIES`レジストラーの置換マップに追加されます。

> [!NOTE]
> ATL レジストリ コンポーネント (レジストラー) に静的にリンクするには、「[リソースリソースからレジストリを静的にリンク](#updateregistryfromresources)する」を参照してください。

置き換え可能なパラメータとスクリプトの詳細については[、「ATL レジストリ コンポーネント (レジストラー)」](../../atl/atl-registry-component-registrar.md)を参照してください。

## <a name="ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>リソースからレジストリを更新します。

ATL 7.0 では`CComModule`、廃止されました:[詳細については、ATL モジュール クラス](../../atl/atl-module-classes.md)を参照してください。

```
virtual HRESULT UpdateRegistryFromResourceS(
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*lpszRes*<br/>
[in]リソース名。

*nResID*<br/>
[in]リソース ID。

*b登録*<br/>
[in]リソース スクリプトを登録するかどうかを示します。

*エントリ*<br/>
[in]スクリプトの置き換え可能パラメーターに関連付けられた値を格納する置換マップへのポインター。 ATL は`%MODULE%`自動的に を使用します。 追加の置き換え可能パラメータを使用する方法については、「解説」を参照してください。 それ以外の場合は、NULL の既定値を使用します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL レジストリ コンポーネント (`UpdateRegistryFromResourceS`レジストラー) への静的リンクを作成する以外は[、UpdateRegistryFromResourceD](#updateregistryfromresourced)と同様です。

`UpdateRegistryFromResourceS`オブジェクト マップが処理されると、*オブジェクト*マップが処理されるときに自動的に`#define _ATL_STATIC_REGISTRY`呼び出されます ( visual Studio 2017 以前のバージョンでは *、stdafx.h)* に追加します。

> [!NOTE]
> 実行時に置換値を置き換える場合は[、DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource)または[DECLARE_REGISTRY_RESOURCEIDマクロを](registry-macros.md#declare_registry_resourceid)指定しないでください。 代わりに、構造体の`_ATL_REGMAP_ENTRIES`配列を作成し、各エントリには、実行時にプレースホルダーを置き換える値と組み合わせた変数のプレースホルダーが含まれています。 次に`UpdateRegistryFromResourceS`*、pMapEntries*パラメーターの配列を渡して 呼び出します。 これにより、構造体内のすべての置換値が`_ATL_REGMAP_ENTRIES`レジストラーの置換マップに追加されます。

置き換え可能なパラメータとスクリプトの詳細については[、「ATL レジストリ コンポーネント (レジストラー)」](../../atl/atl-registry-component-registrar.md)を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
