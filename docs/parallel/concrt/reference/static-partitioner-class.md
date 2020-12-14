---
description: '詳細情報: static_partitioner クラス'
title: static_partitioner クラス
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: f75d2e620a66e0ed347d39d429f59e3e2715369a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188496"
---
# <a name="static_partitioner-class"></a>static_partitioner クラス

`static_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは、この範囲を、基になるスケジューラで使用できるワーカーと同じ数のチャンクに分割します。

## <a name="syntax"></a>構文

```cpp
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

## <a name="requirements"></a>要件

**ヘッダー:** ppl

**名前空間:** concurrency

## <a name="static_partitioner"></a><a name="dtor"></a> ~ static_partitioner

`static_partitioner` オブジェクトを破棄します。

```cpp
~static_partitioner();
```

## <a name="static_partitioner"></a><a name="ctor"></a> static_partitioner

`static_partitioner` オブジェクトを構築します。

```cpp
static_partitioner();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
