---
description: '詳細情報: CAtlModuleT クラス'
title: CAtlModuleT クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
ms.openlocfilehash: 841d4a41b7df818d9e966af1050fd9e376d89447
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147226"
---
# <a name="catlmodulet-class"></a>CAtlModuleT クラス

このクラスは ATL モジュールを実装します。

## <a name="syntax"></a>構文

```cpp
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `CAtlModuleT` 。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlModuleT:: InitLibId](#initlibid)|現在のモジュールの GUID を含むデータメンバーを初期化します。|
|[CAtlModuleT:: RegisterAppId](#registerappid)|EXE をレジストリに追加します。|
|[CAtlModuleT::RegisterServer](#registerserver)|サービスをレジストリに追加します。|
|[CAtlModuleT:: UnregisterAppId](#unregisterappid)|レジストリから EXE を削除します。|
|[CAtlModuleT::UnregisterServer](#unregisterserver)|レジストリからサービスを削除します。|
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|レジストリ内の実行可能ファイルの情報を更新します。|

## <a name="remarks"></a>解説

`CAtlModuleT`[CAtlModule](../../atl/reference/catlmodule-class.md)から派生したは、実行可能 (exe) またはサービス (exe) の ATL モジュールを実装します。 実行可能モジュールはローカルのアウトプロセスサーバーであるのに対し、サービスモジュールは windows の起動時にバックグラウンドで実行される Windows アプリケーションです。

`CAtlModuleT` モジュールの初期化、登録、および登録解除のサポートを提供します。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="catlmoduletcatlmodulet"></a><a name="catlmodulet"></a> CAtlModuleT::CAtlModuleT

コンストラクターです。

```cpp
CAtlModuleT() throw();
```

### <a name="remarks"></a>解説

[CAtlModuleT:: InitLibId](#initlibid)を呼び出します。

## <a name="catlmoduletinitlibid"></a><a name="initlibid"></a> CAtlModuleT:: InitLibId

現在のモジュールの GUID を含むデータメンバーを初期化します。

```cpp
static void InitLibId() throw();
```

### <a name="remarks"></a>解説

コンストラクター [CAtlModuleT:: CAtlModuleT](#catlmodulet)によって呼び出されます。

## <a name="catlmoduletregisterappid"></a><a name="registerappid"></a> CAtlModuleT:: RegisterAppId

EXE をレジストリに追加します。

```cpp
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

## <a name="catlmoduletregisterserver"></a><a name="registerserver"></a> CAtlModuleT::RegisterServer

サービスをレジストリに追加します。

```cpp
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*bRegTypeLib*<br/>
タイプライブラリを登録する場合は TRUE。 既定値は FALSE です。

*pCLSID*<br/>
登録するオブジェクトの CLSID を指します。 NULL (既定値) の場合、オブジェクトマップ内のすべてのオブジェクトが登録されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

## <a name="catlmoduletunregisterappid"></a><a name="unregisterappid"></a> CAtlModuleT:: UnregisterAppId

レジストリから EXE を削除します。

```cpp
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

## <a name="catlmoduletunregisterserver"></a><a name="unregisterserver"></a> CAtlModuleT::UnregisterServer

レジストリからサービスを削除します。

```cpp
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*bUnRegTypeLib*<br/>
タイプライブラリも登録解除される場合は TRUE。

*pCLSID*<br/>
登録を解除するオブジェクトの CLSID を指します。 NULL (既定値) の場合、オブジェクトマップ内のすべてのオブジェクトの登録が解除されます。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

## <a name="catlmoduletupdateregistryappid"></a><a name="updateregistryappid"></a> CAtlModuleT::UpdateRegistryAppId

レジストリ内の実行可能ファイルの情報を更新します。

```cpp
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>パラメーター

*bRegister*<br/>
予約済み。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

## <a name="see-also"></a>関連項目

[CAtlModule クラス](../../atl/reference/catlmodule-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュールクラス](../../atl/atl-module-classes.md)
