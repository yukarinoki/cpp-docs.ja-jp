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
ms.openlocfilehash: d0bc98fa48f84e67ab38106dea3fe22d5ad1757d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78857352"
---
# <a name="catlwinmodule-class"></a>CAtlWinModule クラス

このクラスは、ATL ウィンドウコンポーネントをサポートします。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CAtlWinModule::CAtlWinModule](#catlwinmodule)|コンストラクターです。|
|[CAtlWinModule:: ~ CAtlWinModule](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CAtlWinModule::AddCreateWndData](#addcreatewnddata)|データオブジェクトを追加します。|
|[CAtlWinModule::ExtractCreateWndData](#extractcreatewnddata)|ウィンドウのモジュールデータオブジェクトへのポインターを返します。|

## <a name="remarks"></a>コメント

このクラスは、ウィンドウ機能を必要とするすべての ATL クラスをサポートします。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

##  <a name="addcreatewnddata"></a>CAtlWinModule::AddCreateWndData

このメソッドは、`_AtlCreateWndData` 構造体を初期化して追加します。

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>パラメーター

*pData*<br/>
現在のモジュールに初期化されて追加される `_AtlCreateWndData` 構造体へのポインター。

*pObject*<br/>
オブジェクトの**this**ポインターへのポインター。

### <a name="remarks"></a>コメント

このメソッドは、 [_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体を初期化する[AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata)を呼び出します。 この構造体は、ウィンドウプロシージャでクラスインスタンスを取得するために使用される**this**ポインターを格納します。

##  <a name="catlwinmodule"></a>CAtlWinModule::CAtlWinModule

コンストラクターです。

```
CAtlWinModule();
```

### <a name="remarks"></a>コメント

初期化に失敗した場合は、 **EXCEPTION_NONCONTINUABLE**例外が発生します。

##  <a name="dtor"></a>CAtlWinModule:: ~ CAtlWinModule

デストラクターです。

```
~CAtlWinModule();
```

### <a name="remarks"></a>コメント

割り当てられたすべてのリソースを解放します。

##  <a name="extractcreatewnddata"></a>CAtlWinModule::ExtractCreateWndData

このメソッドは、`_AtlCreateWndData` 構造体へのポインターを返します。

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>戻り値

[CAtlWinModule:: AddCreateWndData](#addcreatewnddata)で以前に追加された `_AtlCreateWndData` 構造体へのポインターを返します。使用可能なオブジェクトがない場合は NULL を返します。

## <a name="see-also"></a>参照

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュールクラス](../../atl/atl-module-classes.md)
