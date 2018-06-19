---
title: CComModule クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 05b4ec763f6ee719e96627be3dc81a1e9b56c2c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366472"
---
# <a name="ccommodule-class"></a>CComModule クラス
ATL 7.0 の時点で`CComModule`は推奨されなくなりました。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
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
|[CComModule::GetClassObject](#getclassobject)|指定された CLSID のオブジェクトを作成します。 Dll の場合のみです。|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|`m_hInst` を返します。|  
|[CComModule::GetResourceInstance](#getresourceinstance)|`m_hInstResource` を返します。|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib` を返します。|  
|[Ccommodule::init](#init)|データ メンバーを初期化します。|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|オブジェクトの標準的なクラスの登録をシステム レジストリに入力します。|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|クラスのオブジェクトを登録します。 Exe ファイルのみです。|  
|[CComModule::RegisterServer](#registerserver)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。|  
|[CComModule::RegisterTypeLib](#registertypelib)|タイプ ライブラリを登録します。|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|クラスのオブジェクトを取り消します。 Exe ファイルのみです。|  
|[:Term](#term)|データ メンバーを解放します。|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|システム レジストリからオブジェクトの標準的なクラスの登録を削除します。|  
|[CComModule::UnregisterServer](#unregisterserver)|オブジェクト マップ内の各オブジェクトの登録を解除します。|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|登録するか、オブジェクトの標準的なクラスの登録の登録を解除します。|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|登録または登録解除オブジェクトに指定されたリソースに含まれるスクリプトを実行します。|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL レジストリ コンポーネントに静的にリンクしています。 登録または登録解除オブジェクトに指定されたリソースに含まれるスクリプトを実行します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|オブジェクト マップ情報への同期アクセスのことを確認します。|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|タイプ ライブラリ情報への同期アクセスのことを確認します。|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|ウィンドウ クラスの情報とウィンドウの作成中に使用される静的データへの同期アクセスのことを確認します。|  
|[CComModule::m_hInst](#m_hinst)|モジュールのインスタンスへのハンドルが含まれています。|  
|[CComModule::m_hInstResource](#m_hinstresource)|既定では、モジュールのインスタンスへのハンドルが含まれています。|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|既定では、モジュールのインスタンスへのハンドルが含まれています。|  
|[CComModule::m_pObjMap](#m_pobjmap)|モジュールのインスタンスで保持されているオブジェクトのマップへのポインター。|  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このクラスは廃止され、今すぐ ATL コードの生成ウィザードを使用して、[残さ](../../atl/reference/catlautothreadmodule-class.md)と[不要](../../atl/reference/catlmodule-class.md)クラスを派生します。 参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。 ATL の以前のリリースで作成されたアプリケーションのために次の情報が、します。 `CComModule` まだ一部の ATL の旧バージョンと機能です。  
  
 `CComModule` クライアントが、モジュールのコンポーネントにアクセスできるよう、COM サーバー モジュールを実装します。 `CComModule` DLL (インプロセス) と EXE (ローカル) のモジュールの両方をサポートしています。  
  
 A`CComModule`インスタンスがクラス オブジェクトの定義のセットを維持するために、オブジェクトのマップを使用します。 このオブジェクトのマップは、の配列として実装されて`_ATL_OBJMAP_ENTRY`構造体、および情報について説明します。  
  
-   入力して、システム レジストリ内のオブジェクトの説明を削除します。  
  
-   クラス ファクトリを使用したオブジェクトをインスタンス化します。  
  
-   コンポーネントで、クライアントと、ルート オブジェクト間の通信を確立します。  
  
-   クラスのオブジェクトの有効期間管理を実行しています。  
  
 ATL COM AppWizard を実行すると、ウィザードは自動的に生成`_Module`のグローバル インスタンス`CComModule`またはその派生クラス。 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトを作成する](../../atl/reference/creating-an-atl-project.md)です。  
  
 加え`CComModule`、ATL には、[は](../../atl/reference/ccomautothreadmodule-class.md)、Exe ファイルおよび Windows サービス用のアパートメント モデル モジュールを実装します。 モジュールからの派生`CComAutoThreadModule`複数アパートメント内でオブジェクトを作成する場合。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="getclassobject"></a>  CComModule::GetClassObject  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HRESULT GetClassObject(  
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rclsid`  
 [in]作成するオブジェクトの CLSID。  
  
 `riid`  
 [in]要求されたインターフェイスの IID です。  
  
 `ppv`  
 [out]によって識別されるインターフェイス ポインターへのポインター`riid`です。 オブジェクトは、このインターフェイスをサポートしていない場合`ppv`に設定されている**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 指定された CLSID のオブジェクトを作成し、このオブジェクトへのインターフェイス ポインターを取得します。  
  
 `GetClassObject` Dll をできるだけです。  
  
##  <a name="getmoduleinstance"></a>  CComModule::GetModuleInstance  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`このモジュールを識別します。  
  
### <a name="remarks"></a>コメント  
 返します、 [m_hInst](#m_hinst)データ メンバーです。  
  
##  <a name="getresourceinstance"></a>  CComModule::GetResourceInstance  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`。  
  
### <a name="remarks"></a>コメント  
 返します、 [m_hInstResource](#m_hinstresource)データ メンバーです。  
  
##  <a name="gettypelibinstance"></a>  CComModule::GetTypeLibInstance  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 `HINSTANCE`。  
  
### <a name="remarks"></a>コメント  
 返します、 [m_hInstTypeLib](#m_hinsttypelib)データ メンバーです。  
  
##  <a name="init"></a>  Ccommodule::init  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]オブジェクト マップ エントリの配列へのポインター。  
  
 `h`  
 [in]`HINSTANCE`に渡される**DLLMain**または`WinMain`です。  
  
 `plibid`  
 [in]プロジェクトに関連付けられているタイプ ライブラリの LIBID へのポインター。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを初期化します。  
  
##  <a name="m_csobjmap"></a>  CComModule::m_csObjMap  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>コメント  
 オブジェクト マップへの同期アクセスのことを確認します。  
  
##  <a name="m_cstypeinfoholder"></a>  CComModule::m_csTypeInfoHolder  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>コメント  
 タイプ ライブラリへの同期のアクセスを保証します。  
  
##  <a name="m_cswindowcreate"></a>  CComModule::m_csWindowCreate  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウ クラスの情報をウィンドウの作成時に使用される静的なデータを同期のアクセスを保証します。  
  
##  <a name="m_hinst"></a>  CComModule::m_hInst  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>コメント  
 モジュールのインスタンスへのハンドルが含まれています。  
  
 [Init](#init)メソッドのセット`m_hInst`に渡されたハンドルを**DLLMain**または`WinMain`です。  
  
##  <a name="m_hinstresource"></a>  CComModule::m_hInstResource  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>コメント  
 既定では、モジュールのインスタンスへのハンドルが含まれています。  
  
 [Init](#init)メソッドのセット`m_hInstResource`に渡されたハンドルを**DLLMain**または`WinMain`です。 明示的に設定することができます`m_hInstResource`リソースへのハンドルにします。  
  
 [GetResourceInstance](#getresourceinstance)に格納されているハンドルを返します`m_hInstResource`です。  
  
##  <a name="m_hinsttypelib"></a>  CComModule::m_hInstTypeLib  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>コメント  
 既定では、モジュールのインスタンスへのハンドルが含まれています。  
  
 [Init](#init)メソッドのセット`m_hInstTypeLib`に渡されたハンドルを**DLLMain**または`WinMain`です。 明示的に設定することができます`m_hInstTypeLib`タイプ ライブラリへのハンドルにします。  
  
 [GetTypeLibInstance](#gettypelibinstance)に格納されているハンドルを返します`m_hInstTypeLib`です。  
  
##  <a name="m_pobjmap"></a>  CComModule::m_pObjMap  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>コメント  
 モジュールのインスタンスで保持されているオブジェクトのマップへのポインター。  
  
##  <a name="registerclasshelper"></a>  CComModule::RegisterClassHelper  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [in]登録するオブジェクトの CLSID。  
  
 `lpszProgID`  
 [in]オブジェクトに関連付けられている ProgID です。  
  
 `lpszVerIndProgID`  
 [in]オブジェクトに関連付けられているバージョン依存 ProgID です。  
  
 `nDescID`  
 [in]オブジェクトの説明の文字列リソースの識別子です。  
  
 `dwFlags`  
 [in]レジストリに入力する、スレッディング モデルを指定します。 指定できる値は**THREADFLAGS_APARTMENT**、 **THREADFLAGS_BOTH**、または**AUTPRXFLAG**です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 オブジェクトの標準的なクラスの登録をシステム レジストリに入力します。  
  
 [UpdateRegistryClass](#updateregistryclass)メソッド呼び出し`RegisterClassHelper`です。  
  
##  <a name="registerclassobjects"></a>  CComModule::RegisterClassObjects  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwClsContext`  
 [in]クラスのオブジェクトが実行されるコンテキストを指定します。 指定できる値は**CLSCTX_INPROC_SERVER**、 **CLSCTX_INPROC_HANDLER**、または**CLSCTX_LOCAL_SERVER**です。 これらの値については、次を参照してください。 [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) Windows SDK に含まれています。  
  
 `dwFlags`  
 [in]クラスのオブジェクトへの接続の種類を決定します。 指定できる値は**REGCLS_SINGLEUSE**、 **REGCLS_MULTIPLEUSE**、または**REGCLS_MULTI_SEPARATE**です。 これらの値については、次を参照してください。 [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) Windows SDK に含まれています。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 他のアプリケーションが接続できるように、EXE クラス オブジェクトを OLE に登録します。 このメソッドは exe のみです。  
  
##  <a name="registerserver"></a>  CComModule::RegisterServer  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bRegTypeLib`  
 [in]タイプ ライブラリを登録するかどうかを示します。 既定値は**FALSE**です。  
  
 `pCLSID`  
 [in]登録するオブジェクトの CLSID を指します。 場合**NULL** (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクトが登録されます。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 によって、`pCLSID`パラメーターが 1 つのクラス オブジェクトまたはオブジェクト マップ内のすべてのオブジェクトのシステムのレジストリを更新します。  
  
 場合`bRegTypeLib`は**TRUE**、タイプ ライブラリ情報も更新されます。  
  
 参照してください[OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto)オブジェクト マップにエントリを追加する方法についてはします。  
  
 `RegisterServer` によって自動的に呼び出される**DLLRegisterServer** DLL か、または`WinMain`を使用して実行 exe、 **/RegServer**コマンド ライン オプションです。  
  
##  <a name="registertypelib"></a>  CComModule::RegisterTypeLib  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszIndex`  
 [in]形式で文字列`"\\N"`ここで、`N`タイプ ライブラリのリソースの整数のインデックスです。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 タイプ ライブラリに関する情報をシステム レジストリに追加します。  
  
 モジュールのインスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの 2 番目のバージョンを使用して、どのタイプ ライブラリを使用する必要がありますを指定します。  
  
##  <a name="revokeclassobjects"></a>  CComModule::RevokeClassObjects  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 クラスのオブジェクトを削除します。 このメソッドは exe のみです。  
  
##  <a name="term"></a>  :Term  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを解放します。  
  
##  <a name="unregisterclasshelper"></a>  CComModule::UnregisterClassHelper  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [in]登録解除するオブジェクトの CLSID。  
  
 `lpszProgID`  
 [in]オブジェクトに関連付けられている ProgID です。  
  
 `lpszVerIndProgID`  
 [in]オブジェクトに関連付けられているバージョン依存 ProgID です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 システム レジストリからオブジェクトの標準的なクラスの登録を削除します。  
  
 [UpdateRegistryClass](#updateregistryclass)メソッド呼び出し`UnregisterClassHelper`です。  
  
##  <a name="unregisterserver"></a>  CComModule::UnregisterServer  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `bUnRegTypeLib`  
 場合**TRUE**、タイプ ライブラリ登録も解除されます。  
  
 `pCLSID`  
 登録解除するオブジェクトの CLSID を指します。 場合**NULL** (既定値) の場合は、オブジェクト マップ内のすべてのオブジェクト登録解除されます。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 によって、 `pCLSID` 1 つのクラス オブジェクトまたはオブジェクト マップ内のすべてのオブジェクトのいずれかのパラメーター、登録を解除します。  
  
 `UnregisterServer` によって自動的に呼び出される**DLLUnregisterServer** DLL か、または`WinMain`を使用して実行 exe、 **/UnregServer**コマンド ライン オプションです。  
  
 参照してください[OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto)オブジェクト マップにエントリを追加する方法についてはします。  
  
##  <a name="updateregistryclass"></a>  CComModule::UpdateRegistryClass  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
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
 `clsid`  
 登録または登録解除するオブジェクトの CLSID。  
  
 `lpszProgID`  
 オブジェクトに関連付けられている ProgID です。  
  
 `lpszVerIndProgID`  
 オブジェクトに関連付けられているバージョン依存 ProgID です。  
  
 `nDescID`  
 オブジェクトの説明の文字列リソースの識別子です。  
  
 `szDesc`  
 オブジェクトの説明を含む文字列。  
  
 `dwFlags`  
 レジストリに入力する、スレッディング モデルを指定します。 指定できる値は**THREADFLAGS_APARTMENT**、 **THREADFLAGS_BOTH**、または**AUTPRXFLAG**です。  
  
 `bRegister`  
 オブジェクトを登録するかどうかを示します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 場合`bRegister`は**TRUE**、このメソッドは、システム レジストリにオブジェクトの標準的なクラスの登録を入力します。  
  
 場合`bRegister`は**FALSE**オブジェクトの登録を削除します。  
  
 値に応じて`bRegister`、`UpdateRegistryClass`いずれかを呼び出して[RegisterClassHelper](#registerclasshelper)または[UnregisterClassHelper](#unregisterclasshelper)です。  
  
 指定して、 [DECLARE_REGISTRY](registry-macros.md#declare_registry)マクロ、`UpdateRegistryClass`オブジェクト マップが処理されるときに自動的に呼び出されます。  
  
##  <a name="updateregistryfromresourced"></a>  CComModule::UpdateRegistryFromResourceD  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
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
 `lpszRes`  
 [in]リソースの名前です。  
  
 `nResID`  
 [in]リソース id です。  
  
 `bRegister`  
 [in]オブジェクトを登録するかどうかを示します。  
  
 `pMapEntries`  
 [in]スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、自動的に`%MODULE%`です。 追加の置き換え可能パラメーターを使用するのには、詳細については、「解説」を参照してください。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 指定されたリソースに含まれているスクリプトを実行`lpszRes`または`nResID`です。  
  
 場合`bRegister`は**TRUE**、このメソッドは、システム レジストリのオブジェクトを登録以外の場合は、オブジェクトの登録を解除、それ以外の場合。  
  
 指定して、[に](registry-macros.md#declare_registry_resource)または[代入](registry-macros.md#declare_registry_resourceid)マクロ、`UpdateRegistryFromResourceD`オブジェクト マップが処理されるときに自動的に呼び出されます。  
  
> [!NOTE]
>  実行時に置換値を置き換えるには指定しないで、`DECLARE_REGISTRY_RESOURCE`または`DECLARE_REGISTRY_RESOURCEID`マクロです。 配列を作成する代わりに、**結果**実行時に、プレース ホルダーを置換する値を持つ対応する構造体、各エントリに変数のプレース ホルダーが含まれています。 呼び出す`UpdateRegistryFromResourceD`配列を渡す、`pMapEntries`パラメーター。 これにより、追加のすべての置換値、**結果**レジストラーの置換マップする構造体。  
  
> [!NOTE]
>  ATL レジストリ コンポーネント (レジストラー) に静的にリンクするには、次を参照してください。[次](#updateregistryfromresources)です。  
  
 置き換え可能パラメーターおよびスクリプトに関する詳細については、記事を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)です。  
  
##  <a name="updateregistryfromresources"></a>  CComModule::UpdateRegistryFromResourceS  
 ATL 7.0 の時点で`CComModule`は廃止されています。 を参照してください[ATL モジュール クラス](../../atl/atl-module-classes.md)詳細についてはします。  
  
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
 `lpszRes`  
 [in]リソースの名前です。  
  
 `nResID`  
 [in]リソース id です。  
  
 `bRegister`  
 [in]リソース スクリプトを登録するかどうかを示します。  
  
 `pMapEntries`  
 [in]スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、自動的に`%MODULE%`です。 追加の置き換え可能パラメーターを使用するのには、詳細については、「解説」を参照してください。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>コメント  
 ような[ため](#updateregistryfromresourced)を除く`UpdateRegistryFromResourceS`ATL レジストリ コンポーネント (レジストラー) への静的リンクを作成します。  
  
 `UpdateRegistryFromResourceS` 呼び出される自動的に、オブジェクトのマップが処理されるときに追加する指定`#define _ATL_STATIC_REGISTRY`stdafx.h にします。  
  
> [!NOTE]
>  実行時に置換値を置き換えるには指定しないで、[に](registry-macros.md#declare_registry_resource)または[代入](registry-macros.md#declare_registry_resourceid)マクロです。 配列を作成する代わりに、**結果**実行時に、プレース ホルダーを置換する値を持つ対応する構造体、各エントリに変数のプレース ホルダーが含まれています。 呼び出す`UpdateRegistryFromResourceS`配列を渡す、`pMapEntries`パラメーター。 これにより、追加のすべての置換値、**結果**レジストラーの置換マップする構造体。  
  
 置き換え可能パラメーターおよびスクリプトに関する詳細については、記事を参照してください。 [ATL レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
