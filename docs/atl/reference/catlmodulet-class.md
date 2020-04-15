---
title: クラス
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
ms.openlocfilehash: bf64c073249b7426fafb430a708573d9d06d11fd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321420"
---
# <a name="catlmodulet-class"></a>クラス

このクラスは ATL モジュールを実装します。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
クラスから派生`CAtlModuleT`したクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カトルモジュールT::カトルモジュール](#catlmodulet)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#initlibid)|現在のモジュールの GUID を含むデータ メンバーを初期化します。|
|[をクリックします。](#registerappid)|EXE をレジストリに追加します。|
|[をクリックします。](#registerserver)|サービスをレジストリに追加します。|
|[を登録解除します。](#unregisterappid)|EXE をレジストリから削除します。|
|[サーバーを登録解除します。](#unregisterserver)|レジストリからサービスを削除します。|
|[をクリックします。](#updateregistryappid)|レジストリ内の EXE 情報を更新します。|

## <a name="remarks"></a>解説

`CAtlModuleT`から[派生した](../../atl/reference/catlmodule-class.md)、実行可能ファイル (EXE) またはサービス (EXE) の ATL モジュールを実装します。 実行可能モジュールは、ローカルのアウトプロセス サーバーですが、サービス モジュールは Windows の起動時にバックグラウンドで実行される Windows アプリケーションです。

`CAtlModuleT`は、モジュールの初期化、登録、および登録解除をサポートします。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[カトルモジュール](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="catlmoduletcatlmodulet"></a><a name="catlmodulet"></a>カトルモジュールT::カトルモジュール

コンストラクターです。

```
CAtlModuleT() throw();
```

### <a name="remarks"></a>解説

を呼び出します[。](#initlibid)

## <a name="catlmoduletinitlibid"></a><a name="initlibid"></a>をクリックします。

現在のモジュールの GUID を含むデータ メンバーを初期化します。

```
static void InitLibId() throw();
```

### <a name="remarks"></a>解説

コンストラクターによって呼び出[されます](#catlmodulet)。

## <a name="catlmoduletregisterappid"></a><a name="registerappid"></a>をクリックします。

EXE をレジストリに追加します。

```
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catlmoduletregisterserver"></a><a name="registerserver"></a>をクリックします。

サービスをレジストリに追加します。

```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
タイプ ライブラリを登録する場合は TRUE。 既定値は FALSE です。

*pCLSID*<br/>
登録するオブジェクトの CLSID へのポイント。 NULL (既定値) の場合、オブジェクト マップ内のすべてのオブジェクトが登録されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catlmoduletunregisterappid"></a><a name="unregisterappid"></a>を登録解除します。

EXE をレジストリから削除します。

```
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catlmoduletunregisterserver"></a><a name="unregisterserver"></a>サーバーを登録解除します。

レジストリからサービスを削除します。

```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
タイプ ライブラリも登録解除される場合は TRUE。

*pCLSID*<br/>
登録解除するオブジェクトの CLSID へのポイント。 NULL (既定値) の場合、オブジェクト マップ内のすべてのオブジェクトの登録が解除されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="catlmoduletupdateregistryappid"></a><a name="updateregistryappid"></a>をクリックします。

レジストリ内の EXE 情報を更新します。

```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>パラメーター

*b登録*<br/>
予約済み。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/catlmodule-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)
