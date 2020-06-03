---
title: グローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 3d7d001a2835514cc5385a7069c0bcda58cdd88e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329360"
---
# <a name="winmodule-global-functions"></a>グローバル関数

これらの関数は、構造体`_AtlCreateWndData`の操作をサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行されるアプリケーションでは使用できません。

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|`_AtlCreateWndData` 構造体を初期化して追加します。|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|既存の `_AtlCreateWndData` 構造体を抽出します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a>データを追加します。

`_AtlCreateWndData` 構造体を初期化して追加します。

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>パラメーター

*モジュール*<br/>
モジュールの[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)構造体へのポインター。

*Pdata*<br/>
初期化および現在のモジュールに追加する[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体へのポインター。

*pObject*<br/>
オブジェクトの**この**ポインターへのポインター。

### <a name="remarks"></a>解説

クラス インスタンス`_AtlCreateWndData`の参照に使用される**this**ポインターを格納するために使用される構造体を初期化し、モジュールの`_ATL_WIN_MODULE70`構造体によって参照されるリストに追加します。 [によって](catlwinmodule-class.md#addcreatewnddata)呼び出されます。

## <a name="atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a>データを抽出します。

既存の `_AtlCreateWndData` 構造体を抽出します。

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>パラメーター

*モジュール*<br/>
モジュールの[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)構造体へのポインター。

### <a name="return-value"></a>戻り値

[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体へのポインターを返します。

### <a name="remarks"></a>解説

この関数は、モジュールの`_AtlCreateWndData`構造によって参照されるリストから既存の`_ATL_WIN_MODULE70`構造を抽出します。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
