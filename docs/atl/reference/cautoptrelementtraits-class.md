---
title: クラスを示します。
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: ac29116dc9beedf587c42cc0e52f8c9dbaf3d782
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318885"
---
# <a name="cautoptrelementtraits-class"></a>クラスを示します。

このクラスは、スマート ポインターのコレクションを作成するときに便利なメソッド、静的関数、および typedef を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<typename T>
class CAutoPtrElementTraits
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[要素の特性::INARGTYPE](#inargtype)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|
|[要素の特性::アウトアルプタイプ](#outargtype)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|

## <a name="remarks"></a>解説

このクラスは、スマート ポインターを含むコレクション クラス オブジェクトの作成を支援するためのメソッド、静的関数、および typedef を提供します。 クラス[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)と[CAutoPtrList から](../../atl/reference/cautoptrlist-class.md)派生`CAutoPtrElementTraits`します。 ベクトルの新しい演算子と削除演算子を必要とするスマート ポインターのコレクションを構築する場合は、代わりに[CAutoVectorPtrElementTraits を使用します](../../atl/reference/cautovectorptrelementtraits-class.md)。

## <a name="inheritance-hierarchy"></a>継承階層

[クセプチュ設定の比較](../../atl/reference/cdefaultcomparetraits-class.md)

[既定のハッシュトレイト](../../atl/reference/cdefaulthashtraits-class.md)

[Cエレメントトレイツベース](../../atl/reference/celementtraitsbase-class.md)

[要素の状態](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cautoptrelementtraitsinargtype"></a><a name="inargtype"></a>要素の特性::INARGTYPE

コレクション クラス オブジェクトに要素を追加するために使用するデータ型。

```
typedef CAutoPtr<T>& INARGTYPE;
```

## <a name="cautoptrelementtraitsoutargtype"></a><a name="outargtype"></a>要素の特性::アウトアルプタイプ

コレクション クラス オブジェクトから要素を取得するために使用するデータ型。

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[クラスの既定値](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
