---
title: auto_partitioner クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
dev_langs:
- C++
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2bb62d76733e77c2528a80dfc4e9ef358878895
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46425412"
---
# <a name="autopartitioner-class"></a>auto_partitioner クラス

`auto_partitioner` クラスは、反復処理する範囲を分割するために、既定のメソッド `parallel_for`、`parallel_for_each`、および `parallel_transform` の使用を表します。 このパーティション分割のメソッドでは、負荷分散および反復ごとの取り消しで範囲スティーリングが使用されます。

## <a name="syntax"></a>構文

```
class auto_partitioner;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[auto_partitioner](#ctor)|`auto_partitioner` オブジェクトを構築します。|
|[~ auto_partitioner デストラクター](#dtor)|`auto_partitioner` オブジェクトを破棄します。|

## <a name="inheritance-hierarchy"></a>継承階層

`auto_partitioner`

## <a name="requirements"></a>要件

**ヘッダー:** ppl.h

**名前空間:** concurrency

##  <a name="dtor"></a> ~auto_partitioner

`auto_partitioner` オブジェクトを破棄します。

```
~auto_partitioner();
```

##  <a name="ctor"></a> auto_partitioner

`auto_partitioner` オブジェクトを構築します。

```
auto_partitioner();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
