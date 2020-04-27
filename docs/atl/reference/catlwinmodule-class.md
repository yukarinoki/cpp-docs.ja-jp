---
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
ms.openlocfilehash: 5cdf13ebbb982ad8184a52dcf1a3e30d71e4e5b0
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167709"
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

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData

このメソッドは、 `_AtlCreateWndData`構造体を初期化して追加します。

```cpp
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>パラメーター

*pData*<br/>
初期化さ`_AtlCreateWndData`れ、現在のモジュールに追加される構造体へのポインター。

*pObject*<br/>
オブジェクトの**this**ポインターへのポインター。

### <a name="remarks"></a>解説

このメソッドは、 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体を初期化する[AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata)を呼び出します。 この構造体は、ウィンドウプロシージャでクラスインスタンスを取得するために使用される**this**ポインターを格納します。

## <a name="catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a>CAtlWinModule::CAtlWinModule

コンストラクターです。

```cpp
CAtlWinModule();
```

### <a name="remarks"></a>解説

初期化に失敗した場合は、 **EXCEPTION_NONCONTINUABLE**例外が発生します。

## <a name="catlwinmodulecatlwinmodule"></a><a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule

デストラクターです。

```cpp
~CAtlWinModule();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData

このメソッドは、 `_AtlCreateWndData`構造体へのポインターを返します。

```cpp
void* ExtractCreateWndData();
```

### <a name="return-value"></a>戻り値

[CAtlWinModule:: AddCreateWndData](#addcreatewnddata)で`_AtlCreateWndData`以前に追加された構造体へのポインターを返します。使用可能なオブジェクトがない場合は NULL を返します。

## <a name="see-also"></a>関連項目

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュールクラス](../../atl/atl-module-classes.md)
