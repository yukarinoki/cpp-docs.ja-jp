---
title: CComModule クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 519837379369f08108d3d5b5b300fe0bcb9ac5e7
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083815"
---
# <a name="ccommodule-class"></a>CComModule クラス

ATL 7.0 では、時点で`CComModule`は非推奨: を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CComModule : public _ATL_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComModule::GetClassObject](#getclassobject)|指定した CLSID のオブジェクトを作成します。 Dll の場合のみです。|
|[CComModule::GetModuleInstance](#getmoduleinstance)|`m_hInst` を返します。|
|[CComModule::GetResourceInstance](#getresourceinstance)|`m_hInstResource` を返します。|
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib` を返します。|
|[Ccommodule::init](#init)|データ メンバーを初期化します。|
|[CComModule::RegisterClassHelper](#registerclasshelper)|オブジェクトの標準のクラスの登録をシステム レジストリに入力します。|
|[CComModule::RegisterClassObjects](#registerclassobjects)|クラスのオブジェクトを登録します。 Exe のみです。|
|[CComModule::RegisterServer](#registerserver)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。|
|[CComModule::RegisterTypeLib](#registertypelib)|タイプ ライブラリを登録します。|
|[CComModule::RevokeClassObjects](#revokeclassobjects)|クラスのオブジェクトを取り消します。 Exe のみです。|
|[CComModule::Term](#term)|データ メンバーを解放します。|
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|システム レジストリからオブジェクトの標準のクラスの登録を削除します。|
|[CComModule::UnregisterServer](#unregisterserver)|オブジェクト マップ内の各オブジェクトを登録解除します。|
|[CComModule::UpdateRegistryClass](#updateregistryclass)|登録または登録オブジェクトの標準のクラスの登録を解除します。|
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。|
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL レジストリ コンポーネントに静的にリンクします。 登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComModule::m_csObjMap](#m_csobjmap)|オブジェクト マップの情報への同期のアクセスを保証します。|
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|タイプ ライブラリ情報への同期のアクセスを保証します。|
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|ウィンドウ クラスの情報をウィンドウの作成時に使用される静的データの同期のアクセスを保証します。|
|[CComModule::m_hInst](#m_hinst)|モジュールのインスタンスを識別するハンドルが含まれています。|
|[CComModule::m_hInstResource](#m_hinstresource)|既定では、モジュールのインスタンスを識別するハンドルが含まれています。|
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|既定では、モジュールのインスタンスを識別するハンドルが含まれています。|
|[CComModule::m_pObjMap](#m_pobjmap)|モジュールのインスタンスによって管理されるオブジェクトのマップへのポインター。|

## <a name="remarks"></a>Remarks

> [!NOTE]
>  このクラスは非推奨し、ATL コードの生成ウィザードを使用して、今すぐ、 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md)と[CAtlModule](../../atl/reference/catlmodule-class.md)クラスを派生します。 参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。 ATL の以前のリリースで作成されたアプリケーションのために以下の情報が、します。 `CComModule` まだの ATL の旧バージョンと機能します。

`CComModule` クライアントが、モジュールのコンポーネントにアクセスできるよう、COM サーバー モジュールを実装します。 `CComModule` (インプロセス) の DLL と EXE (local) モジュールの両方をサポートしています。

A`CComModule`インスタンスは、クラスのオブジェクト定義のセットを維持するために、オブジェクトのマップを使用します。 このオブジェクトのマップがの配列として実装されている`_ATL_OBJMAP_ENTRY`、構造体し、の情報が含まれています。

- 入力して、システム レジストリ内のオブジェクトの説明を削除します。

- クラス ファクトリを使用してオブジェクトをインスタンス化します。

- コンポーネントで、クライアントと、ルート オブジェクト間の通信を確立します。

- クラス オブジェクトの有効期間管理を実行しています。

ATL COM の AppWizard を実行すると、ウィザードは自動的に生成`_Module`のグローバル インスタンス`CComModule`またはその派生クラス。 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)です。

ほかに`CComModule`、atl [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)、Exe および Windows サービス、アパートメント モデルのモジュールを実装します。 モジュールからの派生`CComAutoThreadModule`複数アパートメント内でオブジェクトを作成する場合。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

##  <a name="getclassobject"></a>  CComModule::GetClassObject

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

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

*ppv*<br/>
[out]によって識別されるインターフェイス ポインターへのポインター *riid*します。 オブジェクトは、このインターフェイスをサポートしていない場合*ppv* NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。

`GetClassObject` Dll をできるだけです。

##  <a name="getmoduleinstance"></a>  CComModule::GetModuleInstance

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>戻り値

このモジュールを識別する HINSTANCE。

### <a name="remarks"></a>Remarks

返します、 [m_hInst](#m_hinst)データ メンバー。

##  <a name="getresourceinstance"></a>  CComModule::GetResourceInstance

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>戻り値

HINSTANCE。

### <a name="remarks"></a>Remarks

返します、 [m_hInstResource](#m_hinstresource)データ メンバー。

##  <a name="gettypelibinstance"></a>  CComModule::GetTypeLibInstance

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>戻り値

HINSTANCE。

### <a name="remarks"></a>Remarks

返します、 [m_hInstTypeLib](#m_hinsttypelib)データ メンバー。

##  <a name="init"></a>  Ccommodule::init

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
[in]オブジェクト マップ エントリの配列へのポインター。

*h*<br/>
[in]渡される、HINSTANCE`DLLMain`または`WinMain`します。

*plibid*<br/>
[in]プロジェクトに関連付けられているタイプ ライブラリの LIBID へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

すべてのデータ メンバーを初期化します。

##  <a name="m_csobjmap"></a>  CComModule::m_csObjMap

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>Remarks

オブジェクト マップの同期のアクセスを保証します。

##  <a name="m_cstypeinfoholder"></a>  CComModule::m_csTypeInfoHolder

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>Remarks

タイプ ライブラリへの同期のアクセスを保証します。

##  <a name="m_cswindowcreate"></a>  CComModule::m_csWindowCreate

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>Remarks

ウィンドウ クラスの情報をウィンドウの作成時に使用される静的データの同期のアクセスを保証します。

##  <a name="m_hinst"></a>  CComModule::m_hInst

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>Remarks

モジュールのインスタンスを識別するハンドルが含まれています。

[Init](#init)メソッド セット`m_hInst`に渡されるハンドルを`DLLMain`または`WinMain`します。

##  <a name="m_hinstresource"></a>  CComModule::m_hInstResource

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>Remarks

既定では、モジュールのインスタンスを識別するハンドルが含まれています。

[Init](#init)メソッド セット`m_hInstResource`に渡されるハンドルを`DLLMain`または`WinMain`します。 明示的に設定することができます`m_hInstResource`にリソースを識別するハンドル。

[GetResourceInstance](#getresourceinstance)に格納されているハンドルを返します`m_hInstResource`します。

##  <a name="m_hinsttypelib"></a>  CComModule::m_hInstTypeLib

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>Remarks

既定では、モジュールのインスタンスを識別するハンドルが含まれています。

[Init](#init)メソッド セット`m_hInstTypeLib`に渡されるハンドルを`DLLMain`または`WinMain`します。 明示的に設定することができます`m_hInstTypeLib`にタイプ ライブラリを識別するハンドル。

[GetTypeLibInstance](#gettypelibinstance)に格納されているハンドルを返します`m_hInstTypeLib`します。

##  <a name="m_pobjmap"></a>  CComModule::m_pObjMap

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>Remarks

モジュールのインスタンスによって管理されるオブジェクトのマップへのポインター。

##  <a name="registerclasshelper"></a>  CComModule::RegisterClassHelper

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
[in]登録するオブジェクトの CLSID。

*lpszProgID*<br/>
[in]オブジェクトに関連付けられている ProgID です。

*lpszVerIndProgID*<br/>
[in]オブジェクトに関連付けられているバージョン依存 ProgID です。

*nDescID*<br/>
[in]オブジェクトの説明の文字列リソースの識別子。

*dwFlags*<br/>
[in]レジストリで入力するスレッド処理モデルを指定します。 指定できる値は、THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG は。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

オブジェクトの標準のクラスの登録をシステム レジストリに入力します。

[UpdateRegistryClass](#updateregistryclass)メソッド呼び出し`RegisterClassHelper`します。

##  <a name="registerclassobjects"></a>  CComModule::RegisterClassObjects

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>パラメーター

*dwClsContext*<br/>
[in]クラスのオブジェクトが実行コンテキストを指定します。 指定できる値は、CLSCTX_INPROC_SERVER や CLSCTX_INPROC_HANDLER、CLSCTX_LOCAL_SERVER は。 これらの値については、次を参照してください。 [CLSCTX](/windows/desktop/api/wtypesbase/ne-wtypesbase-tagclsctx) Windows SDK に含まれています。

*dwFlags*<br/>
[in]クラス オブジェクトへの接続の種類を決定します。 指定できる値は、REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、または REGCLS_MULTI_SEPARATE は。 これらの値については、次を参照してください。 [REGCLS](/windows/desktop/api/combaseapi/ne-combaseapi-tagregcls) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

他のアプリケーションが接続できるように、ole EXE クラス オブジェクトを登録します。 このメソッドは、exe だけです。

##  <a name="registerserver"></a>  CComModule::RegisterServer

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*bRegTypeLib*<br/>
[in]タイプ ライブラリを登録するかどうかを示します。 既定値は FALSE です。

*pclsid の値*<br/>
[in]登録するオブジェクトの CLSID を指します。 NULL (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトを登録するかどうか。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

に応じて、*と*パラメーターが 1 つのクラスのオブジェクトまたはオブジェクト マップ内のすべてのオブジェクトのシステムのレジストリを更新します。

場合*bRegTypeLib*が true の場合、タイプ ライブラリ情報も更新されます。

参照してください[OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto)オブジェクト マップにエントリを追加する方法についてはします。

`RegisterServer` によって自動的に呼び出される`DLLRegisterServer`dll または`WinMain`exe の実行、`/RegServer`コマンド ライン オプション。

##  <a name="registertypelib"></a>  CComModule::RegisterTypeLib

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>パラメーター

*lpszIndex*<br/>
[in]文字列の形式で`"\\N"`ここで、`N`はタイプ ライブラリのリソースの整数インデックスです。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

タイプ ライブラリに関する情報をシステム レジストリに追加します。

モジュールのインスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの 2 番目のバージョンを使用して、どのタイプ ライブラリを使用する必要がありますを指定します。

##  <a name="revokeclassobjects"></a>  CComModule::RevokeClassObjects

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

クラスのオブジェクトを削除します。 このメソッドは、exe だけです。

##  <a name="term"></a>  CComModule::Term

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
void Term() throw();
```

### <a name="remarks"></a>Remarks

すべてのデータ メンバーを解放します。

##  <a name="unregisterclasshelper"></a>  CComModule::UnregisterClassHelper

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
[in]登録を解除するオブジェクトの CLSID。

*lpszProgID*<br/>
[in]オブジェクトに関連付けられている ProgID です。

*lpszVerIndProgID*<br/>
[in]オブジェクトに関連付けられているバージョン依存 ProgID です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

システム レジストリからオブジェクトの標準のクラスの登録を削除します。

[UpdateRegistryClass](#updateregistryclass)メソッド呼び出し`UnregisterClassHelper`します。

##  <a name="unregisterserver"></a>  CComModule::UnregisterServer

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>パラメーター

*bUnRegTypeLib*<br/>
TRUE の場合、タイプ ライブラリ登録も解除されます。

*pclsid の値*<br/>
登録解除するオブジェクトの CLSID を指します。 場合は NULL (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトが登録されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

に応じて、*と*パラメーターには、1 つのクラスのオブジェクトまたはオブジェクト マップ内のすべてのオブジェクトのいずれかが登録解除します。

`UnregisterServer` によって自動的に呼び出される`DLLUnregisterServer`dll または`WinMain`exe の実行、`/UnregServer`コマンド ライン オプション。

参照してください[OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto)オブジェクト マップにエントリを追加する方法についてはします。

##  <a name="updateregistryclass"></a>  CComModule::UpdateRegistryClass

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

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

*clsid*<br/>
登録または登録解除するオブジェクトの CLSID。

*lpszProgID*<br/>
オブジェクトに関連付けられている ProgID です。

*lpszVerIndProgID*<br/>
オブジェクトに関連付けられているバージョン依存 ProgID です。

*nDescID*<br/>
オブジェクトの説明の文字列リソースの識別子です。

*szDesc*<br/>
オブジェクトの説明を含む文字列。

*dwFlags*<br/>
レジストリで入力するスレッド処理モデルを指定します。 指定できる値は、THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG は。

*bRegister*<br/>
オブジェクトを登録するかどうかを示します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

場合*bRegister*が true の場合、このメソッドは、システム レジストリで、オブジェクトの標準のクラスの登録を入力します。

場合*bRegister* false で、オブジェクトの登録を削除します。

値に応じて*bRegister*、`UpdateRegistryClass`いずれかを呼び出す[RegisterClassHelper](#registerclasshelper)または[UnregisterClassHelper](#unregisterclasshelper)します。

指定することによって、 [DECLARE_REGISTRY](registry-macros.md#declare_registry)マクロ、`UpdateRegistryClass`オブジェクト マップの処理時に自動的に呼び出されます。

##  <a name="updateregistryfromresourced"></a>  CComModule::UpdateRegistryFromResourceD

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

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
[in]リソースの名前。

*nResID*<br/>
[in]リソース id です。

*bRegister*<br/>
[in]オブジェクトを登録するかどうかを示します。

*この配列*<br/>
[in]スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、自動的に`%MODULE%`します。 追加の置き換え可能パラメーターを使用するには、詳細については、「解説」を参照してください。 それ以外の場合、NULL 既定値を使用します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

指定されたリソースに含まれるスクリプトを実行*lpszRes*または*nResID*します。

場合*bRegister*が true の場合、このメソッドは、システム レジストリで、オブジェクトを登録します。 それ以外の場合、オブジェクトは登録されません。

指定することによって、[に](registry-macros.md#declare_registry_resource)または[代入](registry-macros.md#declare_registry_resourceid)マクロ、`UpdateRegistryFromResourceD`オブジェクト マップの処理時に自動的に呼び出されます。

> [!NOTE]
>  実行時に置換値で置き換えると、代入マクロを指定しないでください。 配列を作成する代わりに、`_ATL_REGMAP_ENTRIES`構造、各エントリが変数のプレース ホルダーが含まれている実行時に、プレース ホルダーを置換する値と組み合わせて使用します。 呼び出して`UpdateRegistryFromResourceD`の配列を渡す、*この配列*パラメーター。 内のすべての置換値が追加されます、`_ATL_REGMAP_ENTRIES`レジストラーの置換のマップの構造体。

> [!NOTE]
>  ATL レジストリ コンポーネント (レジストラー) に静的にリンクするを参照してください。[次](#updateregistryfromresources)します。

置き換え可能パラメーターとスクリプト作成する方法の詳細については、記事を参照してください。 [、ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。

##  <a name="updateregistryfromresources"></a>  CComModule::UpdateRegistryFromResourceS

ATL 7.0 では、時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)の詳細。

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
[in]リソースの名前。

*nResID*<br/>
[in]リソース id です。

*bRegister*<br/>
[in]リソース スクリプトを登録する必要があるかどうかを示します。

*この配列*<br/>
[in]スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、自動的に`%MODULE%`します。 追加の置き換え可能パラメーターを使用するには、詳細については、「解説」を参照してください。 それ以外の場合、NULL 既定値を使用します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ような[ため](#updateregistryfromresourced)を除く`UpdateRegistryFromResourceS`ATL レジストリ コンポーネント (レジストラー) に静的にリンクを作成します。

`UpdateRegistryFromResourceS` 呼び出される自動的に、オブジェクトのマップが処理されるときに追加する指定`#define _ATL_STATIC_REGISTRY`stdafx.h にします。

> [!NOTE]
>  実行時に置換値を置き換えるには指定しないで、[に](registry-macros.md#declare_registry_resource)または[代入](registry-macros.md#declare_registry_resourceid)マクロ。 配列を作成する代わりに、`_ATL_REGMAP_ENTRIES`構造、各エントリが変数のプレース ホルダーが含まれている実行時に、プレース ホルダーを置換する値と組み合わせて使用します。 呼び出して`UpdateRegistryFromResourceS`の配列を渡す、*この配列*パラメーター。 内のすべての置換値が追加されます、`_ATL_REGMAP_ENTRIES`レジストラーの置換のマップの構造体。

置き換え可能パラメーターとスクリプト作成する方法の詳細については、記事を参照してください。 [、ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
