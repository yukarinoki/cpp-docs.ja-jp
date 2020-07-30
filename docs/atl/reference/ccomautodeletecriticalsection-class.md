---
title: CComAutoDeleteCriticalSection クラス
ms.date: 11/04/2016
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
ms.openlocfilehash: f44dbff7d353cb09142ac742b526d3541e9b2265
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224332"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection クラス

このクラスには、クリティカルセクションオブジェクトの所有権を取得および解放するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```

## <a name="remarks"></a>解説

`CComAutoDeleteCriticalSection`クラス[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)から派生します。 ただし、は、 `CComAutoDeleteCriticalSection` にアクセスするための[Term](ccomsafedeletecriticalsection-class.md#term)メソッドをオーバーライドします **`private`** 。これにより、このクラスのインスタンスがスコープ外に出たり、明示的にメモリから削除されたりした場合にのみ、内部メモリのクリーンアップが強制的に行われます。

このクラスでは、基底クラスに追加のメソッドは導入されていません。 クリティカルセクションのヘルパークラスの詳細については、「 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) and [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)

`CComAutoDeleteCriticalSection`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcore .h

## <a name="see-also"></a>関連項目

[CComSafeDeleteCriticalSection クラス](../../atl/reference/ccomsafedeletecriticalsection-class.md)<br/>
[CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
