---
title: クラスを表します。
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
ms.openlocfilehash: 0500ab8f76049aeaf1c89355ea5450a93243b734
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326860"
---
# <a name="cheapptrlist-class"></a>クラスを表します。

このクラスには、ヒープ ポインタのリストを作成するときに便利なメソッドが用意されています。

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
コレクション クラスに格納されるオブジェクト型。

*アロケーター*<br/>
使用するメモリ割り当てクラス。 デフォルトは[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)です。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cヒーププターリスト::Cヒーププターリスト](#cheapptrlist)|コンストラクターです。|

## <a name="remarks"></a>解説

このクラスは、コンストラクターを提供し[、CAtlList](../../atl/reference/catllist-class.md)および[CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)からメソッドを派生して、ヒープ ポインターを格納するコレクション クラス オブジェクトの作成を支援します。

## <a name="inheritance-hierarchy"></a>継承階層

[カトルリスト](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a>Cヒーププターリスト::Cヒーププターリスト

コンストラクターです。

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>パラメーター

*ブロックサイズ*<br/>
ブロックのサイズです。

### <a name="remarks"></a>解説

ブロック サイズは、新しい要素が必要なときに割り当てられるメモリの量を測定します。 ブロック サイズが大きくなると、メモリ割り当てルーチンの呼び出しは減りますが、使用するリソースは多くなります。

## <a name="see-also"></a>関連項目

[クラスを表します。](../../atl/reference/catllist-class.md)<br/>
[Cヒーププタークラス](../../atl/reference/cheapptr-class.md)<br/>
[クラスを見る](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
