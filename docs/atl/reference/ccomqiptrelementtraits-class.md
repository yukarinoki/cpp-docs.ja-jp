---
title: クラスをクラス
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 19f2669c157310be02f746672b22f6c0ed005075
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327407"
---
# <a name="ccomqiptrelementtraits-class"></a>クラスをクラス

このクラスは、COM インターフェイス ポインターのコレクションを作成するときに便利なメソッド、静的関数、および型定義を提供します。

## <a name="syntax"></a>構文

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>パラメーター

*私*<br/>
格納するポインターの型を指定する COM インターフェイス。

*ピッド*<br/>
I の IID への*ポインタ。*

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[要素トレイト::イナルグタイプ](#inargtype)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|

## <a name="remarks"></a>解説

このクラスは、メソッドを派生し[、CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM インターフェイス ポインター オブジェクトのコレクション クラスを作成するときに便利な型定義を提供します。 このクラスは[、CInterfaceArray](../../atl/reference/cinterfacearray-class.md)クラスと[CInterfaceList](../../atl/reference/cinterfacelist-class.md)クラスの両方で使用されます。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[クセプチュ設定の比較](../../atl/reference/cdefaultcomparetraits-class.md)

[既定のハッシュトレイト](../../atl/reference/cdefaulthashtraits-class.md)

[Cエレメントトレイツベース](../../atl/reference/celementtraitsbase-class.md)

[要素の状態](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="ccomqiptrelementtraitsinargtype"></a><a name="inargtype"></a>要素トレイト::イナルグタイプ

コレクション クラス オブジェクトに要素を追加するために使用するデータ型。

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>関連項目

[クラスの既定値](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
