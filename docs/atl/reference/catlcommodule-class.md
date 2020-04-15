---
title: クラス
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
ms.openlocfilehash: 68fdb48edc9304d9d74df6f36bd208cfd35ff307
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321477"
---
# <a name="catlcommodule-class"></a>クラス

このクラスは、COM サーバー モジュールを実装します。

## <a name="syntax"></a>構文

```
class CAtlComModule : public _ATL_COM_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カトルコムモジュール::カトルコムモジュール](#catlcommodule)|コンストラクターです。|
|[をクリックします。](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[サービスを提供します。](#registerserver)|オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。|
|[をクリックします。](#registertypelib)|タイプ ライブラリを登録します。|
|[サーバーを登録解除します。](#unregisterserver)|オブジェクト マップ内の各オブジェクトの登録を解除します。|
|[をクリックします。](#unregistertypelib)|タイプ ライブラリの登録を解除します。|

## <a name="remarks"></a>解説

`CAtlComModule`は、クライアントがモジュールのコンポーネントにアクセスできるように、COM サーバー モジュールを実装します。

このクラスは、以前のバージョンの ATL で使用していた、古い[CComModule](../../atl/reference/ccommodule-class.md)クラスを置き換えます。 詳細については[、「ATL モジュール クラス](../../atl/atl-module-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)

`CAtlComModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="catlcommodulecatlcommodule"></a><a name="catlcommodule"></a>カトルコムモジュール::カトルコムモジュール

コンストラクターです。

```
CAtlComModule() throw();
```

### <a name="remarks"></a>解説

モジュールを初期化します。

## <a name="catlcommodulecatlcommodule"></a><a name="dtor"></a>をクリックします。

デストラクターです。

```
~CAtlComModule();
```

### <a name="remarks"></a>解説

すべてのクラスファクトリを解放します。

## <a name="catlcommoduleregisterserver"></a><a name="registerserver"></a>サービスを提供します。

オブジェクト マップ内の各オブジェクトのシステム レジストリを更新します。

```
HRESULT RegisterServer(BOOL bRegTypeLib = FALSE, const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
タイプ ライブラリを登録する場合は TRUE。 既定値は FALSE です。

*pCLSID*<br/>
登録するオブジェクトの CLSID へのポイント。 NULL (既定値) の場合、オブジェクト マップ内のすべてのオブジェクトが登録されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

グローバル関数を呼び出[します](server-registration-global-functions.md#atlcommoduleregisterserver)。

## <a name="catlcommoduleregistertypelib"></a><a name="registertypelib"></a>をクリックします。

タイプ ライブラリを登録します。

```
HRESULT RegisterTypeLib(LPCTSTR lpszIndex);
HRESULT RegisterTypeLib();
```

### <a name="parameters"></a>パラメーター

*インデックスを使用します。*<br/>
"\N"\\という形式の文字列は、N は TYPELIB リソースの整数インデックスです。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

タイプ ライブラリに関する情報をシステム レジストリに追加します。 モジュール インスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの最初のバージョンを使用して、使用するタイプ ライブラリを指定します。

## <a name="catlcommoduleunregisterserver"></a><a name="unregisterserver"></a>サーバーを登録解除します。

オブジェクト マップ内の各オブジェクトの登録を解除します。

```
HRESULT UnregisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
タイプ ライブラリを登録解除する場合は TRUE。 既定値は FALSE です。

*pCLSID*<br/>
登録解除するオブジェクトの CLSID へのポイント。 NULL (既定値) の場合、オブジェクト マップ内のすべてのオブジェクトの登録が解除されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

グローバル[関数を](server-registration-global-functions.md#atlcommoduleunregisterserver)呼び出します。

## <a name="catlcommoduleunregistertypelib"></a><a name="unregistertypelib"></a>をクリックします。

タイプ ライブラリの登録を解除します。

```
HRESULT UnRegisterTypeLib(LPCTSTR lpszIndex);
HRESULT UnRegisterTypeLib();
```

### <a name="parameters"></a>パラメーター

*インデックスを使用します。*<br/>
"\N"\\という形式の文字列は、N は TYPELIB リソースの整数インデックスです。

### <a name="remarks"></a>解説

タイプ ライブラリに関する情報をシステム レジストリから削除します。 モジュール インスタンスに複数のタイプ ライブラリが含まれている場合は、このメソッドの最初のバージョンを使用して、使用するタイプ ライブラリを指定します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="see-also"></a>関連項目

[_ATL_COM_MODULE](atl-typedefs.md#_atl_com_module)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
