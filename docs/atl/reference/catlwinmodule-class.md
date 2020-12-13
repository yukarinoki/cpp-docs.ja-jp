---
description: '詳細情報: CAtlWinModule クラス'
title: CAtlWinModule クラス
ms.date: 11/04/2016
f1_keywords:
- CAtlWinModule
- ATLBASE/ATL::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::CAtlWinModule
- ATLBASE/ATL::CAtlWinModule::AddCreateWndData
- ATLBASE/ATL::CAtlWinModule::ExtractCreateWndData
helpviewer_keywords:
- CAtlWinModule class
ms.assetid: 7ec844af-0f68-4a34-b0c8-9de50a025df0
ms.openlocfilehash: 4ed0c52a59401fa5411fd6d5acbcaf72f31aeb11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152571"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule クラス

このクラスは、ATL ウィンドウコンポーネントをサポートします。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|コンストラクターです。|
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|データオブジェクトを追加します。|
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|ウィンドウのモジュールデータオブジェクトへのポインターを返します。|

## <a name="remarks"></a>解説

このクラスは、ウィンドウ機能を必要とするすべての ATL クラスをサポートします。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a> CAtlWinModule::AddCreateWndData

このメソッドは、構造体を初期化して追加し `_AtlCreateWndData` ます。

```cpp
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>パラメーター

*pData*<br/>
`_AtlCreateWndData`初期化され、現在のモジュールに追加される構造体へのポインター。

*pObject*<br/>
オブジェクトのポインターへのポインター **`this`** 。

### <a name="remarks"></a>解説

このメソッドは、 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体を初期化する[AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata)を呼び出します。 この構造体は、 **`this`** ウィンドウプロシージャでクラスインスタンスを取得するために使用されるポインターを格納します。

## <a name="catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a> CAtlWinModule::CAtlWinModule

コンストラクターです。

```cpp
CAtlWinModule();
```

### <a name="remarks"></a>解説

初期化に失敗した場合は、 **EXCEPTION_NONCONTINUABLE** 例外が発生します。

## <a name="catlwinmodulecatlwinmodule"></a><a name="dtor"></a> CAtlWinModule:: ~ CAtlWinModule

デストラクターです。

```cpp
~CAtlWinModule();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a> CAtlWinModule::ExtractCreateWndData

このメソッドは、構造体へのポインターを返し `_AtlCreateWndData` ます。

```cpp
void* ExtractCreateWndData();
```

### <a name="return-value"></a>戻り値

`_AtlCreateWndData` [CAtlWinModule:: AddCreateWndData](#addcreatewnddata)で以前に追加された構造体へのポインターを返します。使用可能なオブジェクトがない場合は NULL を返します。

## <a name="see-also"></a>関連項目

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュールクラス](../../atl/atl-module-classes.md)
