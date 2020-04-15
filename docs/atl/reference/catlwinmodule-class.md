---
title: クラス
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
ms.openlocfilehash: 40385fd592563837546b483bb80978cde6a56555
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321273"
---
# <a name="catlwinmodule-class"></a>クラス

このクラスは、ATL ウィンドウ コンポーネントをサポートします。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CAtlWinModule : public _ATL_WIN_MODULE
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[カトルウィンモジュール::カトルウィンモジュール](#catlwinmodule)|コンストラクターです。|
|[CAtlWin モジュール::~CAtlWin モジュール](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を使用します。](#addcreatewnddata)|データ オブジェクトを追加します。|
|[を作成します。](#extractcreatewnddata)|ウィンドウ モジュール データ オブジェクトへのポインターを返します。|

## <a name="remarks"></a>解説

このクラスは、ウィンドウ機能を必要とするすべての ATL クラスをサポートします。

## <a name="inheritance-hierarchy"></a>継承階層

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)

`CAtlWinModule`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="catlwinmoduleaddcreatewnddata"></a><a name="addcreatewnddata"></a>を使用します。

このメソッドは、構造体を初期化`_AtlCreateWndData`して追加します。

```
void AddCreateWndData(_AtlCreateWndData* pData, void* pObject);
```

### <a name="parameters"></a>パラメーター

*Pdata*<br/>
初期化および現在`_AtlCreateWndData`のモジュールに追加する構造体へのポインター。

*pObject*<br/>
オブジェクトの**この**ポインターへのポインター。

### <a name="remarks"></a>解説

このメソッドは[、_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体を初期化する[AtlWinModuleAddCreateWndData](winmodule-global-functions.md#atlwinmoduleaddcreatewnddata)を呼び出します。 この構造体は、ウィンドウ プロシージャでクラス インスタンスを取得するために使用される**this**ポインターを格納します。

## <a name="catlwinmodulecatlwinmodule"></a><a name="catlwinmodule"></a>カトルウィンモジュール::カトルウィンモジュール

コンストラクターです。

```
CAtlWinModule();
```

### <a name="remarks"></a>解説

初期化が失敗すると **、EXCEPTION_NONCONTINUABLE**例外が発生します。

## <a name="catlwinmodulecatlwinmodule"></a><a name="dtor"></a>CAtlWin モジュール::~CAtlWin モジュール

デストラクターです。

```
~CAtlWinModule();
```

### <a name="remarks"></a>解説

割り当てられたすべてのリソースを解放します。

## <a name="catlwinmoduleextractcreatewnddata"></a><a name="extractcreatewnddata"></a>を作成します。

このメソッドは、構造体へのポインター`_AtlCreateWndData`を返します。

```
void* ExtractCreateWndData();
```

### <a name="return-value"></a>戻り値

以前に`_AtlCreateWndData`[追加](#addcreatewnddata)された構造体へのポインターを返します。

## <a name="see-also"></a>関連項目

[_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[モジュール クラス](../../atl/atl-module-classes.md)
