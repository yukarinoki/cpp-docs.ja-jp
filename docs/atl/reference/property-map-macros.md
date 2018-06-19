---
title: プロパティ マップに関するマクロ |Microsoft ドキュメント
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
ms.openlocfilehash: 718028385b3910b955c49ab9e0abddf23b443967
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365016"
---
# <a name="property-map-macros"></a>プロパティ マップ マクロ
これらのマクロは、プロパティ マップとエントリを定義します。  
  
|||  
|-|-|  
|[あり、その場合](#begin_prop_map)|ATL プロパティ マップの先頭をマークします。|  
|[するため](#prop_data_entry)|範囲、またはディメンション、ActiveX コントロールのことを示します。|  
|[PROP_ENTRY_TYPE](#prop_entry_type)|プロパティ マップ プロパティの説明、プロパティの DISPID、およびプロパティ ページの CLSID を入力します。|  
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|プロパティの DISPID、プロパティ ページ、CLSID、プロパティの説明を入力し、`IDispatch`プロパティ マップに IID。|  
|[PROP_PAGE](#prop_page)|プロパティ マップには、プロパティ ページの CLSID を入力します。|  
|[マクロと](#end_prop_map)|ATL プロパティ マップの最後をマークします。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
   
##  <a name="begin_prop_map"></a>  あり、その場合  
 オブジェクトのプロパティ マップの先頭をマークします。  
  
```
BEGIN_PROP_MAP(theClass)
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 [in]プロパティ マップを含むクラスを指定します。  
  
### <a name="remarks"></a>コメント  
 プロパティ マップがプロパティ Dispid、Clsid、 プロパティ ページのプロパティの説明を格納および`IDispatch`Iid。 クラス[IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md)、 [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md)、 [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)、および[ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)プロパティ マップを使用して取得し、この情報を設定します。  
  
 ウィザードが空のプロパティ マップを作成するを指定して ATL プロジェクト ウィザードを使用してオブジェクトを作成するときに`BEGIN_PROP_MAP`続く[マクロと](#end_prop_map)です。  
  
 `BEGIN_PROP_MAP` プロパティ マップを使用してオブジェクトを可能性がありますエクステントもないため、ユーザー インターフェイスがあるないために、プロパティ マップの範囲 (つまり、ディメンション) を保存しません。 オブジェクトがユーザー インターフェイスを持つ ActiveX コントロールの場合は、エクステントがします。 この場合、指定する必要があります[するため](#prop_data_entry)エクステントを提供する、プロパティ マップにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#103](../../atl/codesnippet/cpp/property-map-macros_1.h)]  
  
##  <a name="prop_data_entry"></a>  するため  
 範囲、またはディメンション、ActiveX コントロールのことを示します。  
  
```
PROP_DATA_ENTRY( szDesc, member, vt)
```    
  
### <a name="parameters"></a>パラメーター  
 `szDesc`  
 [in]プロパティの説明。  
  
 `member`  
 [in]エクステント; を含むデータ メンバーたとえば、`m_sizeExtent`です。  
  
 *vt*  
 [in]プロパティのバリアント型を指定します。  
  
### <a name="remarks"></a>コメント  
 このマクロでは、永続化する指定されたデータ メンバーが発生します。  
  
 ActiveX コントロールを作成するときに、このマクロはプロパティ マップ マクロの後に挿入された[あり、その場合](#begin_prop_map)と、プロパティ マップ マクロの前に[マクロと](#end_prop_map)です。  
  
### <a name="example"></a>例  
 次の例では、オブジェクトの範囲 ( `m_sizeExtent`) が永続化します。  
  
 [!code-cpp[NVC_ATL_Windowing#131](../../atl/codesnippet/cpp/property-map-macros_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#132](../../atl/codesnippet/cpp/property-map-macros_3.h)]  
  
##  <a name="prop_entry_type"></a>  PROP_ENTRY_TYPE  
 このマクロを使用すると、オブジェクトのプロパティ マップ プロパティの説明、プロパティの DISPID、およびプロパティ ページの CLSID を入力します。  
  
```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```  
  
### <a name="parameters"></a>パラメーター  
 `szDesc`  
 [in]プロパティの説明。  
  
 `dispid`  
 [in]プロパティの DISPID です。  
  
 `clsid`  
 [in]関連付けられたプロパティ ページの CLSID。 特殊な値を使用して`CLSID_NULL`関連付けられたプロパティ ページがないプロパティです。  
  
 `vt`  
 [in]プロパティの型。  
  
### <a name="remarks"></a>コメント  
 `PROP_ENTRY`マクロが安全でないと非推奨です。 置き換えられました`PROP_ENTRY_TYPE`です。  
  
 [あり、その場合](#begin_prop_map)マクロは、プロパティ マップの開始をマーク;[マクロと](#end_prop_map)マクロは、終了を示します。  
  
### <a name="example"></a>例  
 例を参照して[あり、その場合](#begin_prop_map)です。  
  
##  <a name="prop_entry_type_ex"></a>  PROP_ENTRY_TYPE_EX  
 ような[PROP_ENTRY_TYPE](#prop_entry_type)は、オブジェクトは、複数のデュアル インターフェイスをサポートしている場合、特定の IID を指定するようにします。  
  
```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```    
  
### <a name="parameters"></a>パラメーター  
 `szDesc`  
 [in]プロパティの説明。  
  
 `dispid`  
 [in]プロパティの DISPID です。  
  
 `clsid`  
 [in]関連付けられたプロパティ ページの CLSID。 特殊な値を使用して`CLSID_NULL`関連付けられたプロパティ ページがないプロパティです。  
  
 `iidDispatch`  
 [in]プロパティを定義するデュアル インターフェイスの IID です。  
  
 `vt`  
 [in]プロパティの型。  
  
### <a name="remarks"></a>コメント  
 `PROP_ENTRY_EX`マクロが安全でないと非推奨です。 置き換えられました`PROP_ENTRY_TYPE_EX`です。  
  
 [あり、その場合](#begin_prop_map)マクロは、プロパティ マップの開始をマーク;[マクロと](#end_prop_map)マクロは、終了を示します。  
  
### <a name="example"></a>例  
 次の例のエントリをグループ化`IMyDual1`のエントリを続けて`IMyDual2`です。 デュアル インターフェイスによってグループ化には、パフォーマンスが向上します。  
  
 [!code-cpp[NVC_ATL_Windowing#133](../../atl/codesnippet/cpp/property-map-macros_4.h)]  
  
##  <a name="prop_page"></a>  PROP_PAGE  
 このマクロを使用すると、オブジェクトのプロパティ マップにプロパティ ページの CLSID を入力します。  
  
```
PROP_PAGE(clsid)
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 [in]プロパティ ページの CLSID。  
  
### <a name="remarks"></a>コメント  
 `PROP_PAGE` ような[PROP_ENTRY_TYPE](#prop_entry_type)プロパティの説明または DISPID は必要ありません。  
  
> [!NOTE]
>  場合は、CLSID は既に入力`PROP_ENTRY_TYPE`または[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)に追加エントリを作成する必要はありません`PROP_PAGE`です。  
  
 [あり、その場合](#begin_prop_map)マクロは、プロパティ マップの開始をマーク;[マクロと](#end_prop_map)マクロは、終了を示します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#134](../../atl/codesnippet/cpp/property-map-macros_5.h)]  
  
##  <a name="end_prop_map"></a>  マクロと  
 オブジェクトのプロパティ マップの最後をマークします。  
  
```
END_PROP_MAP()
```  
  
### <a name="remarks"></a>コメント  
 ウィザードが空のプロパティ マップを作成するを指定して ATL プロジェクト ウィザードを使用してオブジェクトを作成するときに[あり、その場合](#begin_prop_map)続く`END_PROP_MAP`です。  
  
### <a name="example"></a>例  
 例を参照して[あり、その場合](#begin_prop_map)です。  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
