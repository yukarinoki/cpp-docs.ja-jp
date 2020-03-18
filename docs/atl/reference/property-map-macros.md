---
title: プロパティマップマクロ
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
ms.openlocfilehash: 1e2e7235dd924467d9d5e0613a704fedf8340ae4
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79422974"
---
# <a name="property-map-macros"></a>プロパティマップマクロ

これらのマクロは、プロパティマップとエントリを定義します。

|||
|-|-|
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL プロパティマップの開始をマークします。|
|[PROP_DATA_ENTRY](#prop_data_entry)|ActiveX コントロールのエクステント (次元) を示します。|
|[PROP_ENTRY_TYPE](#prop_entry_type)|プロパティの説明、プロパティの DISPID、およびプロパティページの CLSID をプロパティマップに入力します。|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|プロパティの説明、プロパティの DISPID、プロパティページの CLSID、および `IDispatch` IID をプロパティマップに入力します。|
|[PROP_PAGE](#prop_page)|プロパティページの CLSID をプロパティマップに入力します。|
|[END_PROP_MAP](#end_prop_map)|ATL プロパティマップの終了をマークします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom. h

##  <a name="begin_prop_map"></a>BEGIN_PROP_MAP

オブジェクトのプロパティマップの開始をマークします。

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
からプロパティマップを含むクラスを指定します。

### <a name="remarks"></a>解説

プロパティマップには、プロパティの説明、プロパティ Dispid、プロパティページの Clsid、および `IDispatch` Iid がが格納されます。 クラス[Iperpropertybrowsingimpl](../../atl/reference/iperpropertybrowsingimpl-class.md)、 [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)、 [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)、および[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)は、プロパティマップを使用してこの情報を取得して設定します。

ATL プロジェクトウィザードを使用してオブジェクトを作成すると、ウィザードによって空のプロパティマップが作成されます。これには、BEGIN_PROP_MAP の後に[END_PROP_MAP](#end_prop_map)を指定します。

プロパティマップを使用しているオブジェクトにはユーザーインターフェイスがない可能性があるため、プロパティマップのエクステント (つまり、次元) は BEGIN_PROP_MAP によって保存されません。そのため、エクステントは存在しません。 オブジェクトがユーザーインターフェイスを持つ ActiveX コントロールである場合は、範囲があります。 この場合は、プロパティマップで[PROP_DATA_ENTRY](#prop_data_entry)を指定して範囲を指定する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

##  <a name="prop_data_entry"></a>PROP_DATA_ENTRY

ActiveX コントロールのエクステント (次元) を示します。

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*<br/>
からプロパティの説明。

*member*<br/>
からエクステントを含むデータメンバー。たとえば、`m_sizeExtent`のようにします。

*vt*<br/>
からプロパティのバリアント型を指定します。

### <a name="remarks"></a>解説

このマクロは、指定されたデータメンバーを永続化します。

ActiveX コントロールを作成すると、プロパティマップマクロ[BEGIN_PROP_MAP](#begin_prop_map)後、プロパティマップマクロ[END_PROP_MAP](#end_prop_map)の前に、ウィザードによってこのマクロが挿入されます。

### <a name="example"></a>例

次の例では、オブジェクト (`m_sizeExtent`) の範囲が永続化されています。

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

##  <a name="prop_entry_type"></a>PROP_ENTRY_TYPE

このマクロを使用して、プロパティの説明、プロパティの DISPID、およびプロパティページの CLSID をオブジェクトのプロパティマップに入力します。

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*<br/>
からプロパティの説明。

*dispid*<br/>
からプロパティの DISPID。

*clsid*<br/>
から関連付けられているプロパティページの CLSID。 プロパティページが関連付けられていないプロパティには、特殊な値 CLSID_NULL を使用します。

*vt*<br/>
からプロパティの型。

### <a name="remarks"></a>解説

PROP_ENTRY マクロは安全ではなく、非推奨とされました。 これは PROP_ENTRY_TYPE に置き換えられました。

[BEGIN_PROP_MAP](#begin_prop_map)マクロは、プロパティマップの先頭をマークします。[END_PROP_MAP](#end_prop_map)マクロは、終了をマークします。

### <a name="example"></a>例

[BEGIN_PROP_MAP](#begin_prop_map)の例を参照してください。

##  <a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX

[PROP_ENTRY_TYPE](#prop_entry_type)に似ていますが、オブジェクトが複数のデュアルインターフェイスをサポートしている場合は、特定の IID を指定することができます。

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*<br/>
からプロパティの説明。

*dispid*<br/>
からプロパティの DISPID。

*clsid*<br/>
から関連付けられているプロパティページの CLSID。 プロパティページが関連付けられていないプロパティには、特殊な値 CLSID_NULL を使用します。

*iidDispatch*<br/>
からプロパティを定義するデュアルインターフェイスの IID。

*vt*<br/>
からプロパティの型。

### <a name="remarks"></a>解説

PROP_ENTRY_EX マクロは安全ではなく、非推奨とされました。 これは PROP_ENTRY_TYPE_EX に置き換えられました。

[BEGIN_PROP_MAP](#begin_prop_map)マクロは、プロパティマップの先頭をマークします。[END_PROP_MAP](#end_prop_map)マクロは、終了をマークします。

### <a name="example"></a>例

次の例では、`IMyDual1` のエントリと `IMyDual2`のエントリをグループ化します。 デュアルインターフェイスでグループ化すると、パフォーマンスが向上します。

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

##  <a name="prop_page"></a>PROP_PAGE

このマクロを使用して、プロパティページの CLSID をオブジェクトのプロパティマップに入力します。

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>パラメーター

*clsid*<br/>
からプロパティページの CLSID。

### <a name="remarks"></a>解説

PROP_PAGE は[PROP_ENTRY_TYPE](#prop_entry_type)に似ていますが、プロパティの説明または DISPID は必要ありません。

> [!NOTE]
>  PROP_ENTRY_TYPE または[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)を持つ CLSID を既に入力している場合は、PROP_PAGE で追加エントリを作成する必要はありません。

[BEGIN_PROP_MAP](#begin_prop_map)マクロは、プロパティマップの先頭をマークします。[END_PROP_MAP](#end_prop_map)マクロは、終了をマークします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

##  <a name="end_prop_map"></a>END_PROP_MAP

オブジェクトのプロパティマップの末尾をマークします。

```
END_PROP_MAP()
```

### <a name="remarks"></a>解説

ATL プロジェクトウィザードを使用してオブジェクトを作成すると、ウィザードによって空のプロパティマップが作成されます。これには、 [BEGIN_PROP_MAP](#begin_prop_map)の後に END_PROP_MAP を指定します。

### <a name="example"></a>例

[BEGIN_PROP_MAP](#begin_prop_map)の例を参照してください。

## <a name="see-also"></a>参照

[マクロ](../../atl/reference/atl-macros.md)
