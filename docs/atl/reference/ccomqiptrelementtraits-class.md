---
description: '詳細情報: CComQIPtrElementTraits クラス'
title: CComQIPtrElementTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 9aa96c5b926263d6ed58125a28f5d0a12d8107d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142338"
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits クラス

このクラスには、COM インターフェイスポインターのコレクションを作成するときに役立つメソッド、静的関数、および typedef が用意されています。

## <a name="syntax"></a>構文

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>パラメーター

*I*<br/>
格納するポインターの型を指定する COM インターフェイス。

*piid*<br/>
*I* の IID へのポインター。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CComQIPtrElementTraits:: INARGTYPE](#inargtype)|コレクションクラスオブジェクトに要素を追加するために使用するデータ型。|

## <a name="remarks"></a>解説

このクラスは、メソッドを派生させると共に、 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM インターフェイスポインターオブジェクトのコレクションクラスを作成するときに役に立つ typedef を提供します。 このクラスは、 [Cinterfacearray](../../atl/reference/cinterfacearray-class.md) クラスと [cinterfacearray](../../atl/reference/cinterfacelist-class.md) クラスの両方で使用されます。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="ccomqiptrelementtraitsinargtype"></a><a name="inargtype"></a> CComQIPtrElementTraits:: INARGTYPE

コレクションクラスオブジェクトに要素を追加するために使用するデータ型。

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>関連項目

[CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
