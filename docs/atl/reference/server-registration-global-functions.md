---
title: サーバー登録グローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
ms.openlocfilehash: fb6353b52f487d0511c54223fe9e31dab88704b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325925"
---
# <a name="server-registration-global-functions"></a>サーバー登録グローバル関数

これらの関数は、オブジェクト マップ内のサーバー オブジェクトの登録と登録解除をサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|オブジェクト マップのオブジェクトをすべて登録します。|
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|オブジェクト マップのオブジェクトの登録をすべて解除します。|
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|この関数は、クラス オブジェクトを登録するために呼び出されます。|
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|この関数は、COM モジュールからクラス オブジェクトを取り消すために呼び出されます。|
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|この関数は、クラス オブジェクトを取得するために呼び出されます。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atlcommoduleregisterserver"></a><a name="atlcommoduleregisterserver"></a>サーバーを構成します。

オブジェクト マップのオブジェクトをすべて登録します。

```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
COM モジュールへのポインター。

*を行う*<br/>
タイプ ライブラリを登録する場合は TRUE。

*pCLSID*<br/>
登録するオブジェクトの CLSID へのポイント。 NULL の場合、オブジェクト マップ内のすべてのオブジェクトが登録されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

`AtlComModuleRegisterServer`ATL 自動生成オブジェクト マップを走査し、マップ内の各オブジェクトを登録します。 *pCLSID*が NULL でない場合は *、pCLSID*によって参照されるオブジェクトのみが登録されます。それ以外の場合は、すべてのオブジェクトが登録されます。

この関数は[、CAtlCom モジュールによって呼び出されます::登録サーバー](catlcommodule-class.md#registerserver)。

## <a name="atlcommoduleunregisterserver"></a><a name="atlcommoduleunregisterserver"></a>サーバーを登録します。

オブジェクト マップのオブジェクトの登録をすべて解除します。

```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
COM モジュールへのポインター。

*をクリックします。*<br/>
タイプ ライブラリを登録する場合は TRUE。

*pCLSID*<br/>
登録解除するオブジェクトの CLSID へのポイント。 NULL の場合、オブジェクト マップ内のすべてのオブジェクトが登録解除されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

`AtlComModuleUnregisterServer`ATL オブジェクト マップを走査し、マップ内の各オブジェクトの登録を解除します。 *pCLSID*が NULL でない場合は *、pCLSID*によって参照されるオブジェクトだけが登録解除されます。それ以外の場合は、すべてのオブジェクトが登録解除されます。

この関数は[、CAtlCom モジュールによって呼び出されます:登録サーバーを登録します](catlcommodule-class.md#unregisterserver)。

## <a name="atlcommoduleregisterclassobjects"></a><a name="atlcommoduleregisterclassobjects"></a>クラスオブジェクト

この関数は、クラス オブジェクトを登録するために呼び出されます。

```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
COM モジュールへのポインター。

*コンテキスト*<br/>
クラス オブジェクトを実行するコンテキストを指定します。 指定できる値は、CLSCTX_INPROC_SERVER、CLSCTX_INPROC_HANDLER、またはCLSCTX_LOCAL_SERVERです。 詳細については[、CLSCTX](/windows/win32/api/wtypesbase/ne-wtypesbase-clsctx)を参照してください。

*dwFlags*<br/>
クラス オブジェクトへの接続の種類を決定します。 指定できる値は、REGCLS_SINGLEUSE、REGCLS_MULTIPLEUSE、またはREGCLS_MULTI_SEPARATEです。 詳細については[、REGCLS](/windows/win32/api/combaseapi/ne-combaseapi-regcls)を参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このヘルパー関数は[、CComModule::レジスタクラスオブジェクト](ccommodule-class.md#registerclassobjects)(ATL 7.0では廃止)と[CAtlExeModuleT::レジスタクラスオブジェクト](catlexemodulet-class.md#registerclassobjects)によって使用されます。

## <a name="atlcommodulerevokeclassobjects"></a><a name="atlcommodulerevokeclassobjects"></a>クラスオブジェクトを取り消す

クラス ファクトリをランニング オブジェクト テーブルから削除します。

```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
COM モジュールへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このヘルパー関数は[、CComModule::取り消しクラスオブジェクト](ccommodule-class.md#revokeclassobjects)(ATL 7.0 では廃止) および[CAtlExeModuleT::取り消しクラスオブジェクト](catlexemodulet-class.md#revokeclassobjects)によって使用されます。

## <a name="atlcommodulegetclassobject"></a><a name="atlcommodulegetclassobject"></a>クラスオブジェクト

この関数は、クラス ファクトリを返すために呼び出されます。

```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
COM モジュールへのポインター。

*rclsid*<br/>
作成するオブジェクトの CLSID。

*riid*<br/>
要求されたインターフェイスの IID。

*Ppv*<br/>
*riid*によって識別されるインターフェイス ポインターへのポインター。 オブジェクトがこのインターフェイスをサポートしていない場合 *、ppv*は NULL に設定されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このヘルパー関数は[、CComModule::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7.0 では廃止) および[CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject)によって使用されます。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
