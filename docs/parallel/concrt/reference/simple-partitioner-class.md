---
title: simple_partitioner クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
dev_langs:
- C++
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89114c96beb49c8f843ec8a04b08802632c61ca1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401512"
---
# <a name="simplepartitioner-class"></a>simple_partitioner クラス

`simple_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは範囲をチャンクに分割します。各チャンクには、少なくともチャンク サイズによって指定された数のイテレーションが含まれます。

## <a name="syntax"></a>構文

```
class simple_partitioner;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[simple_partitioner](#ctor)|`simple_partitioner` オブジェクトを構築します。|
|[~ simple_partitioner デストラクター](#dtor)|`simple_partitioner` オブジェクトを破棄します。|

## <a name="inheritance-hierarchy"></a>継承階層

`simple_partitioner`

## <a name="requirements"></a>要件

**ヘッダー:** ppl.h

**名前空間:** concurrency

##  <a name="dtor"></a> ~simple_partitioner

`simple_partitioner` オブジェクトを破棄します。

```
~simple_partitioner();
```

##  <a name="ctor"></a> simple_partitioner

`simple_partitioner` オブジェクトを構築します。

```
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>パラメーター

*_Chunk_size*<br/>
パーティションの最小サイズ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
