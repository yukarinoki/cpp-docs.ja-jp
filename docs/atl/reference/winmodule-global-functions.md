---
title: WinModule のグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlWinModuleAddCreateWndData
- atlbase/ATL::AtlWinModuleExtractCreateWndData
ms.assetid: 8ce45a5b-26a7-491f-9096-c09ceca5f2c2
ms.openlocfilehash: 1a929fd0f583150e84ce5b1efa7e896bc16e4247
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229936"
---
# <a name="winmodule-global-functions"></a>WinModule のグローバル関数

これらの関数は、 `_AtlCreateWndData` 構造体の演算をサポートします。

> [!IMPORTANT]
> 次の表に示す関数は、Windows ランタイムで実行するアプリケーションでは使用できません。

|||
|-|-|
|[AtlWinModuleAddCreateWndData](#atlwinmoduleaddcreatewnddata)|`_AtlCreateWndData` 構造体を初期化して追加します。|
|[AtlWinModuleExtractCreateWndData](#atlwinmoduleextractcreatewnddata)|既存の `_AtlCreateWndData` 構造体を抽出します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase. h

## <a name="atlwinmoduleaddcreatewnddata"></a><a name="atlwinmoduleaddcreatewnddata"></a>AtlWinModuleAddCreateWndData

`_AtlCreateWndData` 構造体を初期化して追加します。

```
ATLINLINE ATLAPI_(void) AtlWinModuleAddCreateWndData(
    _ATL_WIN_MODULE* pWinModule,
    _AtlCreateWndData* pData,
    void* pObject);
```

### <a name="parameters"></a>パラメーター

*pWinModule*<br/>
モジュールの[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)構造体へのポインター。

*pData*<br/>
現在のモジュールに初期化されて追加される[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体へのポインター。

*pObject*<br/>
オブジェクトのポインターへのポインター **`this`** 。

### <a name="remarks"></a>解説

`_AtlCreateWndData`構造体を初期化します。これは、 **`this`** クラスインスタンスを参照するために使用されるポインターを格納するために使用され、それをモジュールの構造体によって参照されるリストに追加し `_ATL_WIN_MODULE70` ます。 [CAtlWinModule:: AddCreateWndData](catlwinmodule-class.md#addcreatewnddata)によって呼び出されます。

## <a name="atlwinmoduleextractcreatewnddata"></a><a name="atlwinmoduleextractcreatewnddata"></a>AtlWinModuleExtractCreateWndData

既存の `_AtlCreateWndData` 構造体を抽出します。

```
ATLINLINE ATLAPI_(void*) AtlWinModuleExtractCreateWndData(_ATL_WIN_MODULE* pWinModule);
```

### <a name="parameters"></a>パラメーター

*pWinModule*<br/>
モジュールの[_ATL_WIN_MODULE70](../../atl/reference/atl-win-module70-structure.md)構造体へのポインター。

### <a name="return-value"></a>戻り値

[_AtlCreateWndData](../../atl/reference/atlcreatewnddata-structure.md)構造体へのポインターを返します。

### <a name="remarks"></a>解説

この関数は、 `_AtlCreateWndData` モジュールの構造体によって参照されるリストから既存の構造体を抽出 `_ATL_WIN_MODULE70` します。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)
