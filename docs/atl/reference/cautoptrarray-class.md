---
title: クラスを指定します。
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 93fc5cfea4ea655e57e785ca234df59fe10d6570
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318891"
---
# <a name="cautoptrarray-class"></a>クラスを指定します。

このクラスは、スマート ポインターの配列を構築するときに役立つメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>パラメーター

*E*<br/>
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を指定します。](#cautoptrarray)|コンストラクターです。|

## <a name="remarks"></a>解説

このクラスは、コンストラクターを提供し、スマート ポインターを格納するコレクション クラス オブジェクトの作成を支援するために[、CAtlArray](../../atl/reference/catlarray-class.md)および[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)からメソッドを派生させます。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a>を指定します。

コンストラクターです。

```
CAutoPtrArray() throw();
```

### <a name="remarks"></a>解説

スマート ポインター配列を初期化します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/catlarray-class.md)<br/>
[クラスを示します。](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[クラスを実行します。](../../atl/reference/cautoptrlist-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
