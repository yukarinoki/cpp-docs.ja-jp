---
title: static_partitioner クラス
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: a0d06326b2ecbf3c427ae24b45751f7053778a0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500894"
---
# <a name="staticpartitioner-class"></a>static_partitioner クラス

`static_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは範囲をチャンクに分割します。チャンクの数は、基になるスケジューラが使用できるワーカーと同じ数にします。

## <a name="syntax"></a>構文

```
class static_partitioner;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[static_partitioner](#ctor)|`static_partitioner` オブジェクトを構築します。|
|[~ static_partitioner デストラクター](#dtor)|`static_partitioner` オブジェクトを破棄します。|

## <a name="inheritance-hierarchy"></a>継承階層

`static_partitioner`

## <a name="requirements"></a>必要条件

**ヘッダー:** ppl.h

**名前空間:** concurrency

##  <a name="dtor"></a> ~static_partitioner

`static_partitioner` オブジェクトを破棄します。

```
~static_partitioner();
```

##  <a name="ctor"></a> static_partitioner

`static_partitioner` オブジェクトを構築します。

```
static_partitioner();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
