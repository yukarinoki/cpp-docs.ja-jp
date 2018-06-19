---
title: 不要クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2be5d5a777d4b9aed9ee4d07016771ee91c913b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365283"
---
# <a name="catlmodule-class"></a>不要クラス
このクラスは、いくつかの ATL モジュール クラスによって使用されるメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[不要](#catlmodule)|コンストラクターです。|  
|[不要:: ~ 不要](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL レジストリ コンポーネント (レジストラー) 交換マップにパラメーターを追加するには、このメソッドをオーバーライドします。|  
|[CAtlModule::AddTermFunc](#addtermfunc)|モジュールの終了時に呼び出される新しい関数を追加します。|  
|[CAtlModule::GetGITPtr](#getgitptr)|グローバル インターフェイス ポインターを返します。|  
|[CAtlModule::GetLockCount](#getlockcount)|ロック カウントを返します。|  
|[CAtlModule::Lock](#lock)|ロック カウントをインクリメントします。|  
|[CAtlModule::Term](#term)|すべてのデータ メンバーを解放します。|  
|[CAtlModule::Unlock](#unlock)|ロック カウントをデクリメントします。|  
|[して](#updateregistryfromresourced)|登録または登録解除オブジェクトに指定されたリソースに含まれるスクリプトを実行します。|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|このメソッドによって呼び出されます`UpdateRegistryFromResourceD`レジストリが更新を実行します。|  
|[方法については](#updateregistryfromresources)|登録または登録解除オブジェクトに指定されたリソースに含まれるスクリプトを実行します。 このメソッドは、ATL レジストリ コンポーネントに静的にリンクされます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|現在のモジュールの GUID が含まれています。|  
|[されます](#m_pgit)|グローバル インターフェイス テーブルへのポインター。|  
  
## <a name="remarks"></a>コメント  
 このクラスによって使用[CAtlDllModuleT クラス](../../atl/reference/catldllmodulet-class.md)、 [CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)、および[CAtlServiceModuleT クラス](../../atl/reference/catlservicemodulet-class.md)DLL アプリケーション、EXE アプリケーションのサポートを提供してWindows サービス、それぞれします。  
  
 ATL でモジュールの詳細については、次を参照してください。 [ATL モジュール クラス](../../atl/atl-module-classes.md)です。  
  
 このクラスは廃止された置換[CComModule クラス](../../atl/reference/ccommodule-class.md)ATL の以前のバージョンで使用されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>  CAtlModule::AddCommonRGSReplacements  
 ATL レジストリ コンポーネント (レジストラー) 交換マップにパラメーターを追加するには、このメソッドをオーバーライドします。  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 *pRegistrar*  
 予約済み。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 置き換え可能パラメーターを使用すると、レジストラーのクライアントを実行時のデータを指定します。 これを行うには、レジストラーが先は、スクリプトで置き換え可能パラメーターに関連付けられている値が入った置換マップを保持します。 レジストラーでは、実行時にこれらのエントリを作成します。  
  
 トピックを参照して[置き換え可能パラメーターの使用 (レジストラーのプリプロセッサ)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)詳細についてはします。  
  
##  <a name="addtermfunc"></a>  CAtlModule::AddTermFunc  
 モジュールの終了時に呼び出される新しい関数を追加します。  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pFunc*  
 追加する関数へのポインター。  
  
 `dw`  
 ユーザー定義のデータは、関数に渡されます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="catlmodule"></a>  不要  
 コンストラクターです。  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>コメント  
 データ メンバーを初期化し、モジュールのスレッドの周囲のクリティカル セクションを開始します。  
  
##  <a name="dtor"></a>  不要:: ~ 不要  
 デストラクターです。  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを解放します。  
  
##  <a name="getgitptr"></a>  CAtlModule::GetGITPtr  
 グローバル インターフェイス テーブルへのポインターを取得します。  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ppGIT`  
 グローバル インターフェイス テーブルへのポインターを受け取る変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗した場合、エラー コードを返します。 場合に返される E_POINTER`ppGIT`が NULL です。  
  
### <a name="remarks"></a>コメント  
 グローバル インターフェイス テーブル オブジェクトが存在しないは、作成、メンバー変数にそのアドレスが保存されていると[されます](#m_pgit)です。  
  
 場合はデバッグ ビルドで、アサーション エラーが発生`ppGIT`に NULL 値は、グローバル インターフェイス テーブルのポインターを取得できない場合またはします。  
  
 参照してください[については](http://msdn.microsoft.com/library/windows/desktop/ms678517)については、グローバル インターフェイス テーブルにします。  
  
##  <a name="getlockcount"></a>  CAtlModule::GetLockCount  
 ロック カウントを返します。  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ロック カウントを返します。 この値は、診断に役立つとデバッグする場合があります。  
  
##  <a name="lock"></a>  CAtlModule::Lock  
 ロック カウントをインクリメントします。  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ロック カウントをインクリメントし、更新された値を返します。 この値は、診断に役立つとデバッグする場合があります。  
  
##  <a name="m_libid"></a>  CAtlModule::m_libid  
 現在のモジュールの GUID が含まれています。  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>  されます  
 グローバル インターフェイス テーブルへのポインター。  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>  CAtlModule::Term  
 すべてのデータ メンバーを解放します。  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>コメント  
 すべてのデータ メンバーを解放します。 このメソッドは、デストラクターから呼び出されます。  
  
##  <a name="unlock"></a>  CAtlModule::Unlock  
 ロック カウントをデクリメントします。  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ロック カウントをデクリメントし、更新された値を返します。 この値は、診断に役立つとデバッグする場合があります。  
  
##  <a name="updateregistryfromresourced"></a>  して  
 登録または登録解除オブジェクトに指定されたリソースに含まれるスクリプトを実行します。  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszRes`  
 リソースの名前です。  
  
 `nResID`  
 リソース id です。  
  
 `bRegister`  
 **TRUE**場合は、オブジェクトを登録する必要があります。**FALSE**それ以外の場合。  
  
 `pMapEntries`  
 スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、% モジュールが自動的に使用します。 追加の置き換え可能パラメーターを使用するのを参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)です。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 指定されたリソースに含まれているスクリプトを実行*lpszRes または nResID*です。 場合`bRegister`は**TRUE**、このメソッドは、システム レジストリのオブジェクトを登録です。 それ以外の場合、レジストリからオブジェクトを削除します。  
  
 ATL レジストリ コンポーネント (レジストラー) に静的にリンクするには、次を参照してください。[方法については](#updateregistryfromresources)します。  
  
 このメソッドを呼び出す[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)と[IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister)です。  
  
##  <a name="updateregistryfromresourcedhelper"></a>  CAtlModule::UpdateRegistryFromResourceDHelper  
 このメソッドによって呼び出されます`UpdateRegistryFromResourceD`レジストリが更新を実行します。  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszRes`  
 リソースの名前です。  
  
 `bRegister`  
 オブジェクトを登録するかどうかを示します。  
  
 `pMapEntries`  
 スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、% モジュールが自動的に使用します。 追加の置き換え可能パラメーターを使用するのを参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)です。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドの実装を提供する[として](#updateregistryfromresourced)です。  
  
##  <a name="updateregistryfromresources"></a>  方法については  
 登録または登録解除オブジェクトに指定されたリソースに含まれるスクリプトを実行します。 このメソッドは、ATL レジストリ コンポーネントに静的にリンクされます。  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nResID`  
 リソース id です。  
  
 `lpszRes`  
 リソースの名前です。  
  
 `bRegister`  
 リソース スクリプトを登録するかどうかを示します。  
  
 `pMapEntries`  
 スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL では、% モジュールが自動的に使用します。 追加の置き換え可能パラメーターを使用するのを参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)です。 それ以外の場合を使用して、 **NULL**既定値です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 ような[として](#updateregistryfromresourced)を除く`CAtlModule::UpdateRegistryFromResourceS`ATL レジストリ コンポーネント (レジストラー) への静的リンクを作成します。  
  
## <a name="see-also"></a>関連項目  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)   
 [レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)  
