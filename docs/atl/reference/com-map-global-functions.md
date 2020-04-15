---
title: COM マップ グローバル関数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlInternalQueryInterface
- atlbase/ATL::InlineIsEqualIUnknown
helpviewer_keywords:
- COM interfaces, COM map global functions
ms.assetid: b9612d30-eb23-46ef-8093-d56f237d3cf1
ms.openlocfilehash: c4ce7c7a68c0744ad65ef4914088fa12d3340628
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326692"
---
# <a name="com-map-global-functions"></a>COM マップ グローバル関数

これらの関数は、COM マップ`IUnknown`の実装をサポートします。

|||
|-|-|
|[AtlInternalQueryInterface](#atlinternalqueryinterface)|非集約オブジェクト`IUnknown`の にデリゲートします。|
|[InlineIsEqualIUnknown](#inlineisequaliunknown)|インターフェイスを 比較するための効率的なコード`IUnknown`を 生成します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="atlinternalqueryinterface"></a><a name="atlinternalqueryinterface"></a>インターフェイス

要求されたインターフェイスへのポインターを取得します。

```
HRESULT AtlInternalQueryInterface(
    void* pThis,
    const _ATL_INTMAP_ENTRY* pEntries,
    REFIID iid,
    void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*pこれ*<br/>
[in]に公開されているインターフェイスの COM マップを格納しているオブジェクトへのポインター `QueryInterface`。

*エントリー*<br/>
[in]使用可能なインターフェイス`_ATL_INTMAP_ENTRY`のマップにアクセスする構造体の配列。

*Iid*<br/>
[in]要求されているインターフェイスの GUID。

*オブジェクト*<br/>
[アウト]*iid*で指定されたインターフェイス ポインターへのポインター、 またはインターフェイスが見つからない場合は NULL。

### <a name="return-value"></a>戻り値

標準の HRESULT 値の 1 つ。

### <a name="remarks"></a>解説

`AtlInternalQueryInterface` が処理するのは、COM マップ テーブル内のインターフェイスのみです。 オブジェクトが集約されている場合、`AtlInternalQueryInterface`外部不明にデリゲートしません。 COM マップ テーブルにインターフェイスを入力するには、マクロ[COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry)またはそのバリアントを使用します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#94](../../atl/codesnippet/cpp/com-map-global-functions_1.cpp)]

## <a name="inlineisequaliunknown"></a><a name="inlineisequaliunknown"></a>インラインイコールイ不明

のテストの特殊なケースでは、この関数を`IUnknown`呼び出します。

```
BOOL InlineIsEqualUnknown(REFGUID rguid1);
```

### <a name="parameters"></a>パラメーター

*rguid1*<br/>
[in]と比較する GUID`IID_IUnknown`です。

## <a name="see-also"></a>関連項目

[関数](../../atl/reference/atl-functions.md)<br/>
[COM マップ マクロ](../../atl/reference/com-map-macros.md)
