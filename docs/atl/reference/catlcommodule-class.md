---
title: CAtlComModule クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlComModule
- ATLBASE/ATL::CAtlComModule
- ATLBASE/ATL::CAtlComModule::CAtlComModule
- ATLBASE/ATL::CAtlComModule::RegisterServer
- ATLBASE/ATL::CAtlComModule::RegisterTypeLib
- ATLBASE/ATL::CAtlComModule::UnregisterServer
- ATLBASE/ATL::CAtlComModule::UnRegisterTypeLib
helpviewer_keywords:
- CAtlComModule class
ms.assetid: af5dd71a-a0d1-4a2e-9a24-154a03381c75
ms.openlocfilehash: 09adcb33ca9e6f8524063130d6aedca044d6ecb5
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79423454"
---
# <a name="catlcommodule-class"></a>CAtlComModule クラス

このクラスは、COM サーバーモジュールを実装します。

## <a name="syntax"></a>構文

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CAtlComModule::CAtlComModule](#catlcommodule)|コンストラクターです。|
|[CAtlComModule:: ~ CAtlComModule](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CAtlComModule::RegisterServer](#registerserver)|オブジェクトマップ内の各オブジェクトのシステムレジストリを更新するには、このメソッドを呼び出します。|
|[CAtlComModule::RegisterTypeLib](#registertypelib)|タイプライブラリを登録するには、このメソッドを呼び出します。|
|[CAtlComModule::UnregisterServer](#unregisterserver)|オブジェクトマップ内の各オブジェクトの登録を解除するには、このメソッドを呼び出します。|
|[CAtlComModule::UnRegisterTypeLib](#unregistertypelib)|タイプライブラリの登録を解除するには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

`CAtlComModule` は、クライアントがモジュールのコンポーネントにアクセスできるようにするために、COM サーバーモジュールを実装します。

このクラスは、以前のバージョンの ATL で使用されていた古い[CComModule](../../atl/reference/ccommodule-class.md)クラスに代わるものです。 詳細については、「 [ATL モジュールクラス](../../atl/atl-module-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

##  <a name="catlcommodule"></a>CAtlComModule::CAtlComModule

コンストラクターです。

```
CAtlComModule() throw();
```

### <a name="remarks"></a>解説

モジュールを初期化します。

##  <a name="dtor"></a>CAtlComModule:: ~ CAtlComModule

デストラクターです。

```
~CAtlComModule();
```

### <a name="remarks"></a>解説

すべてのクラスファクトリを解放します。

##  <a name="registerserver"></a>CAtlComModule::RegisterServer

オブジェクトマップ内の各オブジェクトのシステムレジストリを更新するには、このメソッドを呼び出します。

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>パラメーター

*bRegTypeLib*<br/>
タイプライブラリを登録する場合は TRUE。 既定値は FALSE です。

*pCLSID*<br/>
登録するオブジェクトの CLSID を指します。 NULL (既定値) の場合、オブジェクトマップ内のすべてのオブジェクトが登録されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

グローバル関数[AtlComModuleRegisterServer](server-registration-global-functions.md#atlcommoduleregisterserver)を呼び出します。

##  <a name="registertypelib"></a>CAtlComModule::RegisterTypeLib

タイプライブラリを登録するには、このメソッドを呼び出します。

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>パラメーター

*lpszIndex*<br/>
"\\\N" 形式の文字列。ここで、N は TYPELIB リソースの整数インデックスです。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

タイプライブラリに関する情報をシステムレジストリに追加します。 モジュールインスタンスに複数のタイプライブラリが含まれている場合は、このメソッドの最初のバージョンを使用して、使用するタイプライブラリを指定します。

##  <a name="unregisterserver"></a>CAtlComModule::UnregisterServer

オブジェクトマップ内の各オブジェクトの登録を解除するには、このメソッドを呼び出します。

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>パラメーター

*bRegTypeLib*<br/>
タイプライブラリの登録を解除する場合は TRUE。 既定値は FALSE です。

*pCLSID*<br/>
登録を解除するオブジェクトの CLSID を指します。 NULL (既定値) の場合、オブジェクトマップ内のすべてのオブジェクトの登録が解除されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

グローバル関数[AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver)を呼び出します。

##  <a name="unregistertypelib"></a>CAtlComModule::UnRegisterTypeLib

タイプライブラリの登録を解除するには、このメソッドを呼び出します。

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>パラメーター

*lpszIndex*<br/>
"\\\N" 形式の文字列。ここで、N は TYPELIB リソースの整数インデックスです。

### <a name="remarks"></a>解説

タイプライブラリに関する情報をシステムレジストリから削除します。 モジュールインスタンスに複数のタイプライブラリが含まれている場合は、このメソッドの最初のバージョンを使用して、使用するタイプライブラリを指定します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

## <a name="see-also"></a>参照

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
