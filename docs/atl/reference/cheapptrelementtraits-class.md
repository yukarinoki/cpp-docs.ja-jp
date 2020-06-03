---
title: クラスを見る
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
ms.openlocfilehash: f09da968b264463eba759372e4e0756397e9978e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326876"
---
# <a name="cheapptrelementtraits-class"></a>クラスを見る

このクラスは、ヒープ ポインターのコレクションを作成するときに便利なメソッド、静的関数、および typedef を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<typename T, class Allocator = ATL::CCRTAllocator>
class CHeapPtrElementTraits :
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクション クラスに格納されるオブジェクト型。

*アロケーター*<br/>
使用するメモリ割り当てクラス。 デフォルトは[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[要素トレイト::イナルグタイプ](#inargtype)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|
|[要素トレイト::アウトバーグタイプ](#outargtype)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|

## <a name="remarks"></a>解説

このクラスは、ヒープ ポインターを含むコレクション クラス オブジェクトの作成を支援するためのメソッド、静的関数、および typedef を提供します。 クラス`CHeapPtrList`は から`CHeapPtrElementTraits`派生します。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[クセプチュ設定の比較](../../atl/reference/cdefaultcomparetraits-class.md)

[既定のハッシュトレイト](../../atl/reference/cdefaulthashtraits-class.md)

[Cエレメントトレイツベース](../../atl/reference/celementtraitsbase-class.md)

[要素の状態](../../atl/reference/cdefaultelementtraits-class.md)

`CHeapPtrElementTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cheapptrelementtraitsinargtype"></a><a name="inargtype"></a>要素トレイト::イナルグタイプ

コレクション クラス オブジェクトに要素を追加するために使用するデータ型。

```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```

## <a name="cheapptrelementtraitsoutargtype"></a><a name="outargtype"></a>要素トレイト::アウトバーグタイプ

コレクション クラス オブジェクトから要素を取得するために使用するデータ型。

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[クラスの既定値](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラス](../../atl/reference/ccomheapptr-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
