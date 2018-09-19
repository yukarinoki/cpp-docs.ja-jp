---
title: CComAutoDeleteCriticalSection クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c8ff6141fb5aa58e8de626675e29b46426ed47f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118441"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection クラス

このクラスは、取得およびクリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。

## <a name="syntax"></a>構文

```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```

## <a name="remarks"></a>Remarks

`CComAutoDeleteCriticalSection` クラスから派生[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)します。 ただし、`CComAutoDeleteCriticalSection`オーバーライド、[用語](ccomsafedeletecriticalsection-class.md#term)メソッドを**プライベート**アクセスで、強制的にのみこのクラスのインスタンス スコープ外に出るまたは明示的に削除されたときから発生する内部メモリ クリーンアップメモリ。  

このクラスは、その基本クラスを追加のメソッドを導入しないします。 参照してください[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)と[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)クリティカル セクションのヘルパー クラスの詳細についてはします。

## <a name="inheritance-hierarchy"></a>継承階層

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

[CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)

`CComAutoDeleteCriticalSection`

## <a name="requirements"></a>要件

**ヘッダー:** atlcore.h

## <a name="see-also"></a>関連項目

[CComSafeDeleteCriticalSection クラス](../../atl/reference/ccomsafedeletecriticalsection-class.md)<br/>
[CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
