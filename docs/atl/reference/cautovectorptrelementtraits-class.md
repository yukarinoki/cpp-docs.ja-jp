---
title: クラスを示します。
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
ms.openlocfilehash: 956fe39c4d3ba89bb9def2f996dca59905753edb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318756"
---
# <a name="cautovectorptrelementtraits-class"></a>クラスを示します。

このクラスは、メソッド、静的関数、および typedef を提供し、ベクトル new 演算子と delete 演算子を使用してスマート ポインターのコレクションを作成するときに便利です。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <typename T>
class CAutoVectorPtrElementTraits :
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[要素トレイト::イナルグタイプ](#inargtype)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|
|[要素の特性::アウトバーグタイプ](#outargtype)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|

## <a name="remarks"></a>解説

このクラスは、スマート ポインターを含むコレクション クラス オブジェクトの作成を支援するためのメソッド、静的関数、および typedef を提供します。 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)とは異なり、このクラスはベクトルの新しい演算子と削除演算子を使用します。

## <a name="inheritance-hierarchy"></a>継承階層

[クセプチュ設定の比較](../../atl/reference/cdefaultcomparetraits-class.md)

[既定のハッシュトレイト](../../atl/reference/cdefaulthashtraits-class.md)

[Cエレメントトレイツベース](../../atl/reference/celementtraitsbase-class.md)

[要素の状態](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cautovectorptrelementtraitsinargtype"></a><a name="inargtype"></a>要素トレイト::イナルグタイプ

コレクション クラス オブジェクトに要素を追加するために使用するデータ型。

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

## <a name="cautovectorptrelementtraitsoutargtype"></a><a name="outargtype"></a>要素の特性::アウトバーグタイプ

コレクション クラス オブジェクトから要素を取得するために使用するデータ型。

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[クラスの既定値](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラス](../../atl/reference/cautovectorptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
