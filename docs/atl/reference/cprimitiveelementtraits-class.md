---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
ms.openlocfilehash: 6b45d93420d1832091cc451a3e6eb309f61d07a3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331432"
---
# <a name="cprimitiveelementtraits-class"></a>クラス

このクラスは、プリミティブ データ型で構成されるコレクション クラスの既定のメソッドと関数を提供します。

## <a name="syntax"></a>構文

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクション クラス オブジェクトに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[要素トレイト::イナルグタイプ](#inargtype)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|
|[要素トレイト::アウトアルプタイプ](#outargtype)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|

## <a name="remarks"></a>解説

このクラスは、コレクション クラス オブジェクトに格納されているプリミティブ データ型要素の移動、コピー、比較、およびハッシュを行うための既定の静的関数とメソッドを提供します。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[クセプチュ設定の比較](../../atl/reference/cdefaultcomparetraits-class.md)

[既定のハッシュトレイト](../../atl/reference/cdefaulthashtraits-class.md)

[Cエレメントトレイツベース](../../atl/reference/celementtraitsbase-class.md)

[要素の状態](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cprimitiveelementtraitsinargtype"></a><a name="inargtype"></a>要素トレイト::イナルグタイプ

コレクション クラス オブジェクトに要素を追加するために使用するデータ型。

```
typedef T INARGTYPE;
```

## <a name="cprimitiveelementtraitsoutargtype"></a><a name="outargtype"></a>要素トレイト::アウトアルプタイプ

コレクション クラス オブジェクトから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[クラスの既定値](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
