---
description: 詳細については、「COM Map グローバル関数」を参照してください。
title: COM マップのグローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: ee502a68a0a3b21849d2fabdadcc9ecbbcc1602d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141337"
---
# <a name="com-map-global-functions"></a>COM マップのグローバル関数

これらの関数は、COM マップの実装をサポート `IUnknown` します。

|機能|説明|
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|`IUnknown`非集計オブジェクトのにデリゲートします。|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|インターフェイスをと比較するための効率的なコードを生成 `IUnknown` します。|

## <a name="requirements"></a>要件

**ヘッダー:** atlbase. h

## <a name="atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a> AtlInternalQueryInterface

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
からに公開されているインターフェイスの COM マップを格納しているオブジェクトへのポインター `QueryInterface` 。

*pEntries*<br/>
から `_ATL_INTMAP_ENTRY` 使用可能なインターフェイスのマップにアクセスする構造体の配列。

*iid*<br/>
から要求されているインターフェイスの GUID。

*ppvObject*<br/>
入出力 *Iid* で指定されたインターフェイスポインターへのポインター。インターフェイスが見つからない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の1つ。

### <a name="remarks"></a>解説

`AtlInternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトが集計されている場合、 `AtlInternalQueryInterface` は外側の不明なに委任しません。 COM マップテーブルには、マクロ [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) またはそのバリアントの1つを使用して、インターフェイスを入力できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

## <a name="inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a> InlineIsEqualIUnknown

のテストの特殊なケースとして、この関数を呼び出し `IUnknown` ます。

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>パラメーター

*rguid1*<br/>
からと比較する GUID `IID_IUnknown` 。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)<br/>
[COM マップマクロ](../../atl/reference/com-map-macros.md)
