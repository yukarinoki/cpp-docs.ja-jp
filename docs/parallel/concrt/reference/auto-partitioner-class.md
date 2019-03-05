---
title: auto_partitioner クラス
ms.date: 11/04/2016
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
ms.openlocfilehash: 2d8bbb8e8af17dd19953487c47e5fd40343fe349
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264821"
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

## <a name="requirements"></a>必要条件

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
