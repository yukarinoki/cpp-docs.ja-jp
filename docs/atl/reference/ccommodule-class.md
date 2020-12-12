---
description: '詳細情報: CComModule クラス'
title: CComModule クラス
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
ms.openlocfilehash: dd0ec6c6aa7d68374a90830b10815a9cbdd54aeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152023"
---
# <a name="ccommodule-class"></a>CComModule クラス

ATL 7.0 では、 `CComModule` が非推奨とされます。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

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
|[CComModule:: GetClassObject](#getclassobject)|指定された CLSID のオブジェクトを作成します。 Dll の場合のみ。|
|[CComModule:: GetModuleInstance](#getmoduleinstance)|`m_hInst` が返されます。|
|[CComModule:: GetResourceInstance](#getresourceinstance)|`m_hInstResource` が返されます。|
|[CComModule:: GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib` が返されます。|
|[CComModule:: Init](#init)|データメンバーを初期化します。|
|[CComModule:: RegisterClassHelper](#registerclasshelper)|オブジェクトの標準クラスの登録をシステムレジストリに入力します。|
|[CComModule:: RegisterClassObjects](#registerclassobjects)|クラスオブジェクトを登録します。 Exe の場合のみ。|
|[CComModule:: RegisterServer](#registerserver)|オブジェクトマップ内の各オブジェクトのシステムレジストリを更新します。|
|[CComModule:: RegisterTypeLib](#registertypelib)|タイプ ライブラリを登録します。|
|[CComModule:: RevokeClassObjects](#revokeclassobjects)|クラスオブジェクトを取り消します。 Exe の場合のみ。|
|[CComModule:: Term](#term)|データメンバーを解放します。|
|[CComModule:: UnregisterClassHelper](#unregisterclasshelper)|オブジェクトの標準クラスの登録をシステムレジストリから削除します。|
|[CComModule:: UnregisterServer](#unregisterserver)|オブジェクトマップ内の各オブジェクトの登録を解除します。|
|[CComModule:: UpdateRegistryClass](#updateregistryclass)|オブジェクトの標準クラスの登録を登録または登録解除します。|
|[CComModule:: UpdateRegistryFromResourceD](#updateregistryfromresourced)|指定したリソースに含まれているスクリプトを実行して、オブジェクトの登録または登録解除を行います。|
|[CComModule:: UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL レジストリコンポーネントに静的にリンクします。 指定したリソースに含まれているスクリプトを実行して、オブジェクトの登録または登録解除を行います。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComModule:: m_csObjMap](#m_csobjmap)|オブジェクトマップ情報への同期アクセスを保証します。|
|[CComModule:: m_csTypeInfoHolder](#m_cstypeinfoholder)|タイプライブラリ情報への同期アクセスを保証します。|
|[CComModule:: m_csWindowCreate](#m_cswindowcreate)|ウィンドウの作成時に使用されるウィンドウクラス情報と静的データへの同期アクセスを保証します。|
|[CComModule:: m_hInst](#m_hinst)|モジュールインスタンスへのハンドルを格納します。|
|[CComModule:: m_hInstResource](#m_hinstresource)|既定では、にはモジュールインスタンスへのハンドルが格納されます。|
|[CComModule:: m_hInstTypeLib](#m_hinsttypelib)|既定では、にはモジュールインスタンスへのハンドルが格納されます。|
|[CComModule:: m_pObjMap](#m_pobjmap)|モジュールインスタンスによって管理されるオブジェクトマップを指します。|

## <a name="remarks"></a>解説

> [!NOTE]
> このクラスは非推奨とされており、ATL コード生成ウィザードでは、 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) および [CAtlModule](../../atl/reference/catlmodule-class.md) 派生クラスが使用されるようになりました。 詳細については、「 [ATL モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。 次の情報は、ATL の旧リリースで作成されたアプリケーションで使用されます。 `CComModule` は、後方の機能のために ATL の一部になっています。

`CComModule` COM サーバーモジュールを実装して、クライアントがモジュールのコンポーネントにアクセスできるようにします。 `CComModule` では、DLL (インプロセス) モジュールと EXE (ローカル) モジュールの両方がサポートされています。

インスタンスは、オブジェクトマップを使用して、 `CComModule` クラスオブジェクト定義のセットを保持します。 このオブジェクトマップは、構造体の配列として実装され `_ATL_OBJMAP_ENTRY` 、次の情報が含まれています。

- システムレジストリにオブジェクトの説明を入力および削除します。

- クラスファクトリを使用したオブジェクトのインスタンス化。

- クライアントと、コンポーネント内のルートオブジェクトとの間の通信を確立します。

- クラスオブジェクトの有効期間の管理を実行しています。

ATL COM AppWizard を実行すると、ウィザードによって `_Module` 、のグローバルインスタンス、 `CComModule` またはそれから派生したクラスが自動的に生成されます。 ATL プロジェクトウィザードの詳細については、「 [Atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)」を参照してください。

に加えて `CComModule` 、ATL には、exe および Windows サービス用のアパートメントモデルモジュールを実装する [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)が用意されています。 `CComAutoThreadModule`複数のアパートメントでオブジェクトを作成する場合は、からモジュールを派生させます。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

[CAtlModuleT](../../atl/reference/catlmodulet-class.md)

`CComModule`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="ccommodulegetclassobject"></a><a name="getclassobject"></a> CComModule:: GetClassObject

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HRESULT GetClassObject(
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```

### <a name="parameters"></a>パラメーター

*rclsid*<br/>
から作成するオブジェクトの CLSID。

*riid*<br/>
から要求されたインターフェイスの IID。

*ppv*<br/>
入出力 *Riid* によって識別されるインターフェイスポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合、 *ppv* は NULL に設定されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

指定した CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイスポインターを取得します。

`GetClassObject` は、Dll でのみ使用できます。

## <a name="ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a> CComModule:: GetModuleInstance

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>戻り値

このモジュールを識別する HINSTANCE。

### <a name="remarks"></a>解説

[M_hInst](#m_hinst)データメンバーを返します。

## <a name="ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a> CComModule:: GetResourceInstance

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>戻り値

HINSTANCE。

### <a name="remarks"></a>解説

[M_hInstResource](#m_hinstresource)データメンバーを返します。

## <a name="ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a> CComModule:: GetTypeLibInstance

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HINSTANCE GetTypeLibInstance() const throw();
```

### <a name="return-value"></a>戻り値

HINSTANCE。

### <a name="remarks"></a>解説

[M_hInstTypeLib](#m_hinsttypelib)データメンバーを返します。

## <a name="ccommoduleinit"></a><a name="init"></a> CComModule:: Init

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
からオブジェクトマップエントリの配列へのポインター。

*h*<br/>
からまたはに渡される HINSTANCE `DLLMain` `WinMain` 。

*plibid*<br/>
からプロジェクトに関連付けられているタイプライブラリの LIBID へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

すべてのデータメンバーを初期化します。

## <a name="ccommodulem_csobjmap"></a><a name="m_csobjmap"></a> CComModule:: m_csObjMap

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
CRITICAL_SECTION m_csObjMap;
```

### <a name="remarks"></a>解説

オブジェクトマップへの同期アクセスを保証します。

## <a name="ccommodulem_cstypeinfoholder"></a><a name="m_cstypeinfoholder"></a> CComModule:: m_csTypeInfoHolder

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
CRITICAL_SECTION m_csTypeInfoHolder;
```

### <a name="remarks"></a>解説

タイプライブラリへの同期アクセスを保証します。

## <a name="ccommodulem_cswindowcreate"></a><a name="m_cswindowcreate"></a> CComModule:: m_csWindowCreate

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
CRITICAL_SECTION m_csWindowCreate;
```

### <a name="remarks"></a>解説

ウィンドウクラスの情報と、ウィンドウの作成時に使用される静的データへの同期アクセスを保証します。

## <a name="ccommodulem_hinst"></a><a name="m_hinst"></a> CComModule:: m_hInst

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HINSTANCE m_hInst;
```

### <a name="remarks"></a>解説

モジュールインスタンスへのハンドルを格納します。

[Init](#init)メソッドは、 `m_hInst` またはに渡されるハンドルにを設定し `DLLMain` `WinMain` ます。

## <a name="ccommodulem_hinstresource"></a><a name="m_hinstresource"></a> CComModule:: m_hInstResource

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HINSTANCE m_hInstResource;
```

### <a name="remarks"></a>解説

既定では、にはモジュールインスタンスへのハンドルが格納されます。

[Init](#init)メソッドは、 `m_hInstResource` またはに渡されるハンドルにを設定し `DLLMain` `WinMain` ます。 明示的にリソースをハンドルするように設定でき `m_hInstResource` ます。

[Getresourceinstance](#getresourceinstance)メソッドは、に格納されているハンドルを返し `m_hInstResource` ます。

## <a name="ccommodulem_hinsttypelib"></a><a name="m_hinsttypelib"></a> CComModule:: m_hInstTypeLib

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HINSTANCE m_hInstTypeLib;
```

### <a name="remarks"></a>解説

既定では、にはモジュールインスタンスへのハンドルが格納されます。

[Init](#init)メソッドは、 `m_hInstTypeLib` またはに渡されるハンドルにを設定し `DLLMain` `WinMain` ます。 を明示的に `m_hInstTypeLib` タイプライブラリへのハンドルに設定できます。

[GetTypeLibInstance](#gettypelibinstance)メソッドは、に格納されているハンドルを返し `m_hInstTypeLib` ます。

## <a name="ccommodulem_pobjmap"></a><a name="m_pobjmap"></a> CComModule:: m_pObjMap

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```

### <a name="remarks"></a>解説

モジュールインスタンスによって管理されるオブジェクトマップを指します。

## <a name="ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a> CComModule:: RegisterClassHelper

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

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
から登録するオブジェクトの CLSID。

*lpszProgID*<br/>
からオブジェクトに関連付けられている ProgID。

*lpszVerIndProgID*<br/>
からオブジェクトに関連付けられているバージョンに依存しない ProgID。

*nDescID*<br/>
からオブジェクトの説明の文字列リソースの識別子。

*dwFlags*<br/>
からレジストリに入力するスレッド処理モデルを指定します。 指定できる値は、THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

オブジェクトの標準クラスの登録をシステムレジストリに入力します。

[UpdateRegistryClass](#updateregistryclass)メソッドはを呼び出し `RegisterClassHelper` ます。

## <a name="ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a> CComModule:: RegisterClassObjects

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```

### <a name="parameters"></a>パラメーター

*dwClsContext*<br/>
からクラスオブジェクトを実行するコンテキストを指定します。 指定できる値は、CLSCTX_INPROC_SERVER、CLSCTX_INPROC_HANDLER、または CLSCTX_LOCAL_SERVER です。 これらの値の詳細については、Windows SDK の「 [Clsctx](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx) 」を参照してください。

*dwFlags*<br/>
からクラスオブジェクトへの接続の種類を決定します。 指定できる値は、REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、または REGCLS_MULTI_SEPARATE です。 これらの値の詳細については、Windows SDK の「 [Regcls](/windows/win32/api/combaseapi/ne-combaseapi-regcls) 」を参照してください。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

他のアプリケーションが接続できるように、EXE クラスのオブジェクトを OLE に登録します。 このメソッドは、Exe でのみ使用できます。

## <a name="ccommoduleregisterserver"></a><a name="registerserver"></a> CComModule:: RegisterServer

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*bRegTypeLib*<br/>
からタイプライブラリを登録するかどうかを示します。 既定値は FALSE です。

*pCLSID*<br/>
から登録するオブジェクトの CLSID を指します。 NULL (既定値) の場合、オブジェクトマップ内のすべてのオブジェクトが登録されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*Pclsid* パラメーターに応じて、によって、単一のクラスオブジェクトまたはオブジェクトマップ内のすべてのオブジェクトのシステムレジストリが更新されます。

*Bregtypelib* が TRUE の場合は、タイプライブラリ情報も更新されます。

オブジェクトマップにエントリを追加する方法については、「 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 」を参照してください。

`RegisterServer` は、DLL に対して、 `DLLRegisterServer` または `WinMain` コマンドラインオプションを指定して実行される EXE によって、によって自動的に呼び出され `/RegServer` ます。

## <a name="ccommoduleregistertypelib"></a><a name="registertypelib"></a> CComModule:: RegisterTypeLib

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```

### <a name="parameters"></a>パラメーター

*lpszIndex*<br/>
から形式の文字列 `"\\N"` 。ここで、 `N` は TYPELIB リソースの整数インデックスです。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

タイプライブラリに関する情報をシステムレジストリに追加します。

モジュールインスタンスに複数のタイプライブラリが含まれている場合は、このメソッドの2番目のバージョンを使用して、使用するタイプライブラリを指定します。

## <a name="ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a> CComModule:: RevokeClassObjects

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HRESULT RevokeClassObjects() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

クラスオブジェクトを削除します。 このメソッドは、Exe でのみ使用できます。

## <a name="ccommoduleterm"></a><a name="term"></a> CComModule:: Term

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```cpp
void Term() throw();
```

### <a name="remarks"></a>解説

すべてのデータメンバーを解放します。

## <a name="ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a> CComModule:: UnregisterClassHelper

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
ATL_DEPRECATED HRESULT UnregisterClassHelper(
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
から登録を解除するオブジェクトの CLSID。

*lpszProgID*<br/>
からオブジェクトに関連付けられている ProgID。

*lpszVerIndProgID*<br/>
からオブジェクトに関連付けられているバージョンに依存しない ProgID。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

オブジェクトの標準クラスの登録をシステムレジストリから削除します。

[UpdateRegistryClass](#updateregistryclass)メソッドはを呼び出し `UnregisterClassHelper` ます。

## <a name="ccommoduleunregisterserver"></a><a name="unregisterserver"></a> CComModule:: UnregisterServer

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```

### <a name="parameters"></a>パラメーター

*bUnRegTypeLib*<br/>
TRUE の場合、タイプライブラリも登録解除されます。

*pCLSID*<br/>
登録を解除するオブジェクトの CLSID を指します。 NULL (既定値) の場合、オブジェクトマップ内のすべてのオブジェクトの登録が解除されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*Pclsid* パラメーターに応じて、は、単一のクラスオブジェクトまたはオブジェクトマップ内のすべてのオブジェクトの登録を解除します。

`UnregisterServer` は、DLL に対して、 `DLLUnregisterServer` または `WinMain` コマンドラインオプションを指定して実行される EXE によって、によって自動的に呼び出され `/UnregServer` ます。

オブジェクトマップにエントリを追加する方法については、「 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 」を参照してください。

## <a name="ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a> CComModule:: UpdateRegistryClass

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

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
オブジェクトに関連付けられている ProgID。

*lpszVerIndProgID*<br/>
オブジェクトに関連付けられているバージョンに依存しない ProgID。

*nDescID*<br/>
オブジェクトの説明の文字列リソースの識別子。

*szDesc*<br/>
オブジェクトの説明を表す文字列です。

*dwFlags*<br/>
レジストリに入力するスレッド処理モデルを指定します。 指定できる値は、THREADFLAGS_APARTMENT、THREADFLAGS_BOTH、または AUTPRXFLAG です。

*bRegister*<br/>
オブジェクトを登録する必要があるかどうかを示します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*Bregister* が TRUE の場合、このメソッドはオブジェクトの標準クラスの登録をシステムレジストリに入力します。

*Bregister* が FALSE の場合は、オブジェクトの登録が削除されます。

*Bregister* の値に応じて、 `UpdateRegistryClass` は [RegisterClassHelper](#registerclasshelper)または [UnregisterClassHelper](#unregisterclasshelper)のいずれかを呼び出します。

[DECLARE_REGISTRY](registry-macros.md#declare_registry)マクロを指定することにより、 `UpdateRegistryClass` オブジェクトマップが処理されるときにが自動的に呼び出されます。

## <a name="ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a> CComModule:: UpdateRegistryFromResourceD

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

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
からリソース名。

*nResID*<br/>
からリソース ID。

*bRegister*<br/>
からオブジェクトを登録する必要があるかどうかを示します。

*pMapEntries*<br/>
からスクリプトの置き換え可能パラメーターに関連付けられた値を格納する置換マップへのポインター。 ATL はを自動的に使用 `%MODULE%` します。 追加の置き換え可能パラメーターを使用するには、詳細について「解説」を参照してください。 それ以外の場合は、NULL の既定値を使用します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*Lpszres* または *nResID* によって指定されたリソースに含まれるスクリプトを実行します。

*Bregister* が TRUE の場合、このメソッドはオブジェクトをシステムレジストリに登録します。それ以外の場合は、オブジェクトの登録を解除します。

[DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource)または[DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid)マクロを指定することにより、 `UpdateRegistryFromResourceD` オブジェクトマップが処理されるときにが自動的に呼び出されます。

> [!NOTE]
> 実行時に置換値を置き換えるには、DECLARE_REGISTRY_RESOURCE または DECLARE_REGISTRY_RESOURCEID マクロを指定しないでください。 代わりに、構造体の配列を作成し `_ATL_REGMAP_ENTRIES` ます。各エントリには、実行時にプレースホルダーを置き換える値と組み合わせた変数プレースホルダーが含まれています。 次に `UpdateRegistryFromResourceD` 、を呼び出し、 *Pmapentries* パラメーターの配列を渡します。 これにより、構造体のすべての置換値が `_ATL_REGMAP_ENTRIES` レジストラーの置換マップに追加されます。

> [!NOTE]
> ATL レジストリコンポーネント (レジストラー) に静的にリンクするには、「 [UpdateRegistryFromResourceS](#updateregistryfromresources)」を参照してください。

置換可能なパラメーターとスクリプトの詳細については、「 [ATL レジストリコンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)」を参照してください。

## <a name="ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a> CComModule:: UpdateRegistryFromResourceS

ATL 7.0 の場合、 `CComModule` は廃止されています。詳細については、「 [Atl モジュールクラス](../../atl/atl-module-classes.md) 」を参照してください。

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
からリソース名。

*nResID*<br/>
からリソース ID。

*bRegister*<br/>
からリソーススクリプトを登録する必要があるかどうかを示します。

*pMapEntries*<br/>
からスクリプトの置き換え可能パラメーターに関連付けられた値を格納する置換マップへのポインター。 ATL はを自動的に使用 `%MODULE%` します。 追加の置き換え可能パラメーターを使用するには、詳細について「解説」を参照してください。 それ以外の場合は、NULL の既定値を使用します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

[UpdateRegistryFromResourceD](#updateregistryfromresourced)と同様に `UpdateRegistryFromResourceS` 、ATL レジストリコンポーネント (レジストラー) への静的リンクを作成します。

`UpdateRegistryFromResourceS` は、オブジェクトマップが処理されると自動的に呼び出されます `#define _ATL_STATIC_REGISTRY` *。* これは、Visual Studio 2017 以前のバージョンである *stdafx.h* に追加した場合に実行されます。

> [!NOTE]
> 実行時に置換値を置き換えるには、 [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) または [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) マクロを指定しないでください。 代わりに、構造体の配列を作成し `_ATL_REGMAP_ENTRIES` ます。各エントリには、実行時にプレースホルダーを置き換える値と組み合わせた変数プレースホルダーが含まれています。 次に `UpdateRegistryFromResourceS` 、を呼び出し、 *Pmapentries* パラメーターの配列を渡します。 これにより、構造体のすべての置換値が `_ATL_REGMAP_ENTRIES` レジストラーの置換マップに追加されます。

置換可能なパラメーターとスクリプトの詳細については、「 [ATL レジストリコンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
