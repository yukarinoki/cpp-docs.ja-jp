---
title: プロパティ マップ マクロ
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
ms.openlocfilehash: 56fdb02939a99e396b9000705753e2475b80f6dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326101"
---
# <a name="property-map-macros"></a>プロパティ マップ マクロ

これらのマクロは、プロパティ マップとエントリを定義します。

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL プロパティ マップの先頭を示します。|
|[PROP_DATA_ENTRY](#prop_data_entry)|ActiveX コントロールの範囲またはサイズを示します。|
|[PROP_ENTRY_TYPE](#prop_entry_type)|プロパティ マップにプロパティの説明、プロパティ DISPID、およびプロパティ ページの CLSID を入力します。|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|プロパティ マップに、プロパティの説明、プロパティ DISPID、プロパティ`IDispatch`ページ CLSID、および IID を入力します。|
|[Prop_page](#prop_page)|プロパティ マップにプロパティ ページ CLSID を入力します。|
|[END_PROP_MAP](#end_prop_map)|ATL プロパティ マップの終わりを示します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="begin_prop_map"></a><a name="begin_prop_map"></a>BEGIN_PROP_MAP

オブジェクトのプロパティ マップの先頭を示します。

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
[in]プロパティ マップを含むクラスを指定します。

### <a name="remarks"></a>解説

プロパティ マップには、プロパティの説明、プロパティの DID、プロパティ ページの CLID、`IDispatch`および IID が格納されます。 クラス[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md) [、IPersistPropertyBagImpl、IPersistStreamInitImpl](../../atl/reference/ipersistpropertybagimpl-class.md)、および[Iは](../../atl/reference/ispecifypropertypagesimpl-class.md)プロパティ マップを使用して、この情報を取得して設定します。 [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)

ATL プロジェクト ウィザードを使用してオブジェクトを作成すると、ウィザードは、BEGIN_PROP_MAPを指定して、空のプロパティ マップ[を作成END_PROP_MAP。](#end_prop_map)

BEGIN_PROP_MAPは、プロパティ マップを使用するオブジェクトにユーザー インターフェイスが存在しない場合があるため、プロパティ マップの範囲 (つまり、ディメンション) を保存しません。 オブジェクトがユーザー インターフェイスを持つ ActiveX コントロールの場合、そのオブジェクトには範囲があります。 この場合、範囲を指定するために、プロパティ マップに[PROP_DATA_ENTRY](#prop_data_entry)を指定する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

## <a name="prop_data_entry"></a><a name="prop_data_entry"></a>PROP_DATA_ENTRY

ActiveX コントロールの範囲またはサイズを示します。

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*<br/>
[in]プロパティの説明。

*メンバー*<br/>
[in]エクステントを含むデータ メンバー。たとえば、`m_sizeExtent`などです。

*vt*<br/>
[in]プロパティのバリアント型を指定します。

### <a name="remarks"></a>解説

このマクロは、指定されたデータ メンバを永続化します。

ActiveX コントロールを作成すると、プロパティ マップ マクロ[BEGIN_PROP_MAP](#begin_prop_map)後、プロパティ マップ マクロ[がEND_PROP_MAP](#end_prop_map)前に、このマクロが挿入されます。

### <a name="example"></a>例

次の例では、オブジェクト ( )`m_sizeExtent`の範囲が永続化されています。

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

## <a name="prop_entry_type"></a><a name="prop_entry_type"></a>PROP_ENTRY_TYPE

このマクロを使用して、プロパティの説明、プロパティ DISPID、およびプロパティ ページの CLSID をオブジェクトのプロパティ マップに入力します。

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*<br/>
[in]プロパティの説明。

*Dispid*<br/>
[in]プロパティの DISPID。

*Clsid*<br/>
[in]関連付けられているプロパティ ページの CLSID。 関連付けられたプロパティ ページがないプロパティには、CLSID_NULL特殊な値を使用します。

*vt*<br/>
[in]プロパティの型。

### <a name="remarks"></a>解説

PROP_ENTRYマクロは安全でなかったし、非推奨です。 PROP_ENTRY_TYPEに置き換えられました。

[BEGIN_PROP_MAP](#begin_prop_map)マクロは、プロパティ マップの先頭を示します。END_PROP_MAP [END_PROP_MAP](#end_prop_map)マクロは終了をマークします。

### <a name="example"></a>例

[BEGIN_PROP_MAP](#begin_prop_map)の例を参照してください。

## <a name="prop_entry_type_ex"></a><a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX

[PROP_ENTRY_TYPE](#prop_entry_type)と同様ですが、オブジェクトが複数のデュアル インターフェイスをサポートしている場合は、特定の IID を指定できます。

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*<br/>
[in]プロパティの説明。

*Dispid*<br/>
[in]プロパティの DISPID。

*Clsid*<br/>
[in]関連付けられているプロパティ ページの CLSID。 関連付けられたプロパティ ページがないプロパティには、CLSID_NULL特殊な値を使用します。

*iid ディスパッチ*<br/>
[in]プロパティを定義するデュアル インターフェイスの IID。

*vt*<br/>
[in]プロパティの型。

### <a name="remarks"></a>解説

PROP_ENTRY_EX マクロはセキュリティで保護されておらず、非推奨でした。 PROP_ENTRY_TYPE_EXに置き換えられました。

[BEGIN_PROP_MAP](#begin_prop_map)マクロは、プロパティ マップの先頭を示します。END_PROP_MAP [END_PROP_MAP](#end_prop_map)マクロは終了をマークします。

### <a name="example"></a>例

次の例では、`IMyDual1`のエントリの後に`IMyDual2`、 のエントリをグループ化します。 デュアル インターフェイスでグループ化すると、パフォーマンスが向上します。

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

## <a name="prop_page"></a><a name="prop_page"></a>Prop_page

このマクロを使用して、オブジェクトのプロパティ マップにプロパティ ページ CLSID を入力します。

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>パラメーター

*Clsid*<br/>
[in]プロパティ ページの CLSID。

### <a name="remarks"></a>解説

PROP_PAGEは[PROP_ENTRY_TYPE](#prop_entry_type)に似ていますが、プロパティの説明や DISPID は必要ありません。

> [!NOTE]
> PROP_ENTRY_TYPE または[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)を含む CLSID を既に入力している場合は、PROP_PAGEを追加する必要はありません。

[BEGIN_PROP_MAP](#begin_prop_map)マクロは、プロパティ マップの先頭を示します。END_PROP_MAP [END_PROP_MAP](#end_prop_map)マクロは終了をマークします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

## <a name="end_prop_map"></a><a name="end_prop_map"></a>END_PROP_MAP

オブジェクトのプロパティ マップの終わりを示します。

```
END_PROP_MAP()
```

### <a name="remarks"></a>解説

ATL プロジェクト ウィザードを使用してオブジェクトを作成する場合、ウィザードは、BEGIN_PROP_MAP[の後に](#begin_prop_map)END_PROP_MAPを指定して、空のプロパティ マップを作成します。

### <a name="example"></a>例

[BEGIN_PROP_MAP](#begin_prop_map)の例を参照してください。

## <a name="see-also"></a>関連項目

[マクロ](../../atl/reference/atl-macros.md)
