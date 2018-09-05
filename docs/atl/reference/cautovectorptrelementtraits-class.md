---
title: CAutoVectorPtrElementTraits クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fd39f56d69aef836714d70b50f6e2c882cad9448
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754827"
---
# <a name="cautovectorptrelementtraits-class"></a>CAutoVectorPtrElementTraits クラス

メソッド、静的関数、および typedef と delete 演算子を新しいベクトルを使用してスマート ポインターのコレクションを作成するときに便利です。 このクラスを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <typename T>  
class CAutoVectorPtrElementTraits : 
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>パラメーター

`T`  
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。|

## <a name="remarks"></a>Remarks

このクラスは、スマート ポインターを格納しているコレクション クラスのオブジェクトを作成するときに役立つ方法、静的関数、および typedef を提供します。 異なり[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)、このクラスは新しいベクターおよび delete 演算子。

## <a name="inheritance-hierarchy"></a>継承階層

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll.h

##  <a name="inargtype"></a>  CAutoVectorPtrElementTraits::INARGTYPE

コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

##  <a name="outargtype"></a>  CAutoVectorPtrElementTraits::OUTARGTYPE

コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
[CAutoVectorPtr クラス](../../atl/reference/cautovectorptr-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
