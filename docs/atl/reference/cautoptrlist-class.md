---
description: '詳細情報: CAutoPtrList クラス'
title: CAutoPtrList クラス
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 51544d464904d0ebfd31b82152088a0dfa638969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152517"
---
# <a name="cautoptrlist-class"></a>CAutoPtrList クラス

このクラスには、スマートポインターのリストを構築するときに役立つメソッドが用意されています。

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
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|コンストラクターです。|

## <a name="remarks"></a>解説

このクラスは、コンストラクターを提供し、 [CAtlList](../../atl/reference/catllist-class.md) および [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) からメソッドを派生させることにより、スマートポインターを格納するリストオブジェクトの作成を支援します。 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md)クラスは、配列オブジェクトに対して同様の関数を提供します。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a> CAutoPtrList::CAutoPtrList

コンストラクターです。

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
ブロックサイズ。既定値は10です。

### <a name="remarks"></a>解説

ブロックサイズは、新しい要素が必要な場合に割り当てられるメモリの量を測定したものです。 ブロックサイズを大きくすると、メモリ割り当てルーチンの呼び出しが減少しますが、より多くのリソースが使用されます。

## <a name="see-also"></a>関連項目

[CAtlList クラス](../../atl/reference/catllist-class.md)<br/>
[CAutoPtrElementTraits クラス](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
