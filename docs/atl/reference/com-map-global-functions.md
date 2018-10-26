---
title: COM マップに関するグローバル関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c158e5b59decd751340f87d5c29c572d6972d8e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077908"
---
# <a name="com-map-global-functions"></a>COM マップに関するグローバル関数

これらの関数では、COM マップのサポート`IUnknown`実装します。

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|デリゲート、`IUnknown`の非集約オブジェクト。|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|インターフェイスを比較するための効率的なコードを生成`IUnknown`します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

##  <a name="atlinternalqueryinterface"></a>  AtlInternalQueryInterface

要求されたインターフェイスへのポインターを取得します。

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*pThis*<br/>
[in]COM に公開されるインターフェイスのマップを格納しているオブジェクトへのポインター`QueryInterface`します。

*pEntries*<br/>
[in]配列の`_ATL_INTMAP_ENTRY`使用可能なインターフェイスのマップにアクセスする構造体。

*iid*<br/>
[in]要求されているインターフェイスの GUID です。

*ppvObject*<br/>
[out]指定されたインターフェイス ポインターへのポインター *iid*インターフェイスが見つからない場合は null です。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>Remarks

`AtlInternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトを集約すると場合、`AtlInternalQueryInterface`不明な外部への委任しません。 インターフェイスは、マクロ、COM マップ テーブルを入力できます[COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)またはそのバリエーションの 1 つ。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

##  <a name="inlineisequaliunknown"></a>  InlineIsEqualIUnknown

この関数の呼び出しのためのテストの特殊なケースの`IUnknown`します。

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>パラメーター

*rguid1*<br/>
[in]比較する GUID`IID_IUnknown`します。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)<br/>
[COM マップに関するマクロ](../../atl/reference/com-map-macros.md)
