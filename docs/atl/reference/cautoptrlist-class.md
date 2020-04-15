---
title: クラスを実行します。
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 48c7ad6fe13c5f5fbbe5829c25ce1c27896841be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318803"
---
# <a name="cautoptrlist-class"></a>クラスを実行します。

このクラスは、スマート ポインターのリストを構築するときに役立つメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>パラメーター

*E*<br/>
ポインター型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[を一覧します。](#cautoptrlist)|コンストラクターです。|

## <a name="remarks"></a>解説

このクラスは、コンストラクターを提供し、スマート ポインターを格納するリスト オブジェクトの作成を支援するために[、CAtlList](../../atl/reference/catllist-class.md)および[CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)からメソッドを派生させます。 クラス[CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)は、配列オブジェクトに対して同様の関数を提供します。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[カトルリスト](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a>を一覧します。

コンストラクターです。

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
ブロック サイズ (既定値は 10)。

### <a name="remarks"></a>解説

ブロック サイズは、新しい要素が必要なときに割り当てられるメモリの量を測定します。 ブロック サイズが大きくなると、メモリ割り当てルーチンの呼び出しは減りますが、使用するリソースは多くなります。

## <a name="see-also"></a>関連項目

[クラスを表します。](../../atl/reference/catllist-class.md)<br/>
[クラスを示します。](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
