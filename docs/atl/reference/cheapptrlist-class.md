---
description: '詳細情報: 不正な Apptrlist クラス'
title: 不正 Apptrlist クラス
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
ms.openlocfilehash: 7e3a97280f7abcd4b7efebf6726ac062215912d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141597"
---
# <a name="cheapptrlist-class"></a>不正 Apptrlist クラス

このクラスには、ヒープポインターのリストを構築するときに役立つメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<typename E, class Allocator = ATL::CCRTAllocator>
class CHeapPtrList
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```

#### <a name="parameters"></a>パラメーター

*E*<br/>
コレクションクラスに格納されるオブジェクトの型。

*アロケーター*<br/>
使用するメモリ割り当てクラス。 既定値は [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)です。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[不正 Apptrlist:: 不正 Apptrlist](#cheapptrlist)|コンストラクターです。|

## <a name="remarks"></a>解説

このクラスは、コンストラクターを提供し、 [CAtlList](../../atl/reference/catllist-class.md) および [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) からメソッドを派生させることにより、ヒープポインターを格納するコレクションクラスオブジェクトの作成を支援します。

## <a name="inheritance-hierarchy"></a>継承階層

[CAtlList](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a> 不正 Apptrlist:: 不正 Apptrlist

コンストラクターです。

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*nBlockSize*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

ブロックサイズは、新しい要素が必要な場合に割り当てられるメモリの量を測定したものです。 ブロックサイズを大きくすると、メモリ割り当てルーチンの呼び出しが減少しますが、より多くのリソースが使用されます。

## <a name="see-also"></a>関連項目

[CAtlList クラス](../../atl/reference/catllist-class.md)<br/>
[CHeapPtr クラス](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrElementTraits クラス](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
