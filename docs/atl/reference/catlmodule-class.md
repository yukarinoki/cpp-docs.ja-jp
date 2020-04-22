---
title: クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
ms.openlocfilehash: cfc11a95a8d5d9354279f4c71698a6bc35c7aca7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748625"
---
# <a name="catlmodule-class"></a>クラス

このクラスには、複数の ATL モジュール クラスで使用されるメソッドが用意されています。

## <a name="syntax"></a>構文

```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カトルモジュール::カトルモジュール](#catlmodule)|コンストラクターです。|
|[CAtl モジュール::~CAtl モジュール](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtl モジュール::一般的なRGS交換](#addcommonrgsreplacements)|ATL レジストリ コンポーネント (レジストラー) 置換マップにパラメーターを追加するには、このメソッドをオーバーライドします。|
|[CAtl モジュール::アドタームファンク](#addtermfunc)|モジュールが終了したときに呼び出される新しい関数を追加します。|
|[カトルモジュール::ゲットギットプター](#getgitptr)|グローバル インターフェイス ポインタを返します。|
|[をクリックします。](#getlockcount)|ロックカウントを返します。|
|[CAtl モジュール::ロック](#lock)|ロックカウントをインクリメントします。|
|[CAtl モジュール::用語](#term)|すべてのデータ メンバーを解放します。|
|[CAtl モジュール::ロック解除](#unlock)|ロック カウントをデクリメントします。|
|[ソースモジュール::リソースからレジストリを更新します。](#updateregistryfromresourced)|オブジェクトを登録または登録解除するために、指定したリソースに含まれるスクリプトを実行します。|
|[リソースを持つモジュールを使用します。](#updateregistryfromresourcedhelper)|このメソッドは、レジストリ`UpdateRegistryFromResourceD`更新を実行するために呼び出されます。|
|[リソースから更新します。](#updateregistryfromresources)|オブジェクトを登録または登録解除するために、指定したリソースに含まれるスクリプトを実行します。 このメソッドは、ATL レジストリ コンポーネントに静的にリンクします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[カトルモジュール:m_libid](#m_libid)|現在のモジュールの GUID が含まれています。|
|[カトルモジュール::m_pGIT](#m_pgit)|グローバル インターフェイス テーブルへのポインタ。|

## <a name="remarks"></a>解説

このクラスは、DLL アプリケーション、EXE アプリケーション、および Windows サービスをサポートするために[、CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md)[クラス、CAtlExeModuleT クラス](../../atl/reference/catlexemodulet-class.md)、および[CAtlServiceModuleT クラス](../../atl/reference/catlservicemodulet-class.md)で使用されます。

ATL のモジュールの詳細については[、「ATL モジュール クラス](../../atl/atl-module-classes.md)」を参照してください。

このクラスは、以前のバージョンの ATL で使用された、古い[CComModule クラス](../../atl/reference/ccommodule-class.md)を置き換えます。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

`CAtlModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="catlmoduleaddcommonrgsreplacements"></a><a name="addcommonrgsreplacements"></a>CAtl モジュール::一般的なRGS交換

ATL レジストリ コンポーネント (レジストラー) 置換マップにパラメーターを追加するには、このメソッドをオーバーライドします。

```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```

### <a name="parameters"></a>パラメーター

*pレジストラ*<br/>
予約済み。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

置き換え可能パラメーターを使用すると、レジストラーのクライアントは実行時データを指定できます。 これを行うために、レジストラーは置換マップを維持し、スクリプト内の置き換え可能なパラメータに関連付けられた値を入力します。 レジストラーは、実行時にこれらのエントリを作成します。

詳細については、[置き換え可能パラメーターの使用 (レジストラーのプリプロセッサ) を](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)参照してください。

## <a name="catlmoduleaddtermfunc"></a><a name="addtermfunc"></a>CAtl モジュール::アドタームファンク

モジュールが終了したときに呼び出される新しい関数を追加します。

```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```

### <a name="parameters"></a>パラメーター

*を見る*<br/>
追加する関数へのポインター。

*dw*<br/>
関数に渡されるユーザー定義データ。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catlmodulecatlmodule"></a><a name="catlmodule"></a>カトルモジュール::カトルモジュール

コンストラクターです。

```
CAtlModule() throw();
```

### <a name="remarks"></a>解説

データ メンバーを初期化し、モジュールのスレッドの周囲にクリティカル セクションを開始します。

## <a name="catlmodulecatlmodule"></a><a name="dtor"></a>CAtl モジュール::~CAtl モジュール

デストラクターです。

```
~CAtlModule() throw();
```

### <a name="remarks"></a>解説

すべてのデータ メンバーを解放します。

## <a name="catlmodulegetgitptr"></a><a name="getgitptr"></a>カトルモジュール::ゲットギットプター

グローバル インターフェイス テーブルへのポインターを取得します。

```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```

### <a name="parameters"></a>パラメーター

*ppgit*<br/>
グローバル インターフェイス テーブルへのポインターを受け取る変数へのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OK、または失敗した場合にエラー コードを返します。 *ppGIT*が NULL に等しい場合は、E_POINTERが返されます。

### <a name="remarks"></a>解説

