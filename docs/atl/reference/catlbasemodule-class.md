---
title: クラス
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
ms.openlocfilehash: a55412eff18fd04ac4e41c0f001991c1cf725b9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321510"
---
# <a name="catlbasemodule-class"></a>クラス

このクラスは、すべての ATL プロジェクトでインスタンス化されます。

## <a name="syntax"></a>構文

```
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[モジュール::カトルベースモジュール](#catlbasemodule)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[インスタンスインスタンス](#addresourceinstance)|格納されているハンドルの一覧にリソース インスタンスを追加します。|
|[インスタンスモジュール::ゲットインスタンスアット](#gethinstanceat)|指定したリソース インスタンスへのハンドルを返します。|
|[インスタンスインスタンス](#getmoduleinstance)|オブジェクトからモジュール インスタンスを`CAtlBaseModule`返します。|
|[インスタンスインスタンス](#getresourceinstance)|オブジェクトからリソース インスタンスを`CAtlBaseModule`返します。|
|[インスタンスインスタンス](#removeresourceinstance)|格納されているハンドルの一覧からリソース インスタンスを削除します。|
|[インスタンスインスタンス](#setresourceinstance)|オブジェクトのリソース インスタンスを`CAtlBaseModule`設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[モジュール:m_bInitFailed](#m_binitfailed)|モジュールの初期化が失敗したかどうかを示す変数。|

## <a name="remarks"></a>解説

名前付き`CAtlBaseModule`_AtlBaseModuleのインスタンスは、モジュール インスタンスへのハンドル、リソースを含むモジュールへのハンドル (既定では同じ) を含む各 ATL プロジェクトに存在し、プライマリ リソースを提供するモジュールへのハンドルの配列を含みます。 `CAtlBaseModule`複数のスレッドから安全にアクセスできます。

このクラスは、以前のバージョンの ATL で使用していた、古い[CComModule](../../atl/reference/ccommodule-class.md)クラスを置き換えます。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore.h

## <a name="catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a>インスタンスインスタンス

格納されているハンドルの一覧にリソース インスタンスを追加します。

```
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>パラメーター

*hInst*<br/>
追加するリソース インスタンス。

### <a name="return-value"></a>戻り値

リソースが正常に追加された場合は true、それ以外の場合は false を返します。

## <a name="catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a>モジュール::カトルベースモジュール

コンストラクターです。

```
CAtlBaseModule() throw();
```

### <a name="remarks"></a>解説

`CAtlBaseModule` を作成します。

## <a name="catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a>インスタンスモジュール::ゲットインスタンスアット

指定したリソース インスタンスへのハンドルを返します。

```
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>パラメーター

*私*<br/>
リソース インスタンスの番号。

### <a name="return-value"></a>戻り値

リソース インスタンスへのハンドルを返します。

## <a name="catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>インスタンスインスタンス

オブジェクトからモジュール インスタンスを`CAtlBaseModule`返します。

```
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>戻り値

モジュール インスタンスを返します。

## <a name="catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a>インスタンスインスタンス

リソース インスタンスを返します。

```
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>戻り値

リソース インスタンスを返します。

## <a name="catlbasemodulem_binitfailed"></a><a name="m_binitfailed"></a>モジュール:m_bInitFailed

モジュールの初期化が失敗したかどうかを示す変数。

```
static bool m_bInitFailed;
```

### <a name="remarks"></a>解説

モジュールが初期化された場合は True、初期化に失敗した場合は false。

## <a name="catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a>インスタンスインスタンス

格納されているハンドルの一覧からリソース インスタンスを削除します。

```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>パラメーター

*hInst*<br/>
削除するリソース インスタンス。

### <a name="return-value"></a>戻り値

リソースが正常に削除された場合は true、それ以外の場合は false を返します。

## <a name="catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a>インスタンスインスタンス

オブジェクトのリソース インスタンスを`CAtlBaseModule`設定します。

```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>パラメーター

*hInst*<br/>
新しいリソース インスタンス。

### <a name="return-value"></a>戻り値

更新されたリソース インスタンスを返します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)
