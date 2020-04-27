---
title: CAutoPtrArray クラス
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
ms.openlocfilehash: 11f39eac8b8d080fd840f6454f393e33ebcb9e1c
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167664"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray クラス

このクラスには、スマートポインターの配列を構築するときに役立つメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```cpp
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```

### <a name="parameters"></a>パラメーター

*つまり*<br/>
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|コンストラクターです。|

## <a name="remarks"></a>解説

このクラスは、コンストラクターを提供し、 [CAtlArray](../../atl/reference/catlarray-class.md)および[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)からメソッドを派生させることにより、スマートポインターを格納するコレクションクラスオブジェクトの作成を支援します。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll. h

## <a name="cautoptrarraycautoptrarray"></a><a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray

コンストラクターです。

```cpp
CAutoPtrArray() throw();
```

### <a name="remarks"></a>解説

スマートポインターの配列を初期化します。

## <a name="see-also"></a>関連項目

[CAtlArray クラス](../../atl/reference/catlarray-class.md)<br/>
[CAutoPtrElementTraits クラス](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[CAutoPtrList クラス](../../atl/reference/cautoptrlist-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
