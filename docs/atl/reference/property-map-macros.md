---
title: プロパティ マップに関するマクロ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::BEGIN_PROP_MAP
- atlcom/ATL::PROP_DATA_ENTRY
- atlcom/ATL::PROP_ENTRY_TYPE
- atlcom/ATL::PROP_ENTRY_TYPE_EX
- atlcom/ATL::PROP_PAGE
- atlcom/ATL::END_PROP_MAP
dev_langs:
- C++
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf82c48cb5b1f9bd93a9c30afe8c698699c8199b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758093"
---
# <a name="property-map-macros"></a>プロパティ マップに関するマクロ

これらのマクロは、プロパティ マップとエントリを定義します。

|||
|-|-|
|[あり、その場合](#begin_prop_map)|ATL プロパティのマップの先頭をマークします。|
|[するため](#prop_data_entry)|範囲、またはディメンションは、ActiveX コントロールのことを示します。|
|[PROP_ENTRY_TYPE("](#prop_entry_type)|プロパティ マップには、プロパティの説明、プロパティの DISPID、およびプロパティ ページの CLSID を入力します。|
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|プロパティの DISPID、プロパティ ページの CLSID、プロパティの説明を入力し、`IDispatch`プロパティ マップに IID。|
|[PROP_PAGE](#prop_page)|プロパティ マップには、プロパティ ページの CLSID を入力します。|
|[マクロと](#end_prop_map)|ATL プロパティのマップの最後をマークします。|  

## <a name="requirements"></a>要件

**ヘッダー:** atlcom.h

##  <a name="begin_prop_map"></a>  あり、その場合

オブジェクトのプロパティのマップの先頭をマークします。

```
BEGIN_PROP_MAP(theClass)
```

### <a name="parameters"></a>パラメーター

*クラス*  
[in]プロパティ マップを含むクラスを指定します。

### <a name="remarks"></a>Remarks

プロパティの Dispid、Clsid、 プロパティ ページのプロパティの説明を格納するプロパティ マップと`IDispatch`Iid。 クラス[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)、 [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)、 [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)、および[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)プロパティ マップを使用して取得し、この情報を設定します。

ATL プロジェクト ウィザードを使用してオブジェクトを作成するときに、ウィザードはマップを作成する空のプロパティを続けて[マクロと](#end_prop_map)します。

プロパティ マップを使用してオブジェクトを可能性がありますエクステントはありませんので、ユーザー インターフェイスがあるないために、あり、その場合は、プロパティ マップのエクステント (つまり、ディメンション) を保存できません。 オブジェクトがユーザー インターフェイスを持つ ActiveX コントロールの場合は、エクステントがあります。 この場合、指定する必要があります[するため](#prop_data_entry)範囲を指定するプロパティ マップします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]

##  <a name="prop_data_entry"></a>  するため

範囲、またはディメンションは、ActiveX コントロールのことを示します。

```
PROP_DATA_ENTRY( szDesc, member, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*  
[in]プロパティの説明。

*メンバー*  
[in]エクステント; を含むデータ メンバーたとえば、`m_sizeExtent`します。

*vt*  
[in]プロパティのバリアント型を指定します。

### <a name="remarks"></a>Remarks

このマクロは、永続化する指定したデータ メンバーをによりします。

ActiveX コントロールを作成するときに、このマクロはプロパティのマップ マクロの後に挿入された[あり、その場合](#begin_prop_map)とプロパティのマップ マクロの前に[マクロと](#end_prop_map)します。

### <a name="example"></a>例

次の例では、オブジェクトの範囲 (`m_sizeExtent`) は、永続化されます。

[!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]

[!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]

##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE("

このマクロを使用すると、オブジェクトのプロパティのマップにプロパティの説明、プロパティの DISPID、およびプロパティ ページの CLSID を入力します。

```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*  
[in]プロパティの説明。

*dispid*  
[in]プロパティの DISPID。

*clsid*  
[in]関連付けられているプロパティ ページの CLSID。 関連付けられたプロパティ ページがないプロパティの特別な値 CLSID_ を使用します。

*vt*  
[in]プロパティの型。

### <a name="remarks"></a>Remarks

PROP_ENTRY マクロは、安全では非推奨にしました。 PROP_ENTRY_TYPE("で交換済みです。

[あり、その場合](#begin_prop_map)マクロには、プロパティ マップの先頭は[マクロと](#end_prop_map)マクロは、終了をマークします。

### <a name="example"></a>例

例をご覧ください[あり、その場合](#begin_prop_map)します。

##  <a name="prop_entry_type_ex"></a>  PROP_ENTRY_TYPE_EX

ような[PROP_ENTRY_TYPE](#prop_entry_type)が、オブジェクトは、複数のデュアル インターフェイスをサポートしている場合、特定の IID を指定できます。

```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```

### <a name="parameters"></a>パラメーター

*szDesc*  
[in]プロパティの説明。

*dispid*  
[in]プロパティの DISPID。

*clsid*  
[in]関連付けられているプロパティ ページの CLSID。 関連付けられたプロパティ ページがないプロパティの特別な値 CLSID_ を使用します。

*iidDispatch*  
[in]プロパティを定義するデュアル インターフェイスの IID。

*vt*  
[in]プロパティの型。

### <a name="remarks"></a>Remarks

PROP_ENTRY_EX マクロは、安全では非推奨にしました。 これは、PROP_ENTRY_TYPE_EX に置き換えられています。

[あり、その場合](#begin_prop_map)マクロには、プロパティ マップの先頭は[マクロと](#end_prop_map)マクロは、終了をマークします。

### <a name="example"></a>例

次の例では、グループのエントリ`IMyDual1`のエントリを続けて`IMyDual2`します。 デュアル インターフェイスによってグループ化には、パフォーマンスが向上します。

[!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]

##  <a name="prop_page"></a>  PROP_PAGE

このマクロを使用すると、オブジェクトのプロパティのマップにプロパティ ページの CLSID を入力します。

```
PROP_PAGE(clsid)
```

### <a name="parameters"></a>パラメーター

*clsid*  
[in]プロパティ ページの CLSID。

### <a name="remarks"></a>Remarks

PROP_PAGE と似ています[PROP_ENTRY_TYPE](#prop_entry_type)プロパティの説明または DISPID は必要ありません。

> [!NOTE]
>  PROP_ENTRY_TYPE("の CLSID を入力した場合または[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)PROP_PAGE で追加のエントリを作成する必要はありません。

[あり、その場合](#begin_prop_map)マクロには、プロパティ マップの先頭は[マクロと](#end_prop_map)マクロは、終了をマークします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]

##  <a name="end_prop_map"></a>  マクロと

オブジェクトのプロパティのマップの最後をマークします。

```
END_PROP_MAP()
```

### <a name="remarks"></a>Remarks

ATL プロジェクト ウィザードを使用してオブジェクトを作成するときに、ウィザードはマップを作成する空のプロパティを指定して[あり、その場合](#begin_prop_map)マクロと続きます。

### <a name="example"></a>例

例をご覧ください[あり、その場合](#begin_prop_map)します。

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)
