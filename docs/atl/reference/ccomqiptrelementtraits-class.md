---
title: CComQIPtrElementTraits クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8af52c0e90f346e99564c839333f85ca396f9fd5
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763179"
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits クラス

このクラスは、COM インターフェイス ポインターのコレクションを作成するときに、メソッド、静的関数、および便利な typedef を提供します。

## <a name="syntax"></a>構文

```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>パラメーター

*I*  
COM インターフェイスを格納するポインターの種類を指定します。

*piid*  
ポインターの IID を*は*します。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|

## <a name="remarks"></a>Remarks

このクラスは、メソッドを派生しのコレクション クラスを作成するときに、便利な typedef を提供します[CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM インターフェイス ポインター オブジェクト。 このクラスは、両方によって使用されて、 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md)と[CInterfaceList](../../atl/reference/cinterfacelist-class.md)クラス。

詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll.h

##  <a name="inargtype"></a>  CComQIPtrElementTraits::INARGTYPE

コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>関連項目

[CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
