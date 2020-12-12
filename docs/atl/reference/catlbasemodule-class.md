---
description: '詳細情報: CAtlBaseModule クラス'
title: CAtlBaseModule クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
ms.openlocfilehash: 249b2ad2d133ba0f407e9c5fabcf716b09605972
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147538"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule クラス

このクラスは、すべての ATL プロジェクトでインスタンス化されます。

## <a name="syntax"></a>構文

```cpp
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlBaseModule:: AddResourceInstance](#addresourceinstance)|格納されているハンドルのリストにリソースインスタンスを追加します。|
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|指定されたリソースインスタンスへのハンドルを返します。|
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|オブジェクトからモジュールインスタンスを返し `CAtlBaseModule` ます。|
|[CAtlBaseModule:: GetResourceInstance](#getresourceinstance)|オブジェクトからリソースインスタンスを返し `CAtlBaseModule` ます。|
|[CAtlBaseModule:: RemoveResourceInstance](#removeresourceinstance)|格納されているハンドルの一覧からリソースインスタンスを削除します。|
|[CAtlBaseModule:: SetResourceInstance](#setresourceinstance)|オブジェクトのリソースインスタンスを設定 `CAtlBaseModule` します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAtlBaseModule:: m_bInitFailed](#m_binitfailed)|モジュールの初期化が失敗したかどうかを示す変数。|

## <a name="remarks"></a>解説

`CAtlBaseModule`_AtlBaseModule という名前のインスタンスは、すべての ATL プロジェクトに存在します。これには、モジュールインスタンスへのハンドル、リソース (既定では1と同じ) を含むモジュールへのハンドル、およびプライマリリソースを提供するモジュールへのハンドルの配列が含まれます。 `CAtlBaseModule` 複数のスレッドから安全にアクセスできます。

このクラスは、以前のバージョンの ATL で使用されていた古い [CComModule](../../atl/reference/ccommodule-class.md) クラスに代わるものです。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>要件

**ヘッダー:** atlcore .h

## <a name="catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a> CAtlBaseModule:: AddResourceInstance

格納されているハンドルのリストにリソースインスタンスを追加します。

```cpp
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>パラメーター

*hInst*<br/>
追加するリソースインスタンス。

### <a name="return-value"></a>戻り値

リソースが正常に追加された場合は true、それ以外の場合は false を返します。

## <a name="catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a> CAtlBaseModule::CAtlBaseModule

コンストラクターです。

```cpp
CAtlBaseModule() throw();
```

### <a name="remarks"></a>解説

`CAtlBaseModule` を作成します。

## <a name="catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a> CAtlBaseModule::GetHInstanceAt

指定されたリソースインスタンスへのハンドルを返します。

```cpp
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>パラメーター

*i*<br/>
リソースインスタンスの番号。

### <a name="return-value"></a>戻り値

リソースインスタンスへのハンドルを返します。対応するリソースインスタンスが存在しない場合は NULL を返します。

## <a name="catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a> CAtlBaseModule::GetModuleInstance

オブジェクトからモジュールインスタンスを返し `CAtlBaseModule` ます。

```cpp
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>戻り値

モジュールのインスタンスを返します。

## <a name="catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a> CAtlBaseModule:: GetResourceInstance

リソースインスタンスを返します。

```cpp
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>戻り値

リソースインスタンスを返します。

## <a name="catlbasemodulem_binitfailed"></a><a name="m_binitfailed"></a> CAtlBaseModule:: m_bInitFailed

モジュールの初期化が失敗したかどうかを示す変数。

```cpp
static bool m_bInitFailed;
```

### <a name="remarks"></a>解説

モジュールが初期化された場合は True。初期化に失敗した場合は false。

## <a name="catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a> CAtlBaseModule:: RemoveResourceInstance

格納されているハンドルの一覧からリソースインスタンスを削除します。

```cpp
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>パラメーター

*hInst*<br/>
削除するリソースインスタンス。

### <a name="return-value"></a>戻り値

リソースが正常に削除された場合は true、それ以外の場合は false を返します。

## <a name="catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a> CAtlBaseModule:: SetResourceInstance

オブジェクトのリソースインスタンスを設定 `CAtlBaseModule` します。

```cpp
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>パラメーター

*hInst*<br/>
新しいリソースインスタンス。

### <a name="return-value"></a>戻り値

更新されたリソースインスタンスを返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュールクラス](../../atl/atl-module-classes.md)
