---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: 78cadfff9a278cf080393ab919f3891b201c91aa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327773"
---
# <a name="ccomheapptr-class"></a>クラス

ヒープ ポインターを管理するためのスマート ポインター クラス。

## <a name="syntax"></a>構文

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ヒープに格納されるオブジェクト型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComヒーププター::CComヒーププター](#ccomheapptr)|コンストラクターです。|

## <a name="remarks"></a>解説

`CComHeapPtr`は から`CHeapPtr`派生しますが、COM ルーチンを使用してメモリを割り当てる[には CComAllocator](../../atl/reference/ccomallocator-class.md)を使用します。 使用可能なメソッドについては[、「C ヒーププター](../../atl/reference/cheapptr-class.md)と[C ヒーププターベース](../../atl/reference/cheapptrbase-class.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ヒーププターベース](../../atl/reference/cheapptrbase-class.md)

[クヒーププター](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a>CComヒーププター::CComヒーププター

コンストラクターです。

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>パラメーター

*Pdata*<br/>
既存の `CComHeapPtr` オブジェクトです。

### <a name="remarks"></a>解説

ヒープ ポインターは、既存`CComHeapPtr`のオブジェクトを使用して任意で作成できます。 その場合、新しい`CComHeapPtr`オブジェクトは、新しいポインターとリソースを管理する責任を負います。

## <a name="see-also"></a>関連項目

[Cヒーププタークラス](../../atl/reference/cheapptr-class.md)<br/>
[クラス](../../atl/reference/cheapptrbase-class.md)<br/>
[コマッロロケータクラス](../../atl/reference/ccomallocator-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