グローバル インターフェイス テーブル オブジェクトが存在しない場合は、そのオブジェクトが作成され、そのアドレスがメンバー変数[CAtlModule::m_pGIT](#m_pgit)に格納されます。

デバッグ ビルドでは *、ppGIT*が NULL に等しい場合、またはグローバル インターフェイス テーブル ポインタを取得できない場合、アサーション エラーが発生します。

グローバル[インターフェイス テーブル](/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable)の詳細については、「IGlobalInterfaceTable」を参照してください。

## <a name="catlmodulegetlockcount"></a><a name="getlockcount"></a>をクリックします。

ロックカウントを返します。

```
virtual LONG GetLockCount() throw();
```

### <a name="return-value"></a>戻り値

ロックカウントを返します。 この値は、診断やデバッグに役立ちます。

## <a name="catlmodulelock"></a><a name="lock"></a>CAtl モジュール::ロック

ロックカウントをインクリメントします。

```
virtual LONG Lock() throw();
```

### <a name="return-value"></a>戻り値

ロックカウントをインクリメントし、更新された値を返します。 この値は、診断やデバッグに役立ちます。

## <a name="catlmodulem_libid"></a><a name="m_libid"></a>カトルモジュール:m_libid

現在のモジュールの GUID が含まれています。

```
static GUID m_libid;
```

## <a name="catlmodulem_pgit"></a><a name="m_pgit"></a>カトルモジュール::m_pGIT

グローバル インターフェイス テーブルへのポインタ。

```
IGlobalInterfaceTable* m_pGIT;
```

## <a name="catlmoduleterm"></a><a name="term"></a>CAtl モジュール::用語

すべてのデータ メンバーを解放します。

```cpp
void Term() throw();
```

### <a name="remarks"></a>解説

すべてのデータ メンバーを解放します。 このメソッドは、デストラクターによって呼び出されます。

## <a name="catlmoduleunlock"></a><a name="unlock"></a>CAtl モジュール::ロック解除

ロック カウントをデクリメントします。

```
virtual LONG Unlock() throw();
```

### <a name="return-value"></a>戻り値

ロックカウントを減算し、更新された値を返します。 この値は、診断やデバッグに役立ちます。

## <a name="catlmoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>ソースモジュール::リソースからレジストリを更新します。

オブジェクトを登録または登録解除するために、指定したリソースに含まれるスクリプトを実行します。

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
リソース名。

*nResID*<br/>
リソース ID。

*b登録*<br/>
オブジェクトを登録する必要がある場合は TRUE。それ以外の場合は FALSE。

*エントリ*<br/>
スクリプトの置き換え可能パラメーターに関連付けられた値を格納する置換マップへのポインター。 ATL は自動的に %モジュール% を使用します。 追加の置き換え可能パラメーターを使用するには[、「CAtlModule::AddCommonRGS 置換」を参照してください](#addcommonrgsreplacements)。 それ以外の場合は、NULL の既定値を使用します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

*lpszRes または nResID*で指定されたリソースに含まれるスクリプトを実行します。 *bRegister*が TRUE の場合、このメソッドはオブジェクトをシステム レジストリに登録します。それ以外の場合は、オブジェクトをレジストリから削除します。

ATL レジストリ コンポーネント (レジストラー) に静的にリンクするには、[次](#updateregistryfromresources)を参照してください。

このメソッド[は、CAtlModule:::リソースDヘルパー](#updateregistryfromresourcedhelper)と[Iレジストラー::リソースアンレジスタ](iregistrar-class.md#resourceunregister)を呼び出します。

## <a name="catlmoduleupdateregistryfromresourcedhelper"></a><a name="updateregistryfromresourcedhelper"></a>リソースを持つモジュールを使用します。

このメソッドは、レジストリ`UpdateRegistryFromResourceD`更新を実行するために呼び出されます。

```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*lpszRes*<br/>
リソース名。

*b登録*<br/>
オブジェクトを登録するかどうかを示します。

*エントリ*<br/>
スクリプトの置き換え可能パラメーターに関連付けられた値を格納する置換マップへのポインター。 ATL は自動的に %モジュール% を使用します。 追加の置き換え可能パラメーターを使用するには[、「CAtlModule::AddCommonRGS 置換」を参照してください](#addcommonrgsreplacements)。 それ以外の場合は、NULL の既定値を使用します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドは[、CAtlModule::レジストリからリソースD](#updateregistryfromresourced)の実装を提供します。

## <a name="catlmoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>リソースから更新します。

オブジェクトを登録または登録解除するために、指定したリソースに含まれるスクリプトを実行します。 このメソッドは、ATL レジストリ コンポーネントに静的にリンクします。

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
リソース ID。

*lpszRes*<br/>
リソース名。

*b登録*<br/>
リソース スクリプトを登録するかどうかを示します。

*エントリ*<br/>
スクリプトの置き換え可能パラメーターに関連付けられた値を格納する置換マップへのポインター。 ATL は自動的に %モジュール% を使用します。 追加の置き換え可能パラメーターを使用するには[、「CAtlModule::AddCommonRGS 置換」を参照してください](#addcommonrgsreplacements)。 それ以外の場合は、NULL の既定値を使用します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[CAtlModule と同様に::レジストリリソースD](#updateregistryfromresourced)は`CAtlModule::UpdateRegistryFromResourceS`、ATL レジストリ コンポーネント (レジストラー) への静的リンクを作成します。

## <a name="see-also"></a>関連項目

[_ATL_MODULE](atl-typedefs.md#_atl_module)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)<br/>
[レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)
