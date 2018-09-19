---
title: CAtlModule クラス |Microsoft Docs
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
ms.openlocfilehash: 88c8ee576af3c50317b86b7016ac198fefdcbaa9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093442"
---
# <a name="catlmodule-class"></a>CAtlModule クラス

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
|[CAtlModule:: ~ CAtlModule](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL レジストリ コンポーネント (レジストラー) 置換マップにパラメーターを追加するには、このメソッドをオーバーライドします。|
|[CAtlModule::AddTermFunc](#addtermfunc)|モジュールの終了時に呼び出される新しい関数を追加します。|
|[CAtlModule::GetGITPtr](#getgitptr)|グローバル インターフェイス ポインターを返します。|
|[CAtlModule::GetLockCount](#getlockcount)|ロック カウントを返します。|
|[CAtlModule::Lock](#lock)|ロック カウントをインクリメントします。|
|[CAtlModule::Term](#term)|すべてのデータ メンバーを解放します。|
|[CAtlModule::Unlock](#unlock)|ロック カウントをデクリメントします。|
|[して](#updateregistryfromresourced)|登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。|
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|このメソッドを呼び出して`UpdateRegistryFromResourceD`レジストリの更新を実行します。|
|[方法については](#updateregistryfromresources)|登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。 このメソッドは、ATL レジストリ コンポーネントに静的にリンクします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAtlModule::m_libid](#m_libid)|現在のモジュールの GUID が含まれています。|
|[されます](#m_pgit)|グローバル インターフェイス テーブルへのポインター。|

## <a name="remarks"></a>Remarks

このクラスによって使用されます[CAtlDllModuleT クラス](../../atl/reference/catldllmodulet-class.md)、 [CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)、および[CAtlServiceModuleT クラス](../../atl/reference/catlservicemodulet-class.md)DLL アプリケーションでは、EXE アプリケーションでは、サポートを提供してWindows サービスは、それぞれします。

ATL でモジュールの詳細については、次を参照してください。 [ATL モジュール クラス](../../atl/atl-module-classes.md)します。

このクラスは廃止された置換[CComModule クラス](../../atl/reference/ccommodule-class.md)以前のバージョンの ATL の使用

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

##  <a name="addcommonrgsreplacements"></a>  CAtlModule::AddCommonRGSReplacements

ATL レジストリ コンポーネント (レジストラー) 置換マップにパラメーターを追加するには、このメソッドをオーバーライドします。

```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>パラメーター

*pRegistrar*<br/>
予約済み。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

置き換え可能パラメーターを使用すると、レジストラーのクライアントで実行時のデータを指定します。 これを行うには、レジストラーは、先が、スクリプトで置き換え可能パラメーターに関連付けられている値に入る置換マップを保持します。 レジストラーは、実行時にこれらのエントリを作成します。

トピックを参照して[置き換え可能パラメーターの使用 (レジストラーのプリプロセッサ)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)の詳細。

##  <a name="addtermfunc"></a>  CAtlModule::AddTermFunc

モジュールの終了時に呼び出される新しい関数を追加します。

```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>パラメーター

*pFunc*<br/>
追加する関数へのポインター。

*dw*<br/>
ユーザー定義のデータは、関数に渡されます。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

##  <a name="catlmodule"></a>  不要

コンストラクターです。

```
CAtlModule() throw();
```

### <a name="remarks"></a>Remarks

データ メンバーを初期化し、モジュールのスレッドの周囲のクリティカル セクションを開始します。

##  <a name="dtor"></a>  CAtlModule:: ~ CAtlModule

デストラクターです。

```
~CAtlModule() throw();
```

### <a name="remarks"></a>Remarks

すべてのデータ メンバーを解放します。

##  <a name="getgitptr"></a>  CAtlModule::GetGITPtr

グローバル インターフェイス テーブルへのポインターを取得します。

```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>パラメーター

*ppGIT*<br/>
グローバル インターフェイス テーブルへのポインターを受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗した場合、エラー コードを返します。 場合に返される E_POINTER *ppGIT*が NULL です。

### <a name="remarks"></a>Remarks

グローバル インターフェイス テーブル オブジェクトが存在しない場合は、作成されると、そのアドレスが、メンバー変数に格納されている[されます](#m_pgit)します。

場合、デバッグ ビルドで、アサーション エラーが発生*ppGIT*が NULL の場合、グローバル インターフェイス テーブルのポインターを取得できない場合またはします。

参照してください[については](/windows/desktop/api/objidl/nn-objidl-iglobalinterfacetable)については、グローバル インターフェイス テーブル。

##  <a name="getlockcount"></a>  CAtlModule::GetLockCount

ロック カウントを返します。

```
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>戻り値

ロック カウントを返します。 この値には、診断に役立ちますし、デバッグがあります。

##  <a name="lock"></a>  CAtlModule::Lock

ロック カウントをインクリメントします。

```
virtual LONG Lock() throw();
```

### <a name="return-value"></a>戻り値

ロック カウントをインクリメントし、更新された値を返します。 この値には、診断に役立ちますし、デバッグがあります。

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

### <a name="remarks"></a>Remarks

すべてのデータ メンバーを解放します。 このメソッドは、デストラクターから呼び出されます。

##  <a name="unlock"></a>  CAtlModule::Unlock

ロック カウントをデクリメントします。

```
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>戻り値

ロック カウントをデクリメントし、更新された値を返します。 この値には、診断に役立ちますし、デバッグがあります。

##  <a name="updateregistryfromresourced"></a>  して

登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。

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

*lpszRes*<br/>
リソースの名前。

*nResID*<br/>
リソース id です。

*bRegister*<br/>
TRUE の場合は、オブジェクトを登録する必要があります。FALSE それ以外の場合。

*この配列*<br/>
スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL は、% モジュールを自動的に使用します。 追加の置き換え可能パラメーターを使用する、次を参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)します。 それ以外の場合、NULL 既定値を使用します。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

指定されたリソースに含まれるスクリプトを実行*lpszRes または nResID*します。 場合*bRegister*が true の場合、このメソッドは、システム レジストリで、オブジェクトを登録します。 それ以外の場合、レジストリからオブジェクトを削除します。

ATL レジストリ コンポーネント (レジストラー) に静的にリンクするを参照してください。[方法については](#updateregistryfromresources)します。

このメソッドを呼び出す[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)と[IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister)します。

##  <a name="updateregistryfromresourcedhelper"></a>  CAtlModule::UpdateRegistryFromResourceDHelper

このメソッドを呼び出して`UpdateRegistryFromResourceD`レジストリの更新を実行します。

```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*lpszRes*<br/>
リソースの名前。

*bRegister*<br/>
オブジェクトを登録するかどうかを示します。

*この配列*<br/>
スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL は、% モジュールを自動的に使用します。 追加の置き換え可能パラメーターを使用する、次を参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)します。 それ以外の場合、NULL 既定値を使用します。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

このメソッドの実装を提供[として](#updateregistryfromresourced)します。

##  <a name="updateregistryfromresources"></a>  方法については

登録またはオブジェクトを登録解除に指定されたリソースに含まれるスクリプトを実行します。 このメソッドは、ATL レジストリ コンポーネントに静的にリンクします。

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

*nResID*<br/>
リソース id です。

*lpszRes*<br/>
リソースの名前。

*bRegister*<br/>
リソース スクリプトを登録する必要があるかどうかを示します。

*この配列*<br/>
スクリプトの置き換え可能パラメーターに関連付けられている値を格納する置換マップへのポインター。 ATL は、% モジュールを自動的に使用します。 追加の置き換え可能パラメーターを使用する、次を参照してください。 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)します。 それ以外の場合、NULL 既定値を使用します。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

ような[として](#updateregistryfromresourced)を除く`CAtlModule::UpdateRegistryFromResourceS`ATL レジストリ コンポーネント (レジストラー) に静的にリンクを作成します。

## <a name="see-also"></a>関連項目

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)<br/>
[レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)  
