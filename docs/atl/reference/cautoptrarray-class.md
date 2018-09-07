---
title: CAutoPtrArray クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d83f98de4f1d07fbebdd07186729453d2ef1d3b2
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108734"
---
# <a name="cautoptrarray-class"></a>CAutoPtrArray クラス

このクラスは、スマート ポインターの配列を構築するときに役立つメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

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
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|コンストラクターです。|

## <a name="remarks"></a>Remarks

このクラスは、コンス トラクターを提供し、メソッドからの派生[CAtlArray](../../atl/reference/catlarray-class.md)と[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)スマート ポインターを格納するコレクション クラスのオブジェクトの作成を支援します。

詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`CAtlArray`

`CAutoPtrArray`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll.h

##  <a name="cautoptrarray"></a>  CAutoPtrArray::CAutoPtrArray

コンストラクターです。

```
CAutoPtrArray() throw();
```

### <a name="remarks"></a>Remarks

スマート ポインターの配列を初期化します。

## <a name="see-also"></a>関連項目

[CAtlArray クラス](../../atl/reference/catlarray-class.md)   
[CAutoPtrElementTraits クラス](../../atl/reference/cautoptrelementtraits-class.md)   
[CAutoPtrList クラス](../../atl/reference/cautoptrlist-class.md)   
[クラスの概要](../../atl/atl-class-overview.md)
